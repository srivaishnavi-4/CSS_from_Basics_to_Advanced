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
   ### Box Sizing
      The CSS box-sizing property defines how to calculate the width and height of an element: should the calculation include padding and borders, or not.
      By default, the width and height of an element is calculated like this:
          width + padding + border = actual width of an element
          height + padding + border = actual height of an element
      This means: When you set the width/height of an element, the element often appears bigger than you have set (because the element's border and padding are added to the element's specified width/height).
  #### The CSS box-sizing Solution
      The box-sizing property allows us to include the padding and border in an element's total width and height.
      If you set box-sizing: border-box; on an element, the padding and border are included in the calculation of the width and height
      Here is the same example as above, with box-sizing: border-box; added to both <div> elements:
      Example
```css
      .div1 {
        width: 300px;
        height: 100px;
        border: 1px solid blue;
        box-sizing: border-box;
      }

      .div2 {
        width: 300px;
        height: 100px;
        padding: 50px;
        border: 1px solid red;
        box-sizing: border-box;
      }
```
  Since the result of using the `box-sizing: border-box;` is so much better, many developers want all elements on their pages to work this way.
  The code below ensures that all elements are sized in this more intuitive way. Many browsers already use `box-sizing: border-box;` for many form elements (but not all - which is why inputs and text areas look different at width: 100%;).
      Applying this to all elements is safe and wise:
      Example
```css
      * {
        box-sizing: border-box;
      } 
```
   ## 6_Typography
    Typography shapes the voice of your interface.
    Combine semantic HTML with CSS font, size, weight, and spacing utilities to craft clear, readable content.
  **Choosing fonts**
        Use system fonts for performance or host web fonts via services like Google Fonts.
        Set a base font on body and use fallbacks: font-family: "Inter", "Segoe UI", sans-serif;
        Limit the number of font families to keep the design cohesive.
    Note: A fallback is a backup font used if the first choice is unavailable.
  ### Scaling type
    Use relative units (rem, em) so text responds to user preferences.
    Note: rem scales from the root font size, while em scales from the parent element.
    Example:
```css
    :root {
      font-size: 100%; /* 16px default */
    }
    body {
      font-size: 1rem; /* 16px */
    }
    h1 { font-size: clamp(2.5rem, 5vw, 3.5rem); }
    h2 { font-size: 2rem; }
    p  { font-size: 1.125rem; }
```
  This scale sets base size on body and uses `clamp()` for headings so text adapts smoothly across viewports.
  ### Font weight and style
  `font-weight: 400; normal, 700; bold, 500 medium.`
  `font-style: italic; applies emphasis.`
    Note: Weights are numeric: the higher the number, the thicker the text.
  ### Line height and spacing
    Set line-height between 1.5 and 1.8 for paragraphs.
    Use letter-spacing sparingly for uppercase text.

    Note: line-height adds vertical space between lines, and letter-spacing adjusts the gap between characters.
  ### Text alignment and decoration
        text-align for horizontal alignment.
        text-transform for uppercase/lowercase.
        text-decoration for underlines; customize color and thickness.
  ### Responsive typography
    Use clamp() and media queries to adjust font sizes on different screens.
