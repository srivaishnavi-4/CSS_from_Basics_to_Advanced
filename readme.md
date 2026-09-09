# CSS
    CSS stands for Cascade Style Sheet is popular stylesheet language used to design an interactive webpage
 ## 1_Syntax & Selectors
   * Selector: CSS selectors are used to select the HTML element or groups of elements you want to style on a web page.
   * Property: A CSS property is an aspect or characteristic of an HTML element that can be styled or modified using CSS, such as color, font-size, or margin.
   * Value: Values are assigned to properties. For example, color property can have value like red, green etc.
```html
selector {
    property: value;
}
```
   ### Multiple Style Rules
    If you want to define multiple rules for a single selectors you can specify those in single block separated by a semicolon (;).
    Syntax
```html
selector{
    property1: value1;
    property2: value2;
    property3: value3;
}
```
   ### CSS Selectors Syntax
   CSS Selectors are used to select the HTML elements you want to style on a web page. They allow you to target specific elements or groups of elements to apply styles like colors, fonts, margins, and more.
   Types
    Simple selector
    Combinator selector
    Pseudo-class selectors
    pseudo element selectors
    Attribute selectors
## Simple selector
used the class,id,element,grouping and universal selectors to style the elements
   **Universal Selector** Universal selectors select and apply styles to all elements in an HTML document.
```css
    * {
    font-family: Verdana, sans-serif;
    color: green;
    }
```
   **Element Selectors** Element selectors select specific HTML elements.
```css
    h1 {
        color: #04af2f;
    }
```
   **Class Selectors** Class selectors select and style an element with a specific value for its class attribute.
```css
    .myDiv {
        color: #04af2f;
    }
```
   **Id Selectors** Id selectors select a single element with a particular value for the id attribute.
```css
    #myDiv {
        color: #04af2f;
    }
```
   **Attribute Selectors** Attribute selectors select an element based on a specific attribute value.
```css
    a[target] {
    background-color: peachpuff;
    }
```
   ### Combinator selectors
    It defines the relationship between one or more selectors
    4 types of combinators in css
        Descendent combinator()
        child combinator(>)
        nextsibling combinator(+)
        subsequent sibling combinator(~)
  ####  Descendent combinator
    select elements that are descending of the first element
    i.e child,grandchild of the element
    syntax element1(space)element2
    example: 
```css
div p{
    text-align:center;
    color:red;
}
```
 #### child combinator
    selects all elements that are direct  children of the first element.
    used(>) symbol.
    syntax: element1>element2
    example:
```css
div >p{
    background-color:yellow;
}
```
  #### next sibling combinator
    used to select an element directlyvafter a specific element
    can be used as(+)
    syntax:element1 + element2
    example:
```css
    div+p{
        background-color:yellow;
    }
```
  #### subsequent sibling combinator:
    used to select all the elements that are next siblings of a specified element
    (~) is used.
    example:
```css
div~p{
    background-color:yellow;
}
```
  ### CSS [attribute] Selector
    The [attribute] selector is used to select elements with the specified attribute.
    The following example selects all <a> elements with a target attribute.
    Example
```css
    a[target] {
    background-color: yellow;
    }
```
  ### CSS [attribute="value"] Selector
        The [attribute="value"] selector is used to select elements with a specific attribute with an exact value.

        The following example selects all <a> elements with a target="_blank" attribute:
        Example
```css
        a[target="_blank"] {
        background-color: yellow;
        }
```
   ### CSS [attribute~="value"] Selector
    The [attribute~="value"] selector is used to select elements with an attribute value containing a specific word.
    The following example selects all elements with a title attribute that contains a space-separated list of words, one of which is "flower":
    Example
```css
    [title~="flower"] {
    border: 5px solid yellow;
    }
```
    The example above will match elements with title="flower", title="summer flower", and title="flower new", but not title="my-flower" or title="flowers".
### CSS [attribute|="value"] Selector
The `[attribute|="value"]` selector is used to select elements with the specific attribute, whose value can be exactly the specific value, or start with the specific value followed by a hyphen (-).

    Note: The value has to be a whole word, either alone, like class="top", or followed by a hyphen ( - ), like class="top-text".
    Example
```css
    [class|="top"] {
    background: yellow;
    } 
```
### pseudo classes
**Interactive Pseudo-classes (`:hover`, `:focus`, `:active`)**

```html
<button class="interactive-btn">Click Me</button>
```

