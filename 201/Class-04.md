# HTML Links, CSS Layout, JS Functions

## Links

Links are the defining feature of the web because they allow you to move from one web page  to another — enabling the very idea of browsing or surfing.

### Writing Links

Links are created using the `<a>` element. Users can click on anything between the opening `<a>` tag and the closing `</a>` tag. You specify which page you want to link to using the href attribute.

![links](https://i1.wp.com/css-tricks.com/wp-content/uploads/2018/09/nested-links.png?ssl=1)

### Directory Structure

On larger websites it's a good idea to organize your code by placing the pages for each different section of the site into a new folder. Folders on a website are sometimes referred to as directories.

* **Structure**
The diagram on the right shows the directory structure for a fictional entertainment listings website called ExampleArts.

The top-level folder is known as the root folder. (In this example, the root folder is called examplearts.) The root folder contains all of the other files and folders for a website.

* **Relationships**
The relationship between files and folders on a website is described using the same terminology as a family tree.

In the diagram on the right, you can see some relationships have been drawn in.

* **Homepages**
The main homepage of a site written in HTML (and the homepages of each section in a child folder) is called index.html.

Web servers are usually set up to return the index.html file if no file name is specified.

![structure](https://i.ytimg.com/vi/RniGO9Ek6yY/maxresdefault.jpg)

### Email Links

mailto: email-links.html HTML To create a link that starts up the user's email program and addresses an email to a specified email address, you use the `<a>` element. However, this time the value of the href attribute starts with mailto: and is followed by the email address you want the email to be sent to.

![mail](https://www.wikihow.com/images/thumb/3/34/Create-an-Email-Link-in-HTML-Step-5.jpg/v4-460px-Create-an-Email-Link-in-HTML-Step-5.jpg.webp)

### Linking to a Specific Part of the Same Page

At the top of a long page you might want to add a list of contents that links to the corresponding sections lower down. Or you might want to add a link from part way down the page back to the top of it to save users from having to scroll back to the top.

Before you can link to a specific part of a page, you need to identify the points in the page that the link will go to. You do this using the id attribute (which can be used on every HTML element). You can see that the `<h1>` and `<h2>` elements in this example have been given id attributes that identify those sections of the page.

### Linking to a Specific Part of Another Page

If you want to link to a specific part of a different page (whether on your own site or a different website) you can use a similar
technique.

As long as the page you are linking to has id attributes that identify specific parts of the page, you can simply add the same syntax to the end of the link for that page.

## Layout

### Key Concepts in Positioning Elements

Building Blocks CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.

### Controlling the Position of Elements

CSS has the following  ositioning schemes that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning. You specify the positioning scheme using the position property in CSS. You can also float elements using the float property.

* **Normal flow**
Every block-level element appears on a new line, causing each item to appear lower down the page than the previous one. Even if you specify the width of the boxes and there is space for two elements to sit side-byside, they will not appear next to each other. This is the default behavior (unless you tell the browser to do something else).

* **Relative Positioning**
This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed. This does not affect the position of surrounding elements; they stay in the position they would be in in normal flow.

* **Absolute positioning**
This positions the element in relation to its containing element. It is taken out of normal flow, meaning that it does not affect the position of any surrounding elements (as they simply ignore the space it would have taken up). Absolutely positioned elements move as users scroll up and down the page.

### Overlapping Elements

When you use relative, fixed, or absolute positioning, boxes can overlap. If boxes do overlap, the elements that appear later in the HTML code sit on top of those that are earlier in the page.

If you want to control which element sits on top, you can use the z-index property. Its value is a number, and the higher the number the closer that element is to the front. For example, an element with a z-index of 10 will appear over the top of one with a z-index of 5.

### Floating Elements

The float property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible. Anything else that sits inside the containing element will flow around the element that is floated.

### Clearing Floats

The clear property allows you to say that no element (within the same containing element) should touch the left or righthand sides of a box. It can take the following values:

* **left**
The left-hand side of the box should not touch any other elements appearing in the same containing element.

* **right**
The right-hand side of the box will not touch elements appearing in the same containing element.

* **both**
Neither the left nor right-hand sides of the box will touch elements appearing in the same containing element.

* **none**
Elements can touch either side.

### Creating Multi-Column Layouts with Floats

Many web pages use multiple columns in their design. This is achieved by using a `<div>` element to represent each column. The following three CSS properties are used to position the columns next to each other:

* **width**
This sets the width of the columns.

* **float**
This positions the columns next to each other.

* **margin**
This creates a gap between the columns.

### Screen Sizes

Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.

### Screen Resolution

Resolution refers to the number of dots a screen shows per inch. Some devices have a higher resolution than desktop computers and most operating systems allow users to adjust the resolution of their screens.

### Page Sizes

Because screen sizes and display resolutions vary so much, web designers often try to create pages of around 960-1000 pixels wide (since most users will be able to see designs this wide on their screens).

### Fixed Width Layouts

Fixed width layout designs do not change size as the user increases or decreases the size of their browser window. Measurements tend to be given in pixels.

* **Advantages**

  * Pixel values are accurate at controlling size and positioning of elements.
  * The designer has far greater control over the appearance and position of items on the page than with liquid layouts.
  * You can control the lengths of lines of text regardless of the size of the user's window.
  * The size of an image will always remain the same relative to the rest of the page.

* **Disadvantages**

  * You can end up with big gaps around the edge of a page.
  * If the user's screen is a much higher resolution than the designer's screen, the page can look smaller and text can be harder to read.
  * If a user increases font sizes, text might not fit into the allotted spaces.
 devices that have a site or resolution similar to that of desktop or laptop computers.
  * The page will often take up more vertical space than a liquid layout with the same content.

### Liquid Layouts

Liquid layout designs stretch and contract as the user increases or decreases the size of their browser window. They tend to use percentages.

* **Advantages**
  * Pages expand to fill the entire browser window so there are no spaces around the page on a large screen.
  * If the user has a small window, the page can contract to fit it without the user having to scroll to the side.
  * The design is tolerant of users setting font sizes larger than the designer intended (because the page can stretch).

* **Disadvantages**
  * If you do not control the width of sections of the page then the design can look very different than you intended, with unexpected gaps around certain elements or items squashed together.
  * If the user has a wide window, lines of text can become very long, which makes them harder to read.
  * If the user has a very narrow window, words may be squashed and you can end up with few words on each line.
  * If a fixed width item (such as an image) is in a box that is too small to hold it (because the user has made the window smaller) the image can overflow over the text.

### CSS Frameworks

CSS frameworks aim to make your life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. You can include the CSS framework code in your projects rather than writing the CSS from scratch.

* **Advantages**
  * They save you from repeatedly writing code for the same tasks.
  * They will have been tested across different browser versions (which helps avoid browser bugs).

* **Disadvantages**
  * They often require that you use class names in your HTML code that only control the presentation of the page (rather than describe its content).
  * In order to satisfy a wide variety of needs, they often contain more code than you need for your particular web page (commonly referred to as code “bloat”).

### Using the 960.GS Grid

Below you can see a sample layout of a page just like the fixed width page example. On the next page, we will recreate this using the 960.gs stylesheet. Instead of writing our own CSS to control layout, we will need to add classes to the HTML indicating how wide each section should be.
![Grid](https://conceptdraw.com/a1012c4/p1/preview/640/pict--website-wireframe-template-960-grid-system-16-column-layout)

### Functions, Methods & Objects

Browsers require very detailed instructions about what we want them to do. Therefore, complex scripts can run to hundreds (even thousands) of lines. Programmers use functions, methods, and objects to organize their code. This chapter is divided into three sections that introduce:

* **Functions & Methods**
Functions consist of a series of statements that have been grouped together because they perform a specific task.
A method is the same as a function, except methods are created inside (and are part of) an object.

* **Objects**
Previously you saw that programmers use objects to create models of the world using data, and that objects are made up of properties and methods.

* **Built-In Objedcts**
The browser comes with a set of objects thta act like a toolkit for creating interactive web pages.

### What is a function?

Functions let you group a series of statements together to perform a specific task. If different parts of a script repeat the same task, you can reuse the function (rather than repeating the same set of st atements).

### A basic function

![basic](https://www.homeandlearn.co.uk/javascript/images/chapter_4/basic_function.gif)

### Declaring a function

To create a function, you give it a name and then write the statements needed to achieve its task inside the curly braces. This is known as a function declaration.

![function](https://lh3.googleusercontent.com/proxy/g7JVE3v7j-is9JshYKcrenyChbfkn_ydymXToOjuD0mKmD2wqPk4ItEK_Prq2LMQstSZX5JYoMgaD70CMp1oSwpcpgDAMBhVZlBAR3KiY84FeWYldNBAeMb4rSkowoS7GyA)

### Calling a function

Having declared the function, you can then execute all of the statements between its curly braces with just one line of code. This is known as calling the function.

![calling](https://i.stack.imgur.com/x93bg.png)

### Declaring functions that need information

Sometimes a function needs specific information to perform its task. In such cases, when you declare the function you give it parameters. Inside the function, the parameters act like variables.

## Why pair program?

1. Greater efficiency
2. Engaged collaboration
3. Learning from fellow students
4. Social skills
5. Job interview readiness
6. Work environment readiness
