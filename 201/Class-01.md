# Introductory HTML and JavaScript

HTML, CSS & Javasript are used to build a complete webpage, but hold on, what are they and how to use them. In this reading we will explain the fundamentals to give you the basic understanding to what these three are and how to use them to create your lovelly webpage.

But before we go any deeper, we must explain some fundamental expressions.

## How people access the web?

### Browsers

People access websites using software called a web browser. Popular examples include Firefox, Internet Explorer, Safari, Chrome, and Opera.
In order to view a web page, users might type a web address into their browser, follow a link from another site, or use a bookmark.

### Web Servers

When you ask your browser for a web page, the request is sent across the Internet to a special computer known as a web server which hosts the website.
Web servers are special computers that are constantly connected to the Internet, and are optimized to send web pages out to people who request them.

### Devices

People are accessing websites on an increasing range of  devices including desktop computers, laptops, tablets, and mobile phones.
It is important to remember that various devices have different screen sizes and some have faster connections to the web than others.

### Screen readers

Screen readers are programs that read out the contents of a computer screen to a user. They are commonly used by people with visual impairments.
In the same way that many countries have legislations that require public buildings to be accessible to those with disabilities, many laws have also been passed that require websites be accessible to those with disabilities.

## How websites are made?

### What you see

When you are looking at a website, it is most likely that your browser will be receiving HTML and CSS from the web server that hosts the site. The web browser interprets the HTML and CSS code to create the page that you see.
In other words, HTML & CSS are not a WYSIWYG, short for What You See Is Not What You Get, type of languages.

### How it is Created

Small websites are often written just using HTML and CSS.
Larger websites ??? in particular those that are updated regularly and use a content management system (CMS), blogging tools, or e-commerce software ??? often make use of more complex technologies on the web server, but these technologies are actually used to produce HTML and CSS that is then sent to the browser. So, if your site uses these technologies, you will be able to use your new HTML and CSS knowledge to take more control over how your site looks.

### HTML5 & CSS3

Since the web was first created there have been several versions of HTML and CSS ??? each intended to be an improvement on the previous version.
It is important to learn these version to build a webpage.

## How the web works

When you visit a website, the web server hosting that site could be anywhere in the world. In order for you to find the location of the web server, your browser will first connect to a Domain Name System (DNS) server.

## So what they are?

**HTML**: HTML stands for Hypertext Markup Language. It creates the structure of your webpage and identify the elements of the page. HTML uses **tages** to identify each element.

**CSS**: CSS stands for Cascading Style Sheet. It is used to make the webpage look more aesthetically pleasing. CSS is not only used to control the look of the content of the page, but also to control where they are positioned in the page.

**Javascript**: is a programming language that conforms to the ECMAScript specification. JavaScript is high-level, often just-in-time compiled, and multi-paradigm. It has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.

All in all, these three, sometimes only HTML & CSS and sometimes much more techonligies, are used to create a complete webpage and bring it to life.

## HTML

### Structure

* HTML pages are text documents.

* HTML uses tags (characters that sit inside angled
brackets) to give the information they surround special
meaning.

* Tags are often referred to as elements.

* Tags usually come in pairs. The opening tag denotes
the start of a piece of content; the closing tag denotes
the end.

* Opening tags can carry attributes, which tell us more
about the content of that element.

* Attributes require a name and a value.

* To learn HTML you need to know what tags are
available for you to use, what they do, and where they
can go.

