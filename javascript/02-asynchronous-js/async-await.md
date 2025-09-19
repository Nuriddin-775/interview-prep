# Async & await

async/await is a modern JavaScript feature that provides a cleaner, more readable syntax for working with asynchronous operations, built on top of Promises. It makes asynchronous code look and feel more like synchronous code.

## What is it? The Core Idea 💡

Think of async/await as a way to tell your JavaScript code to pause and wait for something to finish before moving on.

async: When you put the async keyword before a function declaration, you're telling JavaScript two things:

This function will now automatically return a Promise.

You are now allowed to use the await keyword inside this function.

await: The await keyword can only be used inside an async function. It tells the function to pause execution at that line and wait for the Promise to be resolved or rejected. Once the Promise settles, the function resumes, and the await expression returns the resolved value of the Promise.

Analogy: Ordering coffee. ☕

Without async/await (Promises with .then()): You order a coffee (startPromise()), give the barista your name, and then tell them, ".then() when my coffee is ready, call my name (handleResult) and .catch() if you mess up my order, let me know (handleError)". You can go do other things while you wait.

With async/await: You walk up to the counter and say, "await my coffee, please." You just stand there and wait (pause execution). When the coffee is ready, the barista hands it to you (the resolved value), and you continue with your day. It's a simpler, more direct mental model.

## What Problem Does It Solve?

It solves the problem of "Callback Hell" and the sometimes-clunky syntax of chaining multiple .then() blocks. It dramatically improves code readability and maintainability.

Let's fetch some user data and then their posts.

Before: Using Promises (.then)
This code works, but the nested .then() calls can become hard to read, especially with more steps and error handling. This is often called the "Pyramid of Doom."

```javascript
function getUserPostsWithPromises() {
  fetch("https://api.example.com/users/1") // Returns a promise
    .then((response) => {
      if (!response.ok) {
        throw new Error("User not found!");
      }
      return response.json(); // Returns another promise
    })
    .then((user) => {
      console.log("Got user:", user.name);
      return fetch(`https://api.example.com/posts?userId=${user.id}`); // Returns a third promise
    })
    .then((response) => {
      if (!response.ok) {
        throw new Error("Posts not found!");
      }
      return response.json(); // Returns a fourth promise
    })
    .then((posts) => {
      console.log(`Found ${posts.length} posts for the user.`);
    })
    .catch((error) => {
      console.error("An error occurred:", error.message);
    });
}

getUserPostsWithPromises();
```

After: Using async/await (The Solution)
This code does the exact same thing but is written in a sequential, top-to-bottom style that's much easier to follow. Error handling is also cleaner using a standard try...catch block.

```javascript
async function getUserPostsWithAsyncAwait() {
  try {
    // Pause here until the user data is fetched and parsed
    const userResponse = await fetch("https://api.example.com/users/1");
    if (!userResponse.ok) {
      throw new Error("User not found!");
    }
    const user = await userResponse.json();
    console.log("Got user:", user.name);

    // Then, pause here until the posts are fetched and parsed
    const postsResponse = await fetch(
      `https://api.example.com/posts?userId=${user.id}`
    );
    if (!postsResponse.ok) {
      throw new Error("Posts not found!");
    }
    const posts = await postsResponse.json();
    console.log(`Found ${posts.length} posts for the user.`);
  } catch (error) {
    // If any 'await'ed promise rejects, it gets caught here
    console.error("An error occurred:", error.message);
  }
}

getUserPostsWithAsyncAwait();
```

As you can see, the async/await version is far more intuitive and looks like simple, synchronous code.

## Top Interview Questions & Answers

1. What's the relationship between async/await and Promises?
   async/await is syntactic sugar built on top of Promises. It doesn't replace them; it just provides a more convenient way to work with them. An async function always returns a Promise, and the await keyword is designed to "wait" for a Promise to settle.

2. How do you handle errors in an async function?
   You use a standard try...catch block. This is a major advantage because it's a familiar pattern for synchronous error handling. If any Promise that you await gets rejected, the catch block will be executed.

3. Can you use await outside of an async function?
   No. The await keyword is only valid inside functions declared with the async keyword. (Note: There is an exception for top-level await in modern JavaScript modules, but the general rule for functions still holds).

4. What happens if you await a value that isn't a Promise?
   JavaScript is smart about this. If you await a non-Promise value (e.g., await 42), it wraps the value in a resolved Promise and immediately gives you the value back. The code doesn't break.

```javascript
async function test() {
  const num = await 42; // This works fine!
  console.log(num); // Logs 42
}
```

5. How do you run multiple asynchronous operations in parallel with async/await?
   This is a key concept! If you await multiple promises one after another, they will run sequentially, not in parallel.

❌ Bad (Sequential):

```javascript
async function fetchSequentially() {
  console.time("sequential");
  const result1 = await fetch("https://api.example.com/data/1"); // Waits for this to finish...
  const result2 = await fetch("https://api.example.com/data/2"); // ...before starting this one.
  console.timeEnd("sequential"); // Takes the sum of both fetch times.
}
```

To run them in parallel, you should use Promise.all(). This method takes an array of promises and returns a single new promise that resolves when all of the input promises have resolved.

✅ Good (Parallel):

```javascript
async function fetchInParallel() {
  try {
    console.time("parallel");
    const promise1 = fetch("https://api.example.com/data/1");
    const promise2 = fetch("https://api.example.com/data/2");

    // Promise.all waits for both to complete. They run at the same time.
    const results = await Promise.all([promise1, promise2]);
    console.timeEnd("parallel"); // Takes only the time of the SLOWEST fetch.

    console.log("All promises resolved!", results);
  } catch (error) {
    console.error("One of the promises failed:", error);
  }
}
```
