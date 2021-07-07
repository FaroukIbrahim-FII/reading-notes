# HTML Images; CSS Color & Text

## Images

### Choosing Images for Your Site

A picture can say a thousand words, and great images help make the difference between an average-looking site and a really engaging one.

### Storing Images on Your Site

If you are building a site from scratch, it is good practice to create a folder for all of the images the site uses.

### Adding Images

`<img>` to add an images into page you need to use an `<img>` element. This is an empty element (which means there is no closing tag).

![image](https://easytolearning.com/ck_files/files/html-image-tag.png)

### Three Rules for Creating Images

There are three rules to remember when you are creating images for your website which are summarized below. We go into greater detail on each topic over the next nine pages.

1. Save images in the right format.

2. Save images at the right size.

3. Use the correct resolution.

### Image Di mensions

The images you use on your website should be saved at the same width and height that you want them to appear on the page.

### HTML5: Figure and Figure Caption

Images often come with captions. HTML5 has introduced a new `<figure>` element to contain images and their caption so that the two are associated.

You can have more than one image inside the `<figure>` element as long as they all share the same caption.

## Color

### Foreground Color

The color property allows you to specify the color of text inside an element. You can specify any color in CSS in one of three ways:.

* **rgb values**
These express colors in terms of how much red, green and blue are used to make it up. For example: rgb(100,100,90)

* **hex codes**
These are six-digit codes that represent the amount of red, green and blue in a color, preceded by a pound or hash # sign. For example: #ee3e80

* **color names**
There are 147 predefined color names that are recognized by browsers. For example: DarkCyan

### Contrast

When picking foreground and background colors, it is important to ensure that there is enough contrast for the text to be legible.

## Text

### Typeface Terminology

![text](https://i.pinimg.com/originals/f2/85/d0/f285d07284822a5fd0fd096e358d9f9d.jpg)

### Choosing a Typeface for your Website

When choosing a typeface, it is important to understand that a browser will usually only display it if it's installed on that user's computer.

### Specifying Typefaces

The font-family property allows you to specify the typeface that should be used for any text inside the element(s) to which a CSS rule applies.
The value of this property is the name of the typeface you want to use.

The people who are visiting your site need the typeface you have specified installed on their computer in order for it to be displayed.

### Type Scales

You may have noticed that programs such as Word, Photoshop and InDesign offer the same sizes of text.

### Alignment

The text-align property allows you to control the alignment of text. The property can take one of four values:

* **left**
This indicates that the text should be left-aligned.

* **right**
This indicates that the text should be right-aligned.

* **center**
This allows you to center text.

* **justify**
This indicates that every line in a paragraph, except the last line, should be set to take up the full width of the containing box.

### Attribute Selectors

You met the most popular CSS selectors on page 238. There are also a set of attribute selectors that allow you to create rules that apply to elements that have an attribute with a specific value.

### JPEG vs PNG vs GIF

There is a significant difference in the number of colours that can be supported by these 3 formats.

* **JPEG** images can support around 16 million colours. This is what makes them suitable for storing images of natural scenes.

* **PNG** images mainly have two modes — PNG8 and PNG24. PNG8 can support upto 256 colours whereas PNG24 can handle upto 16 million colours like a JPEG image. Use PNG8 for simple shapes with fewer colours and PNG24 for high quality, complex logos and shapes with rounded corners on a transparent background.

* **GIF** images are limited to 256 colours. If index transparency is used, then one of these 256 colours is assigned as transparent and the remaining 255 are used for other colours.
