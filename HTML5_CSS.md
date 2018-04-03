# HTML5 and CSS Notes and Code

## HTML5
HTML = HyperText Markup Language

HTML header tags:
`<h1>Hello World</h1>`
`<h2>CatPhotoApp</h2>`
h1 is the largest, h6 is smallest

Paragraph:
<p>Hello Paragraph</p>
The 'p' tag creats a paragraph

Comments:
```html
<!-- <h1>Hello World</h1> -->
<h2>CatPhotoApp</h2>
<!-- <p>Hello Paragraph</p> -->
```
In html you can add a comment using `<!--` content here `-->`

Style:
`<h2 style="color: red">CatPhotoApp</h2>`
It is possible to create inline styles in HTML by adding
style="" in the opening of your element

## CSS
CSS = Cascading Style Sheets

Style tags:
```
<style>
  h2 {color: blue;}
</style>

<h2>CatPhotoApp</h2>
```
In your HTML file, you can create a 'style' element
and store all your styles there.

Classes:
```
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text"> CatPhotoApp</h2>
```
Instead of applying a style to every occurance of an element, you can
give an HTML element a 'class', and just apply styles to that class

Classes in CSS are written with a '.' in front of them