```css
.interactive-btn {
  background-color: #3498db;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  transition: background-color 0.2s;
}
/* Mouse is over the button */
.interactive-btn:hover {
  background-color: #2980b9;
}
/* Element has focus (e.g., clicked or tabbed into) */
.interactive-btn:focus {
  outline: 3px solid #f1c40f;
}
/* Element is actively being pressed down */
.interactive-btn:active {
  background-color: #1f618d;
  transform: scale(0.98);
}
```
---
**Link Pseudo-classes (`:link`, `:visited`)**
```html
<p><a href="https://example.com" class="link-demo">Visit Example</a></p>
```
```css
/* Unvisited link */
.link-demo:link {
  color: #2980b9;
  text-decoration: underline;
}
/* Visited link */
.link-demo:visited {
  color: #8e44ad;
}
```
---
**Structural Pseudo-classes (`:first-child`, `:last-child`, `:nth-child`)**
```html
<ul class="list-demo">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
  <li>Item 4</li>
</ul>
```
```css
/* First item in the parent container */
.list-demo li:first-child {
  font-weight: bold;
  color: #e74c3c;
}
/* Every even-numbered item */
.list-demo li:nth-child(even) {
  background-color: #f9f9f9;
}
/* Last item in the parent container */
.list-demo li:last-child {
  border-bottom: 2px solid #ccc;
}
```
  #### **Text Pseudo-elements (`::first-line`, `::first-letter`)**

```html
<p class="article-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>

```

```css
/* Style only the first line of the paragraph */
.article-text::first-line {
  font-weight: bold;
  color: #2c3e50;
  text-transform: uppercase;
}

/* Style only the very first letter (drop cap effect) */
.article-text::first-letter {
  font-size: 3rem;
  float: left;
  line-height: 1;
  margin-right: 8px;
  color: #e74c3c;
}

```

---

**Content Pseudo-elements (`::before`, `::after`)**

```html
<blockquote class="quote">Simplicity is the ultimate sophistication.</blockquote>

```

```css
/* Insert decorative quotation marks via CSS */
.quote::before {
  content: "“";
  font-size: 2rem;
  color: #3498db;
  vertical-align: middle;
}

.quote::after {
  content: "”";
  font-size: 2rem;
  color: #3498db;
  vertical-align: middle;
}

```

---

**List Markers & User Selection (`::marker`, `::selection`)**

```html
<ul class="custom-list">
  <li>First list item</li>
  <li>Second list item</li>
</ul>
<p class="selectable-text">Highlight this text with your mouse to see the custom selection color.</p>

```

```css
/* Style bullet points */
.custom-list li::marker {
  color: #e74c3c;
  font-size: 1.2rem;
}

/* Style text highlighted by the user */
.selectable-text::selection {
  background-color: #f1c40f;
  color: #2c3e50;
}

```

---

**Dialog Backdrop (`::backdrop`)**

```html
<dialog id="my-dialog">
  <p>This is a modal dialog popup.</p>
  <button onclick="document.getElementById('my-dialog').close()">Close</button>
</dialog>
<button onclick="document.getElementById('my-dialog').showModal()">Open Dialog</button>

```