```css
    .hero h1 { font-size: clamp(2.75rem, 8vw, 4rem); }
    .hero p  { font-size: clamp(1.125rem, 3vw, 1.5rem); }
```
  ### Web Font Integration
  ## 7_Color & Backgrounds
  * can be applied to text,borders and backgrounds forms,links,tables etc..
  * colors can be applied by various forms.
    - RGB 
    - HEX
    - HSL 
    - HSLA
    - RGBA
    **why decimal values are used in RGB:**
       decimal values are easily unserstandable for humans and easy to calculate human redability mapping to bytes computers store each color channel in 8 bits an hold 2^8 (256) different values ranging from 0 to 255
       Alpha channel support shorthand hex codes cannot easily show opacity using decimal notation shows the clear decimal fraction directly into the code RGB red green blue(in a decimal form) 0 to 255 values 
       These 3 color values are mixed to get the actual color 
    **RGBA** A-alpha can be used for color transparency it can be started from 0 to 1.0 0.5 s the semi transparency
    **HEX** are specified by combinig the hexadecimal values of red green and blue with each value ranging from 00 to ff.
           00 represents the lower intensity ff represents the higher intensity
           value starts with the `#` sign and includes six digits`(##RRGGBB)`
    **HSL** a color can be specified using hue,saturation and lightness hue is a degree on the color wheel from 0to 360
           red is 0,120 is green 240 is blue 
           sauration is percentage value 0% is a shade of grey 100% is full color 
           Lightness is also a percentage 0% is black and 100% is white 
    **HSLA** comes with an alpha channel 0.0 fully transparent and 1.0 no transparent
             Here are the various color values used on the text
  ### CSS Gradients
    The CSS gradient functions let you display smooth transitions between two or more colors within an element.
    CSS defines three types of gradients:
      -  Linear Gradients - The color transition goes down, up, left, right, or diagonally
      -  Radial Gradients - The color transition goes out from a central point
      -  Conic Gradients - The color transition is rotated around a center point
    The CSS gradient functions are used within the background-image property.
    **A Linear Gradient Background**
    CSS `linear-gradient()` Function
    The CSS `linear-gradient()` function creates a linear gradient.
    A linear gradient defines a color transition that goes in a straight line, it can go down, up, to left, to right, or diagonally.
    A linear gradient requires at least two color stops. Color stops are the colors you want to render smooth transitions among. You can also set a starting point and a direction (or an angle) along with the gradient effect.
    Syntax
    `background-image: linear-gradient(direction, color-stop1, color-stop2, ...);`
    **Direction - Top to Bottom (this is default)**
    The following example shows a linear gradient that goes from top to bottom. It starts red, transitioning to yellow:
    top to bottom (default)
    Example
```css
    #grad {
      background-image: linear-gradient(to bottom, red, yellow);
    }
```
  **Direction - Bottom to Top**
    The following example shows a linear gradient that goes from bottom to top. It starts red, transitioning to yellow:
    bottom to top
    Example
```css
    #grad {
      background-image: linear-gradient(to top, red, yellow);
    }
```
   **Direction - Left to Right**
    The following example shows a linear gradient that goes from left to right. It starts red, transitioning to yellow:
    left to right
    Example
```css
    #grad {
      background-image: linear-gradient(to right, red , yellow);
    }
```
   **Direction - Diagonal**
    The following example shows a linear gradient that goes from top-left to bottom-right. It starts red, transitioning to yellow:
    top left to bottom right
    Example
```css
    #grad {
      background-image: linear-gradient(to bottom right, red, yellow);
    }
```
  **Linear Gradient - Using Angles**
    If you want more control over the direction of the gradient, you can define an angle parameter, instead of the predefined directions (to bottom, to top, to right, to left, to bottom right, etc.).
          A value of 0deg is equivalent to "to top".
          A value of 90deg is equivalent to "to right".
          A value of 180deg is equivalent to "to bottom".
          A value of 270deg equivalent to "to left"

    Syntax
  **background-image: linear-gradient(angle, color-stop1, color-stop2);**
    The following example shows how to use angles on linear gradients:
    180deg
    Example
```css
    #grad {
      background-image: linear-gradient(180deg, red, yellow);
    }
```
  **Linear Gradient - Multiple Color Stops**
    The following example shows a linear gradient (from top to bottom) with multiple color stops:
    Example
```css
    #grad {
      background-image: linear-gradient(red, yellow, green);
    }
```
    The following example shows a linear gradient (from left to right) with the color of the rainbow and some text:
    Rainbow Background
    Example
