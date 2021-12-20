# React 2

## Conditional Rendering

### Element Variables

You can use variables to store elements. This can help you conditionally render a part of the component while the rest of the output doesn’t change.

Consider these two new components representing Logout and Login buttons:

    function LoginButton(props) {
    return (
        <button onClick={props.onClick}>
        Login
        </button>
    );
    }

    function LogoutButton(props) {
    return (
        <button onClick={props.onClick}>
        Logout
        </button>
    );
    }

It will render either `<LoginButton />` or `<LogoutButton />` depending on its current state. It will also render a `<Greeting />` from the previous example:

    class LoginControl extends React.Component {
    constructor(props) {
        super(props);
        this.handleLoginClick = this.handleLoginClick.bind(this);
        this.handleLogoutClick = this.handleLogoutClick.bind(this);
        this.state = {isLoggedIn: false};
    }

    handleLoginClick() {
        this.setState({isLoggedIn: true});
    }

    handleLogoutClick() {
        this.setState({isLoggedIn: false});
    }

    render() {
        const isLoggedIn = this.state.isLoggedIn;
        let button;
        if (isLoggedIn) {      button = <LogoutButton onClick={this.handleLogoutClick} />;    } else {      button = <LoginButton onClick={this.handleLoginClick} />;    }
        return (
        <div>
            <Greeting isLoggedIn={isLoggedIn} />        {button}      </div>
        );
    }
    }

    ReactDOM.render(
    <LoginControl />,
    document.getElementById('root')
    );

### Inline If with Logical && Operator

You may embed expressions in JSX by wrapping them in curly braces. This includes the JavaScript logical && operator. It can be handy for conditionally including an element:

    function Mailbox(props) {
    const unreadMessages = props.unreadMessages;
    return (
        <div>
        <h1>Hello!</h1>
        {unreadMessages.length > 0 &&        <h2>          You have {unreadMessages.length} unread messages.        </h2>      }    </div>
    );
    }

    const messages = ['React', 'Re: React', 'Re:Re: React'];
    ReactDOM.render(
    <Mailbox unreadMessages={messages} />,
    document.getElementById('root')
    );

### Preventing Component from Rendering

In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output.

In the example below, the `<WarningBanner />` is rendered depending on the value of the prop called warn. If the value of the prop is false, then the component does not render:

    function WarningBanner(props) {
    if (!props.warn) {    return null;  }
    return (
        <div className="warning">
        Warning!
        </div>
    );
    }

    class Page extends React.Component {
    constructor(props) {
        super(props);
        this.state = {showWarning: true};
        this.handleToggleClick = this.handleToggleClick.bind(this);
    }

    handleToggleClick() {
        this.setState(state => ({
        showWarning: !state.showWarning
        }));
    }

    render() {
        return (
        <div>
            <WarningBanner warn={this.state.showWarning} />        <button onClick={this.handleToggleClick}>
            {this.state.showWarning ? 'Hide' : 'Show'}
            </button>
        </div>
        );
    }
    }

    ReactDOM.render(
    <Page />,
    document.getElementById('root')
    );

## Lists and Keys

### Rendering Multiple Components

You can build collections of elements and include them in JSX using curly braces {}.

Below, we loop through the numbers array using the JavaScript map() function. We return a `<li>` element for each item. Finally, we assign the resulting array of elements to listItems:

    const numbers = [1, 2, 3, 4, 5];
    const listItems = numbers.map((number) =>  <li>{number}</li>);

We include the entire listItems array inside a `<ul>` element, and render it to the DOM:

    ReactDOM.render(
    <ul>{listItems}</ul>,  document.getElementById('root')
    );

### Keys

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

    const numbers = [1, 2, 3, 4, 5];
    const listItems = numbers.map((number) =>
    <li key={number.toString()}>    {number}
    </li>
    );

The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:

    const todoItems = todos.map((todo) =>
    <li key={todo.id}>    {todo.text}
    </li>
    );

### Keys Must Only Be Unique Among Siblings

Keys used within arrays should be unique among their siblings. However, they don’t need to be globally unique. We can use the same keys when we produce two different arrays:

    function Blog(props) {
    const sidebar = (    <ul>
        {props.posts.map((post) =>
            <li key={post.id}>          {post.title}
            </li>
        )}
        </ul>
    );
    const content = props.posts.map((post) =>    <div key={post.id}>      <h3>{post.title}</h3>
        <p>{post.content}</p>
        </div>
    );
    return (
        <div>
        {sidebar}      <hr />
        {content}    </div>
    );
    }

    const posts = [
    {id: 1, title: 'Hello World', content: 'Welcome to learning React!'},
    {id: 2, title: 'Installation', content: 'You can install React from npm.'}
    ];
    ReactDOM.render(
    <Blog posts={posts} />,
    document.getElementById('root')
    );

### Embedding map() in JSX

In the examples above we declared a separate listItems variable and included it in JSX:

    function NumberList(props) {
    const numbers = props.numbers;
    const listItems = numbers.map((number) =>    <ListItem key={number.toString()}              value={number} />  );  return (
        <ul>
        {listItems}
        </ul>
    );
    }

JSX allows embedding any expression in curly braces so we could inline the map() result:

    function NumberList(props) {
    const numbers = props.numbers;
    return (
        <ul>
        {numbers.map((number) =>        <ListItem key={number.toString()}                  value={number} />      )}    </ul>
    );
    }

## Forms

### Controlled Components

In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().

