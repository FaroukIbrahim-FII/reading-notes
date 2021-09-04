# NODE.JS

1. What Is Node.js?

    This is what the project’s home page has to say:

    Node.js® is a JavaScript runtime built on Chrome’s V8 JavaScript engine.

    And this is what Stack Overflow has to offer:

    Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.

    Node Is Built on Google Chrome’s V8 JavaScript Engine

    The V8 engine is the open-source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers, including Brave, Opera, and Vivaldi. It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.

2. Node.js is a JavaScript runtime that uses Google Chrome's V8 eninge.

3. when we say that Node is built on the V8 engine, we don’t mean that Node programs are executed in a browser. They aren’t. Rather, the creator of Node (Ryan Dahl) took the V8 engine and enhanced it with various features, such as a file system API, an HTTP library, and a number of operating system–related utility methods.

    This means that Node.js is a program we can use to execute JavaScript on our computers. In other words, it’s a JavaScript runtime.

4. npm, a package manager that comes bundled with Node. In addition to being the package manager for JavaScript, npm is also the world’s largest software registry. There are over 1,000,000 packages of JavaScript code available to download, with billions of downloads per week.

5. You can check that Node is installed on your system by opening a terminal and typing node -v. I have version v14.17.1

6. To check which version you have installed on your system, type npm -v.
For me I have version 6.14.13

7. Open your terminal and type the following:

    npm install -g jshint

    This will install the jshint package globally on your system.

8. Now that we know what Node and npm are and how to install them, we can turn our attention to the first of their common uses: installing (via npm) and running (via Node) various build tools — designed to automate the process of developing a modern JavaScript application.

    These build tools come in all shapes and sizes, and you won’t get far in a modern JavaScript landscape without bumping into them. They can be used for anything from bundling your JavaScript files and dependencies into static assets, to running tests, or automatic code linting and style checking.

![node](https://program-ace.com/wp-content/uploads/advantages-node-js-for-backend-1.jpg)

## 6 Reasons for Pair Programming

1. Greater efficiency

    It is a common misconception that pair programming takes a lot longer and is less efficient. In reality, when two people focus on the same code base, it is easier to catch mistakes in the making. Research indicates that pair programing takes slightly longer, but produces higher-quality code that doesn’t require later effort in troubleshooting and debugging (let alone exposing users to a broken product).

2. Engaged collaboration

    When two programmers focus on the same code, the experience is more engaging and both programmers are more focused than if they were working alone. It is harder to procrastinate or get off track when someone else is relying on you to complete the work. Popping open your Facebook timeline is just that less enticing when someone else is looking at your screen.

3. Learning from fellow students

    Everyone has a different approach to problem solving; working with a teammate can expose developers to techniques they otherwise would not have thought of. If one developer has a unique approach to a specific problem, pair programming exposes the other developer to a new solution.

4. Social skills

    Pair programming is great for improving social skills. When working with someone who has a different coding style, communication is key. This can become more difficult when two programmers have different personalities.

5. Job interview readiness

    A common step in many interview processes involves pair programming between a current employee and an applicant, either in person or through a shared screen. They will carry out exercises together, such as code challenges, building a project or feature, or debugging an existing code base. By doing so, companies can get a better feel for how an applicant will fit into the team and their collaboration style.

6. Work environment readiness

    Many companies that utilize pair programing expect to train fresh hires from CS-degree programs on how they operate to actually deliver a product. Code Fellows graduates who are already familiar with how pairing works can hit the ground running at a new job, with one less hurdle to overcome.
