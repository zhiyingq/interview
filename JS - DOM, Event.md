# JS - DOM, Event
#面试相关

### DOM
The Document Object Model (DOM) connects web pages to scripts or programming languages. Usually that means JavaScript. The DOM model represents a document with a **logical tree**. DOM methods allow programmatic access to the tree; with them you can change the document's structure, style or content. DOM nodes can **have event handlers attached to them**. Once an event is triggered, the event handlers get executed.

```js
var box = document.getElementById("box1");
box.innerHTML = "box2"
```

### Search HTML Elements
1. document.getElementById(id): Find an element by element id
2. document.getElementsByTagName(name): Find elements by tag name(array like)
3. document.getElementsByClassName(name): Find elements by class name

### Modify HTML Elements
```js
element.innerHTML = "New HTML Content"
element.attribute = new_value
element.setAttribute(attribute, value)
element.style.property = new style
```

### Create & Delete Elements
```js
document.createElement(element)
document.removeChild(element)   // remove an HTML element
document.appendChild(element)
document.replaceChild(element)
document.write(text) 			// write into the HTML output stream


Examples:
var box2 = document.createElement("div");
box2.className = "box1";
// or box2["className"] = "box1";
var body = document.getElementsByTagName("body");
body[0].appendChild(box2);
```


### Event
HTML events are "things" that happen to HTML elements. When JavaScript is used in HTML pages, JavaScript can "react" on these events.
`<button onclick="..." />`
```js
element.onclick = function() { ... }
element.addEventListener(event, function, useCapture);
```

Example:
```js
var box = document.getElementById("box1");
box.innerHTML = "box2"
box.addEventListener("click",function(){
  this.classList.toggle("clickedbox");
});
```




















