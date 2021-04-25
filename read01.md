# Responsive Web Design

Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop. Responsive web design is focused around providing an intuitive and gratifying experience for everyone. Desktop computer and cell phone users alike all benefit from responsive websites.

## Responsive web design is broken down into three main components

1. **flexible layouts**

The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.

`target ÷ context = result`

```css
.container {
  width: 538px;
}
section,
aside {
  margin: 1.858736059%; /*  10px ÷ 538px = .018587361 */
}
section {
  float: left;
  width: 63.197026%;    /* 340px ÷ 538px = .63197026 */   
}
aside {
  float: right;
  width: 29.3680297%;  /* 158px ÷ 538px = .293680297 */
}
```


2. **Media Queries**

Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation.

***Initializing Media Queries***

using the @media rule inside of an existing style sheet, importing a new style sheet using the @import rule.

```css

/* @media Rule */
@media all and (max-width: 1024px) {...}

/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...}

````

 or by linking to a separate style sheet from within the HTML document.

````html

<!-- Separate CSS File -->
<link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">

``````

There are three different logical operators available for use within media queries

* and : allows an extra condition to be added

```css
@media all and (min-width: 800px) and (max-width: 1024px) {...}
```

* not : specifying any query but the one identified

```css
@media not screen and (color) {...}
```

* only: hiding the styles from devices or browsers that don’t support media queries

```css
@media only screen and (orientation: portrait) {...}
```

**Media Features**

* Height & Width
* Orientation :determines if a device is in the landscape or portrait orientation.

  3. **Flexible Media**

One quick way to make media scalable is by using the max-width property with a value of 100%. Doing so ensures that as the viewport gets smaller any media will scale down according to its containers width.

be carfare about these things:

* parent element needs to have a width of 100%
* parent element also needs to have a height of 0
* Padding-bottom of the parent element, the value of which is set in the same aspect ratio of the video the code

```css
img, video, canvas {
  max-width: 100%;
}
`````

HTML

```html
<figure>
  <iframe src="https://www.youtube.com/embed/4Fqg43ozz7A"></iframe>
</figure>
`````

CSS

```css
figure {
  height: 0;
  padding-bottom: 56.25%; /* 16:9 */
  position: relative;
  width: 100%;
}
iframe {
  height: 100%;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}
`````

-------------------------------

# All About Floats

Float is a CSS positioning property

There are four valid values for the float property:

* Left and Right float elements those directions respectively.
* None (the default) ensures the element will not float
* Inherit which will assume the float value from that elements parent element.

**Clearing the Float**

Float’s sister property is clear. An element that has the clear property set on it will not move up adjacent to the float like the float desires, but will move itself down past the float.

```css
#footer {
  clear: both;   
}
````

**Techniques for Clearing Floats**

1. The Empty Div Method is, quite literally, an empty div.

 `<div style="clear: both;"></div>`

2.  The Overflow Method

 relies on setting the overflow CSS property on a parent element. If this property is set to auto or hidden on the parent element, the parent will expand to contain the floats, effectively clearing it for succeeding elements.

 3. The Easy Clearing Method

  uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent.

  ```css
  .clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
} 
````
