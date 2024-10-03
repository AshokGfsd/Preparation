# Preparation
Here’s a comprehensive overview of frequently asked JavaScript interview questions along with explanations and examples:

### JavaScript Interview Questions

1. **What are the different data types present in JavaScript?**
   - **Primitive Types**: 
     - `String`
     - `Number`
     - `Boolean`
     - `Undefined`
     - `Null`
     - `Symbol` (ES6)
     - `BigInt` (ES11)
   - **Reference Types**: Objects, Arrays, Functions.

2. **Explain Hoisting in JavaScript.**
   - Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compile phase.
   - **Example**:
     ```javascript
     console.log(x); // undefined
     var x = 5;
     ```

3. **Why do we use the word “debugger” in JavaScript?**
   - The `debugger` statement is used to pause the execution of JavaScript, allowing developers to inspect the code at that point.
   - **Example**:
     ```javascript
     debugger; // Execution will pause here
     ```

4. **Difference between `==` and `===` operators.**
   - `==` (loose equality) checks for value equality, performing type coercion if necessary.
   - `===` (strict equality) checks for both value and type equality without coercion.
   - **Example**:
     ```javascript
     console.log(0 == '0'); // true
     console.log(0 === '0'); // false
     ```

5. **Difference between `var`, `const`, and `let` keywords in JavaScript.**
   - `var`: Function-scoped or globally-scoped, can be re-declared and updated.
   - `let`: Block-scoped, can be updated but not re-declared in the same scope.
   - `const`: Block-scoped, cannot be updated or re-declared. It must be initialized at declaration.
   - **Example**:
     ```javascript
     var a = 1;
     let b = 2;
     const c = 3;
     ```

6. **Explain Implicit Type Coercion in JavaScript.**
   - Implicit type coercion occurs when JavaScript automatically converts one data type to another during operations.
   - **Example**:
     ```javascript
     console.log('5' + 1); // '51' (string)
     console.log('5' - 1); // 4 (number)
     ```

7. **Is JavaScript a statically typed or a dynamically typed language?**
   - JavaScript is a dynamically typed language, meaning variable types are determined at runtime.

8. **What is NaN property in JavaScript?**
   - `NaN` stands for "Not-a-Number" and represents a value that is not a legal number.
   - **Example**:
     ```javascript
     console.log(NaN === NaN); // false
     ```

9. **Explain passed by value and passed by reference.**
   - **Passed by Value**: A copy of the value is passed (e.g., primitives).
   - **Passed by Reference**: A reference to the original object is passed (e.g., objects).
   - **Example**:
     ```javascript
     let obj = { name: 'Alice' };
     function modify(o) {
         o.name = 'Bob';
     }
     modify(obj);
     console.log(obj.name); // 'Bob'
     ```

10. **What is an Immediately Invoked Function in JavaScript?**
    - An Immediately Invoked Function Expression (IIFE) is a function that runs as soon as it is defined.
    - **Example**:
      ```javascript
      (function() {
          console.log('IIFE executed');
      })();
      ```

11. **What do you mean by strict mode in JavaScript and characteristics of JavaScript strict-mode?**
    - Strict mode is a way to opt into a restricted variant of JavaScript, which helps catch common coding errors.
    - Characteristics:
      - Prevents usage of undeclared variables.
      - Disallows duplicate parameters.
      - `this` is `undefined` in global functions.
    - **Example**:
      ```javascript
      'use strict';
      x = 3; // ReferenceError: x is not defined
      ```

12. **Explain Higher Order Functions in JavaScript.**
    - Higher-order functions are functions that take other functions as arguments or return functions as their results.
    - **Example**:
      ```javascript
      function higherOrder(fn) {
          return function() {
              fn();
              console.log('After function call');
          };
      }
      const newFunction = higherOrder(() => console.log('Hello'));
      newFunction();
      ```

13. **Explain the “this” keyword.**
    - The `this` keyword refers to the context in which a function is called. Its value depends on how the function is invoked.
    - **Example**:
      ```javascript
      const obj = {
          name: 'Alice',
          greet: function() {
              console.log('Hello, ' + this.name);
          }
      };
      obj.greet(); // 'Hello, Alice'
      ```

14. **What do you mean by Self Invoking Functions?**
    - Self-invoking functions (IIFE) are functions that execute themselves immediately after they are defined.
    - **Example**:
      ```javascript
      (function() {
          console.log('Self Invoking Function');
      })();
      ```

15. **Explain `call()`, `apply()`, and `bind()` methods.**
    - `call()`: Calls a function with a given `this` value and arguments provided individually.
    - `apply()`: Similar to `call()`, but arguments are provided as an array.
    - `bind()`: Returns a new function with a specified `this` value and optional arguments.
    - **Example**:
      ```javascript
      function greet(greeting) {
          console.log(greeting + ', ' + this.name);
      }
      const obj = { name: 'Alice' };
      greet.call(obj, 'Hello'); // 'Hello, Alice'
      greet.apply(obj, ['Hi']); // 'Hi, Alice'
      const greetAlice = greet.bind(obj);
      greetAlice('Hey'); // 'Hey, Alice'
      ```