For example, if we want to make the previous example log the name when it is submitted, we can write the form as a controlled component:

    class NameForm extends React.Component {
    constructor(props) {
        super(props);
        this.state = {value: ''};
        this.handleChange = this.handleChange.bind(this);
        this.handleSubmit = this.handleSubmit.bind(this);
    }

    handleChange(event) {    this.setState({value: event.target.value});  }
    handleSubmit(event) {
        alert('A name was submitted: ' + this.state.value);
        event.preventDefault();
    }

    render() {
        return (
        <form onSubmit={this.handleSubmit}>        <label>
            Name:
            <input type="text" value={this.state.value} onChange={this.handleChange} />        </label>
            <input type="submit" value="Submit" />
        </form>
        );
    }

### The file input Tag

In HTML, an <input type="file"> lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript via the File API.

    <input type="file" />

### ontrolled Input Null Value

Specifying the value prop on a controlled component prevents the user from changing the input unless you desire so. If you’ve specified a value but the input is still editable, you may have accidentally set value to undefined or null.

    The following code demonstrates this. (The input is locked at first but becomes editable after a short delay.)

    ReactDOM.render(<input value="hi" />, mountNode);

    setTimeout(function() {
    ReactDOM.render(<input value={null} />, mountNode);
    }, 1000);

## Lifting State Up

### Writing Conversion Functions

First, we will write two functions to convert from Celsius to Fahrenheit and back:

    function toCelsius(fahrenheit) {
    return (fahrenheit - 32) * 5 / 9;
    }

    function toFahrenheit(celsius) {
    return (celsius * 9 / 5) + 32;
    }

These two functions convert numbers. We will write another function that takes a string temperature and a converter function as arguments and returns a string. We will use it to calculate the value of one input based on the other input.

It returns an empty string on an invalid temperature, and it keeps the output rounded to the third decimal place:

    function tryConvert(temperature, convert) {
    const input = parseFloat(temperature);
    if (Number.isNaN(input)) {
        return '';
    }
    const output = convert(input);
    const rounded = Math.round(output * 1000) / 1000;
    return rounded.toString();
    }

## Composition vs Inheritance

### Containment

Some components don’t know their children ahead of time. This is especially common for components like Sidebar or Dialog that represent generic “boxes”.

We recommend that such components use the special children prop to pass children elements directly into their output:

    function FancyBorder(props) {
    return (
        <div className={'FancyBorder FancyBorder-' + props.color}>
        {props.children}    </div>
    );
    }

This lets other components pass arbitrary children to them by nesting the JSX:

    function WelcomeDialog() {
    return (
        <FancyBorder color="blue">
        <h1 className="Dialog-title">        Welcome      </h1>      <p className="Dialog-message">        Thank you for visiting our spacecraft!      </p>    </FancyBorder>
    );
    }

### Specialization

Sometimes we think about components as being “special cases” of other components. For example, we might say that a WelcomeDialog is a special case of Dialog.

In React, this is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props:

    function Dialog(props) {
    return (
        <FancyBorder color="blue">
        <h1 className="Dialog-title">
            {props.title}      </h1>
        <p className="Dialog-message">
            {props.message}      </p>
        </FancyBorder>
    );
    }

    function WelcomeDialog() {
    return (
        <Dialog      title="Welcome"      message="Thank you for visiting our spacecraft!" />  );
    }

## Thinking in React

Start With A Mock

Imagine that we already have a JSON API and a mock from our designer. The mock looks like this:

![mock](https://reactjs.org/static/1071fbcc9eed01fddc115b41e193ec11/65ed1/thinking-in-react-mock.png)

Our JSON API returns some data that looks like this:

    [
    {category: "Sporting Goods", price: "$49.99", stocked: true, name: "Football"},
    {category: "Sporting Goods", price: "$9.99", stocked: true, name: "Baseball"},
    {category: "Sporting Goods", price: "$29.99", stocked: false, name: "Basketball"},
    {category: "Electronics", price: "$99.99", stocked: true, name: "iPod Touch"},
    {category: "Electronics", price: "$399.99", stocked: false, name: "iPhone 5"},
    {category: "Electronics", price: "$199.99", stocked: true, name: "Nexus 7"}
    ];

### Step 1: Break The UI Into A Component Hierarchy

The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components!

![Components](https://reactjs.org/static/9381f09e609723a8bb6e4ba1a7713b46/90cbd/thinking-in-react-components.png)

### Step 2: Build A Static Version in React 

Now that you have your component hierarchy, it’s time to implement your app. The easiest way is to build a version that takes your data model and renders the UI but has no interactivity. It’s best to decouple these processes because building a static version requires a lot of typing and no thinking, and adding interactivity requires a lot of thinking and not a lot of typing. We’ll see why.

### Step 3: Identify The Minimal (but complete) Representation Of UI State

To make your UI interactive, you need to be able to trigger changes to your underlying data model. React achieves this with state.

To build your app correctly, you first need to think of the minimal set of mutable state that your app needs. The key here is DRY: Don’t Repeat Yourself. Figure out the absolute minimal representation of the state your application needs and compute everything else you need on-demand. For example, if you’re building a TODO list, keep an array of the TODO items around; don’t keep a separate state variable for the count. Instead, when you want to render the TODO count, take the length of the TODO items array.

### Step 4: Identify Where Your State Should Live 

Remember: React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. This is often the most challenging part for newcomers to understand, so follow these steps to figure it out:

For each piece of state in your application:

* Identify every component that renders something based on that state.
* Find a common owner component (a single component above all the components that need the state in the hierarchy).
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

### Step 5: Add Inverse Data Flow 

So far, we’ve built an app that renders correctly as a function of props and state flowing down the hierarchy. Now it’s time to support data flowing the other way: the form components deep in the hierarchy need to update the state in FilterableProductTable.

React makes this data flow explicit to help you understand how your program works, but it does require a little more typing than traditional two-way data binding.
