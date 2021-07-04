# HTML Text, CSS Introduction, and Basic JavaScript Instructions

## Headings

To create a heading in HTML file, all you need to do is a typing `<h1>your heading goes here </h1>`.

Notice the `1` after the `h`, this means you want the heading to be the biggest possible.
In HTML there are six headings:

* `<h1>`
* `<h2>`
* `<h3>`
* `<h4>`
* `<h5>`
* `<h6>`

`<h1>` is used as the meain heading.

`<h2>` is used for subheadings.

If there are further sections under the subheadings then the `<h3>` element is used, and so on...

## Paragraph

To create a paragraph, surround the words that make up the paragraph with an opening `<p>` tag and closing `</p>` tag.

![Paragraph](https://ictacademy.com.ng/wp-content/uploads/2017/10/demo.png)

## Bold & Italic

* `<b>`
By enclosing words in the tags `<b>` and `</b>` we can make characters appear bold.
The `<b>` element also represents a section of text that would be presented in a visually different way (for example key words in a paragraph) although the use of the `<b>` element does not imply any additional meaning.

* `<i>`
By enclosing words in the tags `<i>` and `</i>` we can make characters appear italic.
The `<i>` element also represents a section of text that would be said in a different way from surrounding content — such as technical terms, names of ships, foreign words, thoughts, or other terms that would usually be italicized.

## Superscript & Subscript

* `<sup>`
The `<sup>` element is used
to contain characters that
should be superscript such
as the suffixes of dates or
mathematical concepts like
raising a number to a power such
as 22.

* `<sub>`
The `<sub>` element is used to
contain characters that should
be subscript. It is commonly
used with foot notes or chemical
formulas such as H2O.

![Sup & Sub](https://www.oreilly.com/library/view/web-standards-programmers/9780764588204/9780764588204_superscript_comma_subscript_comma_big_co_image01.png)

## Line Breaks & Horizontal Rules

* `<br />`
As you have already seen, the browser will automatically show each new paragraph or heading on a new line. But if you wanted to add a line break inside the middle of a paragraph you can use the line break tag `<br />`.
![Break](https://www.w3docs.com/uploads/media/default/0001/01/83395ae551d92691b4319c507197339031f32414.png)

* `<hr />`
To create a break between themes — such as a change of topic in a book or a new scene in a play — you can add a horizontal rule between sections using the `<hr />` tag.
There are a few elements that do not have any words between an opening and closing tag. They are known as empty elements and they are written differently.
![hr](https://www.codingmanuals.com/wp-content/uploads/2010/07/hrprog.JPG)

## Semantic Markup

There are some text elements that are not intended to affect the structure of your web pages, but they do add extra information to the pages — they are known as semantic markup.
![semantic](https://qph.fs.quoracdn.net/main-qimg-0e07f207e1a55c01bd2b60389c08e8f9)

## Understanding CSS: Thinking Insi de the Box

The key to understanding how CSS works is to imagine that there is an invisible box around every HTML element.

CSS allows you to create rules that control the way that each individual box (and the contents of that box) is presented.

Image below shows the difference CSS make:

![CSS](https://www.suntos.com.np/before-css-after.jpeg)

## CSS Associates Style rules with HTML elements

CSS works by associating rules with HTML elements. These rules govern how the content of specified elements should be displayed. A CSS rule contains two parts: a selector and a declaration.
![Selector](https://res.cloudinary.com/practicaldev/image/fetch/s--Uvc4p-Vs--/c_imagga_scale,f_auto,fl_progressive,h_900,q_auto,w_1600/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/edojfcbz6sr7j0b2l6v1.jpg)

## CSS Properties Affect How Elements Are Displayed

CSS declarations sit inside curly brackets and each is made up of two parts: a property and a value, separated by a colon. You can specify several properties in one declaration, each separated by a semi-colon.

![Prop](https://res.cloudinary.com/practicaldev/image/fetch/s--AuDj3vTU--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/edojfcbz6sr7j0b2l6v1.jpg)

|Selector| Meaning| Example|
|:---| :---| :---|
|Universal Selector|Applies to all elements in the document|* {} Targets all elements on the page|
|Type Selector|Matches element names|h1, h2, h3 {} Targets the `<h1>`, `<h2>` and `<h3>` elements|
|Class Selector|Matches an element whose class attribute has a value that matches the one specified after the period (or full stop) symbol|.note {} Targets any element whose class attribute has a value of note p.note {} Targets only `<p>` elements whose class attribute has a value of note|
|ID Selector|Matches an element whose id attribute has a value that matches the one specified after the pound or hash symbol|#introduction {} Targets the element whose id attribute has a value of introduction|
|Child Selector|Matches an element that is a direct child of another|li>a {} Targets any `<a>` elements that are children of an `<li>` element (but not other `<a>` elements in the page)|
|Descendant Selector|Matches an element that is a descendent of another specified element (not just a direct child of that element)| p a {} Targets any `<a>` elements that sit inside a `<p>` element, even if there are other elements nested between them|
|Adjacent Sibling Selector|Matches an element that is the next sibling of another|h1+p {} Targets the first `<p>` element after any `<h1>` element (but not other `<p>` elements)|
|General Sibling Selector|Matches an element that is a sibling of another, although it does not have to be the directly preceding element|h1~p {} If you had two `<p>` elements that are siblings of an `<h1>` element, this rule would apply to both|

## How CSS Rules Cascade

If there are two or more rules that apply to the same element, it is important to understand which will take precedence.

* **LAST RULE**
If the two selectors are identical, the latter of the two will take precedence. Here you can see the second i selector takes precedence over the first.

* **SPECIFICITY**
If one selector is more specific than the others, the more specific rule will take precedence over more general ones. In this example:

h1 is more specific than * p b is more specific than p p#intro is more specific than p.

* **IMPORTANT**
You can add !important after any property value to indicate that it should be considered more important than other rules that apply to the same element.

## Inheritance

If you specify the font-family or color properties on the `<body>` element, they will apply to most child elements. This is because the value of the font-family property is inherited by child elements. It saves you from having to apply these properties to as many elements (and results in simpler style sheets).

You can compare this with the background-color or border properties; they are not inherited by child elements. If these were inherited by all child elements then the page could look quite messy.

## Why use External Style Sheets?

When building a website there are several advantages to placing your CSS rules in a separate style sheet.

All of your web pages can share the same style sheet. This is achieved by using the `<link>` element on each HTML page of your site to link to the same CSS document. This means that the same code does not need to be repeated in every page (which results in less code and smaller HTML pages).

Therefore, once the user has downloaded the CSS stylesheet, the rest of the site will load faster. If you want to make a change to how your site appears, you only need to edit the one CSS file and all of your pages will be updated. For example, you can change the style of every `<h1>` element by altering the one CSS style sheet, rather than changing the CSS rules on every page. The HTML code will be easier to read and edit because it does not have lots of CSS rules in the same document. It is generally considered good practice to have the content of the site separated from the rules that determine how it appears.

## PLACING THE SCRIPT IN THE PAGE

You may see JavaScript in the HTML between opening `<script>` and closing `</script>` tags (but it is better to put scripts in their own files).

* try opening the HTML file, removing the src attribute from the opening `<script>` tag, and adding the new code shown on the left between the opening `<script>` tag and the closing `</script>` tag. The s re attribute is no longer needed because the JavaScript is in the HTML page.

* Open the HTML file in your web browser and the welcome greeting is written into the page.

## Javascript runs where it is found in the HTML

When the browser comes across a `<Script>` element, it stops to load the script and then checks to see if it needs to do anything.

## Basic Javascript instructions

### STATEMENTS

A script is a series of instructions that a computer can follow one-by-one. Each individual instruction or step is known as a statement. Statements should end with a semicolon.

![Statement](https://www.bookofnetwork.com/images/javascript-images/JS_Expression-in-Statement_17Oct16_1503.png)

### Comments

You should write comments to explain what your code does. They help make your code easier to read and understand. This can help you and others who read your code.

![Comment](https://prognotes.net/wp-content/uploads/2017/06/php-versus-javascript-comments.png)

### Variable

A script will have to temporarily store the bits of information it needs to do its job. It can store this data in variables.
When you write JavaScript, you have to tell the interpreter every individual step that you want it to perform. This sometimes involves more detail than you might expect.

![var](https://1.bp.blogspot.com/-8UmWFTngfwY/XkVRuoPFfkI/AAAAAAAACmI/93j-FMkA9EYyoRIT1qlJ2sMUbobnWT1UgCLcBGAsYHQ/s1600/javascript_var.png)

### Data types

JavaScript distinguishes between numbers, strings, and true or false values known as Booleans.

![types](https://1.bp.blogspot.com/-EPrHJaCTGoU/X3MajXYktEI/AAAAAAAAB5E/qgkmTg0A0s0aRzvsmhmGpa3z2r9bQjIYwCLcBGAsYHQ/w400-h281/668dfc002312ab58e0d1cb15e0b98a5e.png)

### Quotes inside a string

Sometimes you will want to use a double or single quote mark within a string. Because strings can live in single or double quotes, if you just want to use double quotes in the string, you could surround the entire string in single quotes.

### ARRAYS

An array is a special type of variable. It doesn't just store one value; it stores a list of values.

![array](https://www.encodedna.com/javascript/remove-empty-array-slots-using-flat-method-javascript.png)

### ACCESSING & CHANGING VALUES IN AN ARRAY

The first lines of code on the left create an array containing a list of three colors. (The values can be added on the same line or on separate lines as shown here.) Having created the array, the third item on the list is changed from 'custom' to 'beige'. To access a value from an array, after the array name you specify the index number for that value inside square brackets.

### EXPRESSIONS

An expression evaluates into (results in) a single value. Broadly speaking there are two types of expressions.

![expression](https://i.stack.imgur.com/cnK8e.png)

### OPERATORS

Expressions rely on things called operators; they allow programmers to create a single value from one or more values.

![operators](https://i.pinimg.com/originals/13/09/cb/1309cb725dea3e859a873607dd298d00.png)

### CREATING A DATE OBJECT

![date](https://www.codegrepper.com/codeimages/create-date-object-with-time-javascript.png)

### WORKING WITH DATES & TIMES

To specify a date and time, you can use this format: YYYY, MM, OD, HH, MM, SS 1996, 04, 16, 15, 45, 55 This represents 3:45pm and 55 seconds on April 16, 1996.
The order and syntax for this is:

|Year| four digits|
|:---|:---------|
|Month| 0-11 (Jan is 0)|
|Day| 1-31|
|Hour| 0-23|
|Minutes| 0-59|
|Seconds| 0-59|
|Milliseconds| 0-999|

### EXAMPLE: FUNCTIONS, METHODS & OBJECTS

This example is split into two parts. The first shows you the details about the hotel, room rate, and offer rate. The second part indicates when the offer expires.

All of the code is placed inside an immediately invoked function expression (llFE) to ensure any variable names used in the script do not clash with variable names used in other scripts.

The first part of the script creates a hot el object; it has three properties (the hotel name, room rate, and percentage discount being offered), plus a method to calculate the offer price which is shown to the user.

The details of the discount are written into the page using information from this hote 1 object. To ensure that the discounted rate is shown with two decimal places (like most prices are shown) the . to Fixed () method of the Number object is used.

The second part of the script shows that the offer will expire in seven days. It does this using a function called offerExpi res(). The date currently set on the user's computer is passed as an argument to the offerExpi res() function so that it can calculate when the offer ends.

## Decisions & Loops

### Decision Making

There are often several places in a script where decisions are made that determine which lines of code should be run next. Flowchars can help you plan for these occasions.

![flowchart](https://i.pinimg.com/originals/a3/26/85/a3268554c5429e6d320044d0cceed273.png)

### Evaluating conditions & conditional statements

There are two components to a decision:

1. An expression is evaluated, which returns a value.
2. A conditional statement says what to do in a given situation

![condition](https://image.slidesharecdn.com/ch2javascript-conditional-statements-120510030023-phpapp01/95/javascript-conditionalstatements-3-728.jpg?cb=1336619165)

### Comparision operators: evaluating conditions

You can evaluate a situation by comparing one value in the script to what you expect it might be. The result will be a boolean: true or false.

![comparision](https://i.ytimg.com/vi/wFB-ywsNPwg/maxresdefault.jpg)

### Structuring comparison operators

In any condition, there is usually one operator and two operands. The operands are placed on each side of the perator. They can be values or variables. You often see expressions enclosed in brackets.

![structure](https://qph.fs.quoracdn.net/main-qimg-5b0bfdf375ab189520785f2d2caa6313)