16. **What is the difference between `exec()` and `test()` methods in JavaScript?**
    - `exec()`: Executes a search for a match in a specified string and returns an array of results.
    - `test()`: Tests for a match in a string and returns a boolean.
    - **Example**:
      ```javascript
      const regex = /abc/;
      console.log(regex.test('abcdef')); // true
      console.log(regex.exec('abcdef')); // ['abc']
      ```

17. **What is currying in JavaScript?**
    - Currying is a functional programming technique where a function takes multiple arguments one at a time.
    - **Example**:
      ```javascript
      function multiply(a) {
          return function(b) {
              return a * b;
          };
      }
      const double = multiply(2);
      console.log(double(5)); // 10
      ```

18. **What are some advantages of using External JavaScript?**
    - Improved page load time (caching).
    - Code reusability.
    - Separation of concerns (HTML and JavaScript).
    - Easier maintenance.

19. **Explain Scope and Scope Chain in JavaScript.**
    - **Scope**: The current context of execution, where variables and functions can be accessed.
    - **Scope Chain**: A mechanism that JavaScript uses to resolve variable names when accessing nested functions.
    - **Example**:
      ```javascript
      function outer() {
          let outerVar = 'I am outside!';
          function inner() {
              console.log(outerVar); // 'I am outside!'
          }
          inner();
      }
      outer();
      ```

20. **Explain Closures in JavaScript.**
    - A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope.
    - **Example**:
      ```javascript
      function makeCounter() {
          let count = 0;
          return function() {
              count++;
              return count;
          };
      }
      const counter = makeCounter();
      console.log(counter()); // 1
      console.log(counter()); // 2
      ```

21. **Mention some advantages of JavaScript.**
    - Versatile (runs on client and server).
    - Asynchronous programming support.
    - Rich ecosystem of libraries and frameworks.
    - Excellent for building interactive web applications.

22. **What are object prototypes?**
    - Prototypes are objects from which other objects inherit properties and methods.
    - **Example**:
      ```javascript
      function Person(name) {
          this.name = name;
      }
      Person.prototype.greet = function() {
          console.log('Hello, ' + this.name);
      };
      const alice = new Person('Alice');
      alice.greet(); // 'Hello, Alice'
      ```

23. **What are callbacks?**
    - Callbacks are functions passed as arguments to other functions, allowing for asynchronous execution.
    - **Example**:
      ```javascript
      function fetchData(callback) {
          setTimeout(() => {
              callback('Data received');
          }, 1000);
      }
      fetchData(data => console.log(data)); // 'Data received'
      ```

24. **What are the types of errors in JavaScript?**
    - SyntaxError: Incorrect syntax

.
    - ReferenceError: Accessing a variable that is not defined.
    - TypeError: Operation on an incompatible type.
    - RangeError: Value is not within the set or range of allowed values.
    - EvalError: Issues with the `eval()` function.

25. **What is memoization?**
    - Memoization is an optimization technique where the results of expensive function calls are cached and returned when the same inputs occur again.
    - **Example**:
      ```javascript
      function memoizedAdd() {
          const cache = {};
          return function(num) {
              if (num in cache) {
                  return cache[num];
              } else {
                  const result = num + 10;
                  cache[num] = result;
                  return result;
              }
          };
      }
      const add = memoizedAdd();
      console.log(add(5)); // 15
      console.log(add(5)); // 15 (cached)
      ```

26. **What is recursion in a programming language?**
    - Recursion is a process where a function calls itself to solve a problem, often breaking it into smaller subproblems.
    - **Example**:
      ```javascript
      function factorial(n) {
          if (n === 0) return 1;
          return n * factorial(n - 1);
      }
      console.log(factorial(5)); // 120
      ```

27. **What is the use of a constructor function in JavaScript?**
    - Constructor functions create and initialize objects using the `new` keyword, allowing for object-oriented programming.
    - **Example**:
      ```javascript
      function Car(make, model) {
          this.make = make;
          this.model = model;
      }
      const myCar = new Car('Toyota', 'Corolla');
      ```

28. **What is DOM?**
    - DOM (Document Object Model) is an interface that browsers implement to represent HTML documents as a tree structure of objects, enabling dynamic manipulation of web content.

29. **Which method is used to retrieve a character from a certain index?**
    - The `charAt()` method or bracket notation can be used.
    - **Example**:
      ```javascript
      const str = 'Hello';
      console.log(str.charAt(1)); // 'e'
      console.log(str[1]); // 'e'
      ```

30. **What do you mean by BOM?**
    - BOM (Browser Object Model) provides a way to interact with the browser, allowing manipulation of the browser window and its properties.

31. **What is the distinction between client-side and server-side JavaScript?**
    - **Client-side**: JavaScript executed in the browser, managing UI interactions and asynchronous requests.
    - **Server-side**: JavaScript (Node.js) executed on the server, handling business logic and database interactions.

32. **What are arrow functions?**
    - Arrow functions are a shorter syntax for writing function expressions. They do not have their own `this`, making them lexically bound.
    - **Example**:
      ```javascript
      const add = (a, b) => a + b;
      console.log(add(2, 3)); // 5
      ```

33. **What do you mean by prototype design pattern?**
    - The prototype design pattern creates objects based on a template (prototype) rather than through classes, enabling inheritance.
    - A Prototype Design Pattern is a creational pattern that helps to create new objects by copying an existing object.
    - **Example**:
      ```javascript
      const prototypeObject = {
          greet() {
              console.log('Hello');
          }
      };
      const newObject = Object.create(prototypeObject);
      newObject.greet(); // 'Hello'
      ```