```css
    #grad {
      background-image: linear-gradient(to right, red,orange,yellow,green,blue,indigo,violet);
    }
```
   **Linear Gradient - Transparency**
    CSS gradients also support transparency, which can be used to create fading effects.
    To add transparency, we use the rgba() function to define the color stops. The last parameter in the rgba() function can be a value from 0 to 1, and it defines the transparency of the color: 0 indicates full transparency, 1 indicates full color (no transparency).

    The following example shows a linear gradient that goes from left to right. It starts fully transparent, transitioning to full color red:
    Example
```css
    #grad {
      background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1));
    }
```
  **CSS `repeating-linear-gradient()` Function**
    The CSS repeating-linear-gradient() function is used to repeat linear gradients:
    Example

    A repeating linear gradient:
```css
    #grad {
      background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
    } 
```
  ### CSS Backgrounds
The CSS background properties are used to add background effects for elements.
    background-color
    background-image
    background-repeat
    background-attachment
    background-position
    background (shorthand property)

   #### CSS background-color
    The background-color property specifies the background color of an element.
    Example
```css
    body {
      background-color: lightblue;
    }
```
With CSS, a color is most often specified by:
 -  a valid color name - like "red"
 -  a HEX value - like "#ff0000"
 -  an RGB value - like "rgb(255,0,0)"
Other Elements
You can set the background color for any HTML elements:
Example

Here, the `<h1>`, `<p>`, and `<div>` elements will have different background colors: 
```css
h1 {
  background-color: green;
}

div {
  background-color: lightblue;
}

p {
  background-color: yellow;
}
```
Opacity / Transparency
The opacity property specifies the opacity/transparency of an element. It can take a value from 0.0 - 1.0. The lower value, the more transparent
Example
```css
div {
  background-color: green;
  opacity: 0.3;
}
```
Note: When using the opacity property to add transparency to the background of an element, all of its child elements inherit the same transparency. This can make the text inside a fully transparent element hard to read.

  **Transparency using RGBA**
      An RGBA color value is specified with: rgba(red, green, blue, alpha). The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (fully opaque).
Example
```css
div {
  background: rgba(0, 128, 0, 0.3) /* Green background with 30% opacity */
} 
```
  #### CSS background-image
   The `background-image` property specifies an image to use as the background of an element.
   Note: When using a background image, use an image that does not disturb the text.
   The background image can also be set for specific elements, like the `<p>` element
   Syntax:
```css
body {
  background-image: url("paper.gif");
}
```
  #### CSS background-repeat
    The background-repeat property sets if/how a background image will be repeated.
    By default, a background-image is repeated both vertically and horizontally.
  **CSS background-repeat Horizontally**
    If the image above is repeated only horizontally `(background-repeat: repeat-x;)`, the background will look better:
Example
```css
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```
Tip: To repeat an image only vertically, use background-repeat: repeat-y;
  **CSS background-repeat: no-repeat**
      Showing the background image only once is also specified by the background-repeat property:
      Example
      Show the background image only once
```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
}
```
   **CSS background-position**
     The background-position property is used to set the starting position of the background image.
     Example
Position the background image in the top-right corner
```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
} 
```
  #### CSS background-attachment
  The background-attachment property specifies whether the background image should scroll or be fixed (will not scroll with the rest of the page):
Example
Specify that the background image should be fixed
```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: fixed;
}
```
Example
Specify that the background image should scroll with the rest of the page
```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: right top;
  background-attachment: scroll;
} 
``` 
  ## 8_Display Property
    The CSS display property is the most important property for controlling layout. 
    It defines how an HTML element renders on the screen and how it interacts with surrounding elements. 
     Syntaxcss
```css
     selector {
  display: value;
}
```
Core Display Values & Examples
block
       Starts on a new line and takes up the full width. Respects width and height properties.
       `<div>, <p>, <h1>-<h6>,<section>`
inline
        Sits on the same line and takes up only needed width. Ignores width and height properties.
        `<span>, <a>, <strong>,<em>`
