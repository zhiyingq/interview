# CSS - float, display, inline block, block, position, flex
#面试相关

### How floated elements are positioned：
when an element is floated, it is taken out of the normal flow of the document (though still remaining part of it). It is shifted to the left, or right, until it touches the edge of its **containing box, or another floated element**. The element is removed from the normal flow of the page, though still remaining a part of the flow (in contrast to absolute positioning).
 
### Syntax
float: none|left|right|inherit;

### Common questions:
1. Float Collapsing:
If a parent element contains nothing but floated elements, its height will be collapsed to nothing. It can be fixed by clearing the float after the floated elements in the container but before the close of the container.
 
How to solve this? Use a clearfix trick!
```
#container::after {
	content: "";
	display: block;
	clear: both;
}
```

2. Inline, block, inline-block
Inline: 
Inline elements don’t start on a new line, they appear on the same line as the content and tags beside them. You can add space to the left and right on an inline element, but you cannot add height to the top or bottom padding or margin of an inline element.
	1. Left & right margins, no top & bottom margins
	2. **Cannot have a width and height set**
	3. Allow other elements to sit to their left and right

Block elements
	1. Force a line-break after the block element
	2. Acquires full width if width not defined

Inline-block elements:
	1. Allow other elements to sit to their left and right
	2. Have top & bottom margins and padding
	3. Height and width
	
3. Difference between display:none and visibility:hidden
display:none means that the tag in question will not appear on the page at all (although you can still interact with it through the dom). There will be no space allocated for it between the other tags.

visibility:hidden means that unlike display:none, the tag is not visible, but space is allocated for it on the page. The tag is rendered, it just isn't seen on the page.

## Position
default: static
A positioned element is an element whose computed position value is either relative, absolute, fixed, or sticky. (In other words, it's anything except static.) 

relative: a relatively positioned element is an element whose computed position value is relative. The top and bottom properties specify the vertical offset from its normal position; the left and right properties specify the horizontal offset.

absolute: The top, right, bottom and left properties of an absolute-positioned element will cause it to be positioned relatively to the nearest positioned ancestor.

Elements that are **relatively positioned remain in the normal flow of the document**. (即原来的位置被保留，而不是当前位置）In contrast, an element that is **absolutely positioned is taken out of the flow**; thus, other elements are positioned as if it did not exist. The absolutely positioned element is positioned relative to its nearest positioned ancestor (i.e., the nearest ancestor that is not static). If a positioned ancestor doesn't exist, it is positioned relative to the ICB (initial containing block — see also the W3C definition), which the containing block of the document's root element.

## Z-Index
The z-index property specifies the stack order of an element.
 An element with greater stack order is always in front of an element with a lower stack order.
Note: z-index only works on **positioned elements (position:absolute, position:relative, or position:fixed)**.

### Image middle
```css
.container {
	height: 100%;
	display: inline-block;
	text-align: center;
}

.img {
	vertical-align: middle;
}
```

### How to use flex
```css
1. set the container to be display:flex
2. set the container with justify-content

.container.main {
  border: 1px solid;
  display: flex;
  height: 400px;
  /* align-content: center; */
  justify-content: center;
  align-items: center; 
}
```





















