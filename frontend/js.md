Questions

1. What is Closures
    A closure gives you access to an outer function's scope from an inner function.
    Nested functions

2. What is a pure function
Produces the same output for the same input: Given the same inputs, a pure function will always return the same output, regardless of any external factors or the state of the program.

3. What is the difference between null and undefined in JavaScript?

 definition, undefined means a variable has been declared but has not yet been assigned a value, whereas null is an assignment value, meaning that a variable has been declared and given the value of null .

4. What is Lexical Scoping
Lexical scoping refers to how a parser resolves variable names when functions are nested. The location where a variable is declared within the source code determines where that variable is available. Nested functions have access to variables declared in their outer scope

5. Explain the event bubbling and event capturing in JavaScript
 Event bubbling and event capturing are two mechanisms for handling events in the DOM. In event bubbling, the event starts from the target element and bubbles up through its ancestors to the root of the document. In event capturing, the event starts from the root of the document and trickles down to the target element. Both mechanisms are phases of event propagation in the DOM.

6. What is the difference between == and === operators in JavaScript?
'==' allows coercion between different types, whereas === requires both the value and the type to be the same for the comparison to return true.

7. How does JavaScript handle asynchronous operations?
JavaScript uses asynchronous programming techniques such as callbacks, promises, and async/await to handle asynchronous operations. Callbacks are functions passed as arguments to other functions, promises represent the eventual completion or failure of an asynchronous operation, and async/await provides syntactic sugar for writing asynchronous code in a more synchronous-looking manner.

8. What is Functional Programming?
Functional programming is a programming paradigm that uses pure functions as the primary units of composition.
Functional programming is a declarative programming paradigm, which means that programs are written in terms of what they do, rather than how they do it. This makes functional programs easier to understand, debug, and test than imperative programs. They also tend to be a lot more concise, which reduces code complexity and makes it easier to maintain.

functional programming include:

Immutability — immutable data structures are easier to reason about than mutable data structures.
Higher-order functions — functions that take other functions as arguments or return functions as their result.
Avoiding shared mutable state — shared mutable state makes programs difficult to understand, debug, and test. 

9. What is a Promise?

A Promise in JavaScript is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

10. What is TypeScript?
TypeScript is a superset of JavaScript, It adds static typing to JavaScript, which is a dynamically typed language. Static typing helps developers catch errors early in the development process, improving code quality and maintainability.

### Key Features of TypeScript
Static Typing: Define types for your variables and function parameters to ensure consistency throughout your code.

Enhanced IDE Support: Integrated Development Environments (IDEs) can provide better autocompletion, navigation, and refactoring, making the development process more efficient.

Compilation: TypeScript code is transpiled into JavaScript, making it compatible with any browser or JavaScript environment. During this process, type errors are caught, making the code more robust.

Interfaces: Interfaces allow you to specify abstract contracts that objects and functions must satisfy.

Compatibility with JavaScript: TypeScript is highly compatible with existing JavaScript code. JavaScript code can be gradually migrated to TypeScript, making the transition smooth for existing projects.

11. Write a polyfill of Json.stringify