34. **Differences between declaring variables using `var`, `let`, and `const`.**
    - `var`: Function-scoped, can be redeclared.
    - `let`: Block-scoped, cannot be redeclared in the same scope.
    - `const`: Block-scoped, must be initialized at declaration, cannot be reassigned.

35. **What is the rest parameter and spread operator?**
    - **Rest Parameter**: Collects multiple arguments into an array.
    - **Spread Operator**: Expands an array or object into individual elements.
    - **Example**:
      ```javascript
      function sum(...args) {
          return args.reduce((a, b) => a + b, 0);
      }
      console.log(sum(1, 2, 3)); // 6
      const arr = [1, 2, 3];
      console.log(...arr); // 1 2 3
      ```

36. **In JavaScript, how many different methods can you make an object?**
    - You can create objects using:
      - Object literals
      - Constructor functions
      - Object.create()
      - Classes (ES6)
      - Factory functions

37. **What is the use of promises in JavaScript?**
    - Promises represent the eventual completion (or failure) of an asynchronous operation and allow for chaining operations.
    - **Example**:
      ```javascript
      const promise = new Promise((resolve, reject) => {
          // Async operation
          if (true) {
              resolve('Success');
          } else {
              reject('Error');
          }
      });
      promise.then(result => console.log(result)).catch(err => console.log(err));
      ```

38. **What are classes in JavaScript?**
    - Classes are syntactical sugar over JavaScript’s existing prototype-based inheritance and provide a clearer and simpler syntax for creating objects and dealing with inheritance.
    - **Example**:
      ```javascript
      class Person {
          constructor(name) {
              this.name = name;
          }
          greet() {
              console.log('Hello, ' + this.name);
          }
      }
      const alice = new Person('Alice');
      alice.greet(); // 'Hello, Alice'
      ```

39. **What are generator functions?**
    - Generator functions are functions that can be paused and resumed, yielding multiple values over time.
    - **Example**:
      ```javascript
      function* generatorFunction() {
          yield 1;
          yield 2;
          yield 3;
      }
      const generator = generatorFunction();
      console.log(generator.next().value); // 1
      console.log(generator.next().value); // 2
      ```

40. **Explain WeakSet in JavaScript.**
    - A `WeakSet` is a collection of objects that allows for garbage collection. Objects in a `WeakSet` are held weakly, meaning if there are no other references, they can be removed from memory.
    - **Example**:
      ```javascript
      const weakSet = new WeakSet();
      const obj = {};
      weakSet.add(obj);
      console.log(weakSet.has(obj)); // true
      ```

41. **Why do we use callbacks?**
    - Callbacks allow for asynchronous execution, enabling the execution of code after a task completes without blocking the main thread.

42. **Explain WeakMap in JavaScript.**
    - A `WeakMap` is a collection of key-value pairs where the keys are objects and are held weakly. This allows for garbage collection of the keys if there are no other references to them.
    - **Example**:
      ```javascript
      const weakMap = new WeakMap();
      const obj = {};
      weakMap.set(obj, 'value');
      console.log(weakMap.get(obj)); // 'value'
      ```

43. **What is Object Destructuring?**
    - Object destructuring is a syntax that allows unpacking properties from objects into distinct variables.
    - **Example**:
      ```javascript
      const person = { name: 'Alice', age: 25 };
      const { name, age } = person;
      console.log(name); // 'Alice'
      ```

44. **Difference between prototypal and classical inheritance.**
    - Prototypal inheritance uses prototype chains for inheritance.
    - Classical inheritance uses classes and constructors.
    - JavaScript primarily uses prototypal inheritance, while classical inheritance is implemented using ES6 classes.

45. **What is a Temporal Dead Zone?**
    - The Temporal Dead Zone (TDZ) refers to the time span between the creation of a variable in the scope and its initialization where the variable is inaccessible.
    - **Example**:
      ```javascript
      console.log(a); // ReferenceError
      let a = 3;
      ```

46. **What do you mean by JavaScript Design Patterns?**
    - Design patterns are reusable solutions to common problems in software design, including Singleton, Factory, Observer, and Module patterns.

47. **Is JavaScript a pass-by-reference or pass-by-value language?**
    - JavaScript is pass-by-value for primitive types and pass-by-reference for objects.

48. **Difference between Async/Await and Generators usage to achieve the same functionality.**
    - Async/Await provides a more readable and straightforward syntax for handling asynchronous code than generators, which require the `yield` keyword.
    - **Example**:
      ```javascript
      // Async/Await
      async function fetchData() {
          const response = await fetch('url');
          const data = await response.json();
          return data;
      }

      // Generator
      function* fetchDataGen() {
          const response = yield fetch('url');
          const data = yield response.json();
          return data;
      }
      ```

49. **What are the primitive data types in JavaScript?**
    - Primitive data types include:
      - `String`
      - `Number`
      - `Boolean`
      - `Undefined`
      - `Null`
      - `Symbol`
      - `BigInt`

50. **What is the role of deferred scripts in JavaScript?**
   

 - Deferred scripts are scripts that are executed after the document has been parsed, ensuring that the DOM is fully loaded before the script runs.