inline-block
          Sits on the same line as other elements (like inline), but respects width, height, and vertical padding/margins (like block).
          `<button>, <input>, <img>`
none
      Completely removes the element from the page layout. It takes up zero space.
      None by default
flex
      Turns the element into a Flexbox container.
       Great for alignment and distributing space in a 1D row or column.
       None by default
grid
        Turns the element into a Grid container.
        Ideal for complex, 2D (rows and columns) page layouts.None by default1. display: block;Forces the element to expand to the full horizontal width of its parent.
```html 
<a href="#" class="block-link">Button 1</a>
<a href="#" class="block-link">Button 2</a>
```
```css
block-link {
  display: block;
  background-color: lightblue;
  margin-bottom: 10px;
  width: 200px; /* Block elements respect width */
  height: 40px; /* Block elements respect height */
}
```
display: inline;  
Keeps elements side-by-side. Changing width or height will have no effect Syntax: display: inline;Example: Forcing a default block element (like a list item) to sit horizontally.
```html
<ul class="nav-menu">
  <li>Home</li>
  <li>About</li>
  <li>Contact</li>
</ul>
```
```css
nav-menu li {
  display: inline;
  padding: 10px; /* Horizontal padding works, but vertical space is ignored */
}
```
display: inline-block;
      The best of both worlds: elements stay on the same line but can still accept custom dimensions and vertical margins/paddings. 
```html
<div class="card">Card 1</div>
<div class="card">Card 2</div>
```
```css
.card {
  display: inline-block;
  width: 150px;
  height: 100px;
  background-color: lightgreen;
  margin: 10px;
}
```
 display: none;
        Hides the element. Unlike visibility: hidden (which leaves a blank physical space), display: none; collapses the element completely.
```html
<div class="secret-box">You can't see me!</div>
<p>This text moves up to take over the hidden box's space.</p>
```
```css
.secret-box {
  display: none; /* Element disappears completely from the page flow */
}
```
display: flex;
    Creates a flexible container layout. Its immediate child elements can easily stretch, align, and organize.
```html
  <div class="flex-container">
  <div>Item 1</div>
  <div>Item 2</div>
</div>
```
```css
.flex-container {
  display: flex;
  justify-content: space-between; /* Pushes items to opposite sides */
  align-items: center;            /* Centers items vertically */
  background-color: coral;
}
```
 display: grid;
      Enables a grid layout. Perfect for defining structured multi-column card dashboards or magazine grids.
```html
<div class="grid-container">
  <div>1</div><div>2</div><div>3</div>
  <div>4</div><div>5</div><div>6</div>
</div>
```
```css
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 equal-width columns */
  gap: 15px;                             /* Space between columns/rows */
}
```
  ### 8_Flex
    **CSS Flexbox** (Flexible Box Layout Module) is a one-dimensional layout model designed to distribute space and align items dynamically, even when their sizes are unknown or responsive.

### Core Concepts

Flexbox operates on two axes:

* **Main Axis:** The primary direction along which flex items are laid out (controlled by `flex-direction`).
* **Cross Axis:** The axis perpendicular to the main axis.

---

### Complete Code Example

The following production-ready example includes an HTML structure and comprehensive CSS demonstrating both container and item properties.

#### HTML

```html
<div class="flex-container">
  <div class="flex-item item-1">1</div>
  <div class="flex-item item-2">2</div>
  <div class="flex-item item-3">3</div>
</div>

```

#### CSS

