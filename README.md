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

## JS basic syntax

### JS identifiers (names/命名规则)
1. First character *MUST* be a letter, _ or $. (Number is not allowed)
2. Hyphen cannot be used in names. Often using Camel Case (starting with a lowercase letter). Eg: firstName.
3. Case sensitive
4. 保留字不能用

### Variable declaration
Declaration会被提升到最上方先执行，但是赋值还是在原本代码的位置。
```javascript
console.log(carName); // output "undefined". Assignment is not done yet.
var carName = "Benz";
console.log(carName); // output "Benz"
var carName;

```
Note: 如果输出一个没有被声明过的变量会报错（测试过chrome以及node cmdline tool）.
    如果输出一个被声明过的变量(没有赋值)会输出undefined.

### JS Arithmetic Operators
Most of JS artithmetic operators are the same with other commonly used languages (eg. Java). Here only special characterstics will be noted.

1. +

*Adding numbers

*Connecting strings

*Rules: from left to right

```javascript
console.log(3+3); // output 6
console.log('Hello'+' World'); // output Hello World
console.log(3+3+' hello'); // output 6 hello
console.log('Hello '+3+3); // output Hello 33

```

