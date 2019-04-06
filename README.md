# html-element-picker
Pick and highlight any HTML element on a page using only Vanilla JS. Hovered elements are automatically highlighted in the color you want.

## Installation
### NPM
`npm install html-element-picker`

### CDN
Append the one of the following scripts at the end of `body` tag
1. jsDelivr
```
<script src="https://cdn.jsdelivr.net/npm/html-element-picker@latest"></script>`
```
2. Unpkg
```
<script src="https://unpkg.com/html-element-picker@latest"></script>
```

## Usage
After importing html-element-picker, instantiate the ElementPicker class with optional configurations.
```
new ElementPicker(options);
```
The default configurations are
```
{
container: document.body,
selectors: "*",
background: "rgba(153, 235, 255, 0.5)",
borderWidth: 5,
transition: "all 150ms ease",
ignoreElements: [document.body],
}
```
### 1. container (HTMLElement)
`container` is the boundary of the element picker. No highlights will be shown on mouse hover outside the container. Defaults to the document body.
### 2. selectors (String)
`selectors` serve as the filter for the element picker. Only elements matching the CSS rule specified in the `selectors` string will be highlighted. Defaults to accepting all elements ("*", star operator).
### 3. background (String)
`background` specifies the background color of the higlight when an element is hovered. You should always set a **transparent** color using `"rgba(...)"` or `"hsla(...)"` so as not to block the hovered element. Same as setting `elementPicker.hoverBox.style.background`. Defaults to light blue.
### 4. borderWidth (Integer)
`borderWidth` indicates the width of the highlight box border (in **px**) that covers the hovered element. Pass in a positive value to enlarge the highlight box and a negative to decrease the size (smaller than the hovered element). Zero means no border or same size as the hovered element. Defaults to 5px.
### 5. transition (String)
`transition` specifies the animation when the highlight box transfer to another hovered element. Same as setting `elementPicker.hoverBox.style.transition`. Pass in `""` (empty string) to disable transition. Defaults to `"all 150ms ease"`.
### 6. ignoreElements (Array of HTMLElement)
`ignoreElements` lists the elements to **not** highlight when being hovered over. Add, remove, modify elements in this property same as a normal array (`push`, `pop`, etc). The order of elements does not matter. Defaults to the document body.