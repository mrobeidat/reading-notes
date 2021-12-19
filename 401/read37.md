# React 1 

# ES6 Overview

> # ES6 Syntax and Feature Overview 

## Variables and constant feature comparison 

*explain the concepts of scope and the differences between let, var, and const in the Understanding Variables, Scope, and Hoisting in JavaScript resource on DigitalOcean. This table provides a brief overview.*

| Keyword | Scope | Hoisting | Can Be Reassigned | Can Be Redeclared |
|---------|-------|----------|-------------------|-------------------|
| var | Function scope | Yes | Yes | Yes |
| let | Block scope | No | Yes | No |
| const | Block scope | No | No | No |

## Variable declaration 

*ES6 introduced the let keyword, which allows for block-scoped variables which cannot be hoisted or redeclared.*

## Constant declaration 

*ES6 introduced the const keyword, which cannot be redeclared or reassigned, but is not immutable.*

## Arrow functions 

*The arrow function expression syntax is a shorter way of creating a function expression. Arrow functions do not have their own this, do not have prototypes, cannot be used for constructors, and should not be used as object methods.*

    let func = (a) => {} 
    let func = (a, b, c) => {}

## Template literals

### Concatenation/string interpolation 

*Expressions can be embedded in template literal strings.*

    let str = `Release Date: ${date}`

### Multi-line strings 

*Using template literal syntax, a JavaScript string can span multiple lines without the need for concatenation.*

    let str = `This text
                is on
                multiple lines`

## Implicit returns 

*The return keyword is implied and can be omitted if using arrow functions without a block body.*

    let func = (a, b, c) => a + b + c

## Key/property shorthand

*ES6 introduces a shorter notation for assigning properties to variables of the same name.*

    let obj = {
    a,
    b,
    }
## Method definition shorthand 

*The function keyword can be omitted when assigning methods on an object.*

    let obj = {
    a(c, d) {},
    b(e, f) {},
    }

    obj.a()

## Destructuring (object matching) 

*Use curly brackets to assign properties of an object to their own variable.*

    let {a, b, c} = obj

## Array iteration (looping) 

*A more concise syntax has been introduced for iteration through arrays and other iterable objects.*

    for (let i of arr) {
    console.log(i)
    }

## Default parameters 

*Functions can be initialized with default parameters, which will be used only if an argument is not invoked through the function.*

    let func = (a, b = 2) => {
    return a + b
    }

    func(10) // returns 12
    func(10, 5) // returns 15

## Spread syntax 

*Spread syntax can be used to expand an array.*

    let arr1 = [1, 2, 3]
    let arr2 = ['a', 'b', 'c']
    let arr3 = [...arr1, ...arr2]

    console.log(arr3) // [1, 2, 3, "a", "b", "c"]

*Spread syntax can be used for function arguments.*

    let arr1 = [1, 2, 3]
    let func = (a, b, c) => a + b + c

    console.log(func(...arr1)) // 6

## Classes/constructor functions 

*ES6 introducess the class syntax on top of the prototype-based constructor function.*

    class Func {
    constructor(a, b) {
        this.a = a
        this.b = b
    }

    getSum() {
        return this.a + this.b
    }
    }

    let x = new Func(3, 4)

    x.getSum() // returns 7

## Inheritance

*The extends keyword creates a subclass.*

    class Inheritance extends Func {
    constructor(a, b, c) {
        super(a, b)

        this.c = c
    }

    getProduct() {
        return this.a * this.b * this.c
    }
    }

    let y = new Inheritance(3, 4, 5)

    y.getProduct() // 60

## Modules - export/import 

*Modules can be created to export and import code between files.*

    <script src="export.js"></script>
    <script type="module" src="import.js"></script>

## export.js 

    let func = (a) => a + a
    let obj = {}
    let x = 0

    export {func, obj, x}

    import {func, obj, x} from './export.js'

    console.log(func(3), obj, x)

## Promises/Callbacks

*Promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.*

    let doSecond = () => {
    console.log('Do second.')
    }

    let doFirst = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log('Do first.')

        resolve()
    }, 500)
    })

    doFirst.then(doSecond)

# React

> # React - Hello World 

## Hello World 

