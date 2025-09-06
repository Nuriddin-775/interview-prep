# Here is a comprehensive 4-week roadmap covering the most common topics, questions, and the best resources to study them.

## This plan focuses on what truly gets asked in modern frontend interviews for roles involving React.

🎯 The 4-Week JavaScript Interview Prep Roadmap
Week 1: The Core Fundamentals (Non-Negotiable)
These are the absolute basics. You will be asked about these concepts in almost every interview. Mastering them shows you have a solid foundation.

## 📚 Topics & Concepts:

- Execution Context, Hoisting, & Scope: How JavaScript reads your code. The difference between the global scope, function scope, and block scope.

- var, let, const: The differences in scoping, hoisting, and re-assignability.

- Closures: What a closure is, why it happens, and common use cases (like data privacy/encapsulation).

- Data Types: The difference between Primitive Types (String, Number, Boolean, null, undefined, Symbol, BigInt) and Reference Types (Objects, Arrays, Functions). How they are stored and passed around (pass-by-value vs. pass-by-reference).

- Functions: Function declarations vs. expressions, arrow functions, and the differences between them (especially regarding the this keyword and arguments object).

## 🗣️ Common Interview Questions:

- "What is the difference between var, let, and const?"

- "Can you explain hoisting with an example?"

- "What is a closure? Give me a practical example of why you would use one."

- "What is the difference between == and ===?"

- "What is the output of this code...?" (This will usually involve a tricky scope or closure scenario).

## 🎓 Top Resources:

- Video Series: Namaste JavaScript by Akshay Saini (YouTube). His playlist covers Execution Context, Hoisting, Closures, and more. It's considered one of the best free resources for understanding these core concepts deeply.

- Website/Reading: JavaScript.info (The "JavaScript Fundamentals" and "Code Quality" sections).

- MDN Web Docs: The ultimate reference for any specific function or concept.

## Week 2: Asynchronous JavaScript (The Heart of Modern JS)

This is the most critical topic for any role involving APIs and data fetching. Interviewers will press hard on this.

## 📚 Topics & Concepts:

- The Event Loop: Understand the roles of the Call Stack, Callback Queue (or Task Queue), and Microtask Queue.

- Callbacks: The original async method. Understand what "Callback Hell" is.

- Promises: The modern solution. Know the states (pending, fulfilled, rejected) and how to use .then(), .catch(), and .finally(). Understand methods like Promise.all() and Promise.race().

- async/await: Syntactic sugar over Promises. Know how it works and how to handle errors with try...catch.

## 🗣️ Common Interview Questions:

- "Can you explain the Event Loop in simple terms?"

- "What is a Promise? How is it different from a callback?"

- "What is the difference between Promise.all and Promise.race?"

- "What are the benefits of using async/await over raw Promises?"

- "What will be the order of logs in this code...?" (Usually involves a mix of setTimeout, Promises, and synchronous code to test your Event Loop knowledge).

## 🎓 Top Resources:

- Must-Watch Video: "What the heck is the event loop anyway?" by Philip Roberts (YouTube). This is the single best explanation available.

- Interactive Tool: Loupe by LatentFlip - A visualizer that lets you see the Call Stack and Event Loop in action.

- MDN Web Docs: Their guides on Promises and async/await are excellent.

## Week 3: The "How It Works" Topics

These concepts separate a good developer from a great one. They show you understand JavaScript's object-oriented and functional aspects.

## 📚 Topics & Concepts:

- The this Keyword: Understand the 4 rules of this binding: Global, Implicit, Explicit (.call(), .apply(), .bind()), and new binding. Know how arrow functions change this behavior.

- Prototypes & Prototypal Inheritance: The foundation of objects in JavaScript. Understand how objects inherit properties and methods from other objects.

- The class Keyword: Know that it's "syntactic sugar" over prototypal inheritance.

- Higher-Order Functions: Master the core array methods: .map(), .filter(), and .reduce().

## 🗣️ Common Interview Questions:

- "Explain how the this keyword works. How is its value determined?"

- "What is prototypal inheritance and how does it work?"

- "What is the difference between map and forEach?"

- "Can you implement your own .bind() function?" (A more advanced but common question).

- "What is the main use case for .reduce()?"

## 🎓 Top Resources:

- Video Series: Once again, Namaste JavaScript by Akshay Saini has phenomenal deep dives on these topics.

- Book (Free Online): "You Don't Know JS" by Kyle Simpson. The "Scope & Closures" and "this & Object Prototypes" books are considered essential reading for a deep understanding.

## Week 4: Practical Application & Data Structures

This week is about applying your knowledge to practical browser-based scenarios and common coding challenges.

## 📚 Topics & Concepts:

- DOM Manipulation & Events: Event delegation, bubbling vs. capturing.

- Browser Storage: Differences between localStorage, sessionStorage, and Cookies.

- ES6+ Features: Destructuring, Spread/Rest operators (...), Modules (import/export).

- Basic Data Structures: How to effectively use Objects and Arrays. When to use a Map or a Set.

- Coding Challenges: Common problems like "reverse a string," "find duplicates in an array," "debounce/throttle a function."

## 🗣️ Common Interview Questions:

- "What is event delegation and why is it useful?"

- "When would you use localStorage versus a cookie?"

- "How would you remove duplicate values from an array?" (Tip: Using Set is a great answer).

- "Explain the difference between the spread (...) and rest (...) operators."

- Live Coding: You will almost certainly be asked to solve 1-2 simple data structure or logic problems.

## 🎓 Top Resources:

- Practice Platform: NeetCode.io (select JavaScript). It organizes LeetCode problems by pattern and has excellent video explanations. Start with the "Arrays & Hashing" and "Two Pointers" sections.

- GitHub Repo: Frontend Interview Handbook - Has a huge collection of questions, answers, and resources for frontend roles.

- JS Challengers: A great site with small, interactive challenges to test your knowledge.
