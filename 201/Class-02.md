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
