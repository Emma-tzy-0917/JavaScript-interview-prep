# JavaScript-interview-prep

This project aims to create notes for basic javascript syntax and usages (ECMAScript5). Things about ES6, Angular2, etc is excluded in the current project.

## JavaScript Browser BOM

### Window

### Navigator

### Screen

### History

### Location





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
1. Declaration会被提升(hoisting)到最上方先执行，但是赋值还是在原本代码的位置。
2. 注意Function declaration会连带花括号里的内容一起被提前。  --声明
3. 如果function使用expression方式赋值，那么在赋值前试图访问该函数会报错。 --赋值

```javascript
console.log(carName); // output "undefined". Assignment is not done yet.
var carName = "Benz";
console.log(carName); // output "Benz"
var carName;

console.log(f()); // output 3;
console.log(g()); // output 运行报错，因为()会invoke一个function, 而g不是一个function, 因为赋值还没有发生; 
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

## JavaScript Data Types

### JS primitive types 
1. String
2. Number
3. Null
4. Undefined
5. Boolean

### JS Object

  * 1. 除了primitive 类的，所有都是Object
  * 2. "this" in a function: the object that "owns" the function; “this” in an object: the object itselt（Constructor的this指的是这个原型的实例对象.见收藏夹).
  * 3. Object也可以使用for in 来历遍
  ```javascript
  var person = {fname:"John", lname:"Doe", age:25}; 

  for (x in person) {
    txt += person[x];
  }
  ``` 
  * 4. Accessing、Adding、Deleting property
  ```javascript
  person.firstName； // access
  person["firstName"]; // access
  person.lastName = "Tan"; // add
  person["lastName"] = "Tan"; // add
  delete person.lastName; // delete
  ```  
  * 5. Object的指针特性

### JS Object型 1 -- Function Object

#### 1. 基本注意事项

##### 注意Function Declaration 和 Function Expression的区别
  * 1） 有没有Hoisting：Declaration方式声明函数，函数体随着声明一起被提前。
  * 2） Self-Invoking的区别：expression可以直接在后面加()来invoke；declaration需先括号扩住再在后面加括号
   ```javascript
   var a = function(){
     console.log(4);
   }();

   (function(){
     console.log(4);
   })();
   ```

##### 注意Function Object的特点
  * 1) typeof operator returns "function".
  * 2） 可使用arguments这个object，这样就不用管有几个parameters了；常用的property：arguments.length
  ```javascript
   function sumAll() {
      var i, sum = 0;
      for (i = 0; i < arguments.length; i++) {
         sum += arguments[i];
      }
      return sum;
   }
   x = sumAll(1, 123, 500, 115, 44, 88);
  ``` 
  * 3) Arguments are passed by Value, Objects are passed by Reference(指针)
  ```javascript
  var obj1 = {"name":"Emma"},
      obj2 = {"name":"Shawn"};
  var str = "String Primitive";

  function changeName(arg1,arg2,arg3){
    arg1["name"] += " Tan";
    arg1["age"] = 18;
    arg2["name"] += " Li";
    arg3 += " not Changed";
    console.log(arg3); // output "String Primitive not Changed" 
  }

  changeName(obj1,obj2,str);

  console.log(obj1); // output { name: 'Emma Tan', age: 18 }
  console.log(obj2); // output { name: 'Shawn Li' }
  console.log(str); // output String Primitive
  ```  

  * 4） W3School上闭包的例子以及scope总结（待补充）
  
#### 2. Function object methods

##### 1) function.prototype.call

```javascript
var myObject = {
   emma:"Tan"
}

var emma = 0;
function myFunction() {
    var emma = 5;
    return this.emma;
}

console.log(myFunction.call(myObject)); // output Tan
console.log(myFunction()); // output 0
```
##### 2) function.prototype.apply

```javascript
var myObject = {
   emma:"Tan"
}

var emma = 0;
function myFunction(a,b) {
    var emma = 5;
    return (a+b) + this.emma;
}

console.log(myFunction.apply(myObject,[1,2])); //output 3Tan
console.log(myFunction(1,2)); // output 3
```
apply()的妙用见 http://web.jobbole.com/83642/

##### 3) function.prototype.bind


##### 4) function.prototype.toString



### JS Object型 2 -- String Object
### JS Object型 3 -- Array Object
### JS Object型 4 -- JSON Object
### JS Object型 5 -- Date Object
### JS Object型 6 -- Math Object
### JS Object型 7 -- Boolean Object
### JS Object型 8 -- Number Object

### Checking JS types

1. typeof

2. instanceof

3. toString


### JS references
1. String
2. Number
3. Operator
4. Statement
5. Math
6. Date
7. Array
8. Boolean
9. RegExp
10. Global
11. Conversion




