# Notes

## Selectors
CSS selectors define the pattern to select elements to which a set of CSS rules are then applied
### Universal
Selects all elements. Optionally, it may be restricted to a specific namespace or to all namespaces
```css
* {
    color: blue;
}
```
### Type/Element Selector
Selects all elements that have the given node name 
```html
<tag>some text</tag>
```
```css
tag {
    color: red;
}
```
### Class Selector
Selects all elements that have the given `class` attribute
```html
<tag>some text</tag>
<tag class="user-name">Andres Echeverri</tag>
```
```css
.user-name {
    color: green;
}
```
### ID Selector
Selects an element based on the value of its `id` attribute. There should be only one element with a given ID in a document.
```html
<tag>some text</tag>
<section id="prices">List of prices</section>
```
```css
#prices {
    background: red;
}
```
### Attribute Selector
Selects all elements that have the given attribute.
```html
<button disabled>Save</section>
```
```css
[disabled] {
    background: gray;
}
```
<hr>

## Specificity
Specificity determine the CSS declaration that is the most relevant to an element. It determines the property value to apply to the element.

### id > class, :pseudo-class, [attribute] > type/element > universal

<hr>

## Inheritance
In CSS, inheritance controls what happens when no value is specified for a property on an element.

<hr>

## Convinators
Allow to us be more clear about our rules and select elements by passing more information to the selector

### + Adjacent Sibling
Separates two selectors and matches the second element only if it immediately follows the first element, and both are children of the same parent element
```css
h2 + p {
    color: red;
}
```
```html
<div>
    <h2>Not applied<h2>
    <p>CSS applied</p>
    <h2>Not applied<h2>
    <h3>Not applied<h3>
    <p>Not applied<p>
    <h2>Not applied<h2>
    <p>CSS applied</p>
</div>
```
### ~ General Sibling
```css
div ~ p {
    color: red;
}
```
```html
<div>
    <h2>Not applied<h2>
    <p>CSS applied</p>
    <h2>Not applied<h2>
    <h3>Not applied<h3>
    <p>CSS applied</p>
</div>
```
### > Child
```css
div > p {
    color: red;
}
```
```html
<div>
    <div>Not applied</div>
    <p>CSS applied</p>
    <div>Not applied</div>
    <article>
        <p>Not applied</p>
    </article>
    <p>CSS applied</p>
</div>
```
### Descendant
```css
div  p {
color: red;
}
```
```html
<div>
    <div>Not applied</div>
    <p>CSS applied</p>
    <div>Not applied</div>
    <article>
        <p>CSS applied</p>
    </article>
    <p>CSS applied</p>
</div>
```
<hr>

## The Box Model
The CSS box model is essentially a box that wraps around every HTML element. It consists of: margins, borders, padding, and the actual content.

<hr/>

## Margin collapsing
The top and bottom margins of blocks are sometimes combined (collapsed) into a single margin whose size is the largest of the individual margins (or just one of them, if they are equal).
* Collapsing margins is only relevant in the vertical direction.
* Margins don't collapse in a container with display set to flex.

<hr/>

## Pseudo Classes
Define the style of a special state of an element
* Are defined with a single colon `:` and then the class name like `hover` or `active`


## Pseudo Elements
Defines the style of a specific part of an element
* Are defined by adding two colons `::` and then the element name.


## Position

### Fixed
* When applying fixed position to an element, it is outside the actual document flow.
* When applying fixed position to an element, it changes the general behavior from a block level element to a inline block element.
* When applying fixed position to an element, its context position is the viewport.

### Absolute
* When applying absolute position to an element, its context position is defined based on two cases
    * if none of the ancestors of the parent elements has a position applied then the positioning context is simply the HTML element.
    * If we have any position ancestors, then the closest ancestors which has the position property applied is the positioning contextfor the element.

### Relative
* When applying relative position to an element, its context position is the element itself.
* When applying relative position to an element, it is NOT outside the actual document flow.