*The smallest React example looks like this:*

    ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('root')
    );

> # React - JSX 

## Introducing JSX 

*Consider this variable declaration:*

    const element = <h1>Hello, world!</h1>;

## Why JSX?  

*React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.*

*Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both.*

*React doesn’t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code. It also allows React to show more useful error and warning messages.*

## JSX is an Expression Too 

*JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects.*

> # React - Rendering Elements 

## Rendering an Element into the DOM  

*To render a React element into a root DOM node, pass both to ReactDOM.render():*

    const element = <h1>Hello, world</h1>;
    ReactDOM.render(element, document.getElementById('root'));

## Updating the Rendered Element  

*the only way to update the UI is to create a new element, and pass it to ReactDOM.render().*

    function tick() {
    const element = (
        <div>
        <h1>Hello, world!</h1>
        <h2>It is {new Date().toLocaleTimeString()}.</h2>
        </div>
    );
    ReactDOM.render(element, document.getElementById('root'));}

    setInterval(tick, 1000);

## React Only Updates What’s Necessary 

*React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.*

> # React - Components & Props 

***Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.***

## Function and Class Components  

*The simplest way to define a component is to write a JavaScript function:*

    function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
    }

*You can also use an ES6 class to define a component:*

    class Welcome extends React.Component {
    render() {
        return <h1>Hello, {this.props.name}</h1>;
    }
    }

## Composing Components  

*Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.*

***All React components must act like pure functions with respect to their props.***

> # React - State & Lifecycle

## Converting a Function to a Class 

*You can convert a function component like Clock to a class in five steps:*

1. Create an ES6 class, with the same name, that extends React.Component.
2. Add a single empty method to it called render().
3. Move the body of the function into the render() method.
4. Replace props with this.props in the render() body.
5. Delete the remaining empty function declaration.

## Adding Lifecycle Methods to a Class 

*In applications with many components, it’s very important to free up resources taken by the components when they are destroyed.*

## Using State Correctly  

*There are three things you should know about setState().*

* Do Not Modify State Directly

* State Updates May Be Asynchronous

*React may batch multiple setState() calls into a single update for performance.*

*Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state.*

* State Updates are Merged

*When you call setState(), React merges the object you provide into the current state.*

## The Data Flows Down 

*Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class.*

*This is why state is often called local or encapsulated. It is not accessible to any component other than the one that owns and sets it.*

> # React - Handling Events

* React events are named using camelCase, rather than lowercase.
* With JSX you pass a function as the event handler, rather than a string.

# Tailwind CSS

> # Utility First CSS 

***Using utility classes to build custom designs without writing CSS***

    <div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-md flex items-center space-x-4">
    <div class="flex-shrink-0">
        <img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo">
    </div>
    <div>
        <div class="text-xl font-medium text-black">ChitChat</div>
        <p class="text-gray-500">You have a new message!</p>
    </div>
    </div>

## Why not just use inline styles?

*A common reaction to this approach is wondering, “isn’t this just inline styles?” and in some ways it is — you’re applying styles directly to elements instead of assigning them a class name and then styling that class.*

*But using utility classes has a few important advantages over inline styles:*

* Designing with constraints : Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.
* Responsive design : You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.
* Hover, focus, and other states : Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with utility classes.

# Next.js

> # Learn Next.js

*To build a complete web application with React from scratch, there are many important details you need to consider:*

* Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
* You need to do production optimizations such as code splitting.
* You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
* You might have to write some server-side code to connect your React app to your data store.

**A framework can solve these problems. But such a framework must have the right level of abstraction — otherwise it won’t be very useful. It also needs to have great "Developer Experience", ensuring you and your team have an amazing experience while writing code.**

## Next.js: The React Framework 

*Next.js aims to have best-in-class developer experience and many built-in features, such as:*

* An intuitive page-based routing system
* Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
* Automatic code splitting for faster page loads
* Client-side routing with optimized prefetching
* Built-in CSS and Sass support, and support for any CSS-in-JS library
* Development environment with Fast Refresh support
* API routes to build API endpoints with Serverless Functions
* Fully extendable

***Next.js is used in tens of thousands of production-facing websites and web applications, including many of the world's largest brands.***
