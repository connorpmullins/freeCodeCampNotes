# HTML5 and CSS Notes and Code Examples

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

### Images:
```
<img src="https://bit.ly/fcc-relaxing-cat" alt="Cute cat ">
```
* NOTE The image tag is self closing. Unlike 'p' or 'div', it only needs an opening tag
* You can add images to an HTML file with an img tag
* The two attributes you NEED to include in an img tag are src (where the image comes from), and alt, which is what will be displayed if the image isn't avaiable OR if a person with visual imparements is using your site

### Linking to External Pages:
```
<a href="http://freecatphotoapp.com">
  Cat Photos
</a>
```
* The 'a' tag in HTML creates clickable links with the href attribute
* In this example, 'cat photos' would be blue and clickable
* Note that this 'a' element could be nested in somthing else like a div or p tag

### Nesting Elements:
```
<div>
  <p>Things cats love:</p>
  <p>Pineapple yogurt and such</p>
  <img src="https://bit.ly/fcc-relaxing-cat" alt="Cute cat ">
</div>
```
* It is possible to nest elements within a 'parent' element (here, div)
* This is useful if you want to apply a style to everything inside the parent
* This is also essential for page layout (later)
* In the next couple sections you'll see examples of nesting

### Turning an Image Into a Link:
```
<a href="#"><img src="https://bit.ly/fcc-running-cats" alt="Three kittens running towards the camera. "></a>
```
* If you want to be able to click on an image, just nest the img tag inside an 'a' tag

### Lists:
```
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>

<ol>
  <li>Garfield</li>
  <li>Sylvester</li>
</ol>
```
* There are two types of lists:
  1. ordered lists
  1. unordered lists
* These are marked by either `<ul>` or `<ol>`
* Inside these lists are list items, marked by `<li>` either way

### Text Fields:
`<input type="text" placeholder="this is placeholder text">`
* The above code will show a text-submission field. This is useful in lots of scenarios
* Note that I had to give the input a 'type' of text and also gave it some placeholder text that will dissapear when the user enters something

### Forms:
```
<form action="/submit-cat-photo">
  <label><input type="radio" name="indoor-outdoor"> Indoor</label>
  <label><input type="checkbox" name="personality"> Loving</label>
  <label><input type="checkbox" name="personality"> Loving</label>
  <input type="text" placeholder="cat photo URL" required>
  <button type="submit">Submit</button>
```
* This is an example of a form with one radio button, two checkboxes, a text box, and a button that will submit the form info
* There's a good amount to say about forms, but I'm just going to note that they exist and are worth knowing about

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

### IDs:
```
<style>
  #title {
    color: blue;
  }
</style>

<h2 id="title"> CatPhotoApp</h2>
```
* Sometimes you want to be able to reference one particular element in a file
* Instead of doing this with 'class', which can describe multiple elements, use id
* In your CSS, you reference an ID by putting a # before it

### Styling the HTML body:
```
<style>
body {
background-color: black;
}
</style>
```
* In an HTML file, everything you create is on the canvass of a page
* You can style the entire HTML page with 'body' In this example, the entire web page would be black

### Inheritance:
```
<style>
  body {
    color: green || #008000;
  }
  .important {
    color: #FFC0CB;
  }
  #special {
    color: blue;
  }
</style>

<h1 class="important"> This text would be pink </h1>
<h2> This text would be green </h2>
<h3 id="special" class="important"> This text would be blue </h3>
```
* In CSS, elements inherit all applicable properties from their parents
* This means that the `<h2>` tag above would get its color from 'body'
* What happens if styles conflict?
* One style will take precedence over the other
* In order of highest precedence to lowest, this is how styling issues are resolved:
  * ID > Class > Parent

### Font Size:
```
  p {
    font-size: 16px;
  }
```
* Font-size is the CSS tag that changes... font size
* Most styling options do exist in CSS
* If unsure of the proper name, use google or https://www.w3schools.com/css/default.asp

### Font Family:
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

### Color:
```
color: #008000;
color: green;
color: rgb(0,128,0);
```
* All the above lines do the same thing, set the color to green
* The first is using 'hex code', the second plain text, the third uses rgb


### Borders:
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

### Layout:
* How you lay out elements in your HTML page is really important
* This can be done a few different ways, but because users have so many different screen sizes, you want a 'responsive' design that looks good on mobile and desktop devices
* The best way to make your layout responsive is with something called flexbox
* Here's a great link:
  * https://css-tricks.com/snippets/css/a-guide-to-flexbox/