```css
/* 1. THE FLEX CONTAINER (PARENT) */
.flex-container {
  display: flex;                  /* Enables the flexbox layout */
  flex-direction: row;            /* Main axis: horizontal (default) */
  flex-wrap: wrap;                /* Allows items to wrap to the next line if needed */
  justify-content: space-between; /* Distributes items evenly along the main axis */
  align-items: center;            /* Centers items vertically along the cross axis */
  gap: 15px;                      /* Adds consistent spacing between items */
  
  height: 400px;
  background-color: #f4f4f4;
  padding: 20px;
}

/* 2. BASE STYLES FOR FLEX ITEMS (CHILDREN) */
.flex-item {
  background-color: #3498db;
  color: white;
  font-size: 24px;
  padding: 40px;
  text-align: center;
}

/* 3. FLEX ITEM SPECIFIC PROPERTIES */
.item-1 {
  flex-grow: 1;   /* Takes up 1 share of the remaining free space */
}

.item-2 {
  flex-grow: 2;   /* Takes up twice as much free space as item-1 */
}

.item-3 {
  flex-grow: 1;
  align-self: flex-end; /* Overrides container's align-items for this specific item */
}

```

---

### Property Breakdown Reference

#### Container Properties (Applied to Parent)

* `display: flex | inline-flex;` — Initializes the flex context.
* `flex-direction: row | row-reverse | column | column-reverse;` — Sets the flow direction.
* `justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;` — Aligns items along the **main axis**.
* `align-items: stretch | flex-start | flex-end | center | baseline;` — Aligns items along the **cross axis**.
* `flex-wrap: nowrap | wrap | wrap-reverse;` — Controls whether items force a single line or wrap.

#### Item Properties (Applied to Children)

* `flex-grow: <number>;` — Defines how much an item can grow relative to the rest.
* `flex-shrink: <number>;` — Defines how much an item can shrink if space is restricted.
* `flex-basis: <length> | auto;` — Sets the initial main size of an item before free space is distributed.
* `flex: <grow> <shrink> <basis>;` — Shorthand combining the three properties above (e.g., `flex: 1 1 auto`).
* `align-self: auto | flex-start | flex-end | center | stretch;` — Allows a single item to override the container's `align-items` rule.
* `order: <integer>;` — Changes the visual rendering order without modifying the HTML markup.
   
    ## 10_GRID
      **CSS Grid** is a powerful two-dimensional layout system for the web that handles both columns and rows simultaneously, making it ideal for complex page structures and overall layout design.

