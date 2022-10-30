# JavaScript
JavaScript is a lightweight, interpreted compiled programming language. 
It is also known as scripting language for web pages. It can be used for Client-side as well as Server-side developments. 
It is an interpreted, full-fledged programming language that enables dynamic interactivity on websites when applied to an HTML document. It was introduced in the year 1995 for adding programs to the webpages in the Netscape Navigator browser. Since then, it has been adopted by all other graphical web browsers. With JavaScript, users can build modern web applications to interact directly without reloading the page every time. The traditional website uses js to provide several forms of interactivity and simplicity.

## Features of JavaScript
* All popular web browsers support JavaScript as they provide built-in execution environments.
* JavaScript follows the syntax and structure of the C programming language. Thus, it is a structured programming language.
* JavaScript is a weakly typed language, where certain types are implicitly cast (depending on the operation).
* JavaScript is an object-oriented programming language that uses prototypes rather than using classes for inheritance.
* It is a light-weighted and interpreted language.
* It is a case-sensitive language.
* JavaScript is supportable in several operating systems including, Windows, macOS, etc.
* It provides good control to the users over the web browsers.

## Adding JavaScript into the Web Page
JavaScript can be added to your HTML file in two ways:

* Internal JavaScript: We can add JavaScript code directly to our HTML file by writing the code inside the <script> tag. The <script> tag can either be placed inside the <head> or the <body> tag according to the requirement.
```c
  <!DOCTYPE html>
<html lang="en">
 
<head>
    <title>
        Basic Example to Describe JavaScript
    </title>
</head>
 
<body>
 
    <!-- JavaScript code can be embedded inside
        head section or body section -->
    <script>
        console.log("Welcome to JavaScript");
    </script>
</body>
 
</html>
```
* External JavaScript File: We can create a file with .js extension and paste the JavaScript code inside it. After creating the file, add this file in <script src=”file_name.js”> tag inside <head> tag of the HTML file.
  
## JavaScript Engines
  A JavaScript engine is a computer program that executes JavaScript code and converts it into computer understandable language.
  Major JavaScript engines include:
* V8: It is a JavaScript engine developed by the Chrome project for the Google Chrome and Chromium web browser.
* Chakra: Chakra is a JScript engine developed by Microsoft. It is proprietary software. It is used in the Internet Explorer web browser.
* Spider Monkey: SpiderMonkey is the first JavaScript engine, written by Brendan Eich at Netscape Communications, later released as open-source and currently maintained by the Mozilla Foundation.
* Webkit: WebKit is developed by Apple and  used in its Safari web browser, as well as all iOS web browsers.
  
## Some important topics of JavaScript
* includes(): includes() method is used to find whether one string may be found within another string or not. It returns a boolean value of true or false.
* parseInt(): It is used to accept the string and radix/base as parameters then converts it into an integer. The second parameter is optional and is used to specify which numerical system to be used as the first parameter. 
* forEach(): It is a method that executes a provided callback function once for each array element in an ascending order. There is no way to stop or break a forEach() loop other than by throwing an exception.
* Array.concat(): The concat() method is used to merge two or more arrays. This method returns a new array. It has no impact on the existing array as it returns a new array.
* let, var, & const: let, const, and var those are used at the time of variable declaration. let allows us to declare block-level variables that means, if you declare variable using let then the variable can only be accessible from the block it is enclosed in. const allows us to declare variables whose values are unchangeable. var is the keyword that doesn’t have restrictions like the other two keywords have. It is the most common declarative keyword. 
* Document Object Model (DOM): Every HTML tag is an object and nested tags are “children” of the enclosing one. The text inside the tag is an object as well. We can access all these objects using JavaScript and we can use them to modify the page. For example, document.body is the object representing the <body> tag.