```css
/* Style the background overlay behind an open <dialog> */
dialog::backdrop {
  background-color: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(4px);
}

```
## 2_Cascade and Specificity
  ### How Cascading Works in CSS?
    CSS rules can come from multiple sources: user-defined styles, browser default styles, and custom styles from a website. The cascading process determines which of these styles is applied when they conflict.
    How they works
        Specificity: CSS rules with more specific selectors take priority over less specific ones. For example, an ID selector (#header) is more specific than a class selector (.header), so it will override it if both are applied to the same element.
        Importance: Styles marked with !important take precedence over all other styles, even if they are less specific. However, overusing !important can lead to maintenance problems and should be avoided unless absolutely necessary.
        Source Order: When two rules have the same specificity and importance, the order in which the rules are defined matters. The later rule (appearing further down the CSS file or in the later <style> block) will override the earlier one.
    Cascading Order Breakdown
    Here’s a simplified breakdown of the cascading order from highest priority to lowest priority:
        !important: Highest priority, regardless of source.
        Inline styles: Next in priority, unless overridden by !important.
        Internal CSS: Styles within a <style> tag which apply only to that document.
        External CSS: Styles from external CSS files linked to the HTML document, which apply globally across multiple pages.
        Browser/User styles: Defaults or user-defined preferences.
  ### CSS Specificity
        CSS specificity is an algorithm that determines which style declaration is ultimately applied to an element.
        If two or more CSS rules point to the same element, the declaration with the highest specificity will "win", and that style will be applied to the HTML element.
Look at the following examples:
Example
Here, we have specified a red color for <p> elements. Result: The text will be red:
```html
<html>
<head>
  <style>
    p {color: red;}
  </style>
</head>
<body>

<p>Hello World!</p>

</body>
</html>
```
Now, look at next example:
Example
Here, we have added a class selector (named "test"), and specified a green color for this class. Result: The text will be green, because the class selector has higher specificity:
```html
<html>
<head>
  <style>
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p class="test">Hello World!</p>

</body>
</html>
```
Now, look at next example:
Example
Here, we have added the id selector (named "demo"). Result: The text will be blue, because the id selector has higher specificity:
```html
<html>
<head>
  <style>
    #demo {color: blue;}
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p id="demo" class="test">Hello World!</p>

</body>
</html>
```
Now, look at next example:
Example
Here, we have added an inline style for the <p> element. Result: The text will be pink, because the inline style has the highest specificity:
```html
<html>
<head>
  <style>
    #demo {color: blue;}
    .test {color: green;}
    p {color: red;}
  </style>
</head>
<body>

<p id="demo" class="test" style="color: pink;">Hello World!</p>

</body>
</html> 
```
  #### Specificity Hierachy
```jon
    Selector 	                                        Example 	                Description                   Weight
    Inline styles 	                                    <h1 style="color: pink;"> 	Highest priority, will override all other selectors 	 
    Id selectors 	                                     #navbar 	                Second highest priority 	1-0-0
    Classes, attribute selectors and pseudo-classes 	.test, [type="text"], :hover Third highest priority 	0-1-0
    Elements and pseudo-elements 	                     h1, ::before, ::after 	     Low priority 	            0-0-1
    Universal selector and :where() 	                  *, where() 	              No priority 	            0-0-0
```
## 3_CSS Inheritance
    CSS inheritance is about what happens if no value is specified for a property on an element.
    If no value is specified for a property, the value can either be inherited from the parent element, or be set to its initial (default) value.
    For CSS inheritance, properties are categorized in two types:
        inherited properties
        non-inherited properties

**Inherited Properties**
    Inherited properties are, by default, set to the computed value of the parent element.
    Properties related to text, such as color, font-family, font-size, line-height, and text-align, are typically inherited. This ensures consistent text styling throughout a document.
    In the following example, the text inside the `<strong>` element will appear in 20px and in blue, since the `<strong>` element inherits the color and the font-size value from the parent `(<p>)` element.
    Example
    The color and font-size properties are inherited:
```html
    <style>
    p {
    color: blue;
    font-size: 20px;
    }
    </style>

    <body>
    <p>This is a paragraph with some <strong>important</strong> text.</p>
    </body>
```
**Non-inherited Properties**
    If there is not set a value for a non-inherited property, the value is set to the initial (default) value of that property.
    Properties related to the box model or layout, like border, background, margin, padding, width, and height, are typically not inherited.
    In the following example, the `<strong>` element, inside the `<p>` element, will not have an additional border (since the initial value of border-style is none).
    Example
    The border property is not inherited:
```html
    <style>
    p {
    border: 1px solid red;
    }
    </style>

    <body>
    <p>This is a paragraph with some <strong>important</strong> text.</p>
    </body>
```
**The inherit Keyword**
    The inherit keyword is used to explicitly specify inheritance. It works on both inherited and non-inherited properties.
    In the following example, the `<strong>` element, inside the `<p>` element, will have an additional border, since we have used the inherit keyword to explicitly specify that the border value should be inherit.
    Example
    Explicitly set the inheritance with the inherit keyword:
```html
    <style>
    p {
    border: 1px solid red;
    }

    strong {
    border: inherit;
    }
    </style>

    <body>
    <p>This is a paragraph with some <strong>strong</strong> text.</p>
    </body>
``` 
## 4_CSS Units
CSS units are used to define the length and size of several properties.
Several CSS properties take "length" values, such as font-size, width, margin, padding, border, etc.
CSS has two types of units:
    Absolute units
    Relative units
### Absolute units
    Absolute units are fixed, and the length expressed in any of these will appear exactly that size.
    Absolute units do not change when the screen size change, and are not recommended for websites. However, they can be used if the output medium is known, such as for print layout.
    The most used absolute unit is px (pixels).
    Unit 	Name 	        Description 	
    px  	Pixels 	        The most used absolute unit for screens (1px = 1/96th of 1in) 	
    cm  	Centimeters 	Primarly used in print stylesheet 	
    mm  	Millimeters 	Primarly used in print stylesheet 	
    in 	    Inches 	        Primarly used in print stylesheet (1in = 96px = 2.54cm) 	
    pt  	Points      	A typographical unit (1pt = 1/72 of 1in) 	
    pc  	Picas 	        A print unit (1pc = 12 pt) 	
    
    Set Font Size With Px
    Setting the text size with px (pixels) gives you full control over the text size.
    If we use pixels, the web page may not scale very well on different screen sizes and the users cannot adjust the text size in their browser settings. However, users can still use the zoom tool to resize the entire page.
    Example
```css
    h1 {
    font-size: 40px;
    }

    h2 {
    font-size: 30px;
    }

    p {
    font-size: 17px;
    }
```
    Note: A whitespace cannot appear between the number and the unit. However, if the value is 0, the unit can be omitted.
### Relative units
    Relative units specify a length relative to another length property (like parent element, root element, or viewport).
    Relative length units scale better between different screen sizes.
    Tip: The em and rem units are perfect for creating scalable and responsive websites!
```json
    Unit 	 Description 	
    em 	     Relative to the font-size of the parent element 	
    rem 	 Relative to the font-size of the root HTML element 	
    vw 	     Relative to 1% of the width of the viewport*. 100vw = full width of the viewport 	
    vh 	     Relative to 1% of the height of the viewport*. 100vh = full height of the viewport 	
    vmin 	 Relative to 1% of viewport's* smaller dimension 	
    vmax 	 Relative to 1% of viewport's* larger dimension 	
    % 	     Relative to the size of the parent element 	
    fr     	 A fractional unit. 1fr equals 1 part of the available space 	
    ch 	     Relative to width of the "0" (zero) character 	
```
    * Viewport = the browser window size. 1vw = 1% of the current width of the browser's viewport. So, if the viewport is 500px wide, 1vw is 5px.
   **Set Font Size With Em**
    The em unit is relative to the font size of the parent element. So, if the parent element has a font size of 16px, then 2.5em would result in 40px.
    In the following example, the text size in em is the same as the previous example in pixels. However, the em unit allows the user to adjust the text size in the browser settings.
    Example
    Set font sizes with em:
```css
    body {
    font-size: 16px; /* Base font size */
    }

    h1 {
    font-size: 2.5em; /* 2.5 * 16 = 40px */
    }

    h2 {
    font-size: 1.875em; /* 1.875 * 16 = 30px */
    }

    p {
    font-size: 1em; /* 1 * 16 = 16px */
    }
```
  **Set Font Size With Rem**
    The rem unit is relative to the font size of the root HTML element `(<html>)`.
    Unlike em, which is relative to the font-size of its parent element, rem always refers to the font-size of the `<html>` element, regardless of its position in the document tree. This makes rem very useful for creating scalable and responsive designs. By changing the font-size of the `<html>` element, all elements sized with rem units will scale proportionally throughout the entire page.
    The default font-size of the `<html>` element in most browsers, is 16px. So, by default, 1rem equals 16px unless explicitly overridden in the CSS.
    Example
    Set font sizes with rem:
```css
    html {
    font-size: 16px; /* Set the root font size */
    }

    h1 {
    font-size: 2.5rem; /* 2.5 * 16 = 40px */
    }

    h2 {
    font-size: 1.875rem; /* 1.875 * 16 = 30px */
    }

    p {
    font-size: 1rem; /* 1 * 16 = 16px */
    } 
```
 ## 5_Box Model
 * In CSS, the term "box model" is used when talking about web design and layout.
 * The CSS box model is essentially a box that wraps around every HTML element.
 * Every box consists of four parts: content, padding, borders and margins.
 Explanation of the different parts (from innermost part to outermost part):
    **Content** - The content of the box, where text and images appear
    **Padding** - Clears an area around the content. The padding is transparent.can mention through by mentioning the sides
    **Border** - A border that goes around the padding and content
    **Margin** - Clears an area outside the border. The margin is transparent. Like padding, margins can also be set separately for each side
The box model allows us to add a border around elements, and to define space between elements.
Sample code format
```html
<style>
            div{
                width:150px;
                border: 2px solid green;
                padding:50px;
                margin:40px;
            }
            span{
                margin: 100px;
                border: 2px solid black;
                border-radius: 10px;
                padding: 20px;
                background-color: lightblue;
                display:block;
            }
        </style>
        <h1>Box Model</h1>
        <span>This is a sample paragraph for box model</span>
        <span>Sample Button</span>
        <div>Sample Box Format</div>
```



