# HTML5 and CSS Notes and Code

## HTML5
HTML = HyperText Markup Language

### HTML header tags:
`<h1>Hello World</h1>`
`<h2>CatPhotoApp</h2>`
* h1 is the largest, h6 is smallest

### Paragraph:
`<p>Hello Paragraph</p>`
* The 'p' tag creats a paragraph

### Comments:
```html
<!-- <h1>Hello World</h1> -->
<h2>CatPhotoApp</h2>
<!-- <p>Hello Paragraph</p> -->
```
* In html you can add a comment using `<!--` *content here* `-->`

### Images
```
<img src="https://bit.ly/fcc-relaxing-cat" alt="Cute cat ">
```
* NOTE The image tag is self closing. Unlike 'p' or 'div', it only needs an opening tag
* You can add images to an HTML file with an img tag
* The two attributes you NEED to include in an img tag are src (where the image comes from), and alt, which is what will be displayed if the image isn't avaiable OR if a person with visual imparements is using your site

### Linking to External Pages
```
<a href="http://freecatphotoapp.com">
  Cat Photos
</a>
```
* The 'a' tag in HTML creates clickable links with the href attribute
* In this example, 'cat photos' would be blue and clickable
* Note that this 'a' element could be nested in somthing else like a div or p tag

### Turning an Image Into a Link
```
<a href="#"><img src="https://bit.ly/fcc-running-cats" alt="Three kittens running towards the camera. "></a>
```
* If you want to be able to click on an image, just nest the img tag inside an 'a' tag

### Style:
`<h2 style="color: red">CatPhotoApp</h2>`
* It is possible to create inline styles in HTML by adding 'style=""' in the opening of your element

## CSS

CSS = Cascading Style Sheets

### Style tags:
```
<style>
  h2 {color: blue;}
</style>

<h2>CatPhotoApp</h2>
```
* In your HTML file, you can create a 'style' element and store all your styles there.

### Classes:
```
<style>
  .red-text {
    color: red;
  }
</style>

<h2 class="red-text"> CatPhotoApp</h2>
<p class="red-text">Kitty </p>
```
* Instead of applying a style to every occurance of an element, you can
give an HTML element a 'class', and just apply styles to that class
* Classes in CSS are written with a '.' in front of them
* Multiple elements can have the same class

### Font Size:
```
  p {
    font-size: 16px;
  }
```
* Font-size is the CSS tag that changes... font size
* Most styling options do exist in CSS
* If unsure of the proper name, use google or https://www.w3schools.com/css/default.asp

### Font Family
```
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">

<style>
  h2 {
    font-family: Lobster;
  }
</style>
```
* Some font-families will be available by default in most browsers
* If you want to import a different family, you can do so with a 'link' tag at the top of your HTML (or CSS) file

### Borders
```
.thick-green-border {
  border-color: green;
  border-radius: 10px;
  border-style: solid;
  border-width: 10px;
}
```
* Borders in CSS can be styled like so ^
* I also use borders to help me figure out what the edges of an element are when styling with flexbox