### Complete Implementation Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>CSS Grid </title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: Arial, sans-serif; }
    body { padding: 20px; background-color: #f9f9f9; }

    .grid-container {
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* Creates 3 columns of equal fraction width */
      grid-template-rows: 100px 200px;         /* Sets explicit row heights */
      gap: 15px;                               /* Adds consistent spacing between cells */
      background-color: #2c3e50;
      padding: 15px;
      border-radius: 8px;
    }

    .grid-item {
      background-color: #ecf0f1;
      color: #2c3e50;
      font-size: 18px;
      font-weight: bold;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 4px;
    }

    /* Item placement and spanning */
    .header {
      grid-column: 1 / span 3; /* Spans across all 3 columns */
      background-color: #e74c3c;
      color: white;
    }

    .sidebar {
      grid-column: 1;          /* Stays in the first column */
      background-color: #3498db;
      color: white;
    }

    .main-content {
      grid-column: 2 / span 2; /* Spans across columns 2 and 3 */
      background-color: #2ecc71;
      color: white;
    }
  </style>
</head>
<body>

  <div class="grid-container">
    <div class="grid-item header">Header (Spans 3 Columns)</div>
    <div class="grid-item sidebar">Sidebar</div>
    <div class="grid-item main-content">Main Content (Spans 2 Columns)</div>
  </div>

</body>
</html>

```

**Key Container Properties**

* `display: grid | inline-grid;` — Establishes the grid container context.
* `grid-template-columns` / `grid-template-rows` — Defines column and row tracks using values like pixels, percentages, or the fraction (`fr`) unit.
* `gap` (or `row-gap` / `column-gap`) — Specifies the gutter size between rows and columns.
* `grid-template-areas` — Maps out a visual grid layout using named template sections.

**Key Item Properties**

* `grid-column` / `grid-row` — Controls where an item starts and ends using line numbers or the `span` keyword.
* `grid-area` — Shorthand property for combining row and column placement lines.
* `justify-self` / `align-self` — Aligns an individual item inside its specific grid cell horizontally or vertically.
    ## 11_Positioning
    CSS positioning is about controlling the placement of elements within a web page.
With CSS positioning, you can override the normal document flow.
 **Static Positioning (Default)**
Elements follow the normal layout flow. Offset properties (`top`, `left`, etc.) have no effect.

```html
<div style="position: static; background-color: #f1f1f1; padding: 15px; margin-bottom: 10px;">
  This is a static element. It sits wherever it naturally lands in the HTML.
</div>

```

**Relative Positioning**
The element is shifted relative to its original spot, but its original space is still reserved in the layout.

```html
<div style="position: relative; top: 15px; left: 20px; background-color: #e9f2ff; padding: 15px; margin-bottom: 10px;">
  This element is relative. It moved 15px down and 20px right from its normal place.
</div>

```

**Absolute Positioning**
The element is removed from the layout flow and pinned precisely to its nearest positioned ancestor (or the page body).

```html
<div style="position: relative; background-color: #f8f9fa; padding: 30px; border: 1px solid #ccc;">
  <span style="position: absolute; top: 0; right: 0; background-color: #6f42c1; color: white; padding: 5px 10px; font-size: 0.8rem;">
    Absolute Badge
  </span>
  Parent container is relative, holding the absolute child in the top-right corner.
</div>

```

**Fixed Positioning**
The element is removed from the flow and locked permanently to the browser viewport, staying in place even when scrolling.

```html
<div style="position: fixed; bottom: 20px; right: 20px; background-color: #dc3545; color: white; padding: 10px 20px; border-radius: 4px; z-index: 1000;">
  Fixed Element (Stays on screen)
</div>

```

**Sticky Positioning**
The element behaves normally until the user scrolls past a specified threshold, after which it locks into place like a fixed element.

```html
<div style="position: sticky; top: 0; background-color: #198754; color: white; padding: 15px; z-index: 10;">
  Sticky Header (Locks to top of screen when scrolling)
</div>

```
   ## 12_z index and stacking elements
    CSS stacking determines how overlapping elements render along the z-axis (depth), controlled by the natural document order, positioning states, and the z-index property.
Natural Stacking Order (The Painter's Algorithm)
When elements overlap without explicit positioning rules, browsers render them in a specific background-to-foreground sequence:
    Backgrounds and borders of the root element (<html>).
    Non-positioned block-level elements in the order they appear in the HTML.
    Floated elements
    Inline elements in normal flow.
    Positioned elements (elements with a position other than static).
The Mechanics of z-index
    Prerequisite: The z-index property only applies to positioned elements (relative, absolute, fixed, sticky) or items within a Flexbox/Grid container. Elements with position: static entirely ignore z-index.
    Integer Values: Accepts negative (-1), zero (0), and positive (10, 999) integers. Elements with higher numerical values sit closer to the user, overlapping those with lower values.
Understanding Stacking Contexts (The Trap)
A stacking context is an isolated group of elements layered together relative to their parent container. Elements create a new stacking context when they possess certain properties, such as:
    A position value (relative, absolute, etc.) combined with an explicit z-index (other than auto).
    An opacity value less than 1.
    Properties like transform, filter, backdrop-filter, or will-change.
Crucial Caveat: Child elements are completely trapped inside their parent's stacking context. If Parent A has z-index: 1 and Parent B has z-index: 2, any child inside Parent A—even if assigned z-index: 9999—will stay trapped under Parent B because Parent A itself sits on a lower global layer.
```html
<div style="position: relative; z-index: 1; width: 150px; height: 150px; background-color: #ff416c; color: white; padding: 20px;">
  Box 1 (z-index: 1)
</div>
<div style="position: relative; z-index: 2; margin-top: -80px; margin-left: 50px; width: 150px; height: 150px; background-color: #4facfe; color: white; padding: 20px;">
  Box 2 (z-index: 2 - sits on top)
</div>
```
