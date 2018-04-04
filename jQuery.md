# jQuery Notes
## The Basics
What is jQuery?
jQuery is 'the most popular javascript tool of all time' - other than the to-do list app that I made last June. It shares most of its syntax with javascript and there's a lot to learn, but you can accomplish tons in terms of web development with just a limited knowledge of jQuery.

### Script Tags:
```
<script>
/* Javascript & jQuery Code Here */
</script>
```
* If you are writing your jQuery code in the same file as your HTML, you'll need to nest it inside a script tag at the head of the file
  'script' derives from javascript and tells the browser what to do with the code

### Document Ready Function:
```
<script>
  $(document).ready(function() {

});
</script>
```
* This 'document ready' function will execute code you put inside it as soon as your document is fully loaded.
* This is useful if you want to use JS/jQuery to populate a web page with data
* By nesting code inside this function you can also ensure that your code doesn't execute too early and cause bugs

### Targeting Elements in jQuery:
```
<script>
  $(document).ready(function() {
    $("button").addClass("animated bounce");
    $(".well").addClass("animated shake");
    $("#target3").addClass("animated fadeOut")
  });
</script>
```
* Just like with CSS, there are three ways to target HTML elements with jQuery
* You can target every elememt of a type, you can target by class, or by ID
* The code above give an example of these three in descending order and just adds a class to each

### What else can jQuery do??
* jQuery can be used to do almost anything on a webpage, here's a link to some of its basic functions:
* https://www.w3schools.com/jquery/jquery_examples.asp