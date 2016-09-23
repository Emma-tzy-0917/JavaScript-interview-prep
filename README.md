# JavaScript-interview-prep

This project aims to create notes for basic javascript syntax and usages (ECMAScript5). Things about ES6, Angular2, etc is excluded in the current project.

## JavaScript Data Types

### JS primitive types 
1. String
2. Number
3. Null
4. Undefined
5. Boolean

### JS references


## JavaScript Browser BOM

### Window

### Navigator

### Screen

### History

### Location

## JS String object methods

## JS Array object methods

## JS output

###1. console.log: displaying content in browser console

###2. alert: writing into alert box

###3. document.write: writing to html
```html
<h1> I AM TITLE </h1>

<script>
    document.write(5 + 6);
    document.write("<h3> HEY I'm here! </h3>");
</script>

<p> I'm content. </p>
```
NOTE: IMPORTANT! Calling document.write AFTER a html is loaded will wipe out all existing html.

###4. innerHTML: writing to an html element
```html
<h1 id="title"> I AM TITLE </h1>

<script>
    document.getElementById("title").innerHTML = "I AM NEW";
    document.getElementsByClassName("content").innerHTML = "I'm new content";
</script>

<p class="content"> I'm content. </p>
<p class="content"> I'm content. </p>
<p class="content"> I'm content. </p>
<p> I'm content. </p>
```
