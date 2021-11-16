# Data Visualization

## Introduction

matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats. We are going to explore matplotlib in interactive mode covering most common cases.

### IPython

IPython is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands.

### pyplot

pyplot provides a convenient interface to the matplotlib object-oriented plotting library. It is modeled closely after Matlab(TM).

## Simple plot

Let us draw the cosine and sine functions on the same plot. Starting from the default settings.

The first step is to get the data for the sine and cosine functions:

    import numpy as np

    X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
    C, S = np.cos(X), np.sin(X)

X is now a NumPy array with 256 values ranging from -π to +π (included). C is the cosine (256 values) and S is the sine (256 values).

To run the example, you can download each of the examples and run it using:

    $ python exercice_1.py

![sin](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_1.png)

Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: figure size and dpi, line width, color and style, axes, axis and grid properties.

Ticks are now properly placed but their label is not very explicit. We could guess that 3.142 is π but it would be better to make it explicit.

### Setting tick labels

![color](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_6.png)

### Moving spines

![spines](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_7.png)

Spines are the lines connecting the axis tick marks and noting the boundaries of the data area.

### Adding a legend

![legend](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_8.png)

This only requires adding the keyword argument label (that will be used in the legend box) to the plot commands.

    ...
    plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-", label="cosine")
    plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-", label="sine")

    plt.legend(loc='upper left', frameon=False)
    ...

## Figures, Subplots, Axes and Ticks

So far we have used implicit figure and axes creation. This is handy for fast plots. We can have more control over the display using figure, subplot, and axes explicitly. A figure in matplotlib means the whole window in the user interface. Within this figure there can be subplots. While subplot positions the plots in a regular grid, axes allows free placement within the figure.

### Figures

A figure is the windows in the GUI that has "Figure #" as title. Figures are numbered starting from 1 as opposed to the normal Python way starting from 0.

### Subplots

With subplot you can arrange plots in a regular grid.

![subplots](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/subplot-horizontal.png)

### Axes

Axes are very similar to subplots but allow placement of plots at any location in the figure. 

![axes](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/axes.png)

### Ticks

Well formatted ticks are an important part of publishing-ready figures. Matplotlib provides a totally configurable system for ticks.

## Animation

For quite a long time, animation in matplotlib was not an easy task and was done mainly through clever hacks.

### Drip drop

A very simple rain effect can be obtained by having small growing rings randomly positioned over a figure.

![drop](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/rain-static.png)

    # Number of ring
    n = 50
    size_min = 50
    size_max = 50*50

    # Ring position
    P = np.random.uniform(0,1,(n,2))

    # Ring colors
    C = np.ones((n,4)) * (0,0,0,1)
    # Alpha color channel goes from 0 (transparent) to 1 (opaque)
    C[:,3] = np.linspace(0,1,n)

    # Ring sizes
    S = np.linspace(size_min, size_max, n)

    # Scatter plot
    scat = ax.scatter(P[:,0], P[:,1], s=S, lw = 0.5,
                    edgecolors = C, facecolors='None')

    # Ensure limits are [0,1] and remove ticks
    ax.set_xlim(0,1), ax.set_xticks([])
    ax.set_ylim(0,1), ax.set_yticks([])

### Earthquakes

We'll now use the rain animation to visualize earthquakes on the planet from the last 30 days. The USGS Earthquake Hazards Program is part of the National Earthquake Hazards Reduction Program (NEHRP) and provides several data on their website.

First step is to read and convert data. We'll use the urllib library that allows us to open and read remote data. Data on the website use the CSV format whose content is given by the first line:

    time,latitude,longitude,depth,mag,magType,nst,gap,dmin,rms,net,id,updated,place,type
    2015-08-17T13:49:17.320Z,37.8365,-122.2321667,4.82,4.01,mw,...
    2015-08-15T07:47:06.640Z,-10.9045,163.8766,6.35,6.6,mwp,...

We are only interested in latitude, longitude and magnitude and we won't parse time of event (ok, that's bad, feel free to send me a PR).

import urllib
from mpl_toolkits.basemap import Basemap

    # -> http://earthquake.usgs.gov/earthquakes/feed/v1.0/csv.php
    feed = "http://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/"

    # Significant earthquakes in the last 30 days
    # url = urllib.request.urlopen(feed + "significant_month.csv")

    # Magnitude > 4.5
    url = urllib.request.urlopen(feed + "4.5_month.csv")

    # Magnitude > 2.5
    # url = urllib.request.urlopen(feed + "2.5_month.csv")

    # Magnitude > 1.0
    # url = urllib.request.urlopen(feed + "1.0_month.csv")

    # Reading and storage of data
    data = url.read()
    data = data.split(b'\n')[+1:-1]
    E = np.zeros(len(data), dtype=[('position',  float, 2),
                                ('magnitude', float, 1)])

    for i in range(len(data)):
        row = data[i].split(',')
        E['position'][i] = float(row[2]),float(row[1])
        E['magnitude'][i] = float(row[4])

![earthquick](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/scatter.png)