51. **What has to be done in order to put Lexical Scoping into practice?**
    - Use functions nested within other functions to create a closure, allowing the inner function to access variables from the outer function's scope.

52. **What is the purpose of the following JavaScript code?**
    - Without specific code, I can't provide a detailed purpose. Please share the code snippet for analysis.

53. **Difference between `forEach` and `map()`.**
    - `forEach`: Executes a provided function once for each array element. It does not return a new array.
    - `map()`: Creates a new array populated with the results of calling a provided function on every element in the calling array.
    - **Example**:
      ```javascript
      const arr = [1, 2, 3];
      arr.forEach(num => console.log(num)); // Logs 1, 2, 3
      const doubled = arr.map(num => num * 2);
      console.log(doubled); // [2, 4, 6]
      ```

54. **Simple code for `map` and `filter`, `forEach`?**
    ```javascript
    const numbers = [1, 2, 3, 4, 5];

    // forEach
    numbers.forEach(num => console.log(num)); // Logs each number

    // map
    const doubled = numbers.map(num => num * 2);
    console.log(doubled); // [2, 4, 6, 8, 10]

    // filter
    const evens = numbers.filter(num => num % 2 === 0);
    console.log(evens); // [2, 4]
    ```

55. **How can we call the nested function from the outside?**
    - By returning the nested function from its outer function or by exposing it as a property of an object.
    - **Example**:
      ```javascript
      function outer() {
          function inner() {
              console.log('Inner function');
          }
          return inner;
      }
      const innerFunc = outer();
      innerFunc(); // 'Inner function'
      ```

### Problem Based Questions

1. **Print the following pattern:**
    ```
    *
    **
    ***
    ****
    *****
    ```
    **Code**:
    ```javascript
    for (let i = 1; i <= 5; i++) {
        console.log('*'.repeat(i));
    }
    ```

2. **Print reverse without using default function.**
    **Code**:
    ```javascript
    function reverseString(str) {
        let reversed = '';
        for (let i = str.length - 1; i >= 0; i--) {
            reversed += str[i];
        }
        return reversed;
    }
    console.log(reverseString('hello')); // 'olleh'
    ```

