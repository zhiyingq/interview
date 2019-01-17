# CSS - basic
#面试相关

CSS: Cascading Style Sheets
Import css to HTML

## CSS font
em - 1em is the same as the font-size of the current element (more specifically, the width of a capital letter M.) The default base font-size given to web pages by web browsers before CSS styling is applied is 16 pixels, which means the computed value of 1em is 16 pixels for an element by default. But beware — font sizes are inherited by elements from their parents, so if different font sizes have been set on parent elements, the pixel equivalent of an em can start to become complicated.

rem - The rem (root em) works in exactly the same way as the em, except that it will always equal the size of the default base font-size

## How to add CSS to HMTL
Inline styles - 优先级最高
`<h1 style="color:blue;">Head1</h1>`
Internal style - 优先级低于Inline style
```html
<head>
	<style>
		h1 {
			color: blue;
		}
	</sytle>
</head>
```
External style - 优先级低于内嵌模式
`<link rel="stylesheet" type="text/css" href="style.css">`

## Selectors
简单属性: width, height, color, background-color, font-size
1. * - all elements
2. Element
3. # id
4. .class
### CSS Combinators
5. Descendant selector (split by space)
The descendant selector matches all elements that are descendants of a specified element.
6. 并集选择器 (,)
 div, p: selects all <div> elements and all <p> elements
They don’t need to have any relationships. Just like “U”
7. Child selector (>)
The child selector selects all elements that are the **immediate** children of a specified element.
8. Adjacent sibling selector (+): siblings immediately following
9. General sibling selector (~): general siblings after
10. Select element with certain attribute_attribute_value_containing a specific word:
```css
a[target] {
	background-color: yellow;
}
a[target="_blank"] {  // target can also be _self
	background-color: yellow;
}
a[title~="flower"] {
	background-color: yellow;
}
```
### CSS Sudo classes
Pseudo classes are similar to pseudo elements, but instead of styling a part of an element, they apply styles when an element is in **a certain state**. For example, you could style a button differently based on whether the user has their mouse pointer over it, or when they click the button.

Another common use case is to **style only certain occurrences of elements in a row**. For example, styling the first tab in a series of tabs, or every second tab.

They all start with a single colon and look like this:
- - - -
:link: select all unvisited links 未点击的时候
:hover: select links on mouse over 悬空的时候
:active: select the active (pressed down) link 按下去的时候
:visited: select the already clicked link 已经按过了
:first-child: represents the first element among a group of sibling elements.
:first-of-type: represents the first element of its type among a group of sibling elements.
```
a:active {
	color: red
}	
```
The :active pseudo-class is commonly used on <a> and <button> elements. Other common targets of this pseudo-class include elements that contain an activated element, and form elements that are being activated through their associated <label>.

### CSS Sudo elements
Pseudo elements are used to style particular parts of an element, rather than the whole thing. For example, you can use it to style the first line or first letter of a paragraph, text you’ve selected, or you can use it to insert text or shapes before or after an element.

They always start with a double colon - although a single colon is still allowed for backwards compatibility - and they look like this:
::first-letter: select the first letter of the element
::before: It is often used to add cosmetic content to an element with the content property. It is inline by default.
```css
/* Selects the first letter of a <p> */
p::first-letter {
  font-size: 130%;
}
q::before { 
  content: "«---";
  color: blue;
}
q::after {
	content: "--->";
  color: blue;
}
```

- - - -
### CSS Cascade and Inheritance
In CSS, there is a special piece of syntax you can use to make sure that a certain declaration will always win over all others: !important. For example:
```
p {
  color: red !important;
}

div p {
  color: green;
}
```

Specificity:
Specificity is basically a measure of how specific a selector is — how many elements it could match.

Specificity - CSS provides a formula for determining a style’s specificity that’s based on a value assigned to the style’s selector - a tag selector, class selector, ID selector, and so on. Here’s how the system works:
1. A tag / pseudo element (::before) selector is worth one
2. A class / pseudo class (:link) selector is worth ten
3. A ID selector is worth hundreds
4. An inline style is worth thousands

Source Order: As mentioned above, if multiple competing selectors have the same importance and specificity, the third factor that comes into play to help decide which rule wins is source order — later rules will win over earlier rules

Inheritance: some property values applied to an element will be inherited by that element's children, and some won't.
font-family and color to be inherited, as that makes it easy for you to set a site-wide base font by applying a font-family to the <html> element; 
margin, padding, border, and background-image to NOT be inherited
- - - -
### CSS Box Model
W3C standard (content-box) & IE model (border-box)
Content-box:
This is the initial and default value as specified by the CSS standard. The width and height properties include the content, but does not include the padding, border, or margin. For example, .box {width: 350px; border: 10px solid black;} renders a box that is 370px wide.
Border-box:
The width and height properties include the content, padding, and border, but do not include the margin. Note that padding and border will be inside of the box. For example, .box {width: 350px; border: 10px solid black;} renders a box that is 350px wide. The content box can't be negative and is floored to 0, making it impossible to use border-box to make the element disappear.

```html
<div class="content-box">Content box</div>
<br>
<div class="border-box">Border box</div>
```

```css
div {
  width: 160px;
  height: 80px;
  padding: 20px;
  border: 8px solid red;
  background: yellow;
}

.content-box { 
  box-sizing: content-box; 
  /* Total width: 160px + (2 * 20px) + (2 * 8px) = 216px
     Total height: 80px + (2 * 20px) + (2 * 8px) = 136px
     Content box width: 160px
     Content box height: 80px */
}

.border-box { 
  box-sizing: border-box;
  /* Total width: 160px
     Total height: 80px
     Content box width: 160px - (2 * 20px) - (2 * 8px) = 104px
     Content box height: 80px - (2 * 20px) - (2 * 8px) = 24px */
}
```

### Margin collapsing: The top and bottom margins of blocks are sometimes combined (collapsed) into a single margin whose size is the largest of the individual margins (or just one of them, if they are equal), a behavior known as margin collapsing. Note that the margins of floating and absolutely positioned elements never collapse.