![HTML Tags](https://tutorial.techaltum.com/images/element.png)

This is how tags look like with their components.

and following is how a HTML file look like:

![HTML](https://henryegloff.com/media/How-to-Develop-a-Basic-Webpage-Using-HTML-and-CSS-Tutorial-2.jpg)

### Extra Markup

* **Doctypes**:

Because there has been several versions of HTML, each web page should begin with a DOCTYPE declaration to tell a browser which version of HTML the page is using

![DocType](https://img.yumpu.com/19454096/1/500x640/doctype-declaration-is-not-a-tag-it-is-an-instruction-.jpg)

* **Comments in HTML**:

If you want to add a comment
to your code that will not be
visible in the user's browser, you
can add the text between these
characters:

![Comment](https://i.ytimg.com/vi/AS_DY-B4LK4/hqdefault.jpg)

* **ID Attribute**:

Every HTML element can carry the id attribute. It is used to uniquely identify that element from other elements on the page. Its value should start with a letter or an underscore (not a number or any other character). It is important that no two elements on the same page have the same value for their id attributes (otherwise the value is no longer unique).
![ID](https://i.stack.imgur.com/UGEIL.png)

* **Class Attribute**:

Every HTML element can also carry a class attribute. Sometimes, rather than uniquely identifying one element within a document, you will want a way to identify several elements as being different from the other elements on the page. For example, you might have some paragraphs of text that contain information that is mor important than others and want to distinguish these elements, or you might want to differentiate between links that point to other pages on your own site and links that point to external sites.
To do this you can use the class attribute. Its value should describe the class it belongs to. In the example on the left, key paragraphs have a class attribute whose value is important.

* **Block Elements**:

Some elements will always appear to start on a new line in the browser window. These are known as block level elements.

* **Grouping Text & Elements In a Block**:

  * **div**: block-elements.html HTML The div element allows you to group a set of elements together in one block-level box. For example, you might create a div element to contain all of the elements for the header of your site (the logo and the navigation), or you might create a div element to contain comments from visitors.
 In a browser, the contents of the div element will start on a new line, but other than this it will make no difference to the presentation of the page.
 Using an id or class attribute on the div element, however, means that you can create CSS style rules to indicate how much space the div element should occupy on the screen and change the appearance of all the elements contained within it.

  * **span**: The span element acts like an inline equivalent of the div element. It is used to either:
  1. Contain a section of text where there is no other suitable element to differentiate it from its surrounding text.
  2. Contain a number of inline elements The most common reason why people use span elements is so that they can control the appearance of the content of these elements using CSS.

* **IFrames**:

An iframe is like a little window that has been cut into your page ??? and in that window you can see another page. The term iframe is an abbreviation of inline frame. One common use of iframes (that you may have seen on various websites) is to embed a Google Map into a page. The content of the iframe can be any html page (either located on the same server or anywhere else on the web).

* **Information About Your Pages**:

The meta element lives inside the head element and contains information about that web page. It is not visible to users but fulfills a number of purposes such as telling search engines about your page, who created it, and whether or not it is time sensitive. (If the page is time sensitive, it can be set to expire.)
The meta element is an empty element so it does not have a closing tag. It uses attributes to carry the information.

### HTML5 Layout

* The new HTML5 elements i XX ndicate the purpose of
different parts of a web page and help to describe
its structure.

* The new elements provide clearer code (compared
with using multiple div elements).

* Older browsers that do not understand HTML5
elements need to be told which elements are
block-level elements.

* To make HTML5 elements work in Internet Explorer 8
(and older versions of IE), extra JavaScript is needed,
which is available free from Google.

### Process & Design

* It's important to understand w XX ho your target audience
is, why they would come to your site, what information
they want to find and when they are likely to return.
* Site maps allow you to plan the structure of a site.
* Wireframes allow you to organize the information that
will need to go on each page.
* Design is about communication. Visual hierarchy helps
visitors understand what you are trying to tell them.
* You can differentiate between pieces of information
using size, color, and style.
* You can use grouping and similarity to help simplify
the information you present.

## Javascript

### What does Javascript do?

Being able to change the content of an HTML page while it is loaded in the browser is very powerful, right?
Javascript brings functionality to the webpage and makes your page alive. Think about it like you are building a house. When building any house, you would start with creating the structure of the house, then you would bring functional systems to the house. at the end you would make it more pleasing to live in.
HTML is the one responsible to create the structure to existence. While CSS is the one responsible to make your webpage more pleasing to the eye. Javascript, on the other hand, is responsible to bring functionality to the webpage.

### EXAMPLES OF JAVASCRIPT IN THE BROWSER

The examples below rely on the ability to:

* **Access**:  the content of the page
* **Modify**:  the content of the page
* **Program**: rules or instructions the browser can follow
* **React**:   to events triggered by the user or browser

* **SLIDESHOWS**

Slideshows in a webpage is an expamle. Slideshows can display a number of different images(or other HTML content) within the same space on a given page. They can play automatically as a sequence, or users can click through the slides manually. They allow more content to be displayed within a limited amount of space.

![Slide](https://bashooka.com/wp-content/uploads/2017/11/slideshow-navigation-website-23.jpg)

**React**: Script triggered when the page loads

**Access**: Get each slide from the slideshow

**Modify**: Only show the first slide (hide others)

**Program**: Set a timer: when to show next slide

**Modify**: Change which slide is shown

**React**: When user clicks button for diffe rent slide

**Program**: Determine which slide to show

**Modify**: Show the requested slide

* **FORMS**

Validating forms (checking whether they have been filled in correctly) is important when information is supplied by users. JavaScript lets you alert the user if mistakes have been made. It can also perform sophisticated calculations based on any data entered and reveal the results to the user.

**React**: User presses the submit button when they have entered their name

**Access**: Get value from form field

**Program**: Check that the name is long enough

**Modify**: Show a warning message if the name is not long enough

### What is script?

But you may ask: what is script and how to create one?

Scripts are made up of instructions a computer can follow step-by-step.

A browser may use different parts of the script depending on how the user interacts with the web page.

Scripts can run different sections of the code in response to the situation around them.

To write a script, you need to first state your goal and then list the tasks that need to be completed in order to achieve it.

Start with the big picture of what you want to achieve, and break that down into smaller steps.

1. **DEFINE THE GOAL**: First, you need to define the task you want to achieve. You can think of this as a puzzle for the computer to solve.

2. **DESIGN THE SCRIPT**: To design a script you split the goal out into a series of tasks that are going to be involved in solving this puzzle. This can be represented using a flowchart.

3. **CODE EACH STEP**: Each of the steps needs to be written in a programming language that the computer understands. In our case, this is JavaScript.

#### FROM STEPS TO CODE

Every step for every task shown in a flowchart needs to be written in a language the computer can understand and follow.

#### THE DOCUMENT OBJECT REPRESENTS AN HTML PAGE

Using the document object, you can access and change what content users see on the page and respond to how they interact with it.

Like other objects that represent real-world things, the document object has:

* **PROPERTIES**: Properties describe characteristics of the current web page (such as the t itle of the page).

* **METHODS**: Methods perform tasks associated with the
document currently loaded in the browser (such as getting information from a specified element or adding new content).

* **EVENTS**: You can respond to events, such as a user clicking or tapping on an element.

#### HOW HTML, CSS, & JAVASCRIPT FIT TOGETHER?

Before diving into the JavaScript language, you need to know how it will fit together with the HTML and CSS in your web pages.

Web developers usually talk about three languages that
are used to create web pages: HTML, CSS, and JavaScript.

Where possible, aim to keep the three languages in separate files, with the HTML page linking to CSS and JavaScript files.

Each language forms a separate layer with a different purpose. Each layer, from left to right. builds on the previous one.

#### CREATING A BASIC JAVASCRIPT

JavaScript is written in plain text, just like HTML and CSS, so you do not need any new tools to write a script. This example adds a greeting into an HTML page. The greeting changes depending on the time of day.

![Greeting](https://miro.medium.com/max/1425/1*OcpJ4iEDSlFJCcvqB-L7sw.png)

#### LINKING TO A JAVASCRIPT FILE FROM AN HTML PAGE

When you want to use JavaScript with a web page, you use the HTML `<script>` element to tell the browser it is coming across a script. Its s re attribute tells people where the JavaScript file is stored.

![Link](https://www.theengineeringprojects.com/wp-content/uploads/2019/12/Where-To-Add-Your-JavaScript-File-1-1.png)