3. **Array & object based questions:**
   - **How do you reverse an array in JavaScript?**
     **Code**:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     const reversedArr = arr.reverse(); // [5, 4, 3, 2, 1]
     ```

   - **How do you find the maximum/minimum number in an array?**
     **Code**:
     ```javascript
     const maxNum = Math.max(...arr); // Maximum
     const minNum = Math.min(...arr); // Minimum
     ```

   - **How do you remove duplicates from an array?**
     **Code**:
     ```javascript
     const uniqueArr = [...new Set(arr)];
     ```

4. **Output expectation or you want to write code:**
   - **Example 1**:
     ```javascript
     console.log("1. Start");
     setTimeout(() => {
         console.log("3. Timeout");
     }, 1000);
     console.log("2. End");
     ```
     **Output**:
     ```
     1. Start
     2. End
     3. Timeout
     ```

   - **Example 2**:
     ```javascript
     console.log('Start');
     setTimeout(() => {
         console.log('Timeout 1');
     }, 1000);
     setTimeout(() => {
         console.log('Timeout 2');
     }, 800);
     console.log('End');
     ```
     **Output**:
     ```
     Start
     End
     Timeout 2
     Timeout 1
     ```

Sure! Here’s an overview of frequently asked React interview questions, along with explanations and examples where applicable.

### ReactJS Frequently Asked Interview Questions

1. **What is ReactJS?**
   - ReactJS is an open-source JavaScript library used for building user interfaces, particularly for single-page applications. It allows developers to create reusable UI components.

2. **Why ReactJS is Used?**
   - ReactJS is used for its efficiency, flexibility, and ease of integration with other libraries or frameworks. It enables developers to build dynamic, high-performance web applications with a component-based architecture.

3. **How Does ReactJS work?**
   - React creates a virtual DOM representation of the UI, allowing it to determine changes quickly. When the state of an object changes, React updates only the part of the DOM that needs to change, improving performance.

4. **What are the features of ReactJS?**
   - Key features include:
     - Virtual DOM
     - JSX (JavaScript XML)
     - Component-based architecture
     - Unidirectional data flow
     - Hooks for state and lifecycle management

5. **What is JSX?**
   - JSX is a syntax extension that allows mixing HTML with JavaScript. It makes writing React components easier and more intuitive.
   - **Example**:
     ```javascript
     const element = <h1>Hello, world!</h1>;
     ```

6. **How to create components in ReactJS?**
   - Components can be created as either functional or class components. 
   - **Functional Component**:
     ```javascript
     const MyComponent = () => <div>Hello</div>;
     ```
   - **Class Component**:
     ```javascript
     class MyComponent extends React.Component {
         render() {
             return <div>Hello</div>;
         }
     }
     ```

7. **What are the advantages of ReactJS?**
   - Advantages include:
     - Component reusability
     - Fast rendering using Virtual DOM
     - Strong community support
     - Rich ecosystem of libraries and tools

8. **Differentiate between real DOM and virtual DOM?**
   - The real DOM updates the UI directly, which can be slow. The virtual DOM is a lightweight copy of the real DOM that allows React to batch updates and minimize direct DOM manipulations, leading to better performance.

9. **What are forms in ReactJS?**
   - Forms in React are controlled components where the form data is handled by the component's state. Each form element is tied to a state variable, ensuring controlled behavior.

10. **How is React different from React Native?**
    - React is used for web applications, while React Native is used for building mobile applications. React Native allows you to use native components instead of web components.

11. **What are the limitations of React?**
    - Limitations include:
      - Learning curve for new users
      - JSX might be confusing initially
      - Not a complete framework (often requires additional libraries for routing, state management)

12. **What do you understand by Virtual DOM? Explain its working.**
    - The Virtual DOM is a lightweight representation of the real DOM. When a component's state changes, React creates a new virtual DOM and compares it with the previous version using a process called "reconciliation." Only the parts that changed are updated in the real DOM.

13. **Why can’t browsers read JSX?**
    - Browsers cannot read JSX because it is not valid JavaScript. JSX must be transpiled into JavaScript using tools like Babel before it can be executed in the browser.

14. **How different is React’s ES6 syntax when compared to ES5?**
    - ES6 introduced features like arrow functions, classes, template literals, and destructuring, making the syntax more concise and easier to read.
    - **Example** (ES5 vs. ES6):
      ```javascript
      // ES5
      var add = function(a, b) {
          return a + b;
      };

      // ES6
      const add = (a, b) => a + b;
      ```

15. **How is React different from Angular?**
    - React is a library focused on building UI components, while Angular is a full-fledged MVC framework. React uses a component-based architecture, whereas Angular employs a directive-based approach.

16. **What is useState() in React?**
    - `useState()` is a React Hook that lets you add state to functional components. It returns an array with the current state value and a function to update it.
    - **Example**:
      ```javascript
      const [count, setCount] = useState(0);
      ```

17. **What are keys in React?**
    - Keys are unique identifiers for React elements in a list. They help React identify which items have changed, are added, or are removed, enhancing performance during re-renders.

18. **What are the differences between controlled and uncontrolled components?**
    - **Controlled Components**: Form data is handled by the state of the component.
      ```javascript
      <input value={this.state.value} onChange={this.handleChange} />
      ```
    - **Uncontrolled Components**: Form data is handled by the DOM itself.
      ```javascript
      <input defaultValue="initial" />
      ```

19. **What are props in React?**
    - Props (short for properties) are used to pass data from one component to another. They are immutable and can be used to render dynamic content.
    - **Example**:
      ```javascript
      <MyComponent name="Alice" />
      ```

20. **Explain about types of side effects in React component.**
    - Side effects can include:
      - Data fetching
      - Subscriptions
      - Manually changing the DOM
    - These are managed using the `useEffect` Hook.

21. **What is prop drilling in React?**
    - Prop drilling is the process of passing data through multiple layers of components to reach a deeply nested component. This can lead to cumbersome code and can be alleviated using context or state management libraries.

22. **Explain React Hooks.**
    - Hooks are functions that let you use state and other React features in functional components. Common hooks include `useState`, `useEffect`, `useContext`, and `useReducer`.

23. **What are the rules that must be followed while using React Hooks?**
    - Rules include:
      - Only call hooks at the top level of a function component or custom hook.
      - Only call hooks from React functions.

24. **What is the use of useEffect React Hooks?**
    - `useEffect` is used to perform side effects in functional components, such as data fetching, subscriptions, or manually changing the DOM. It runs after the render, making it perfect for operations that require the DOM to be in a certain state.

25. **How to pass data between react components?**
    - Data can be passed via props. For more complex state management, consider using context or a state management library like Redux.

26. **Explain about types of Hooks in React.**
    - Common hooks include:
      - `useState`: Manages state in functional components.
      - `useEffect`: Manages side effects.
      - `useContext`: Accesses context values.
      - `useReducer`: Manages state in complex components.

27. **What is React Router?**
    - React Router is a library for routing in React applications. It allows for navigation between different components and pages without reloading the entire app.

28. **What are the different phases of React component’s lifecycle?**
    - The lifecycle of a React component can be divided into three phases:
      - **Mounting**: Birth of the component.
      - **Updating**: When props or state change.
      - **Unmounting**: When the component is removed from the DOM.

29. **Explain the lifecycle methods of React components in detail.**
    - Key lifecycle methods include:
      - `componentDidMount()`: Invoked immediately after a component is mounted. Ideal for fetching data.
      - `componentDidUpdate()`: Invoked immediately after updating occurs.
      - `componentWillUnmount()`: Invoked immediately before a component is unmounted and destroyed.

30. **What is "key" prop and what is the benefit of using it in arrays of elements?**
    - The `key` prop helps React identify which items have changed, are added, or are removed. It should be a unique value for each element to optimize rendering.

31. **What are controlled components?**
    - Controlled components are components that do not maintain their own state. Instead, the state is controlled by React, and any changes in the form inputs update the component state.

32. **What is reconciliation?**
    - Reconciliation is the process by which React updates the DOM. It involves comparing the previous and new virtual DOMs to determine what has changed and efficiently updating the real DOM.

33. **Why React uses className over class attribute?**
    - In React, `className` is used instead of `class` because `class` is a reserved keyword in JavaScript.

34. **What are fragments?**
    - Fragments are a way to group multiple elements without adding extra nodes to the DOM. They help in returning multiple elements from a component.
    - **Example**:
      ```javascript
      return (
          <>
              <Child1 />
              <Child2 />
          </>
      );
      ```

35. **Why fragments are better than container divs?**
    - Fragments avoid unnecessary divs in the DOM, leading to cleaner HTML and improved performance.

36. **What are the limitations of React?**
    - Some limitations include:
      - The initial learning curve.
      - Reliance on third-party libraries for state management.
      - SEO challenges due to

 its client-side rendering.

37. **What is the purpose of render method of react-dom?**
    - The `render` method from `react-dom` is used to render a React element into the DOM, updating the content of the target node.

38. **How to use styles in React?**
    - Styles can be applied using:
      - Inline styles: `{ style={{ color: 'red' }} }`
      - CSS classes: `className="my-class"`
      - CSS modules for scoped styles.

39. **How events are different in React?**
    - React's event handling is normalized across browsers. Events are named using camelCase, and the `addEventListener` method is replaced by a synthetic event system.

40. **What will happen if you use props in initial state?**
    - Using props in the initial state can lead to issues with component re-renders, as state won't automatically update when props change. It's better to use `componentDidUpdate` to handle props changes.

41. **What is a switching component?**
    - A switching component (like `Switch` from React Router) renders the first child `<Route>` that matches the current location.

42. **How to loop inside JSX?**
    - Use JavaScript's array methods like `map()` to loop through data in JSX.
    - **Example**:
      ```javascript
      const items = ['Apple', 'Banana', 'Cherry'];
      const listItems = items.map(item => <li key={item}>{item}</li>);
      ```

43. **Why ReactDOM is separated from React?**
    - React focuses on building UI components, while ReactDOM specifically handles rendering those components into the DOM. This separation allows for React to be used in environments other than the browser.

44. **Why you get "Router may have only one child element" warning?**
    - This warning occurs when a `<Router>` component has multiple direct children. It requires a single child, typically wrapped in a `<Switch>` or `<Fragment>`.

45. **How to implement default or NotFound page?**
    - Use a `Route` without a `path` attribute to render a NotFound page.
    - **Example**:
      ```javascript
      <Route component={NotFound} />
      ```

46. **How to dispatch an action on load?**
    - Use the `useEffect` hook to dispatch an action when the component mounts.
    - **Example**:
      ```javascript
      useEffect(() => {
          dispatch(fetchData());
      }, []);
      ```

47. **What is the difference between React context and React Redux?**
    - React Context is used for passing data through the component tree without passing props down manually. Redux is a state management library that provides a centralized store for all components, along with predictable state updates.

48. **Why are Redux state functions called reducers?**
    - They are called reducers because they take the current state and an action as arguments and return a new state, effectively reducing the complexity of state management.

49. **How to make AJAX request in Redux?**
    - Use middleware like `redux-thunk` or `redux-saga` to handle asynchronous actions and make AJAX requests.
    - **Example with redux-thunk**:
      ```javascript
      const fetchData = () => {
          return dispatch => {
              fetch('url')
                  .then(response => response.json())
                  .then(data => dispatch({ type: 'FETCH_SUCCESS', payload: data }));
          };
      };
      ```

50. **What is the difference between component and container in React Redux?**
    - **Component**: A presentational component focused on UI without business logic.
    - **Container**: A component that is connected to the Redux store, often containing logic to manage state.

51. **What is React lazy function?**
    - React's `React.lazy()` allows you to load components lazily, splitting code to optimize loading performance. It works with `Suspense` to show a fallback UI while loading.
    - **Example**:
      ```javascript
      const LazyComponent = React.lazy(() => import('./LazyComponent'));
      ```

### React HOE (Hands-on Experience)
1. **Hooks**: Practice using built-in hooks like `useState`, `useEffect`, and custom hooks.
2. **API Calls (Mock API)**: Use libraries like `axios` or `fetch` to make HTTP requests to a mock API.
3. **CRUD Operations**: Implement Create, Read, Update, Delete functionality with checkboxes, dropdowns, and search buttons.
4. **Redux**: Manage state with Redux, integrating actions, reducers, and middleware.
5. **Context**: Use React Context API for state management across components.
6. **Form Validation**: Implement forms with validation using libraries like Formik and Yup.
7. **ToDo App**: Create a ToDo application using hooks like `useRef` and `useState`.
8. **Routing**: Implement routing in your application using React Router.
9. **File Handling**: Implement file upload and download functionality.
10. **Authentication**: Implement login functionality with providers like Google, Facebook, or GitHub.
11. **Firebase**: Use Firebase for authentication and real-time database features.
12. **Material-UI / Tailwind CSS**: Style your components using popular CSS frameworks.

### Frontend Example Projects for Portfolio
- Order Management System
- E-commerce Application
- Travel Blog
- Recipe App
- Hospital Management System
- Expenses Tracker

### Ultimate Task
1. **Personal Portfolio Website**: Build a portfolio website showcasing your projects.
2. **Prepare for Placement**: Focus on technical development and interview preparation.



### MongoDB Interview Questions

1. **Difference between `update` and `findOneAndUpdate`?**
   - `update` modifies documents without returning the modified document(s). 
   - `findOneAndUpdate` updates a document and returns the original or updated document based on the options provided.
   - **Example**: 
     ```javascript
     db.collection.update({ name: "John" }, { $set: { age: 30 } }); // no return
     db.collection.findOneAndUpdate({ name: "John" }, { $set: { age: 30 } }); // returns updated document
     ```

2. **Difference between `drop` and `remove`?**
   - `drop` removes an entire collection or database.
   - `remove` deletes documents that match a specified query.
   - **Example**:
     ```javascript
     db.collection.drop(); // drops the entire collection
     db.collection.remove({ age: { $lt: 18 } }); // removes documents with age < 18
     ```

3. **Difference between `createIndex` and `reIndex`?**
   - `createIndex` creates a new index on a collection.
   - `reIndex` rebuilds all indexes on a collection.
   - **Example**:
     ```javascript
     db.collection.createIndex({ name: 1 }); // creates index on 'name'
     db.collection.reIndex(); // rebuilds all indexes
     ```

4. **How to get system info on which MongoDB is running?**
   - Use `db.runCommand({ serverStatus: 1 })` to get server info.
   - **Example**:
     ```javascript
     const info = db.runCommand({ serverStatus: 1 });
     console.log(info);
     ```

5. **How to remove current database?**
   - Use `db.dropDatabase()` to delete the current database.
   - **Example**:
     ```javascript
     db.dropDatabase(); // drops the current database
     ```

6. **How to rename a collection?**
   - Use `renameCollection` method.
   - **Example**:
     ```javascript
     db.collection.renameCollection("newCollectionName");
     ```

7. **Difference between `findAndModify()` and `findOneAndUpdate()`?**
   - `findAndModify` is a more general operation that can return documents and modify them in a single atomic operation.
   - `findOneAndUpdate` is a simpler version focused on updating a single document.
   - **Example**:
     ```javascript
     db.collection.findAndModify({
       query: { name: "John" },
       update: { $set: { age: 30 } }
     });
     ```

8. **What is MongoDB?**
   - MongoDB is a NoSQL database that stores data in flexible, JSON-like documents.

9. **What is a document in MongoDB?**
   - A document is a basic unit of data in MongoDB, represented as a JSON object.

10. **What is a collection in MongoDB?**
    - A collection is a grouping of MongoDB documents, similar to a table in relational databases.

11. **What is a replica set in MongoDB?**
    - A replica set is a group of MongoDB servers that maintain the same dataset, providing redundancy and high availability.

12. **What is sharding in MongoDB?**
    - Sharding is a method for distributing data across multiple servers to ensure scalability and manage large datasets.

13. **What is indexing in MongoDB?**
    - Indexing improves the speed of data retrieval operations on a collection.

14. **What are the different types of indexing in MongoDB?**
    - Types include single field, compound, multi-key, geospatial, text, and hashed indexes.

15. **What is mapReduce in MongoDB?**
    - A method for processing large datasets using a distributed algorithm. It involves mapping, shuffling, and reducing.

16. **What is aggregation pipeline in MongoDB?**
    - A framework for data aggregation using stages like `$match`, `$group`, `$sort`, and `$project`.

17. **Difference between `update` and `save` in MongoDB?**
    - `update` modifies existing documents; `save` can insert a new document or update an existing one based on the `_id`.

18. **Difference between primary key and secondary key in MongoDB?**
    - A primary key uniquely identifies documents (default `_id`); a secondary key is used for indexing but does not have to be unique.

19. **How does MongoDB ensure data consistency?**
    - MongoDB provides consistency through write concerns, journaling, and replica sets.

20. **How does MongoDB handle schema changes?**
    - MongoDB's flexible schema allows for changes without requiring a fixed schema, enabling dynamic field additions.

21. **How does MongoDB handle transactions?**
    - It supports multi-document ACID transactions starting from version 4.0, allowing operations to be executed atomically.

22. **What is the role of the mongo shell in MongoDB?**
    - The mongo shell is an interactive JavaScript interface to interact with MongoDB for CRUD operations and administration.

23. **Is MongoDB better than other SQL databases? If yes, how?**
    - MongoDB is better for applications requiring high scalability, flexibility in schema, and the ability to handle unstructured data.

24. **What is the difference between MongoDB and MySQL?**
    - MongoDB is document-oriented and schema-less, while MySQL is a relational database with a fixed schema.

25. **Why is MongoDB known as the best NoSQL database?**
    - Its flexibility, scalability, rich querying capabilities, and strong community support make it a top choice.

26. **What are some features of MongoDB?**
    - Features include a flexible schema, built-in sharding, replication, full-text search, and aggregation framework.

27. **How do you update a document?**
    - Use `updateOne`, `updateMany`, or `findOneAndUpdate`.
    - **Example**:
      ```javascript
      db.collection.updateOne({ name: "John" }, { $set: { age: 30 } });
      ```

28. **How do you delete a document?**
    - Use `deleteOne` or `deleteMany`.
    - **Example**:
      ```javascript
      db.collection.deleteOne({ name: "John" });
      ```

29. **What are the data types in MongoDB?**
    - Common data types include String, Number, Boolean, Date, Array, Object, Null, and ObjectId.

---

### Node.js Interview Questions

1. **What is Node.js?**
   - Node.js is a JavaScript runtime built on Chrome's V8 engine that allows you to run JavaScript on the server.

2. **How does Node.js work?**
   - Node.js uses an event-driven, non-blocking I/O model, making it lightweight and efficient for I/O-heavy applications.

3. **What do you understand by the term I/O?**
   - I/O stands for Input/Output, which involves reading data from or writing data to external sources like files, databases, or network connections.

4. **Difference between FE and BE?**
   - Frontend (FE) refers to the client-side of an application (UI/UX), while Backend (BE) involves server-side logic and database interactions.

5. **What is npm?**
   - npm (Node Package Manager) is a package manager for JavaScript, allowing developers to share and reuse code.

6. **What are modules in Node.js?**
   - Modules are reusable pieces of code that encapsulate related functionality. They can be imported and exported between files.

7. **Difference between Angular and Node.js?**
   - Angular is a front-end framework for building single-page applications, while Node.js is a server-side runtime environment.

8. **Which database is mostly used in Node.js?**
   - MongoDB is commonly used with Node.js due to its compatibility with JSON-like data.

9. **What are the pros and cons of Node.js?**
   - **Pros**: Fast performance, scalability, large community, and non-blocking I/O. 
   - **Cons**: Callback hell, single-threaded, and less mature than some other technologies.

10. **What does event-driven programming mean?**
    - It’s a programming paradigm where the flow of the program is determined by events like user actions or sensor outputs.

11. **What is the event loop?**
    - The event loop is a mechanism that allows Node.js to perform non-blocking I/O operations by offloading operations to the system kernel.

12. **What is an event emitter?**
    - An event emitter is an object that can emit events and listen for them, enabling asynchronous event-driven programming.

13. **What are types of API functions in Node?**
    - Types include synchronous and asynchronous functions, event-driven functions, and callback functions.

14. **What is package.json?**
    - package.json is a file that contains metadata about the project, including dependencies, scripts, and configuration.

15. **What is the express package?**
    - Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.

16. **Explain asynchronous and non-blocking API in Node.js?**
    - Asynchronous APIs allow operations to occur without blocking the execution of other code. Non-blocking means the server can handle other requests while waiting for an I/O operation to complete.

17. **How do we implement async in Node.js?

**
    - Use async/await, Promises, or callbacks to manage asynchronous operations.
    - **Example**:
      ```javascript
      async function fetchData() {
          const data = await fetch('https://api.example.com/data');
          console.log(data);
      }
      ```

18. **What is the purpose of module.exports?**
    - `module.exports` is used to export functions or objects from a module so they can be imported in other files.

19. **What is a callback function?**
    - A callback function is a function passed as an argument to another function, executed after a certain task is completed.

20. **What is a control flow function?**
    - Control flow functions manage the order of asynchronous operations, like `async.waterfall` or `async.series` from the async library.

21. **What do you mean by Asynchronous API?**
    - An asynchronous API allows calls to be made without waiting for the operation to complete, enhancing performance in I/O-bound applications.

22. **What are the benefits of using Node.js?**
    - Benefits include high performance, scalability, real-time capabilities, a unified JavaScript development stack, and a large ecosystem of packages.

---

Great! Here’s an example of how you might explain your fitness tracker project based on the provided URL:

---

### Project Name: Fitness Tracker  
**URL**: [Fitness Tracker](https://fitness-tracker-frontend-phi.vercel.app/)

### 1. Introduction
This project is a **Fitness Tracker** application designed to help users monitor their fitness activities, track workouts, and maintain a healthy lifestyle. The application serves as a central hub for users to log their exercises, manage their goals, and analyze their progress over time.

### 2. Features
- **User Registration and Authentication**: Users can create accounts to securely log their fitness activities.
- **Workout Logging**: Users can easily log different types of workouts, including duration, type, and calories burned.
- **Progress Tracking**: Visual graphs and statistics help users track their progress over time, making it easy to see improvements.
- **Goal Setting**: Users can set fitness goals and monitor their progress toward achieving them.
- **Responsive Design**: The application is designed to be user-friendly across various devices, including mobile and tablet.

### 3. Technology Stack
- **Frontend**: Built with **React**, utilizing hooks for state management and functional components for a modern approach.
- **Styling**: CSS modules for styling, ensuring scoped styles for better maintainability.
- **API Integration**: The app communicates with a backend API (assumed based on standard practice) to manage user data and workout logs.

### 4. Architecture
The application follows a component-based architecture typical of React applications. It features a clean separation between UI components and business logic, making it easy to maintain and scale.

### 5. Challenges Faced
One significant challenge was ensuring smooth data flow between components and the backend. Implementing **error handling** for API requests was crucial to enhance the user experience, especially when the network connection was unstable.

### 6. User Experience
The user interface is intuitive, allowing users to navigate effortlessly through the app. Feedback from initial users highlighted the app’s simplicity and effectiveness in tracking workouts.

### 7. Future Improvements
Future enhancements could include:
- **Social Features**: Allowing users to connect and share progress with friends.
- **Integration with Wearable Devices**: Syncing with fitness trackers or smartwatches for automated logging.
- **Personalized Recommendations**: Suggesting workouts based on user preferences and progress.

### 8. Conclusion
The Fitness Tracker application not only demonstrates my skills in React development but also addresses a common need for fitness enthusiasts. By providing a platform to track workouts and monitor progress, it empowers users to take control of their fitness journeys.

---

Feel free to customize any sections based on your specific insights and experiences related to the project! If there are additional features or details you want to emphasize, just let me know!
