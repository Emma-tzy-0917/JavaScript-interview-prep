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
1. Declaration会被提升到最上方先执行，但是赋值还是在原本代码的位置。
2. 注意Function declaration会连带花括号里的内容一起被提前。
3. 如果function使用statement方式赋值，那么在赋值前试图访问该函数会报错。

```javascript
console.log(carName); // output "undefined". Assignment is not done yet.
var carName = "Benz";
console.log(carName); // output "Benz"
var carName;

console.log(f()); // output 3;
console.log(g()); // output 运行报错，g不是一个function, 因为赋值还没有发生
function f(){
    return 3;
}
var g = function(){
    return 4;
}
console.log(g()); // output 4，赋值已发生，g是一个function
```
Note: 如果输出一个没有被声明过的变量会报错（测试过chrome以及node cmdline tool）.
    如果输出一个被声明过的变量(没有赋值)会输出undefined.

### JS Operators
Most of JS operators are the same with other commonly used languages (eg. Java). Here only special characterstics will be noted.

1. Adding ("+")

  * Adding numbers

  * Connecting strings

  * Rules: from left to right

   ```javascript
   console.log(3+3); // output 6
   console.log('Hello'+' World'); // output Hello World
   console.log(3+3+' hello'); // output 6 hello
   console.log('Hello '+3+3); // output Hello 33
   ```

2. Comparison Operators ( == And ===)
  * == means equal value 仅仅比较值
  * === means equal value and equal type 值和类型都要相等
  * Note: NaN == NaN 以及 NaN === NaN 都是false.

3. typeof and instanceof是JS的type operators，具体内容会在JS data types里说明。
