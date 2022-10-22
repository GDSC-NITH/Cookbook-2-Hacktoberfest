# **React JSX**

[Click here to check in official docs of React](https://reactjs.org/docs/getting-started.html)

## **Introduction**

As we know all of the React components have a render function. The render function specifies the HTML output of a React component. JSX(JavaScript Extension), is a React extension which allows writing JavaScript code that looks like HTML. In other words, JSX is an HTML-like syntax used by React that extends ECMAScript so that HTML-like syntax can co-exist with JavaScript/React code. The syntax is used by preprocessors (i.e., transpilers like babel) to transform HTML-like syntax into standard JavaScript objects that a JavaScript engine will parse.

JSX provides you to write HTML/XML-like structures (e.g., DOM-like tree structures) in the same file where you write JavaScript code, then preprocessor will transform these expressions into actual JavaScript code. Just like XML/HTML, JSX tags have a tag name, attributes, and children.

### **Example:**

Here, we will write JSX syntax in JSX file and see the corresponding JavaScript code which transforms by preprocessor(babel).

### **JSX File**

```
<div>Hello JavaTpoint</div>
```

Corresponding Output:

```
React.createElement("div", null, "Hello JavaTpoint");
```

The above line creates a react element and passing three arguments inside where the first is the name of the element which is div, second is the attributes passed in the div tag, and last is the content you pass which is the "Hello JavaTpoint."

## **Why use JSX?**

- It is faster than regular JavaScript because it performs optimization while translating the code to JavaScript.
- Instead of separating technologies by putting markup and logic in separate files, React uses components that contain both. We will learn components in a further section.
- It is type-safe, and most of the errors can be found at compilation time.
- It makes easier to create templates.

## **Nested Elements in JSX**

To use more than one element, you need to wrap it with one container element. Here, we use div as a container element which has three nested elements inside it.

**App. JSX**

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
            <h1>JavaTpoint</h1>
          <h2>Training Institutes</h2>
            <p>This website contains the best CS tutorials.</p>
         </div>
      );
   }
}
export default App;
```

Output:

<br>

<p align="center">
  <img src="https://static.javatpoint.com/tutorial/reactjs/images/reactjs-jsx-output.png" alt="Text Widget Output" width="500" height="75">
</p>

<br>

## **JSX Attributes**

JSX use attributes with the HTML elements same as regular HTML. JSX uses camelcase naming convention for attributes rather than standard naming convention of HTML such as a class in HTML becomes className in JSX because the class is the reserved keyword in JavaScript. We can also use our own custom attributes in JSX. For custom attributes, we need to use data- prefix. In the below example, we have used a custom attribute data-demoAttribute as an attribute for the <p> tag.

**Example:**

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
             <h1>JavaTpoint</h1>
           <h2>Training Institutes</h2>
             <p data-demoAttribute = "demo">This website contains the best CS tutorials.</p>
         </div>
      );
   }
}
export default App;
```

In JSX, we can specify attribute values in two ways:

1. As String Literals: We can specify the values of attributes in double quotes:

```
var element = <h2 className = "firstAttribute">Hello JavaTpoint</h2>;
```

Example:

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
            <h1 className = "hello" >JavaTpoint</h1>
            <p data-demoAttribute = "demo">This website contains the best CS tutorials.</p>
         </div>
      );
   }
}
export default App;
```

Output:

```
JavaTpoint
This website contains the best CS tutorials.
```

2. As Expressions: We can specify the values of attributes as expressions using curly braces {}:

```
var element = <h2 className = {varName}>Hello JavaTpoint</h2>;
```

Example:

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
            <h1 className = "hello" >{25+20}</h1>
         </div>
      );
   }
}
export default App;
```

Output:

```
45
```

## **JSX Comments**

JSX allows us to use comments that begin with /_ and ends with _/ and wrapping them in curly braces {} just like in the case of JSX expressions. Below example shows how to use comments in JSX.

Example:

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      return(
         <div>
            <h1 className = "hello" >Hello JavaTpoint</h1>
        {/* This is a comment in JSX */}
         </div>
      );
   }
}
export default App;
```

## **JSX Styling**

React always recommends to use inline styles. To set inline styles, you need to use camelCase syntax. React automatically allows appending px after the number value on specific elements. The following example shows how to use styling in the element.

Example:

```
import React, { Component } from 'react';
class App extends Component{
   render(){
     var myStyle = {
         fontSize: 80,
         fontFamily: 'Courier',
         color: '#003300'
      }
      return (
         <div>
            <h1 style = {myStyle}>www.javatpoint.com</h1>
         </div>
      );
   }
}
export default App;
```

Output:
<br>

<p align="center">
  <img src="https://static.javatpoint.com/tutorial/reactjs/images/reactjs-jsx-output2.png" alt="Text Widget Output" width="500" height="75">
</p>

<br>

Example:

```
import React, { Component } from 'react';
class App extends Component{
   render(){
      var i = 5;
      return (
         <div>
            <h1>{i == 1 ? 'True!' : 'False!'}</h1>
         </div>
      );
   }
}
export default App;
```

output:

```
False!
```

## **Resources:**

- [`Javatpoint`](https://www.javatpoint.com/react-jsx)
