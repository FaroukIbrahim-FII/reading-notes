# React 1

![react](https://i.ytimg.com/vi/06pWsB_hoD4/maxresdefault.jpg)

## ES6 Syntax and Feature Overview

Variables and constant feature comparison

I explain the concepts of scope and the differences between let, var, and const in the Understanding Variables, Scope, and Hoisting in JavaScript resource on DigitalOcean. This table provides a brief overview.

|Keyword |Scope |Hoisting |Can Be Reassigned |Can Be Redeclared|
|---|---|---|---|--|
|var |Function scope |Yes |Yes |Yes|
|let |Block scope |No |Yes |No|
|const |Block scope |No |No |No|

### Template literals
Concatenation/string interpolation

Expressions can be embedded in template literal strings.

ES5

    var str = 'Release date: ' + date

ES6

    let str = `Release Date: ${date}`

### Spread syntax

Spread syntax can be used to expand an array.
ES6

    let arr1 = [1, 2, 3]
    let arr2 = ['a', 'b', 'c']
    let arr3 = [...arr1, ...arr2]

    console.log(arr3) // [1, 2, 3, "a", "b", "c"]

### Modules - export/import

Modules can be created to export and import code between files.
index.html

    <script src="export.js"></script>
    <script type="module" src="import.js"></script>

## Hello World

    ReactDOM.render(
    <h1>Hello, world!</h1>,
    document.getElementById('root')
    );

## Introducing JSX

### Why JSX?

React embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time, and how the data is prepared for display.

Instead of artificially separating technologies by putting markup and logic in separate files, React separates concerns with loosely coupled units called “components” that contain both. We will come back to components in a further section, but if you’re not yet comfortable putting markup in JS, this talk might convince you otherwise.

### Embedding Expressions in JSX

In the example below, we declare a variable called name and then use it inside JSX by wrapping it in curly braces:

    const name = 'Josh Perez';const element = <h1>Hello, {name}</h1>;
    ReactDOM.render(
    element,
    document.getElementById('root')
    );

### JSX Represents Objects

Babel compiles JSX down to React.createElement() calls.

These two examples are identical:

    const element = (
    <h1 className="greeting">
        Hello, world!
    </h1>
    );

## Rendering Elements

Rendering an Element into the DOM

Let’s say there is a <div> somewhere in your HTML file:

    <div id="root"></div>

We call this a “root” DOM node because everything inside it will be managed by React DOM.

### Updating the Rendered Element

React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.

With our knowledge so far, the only way to update the UI is to create a new element, and pass it to ReactDOM.render().

Consider this ticking clock example:

    function tick() {
    const element = (
        <div>
        <h1>Hello, world!</h1>
        <h2>It is {new Date().toLocaleTimeString()}.</h2>
        </div>
    );
    ReactDOM.render(element, document.getElementById('root'));}

    setInterval(tick, 1000);

## Components and Props

### Function and Class Components

The simplest way to define a component is to write a JavaScript function:

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

### Rendering a Component

Previously, we only encountered React elements that represent DOM tags:

    const element = <div />;

However, elements can also represent user-defined components:

    const element = <Welcome name="Sara" />;

### Composing Components

Components can refer to other components in their output. This lets us use the same component abstraction for any level of detail. A button, a form, a dialog, a screen: in React apps, all those are commonly expressed as components.

For example, we can create an App component that renders Welcome many times:

    function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
    }

    function App() {
    return (
        <div>
        <Welcome name="Sara" />      <Welcome name="Cahal" />      <Welcome name="Edite" />    </div>
    );
    }

    ReactDOM.render(
    <App />,
    document.getElementById('root')
    );

### Extracting Components

Don’t be afraid to split components into smaller components.

For example, consider this Comment component:

    function Comment(props) {
    return (
        <div className="Comment">
        <div className="UserInfo">
            <img className="Avatar"
            src={props.author.avatarUrl}
            alt={props.author.name}
            />
            <div className="UserInfo-name">
            {props.author.name}
            </div>
        </div>
        <div className="Comment-text">
            {props.text}
        </div>
        <div className="Comment-date">
            {formatDate(props.date)}
        </div>
        </div>
    );
    }

## State and Lifecycle

### Converting a Function to a Class

You can convert a function component like Clock to a class in five steps:

1. Create an ES6 class, with the same name, that extends React.Component.
2. Add a single empty method to it called render().
3. Move the body of the function into the render() method.
4. Replace props with this.props in the render() body.
5. Delete the remaining empty function declaration.

        class Clock extends React.Component {
        render() {
            return (
            <div>
                <h1>Hello, world!</h1>
                <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
            </div>
            );
        }
        }

Adding Lifecycle Methods to a Class

In applications with many components, it’s very important to free up resources taken by the components when they are destroyed.

We want to set up a timer whenever the `Clock` is rendered to the DOM for the first time. This is called “mounting” in React.

## Handling Events

### Passing Arguments to Event Handlers

Inside a loop, it is common to want to pass an extra parameter to an event handler. For example, if id is the row ID, either of the following would work:

    <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
    <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>

The above two lines are equivalent, and use arrow functions and Function.prototype.bind respectively.

## Utility-First Fundamentals

This approach allows us to implement a completely custom component design without writing a single line of custom CSS.

Now I know what you’re thinking, “this is an atrocity, what a horrible mess!” and you’re right, it’s kind of ugly. In fact it’s just about impossible to think this is a good idea the first time you see it.

Why not just use inline styles?

A common reaction to this approach is wondering, “isn’t this just inline styles?” and in some ways it is — you’re applying styles directly to elements instead of assigning them a class name and then styling that class.

But using utility classes has a few important advantages over inline styles:

* Designing with constraints. Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.
* Responsive design. You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.
* Hover, focus, and other states. Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with utility classes.

## Create a Next.js App

![next](https://nx.dev/documentation/latest/shared/nextjs-logo.png)

To build a complete web application with React from scratch, there are many important details you need to consider:

* Code has to be bundled using a bundler like webpack and transformed using a compiler like Babel.
* You need to do production optimizations such as code splitting.
* You might want to statically pre-render some pages for performance and SEO. You might also want to use server-side rendering or client-side rendering.
* You might have to write some server-side code to connect your React app to your data store.

### Next.js: The React Framework

Enter Next.js, the React Framework. Next.js provides a solution to all of the above problems. But more importantly, it puts you and your team in the pit of success when building React applications.

