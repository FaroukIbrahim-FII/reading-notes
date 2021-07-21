# Assorted Topics

## Images

### Controlling Sizes of Images in CSS

You can control the size of an image using the width and height properties in CSS, just like you can for any other box.

Specifying image sizes helps pages to load more smoothly because the HTML and CSS code will often load before the images, and telling the browser how much space to leave for an image allows it to render the rest of the page without waiting for the image to download.

### Aligning images Using CSS

In the last chapter, you saw how the float property can be used to move an element to the left or the right of its containing block, allowing text to flow around it.

Rather than using the `<img>` element's align attribute, web page authors are increasingly using the float property to align images.

### Centering Images Using CSS

By default, images are inline elements. This means that they flow within the surrounding text. In order to center an image, it should be turned into a blocklevel element using the display property with a value of block.

Once it has been made into a block-level element, there are two common ways in which you can horizontally center an image:

1. On the containing element, you can use the text-align property with a value of center.

2. On the image itself, you can use the use the margin property and set the values of the left and right margins to auto.

### Background Images

The background-image property allows you to place an image behind any HTML element. This could be the entire page or just part of the page. By default, a background image will repeat to fill the entire box.

The path to the image follows the letters url, and it is put inside parentheses and quotes.

### Repeating Images

The background-repeat property can have four values:

* **repeat**

The background image is repeated both horizontally and vertically (the default way it is shown if the backgroundrepeat property isn't used).

* **repeat-x**

The image is repeated horizontally only (as shown in the first example on the left).

* **repeat-y**

The image is repeated vertically only.

* **no-repeat**
The image is only shown once. The background-attachment property specifies whether a background image should stay in one position or move as the user scrolls up and down the page.

### Background Position

When an image is not being repeated, you can use the background-position property to specify where in the browser window the background image should be placed. This property usually has a pair of values. The first represents the horizontal position and the second represents the vertical.

### shorthand

The background property acts like a shorthand for all of the other background properties you have just seen, and also the background-color property. The properties must be specified in the following order, but you can miss any value if you do not want to specify it.

## Practical Information

### Search Engine Optimization

SEO is a huge topic and several books have been written on the subject. The following pages will help you understand the key concepts so you can improve your website's visibility on search engines.

### How to Identify Keywords and Phrases

Determining which keywords to use on your site can be one of the hardest tasks when you start to think about SEO. Here are six steps that will help you identify the right keywords and phrases for your site.

### Analytics: Learning about your Visitors

As soon as people start coming to your site, you can start analyzing how they found it, what they were looking at and at what point they are leaving. One of the best tools for doing this is a free service offered by Google called Google Analytics.

### How Many People Are Coming to Your Site?

The overview page gives you a snapshot of the key information you are likely to want to know. In particular, it tells you how many people are coming to your site.

### What Are Your Visitors Looking At?

The content link on the left-hand side allows you to learn more about what the visitors are looking at when they come to your site.

### FTP & Third Party Tools

To transfer your code and images from your computer to your hosting company, you use something known as File Transfer Protocol.

As the name suggests, File Transfer Protocol (or FTP) allows you to transfer files across the Internet from your computer to the web server hosting your site.

There are many FTP programs that offer a simple interface that shows you the files on your computer alongside the files that are on your web server. These allow you to drag and drop files from your computer to the server or vice versa.
