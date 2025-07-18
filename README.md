![React Cover Image](image/React.png) 
# React 19 Exercises
These exercises are designed to help you practice with React 19, incorporating its new features and best practices.

# Beginner Level
These exercises focus on fundamental React concepts, with a touch of React 19's new capabilities like the use hook for promises and server components (conceptual).

## Exercise 1: Simple Counter with use for Async Data
**Objective** : Create a basic counter application that also displays a "message of the day" fetched asynchronously using the use hook.
* **Concepts to practice** : 
    * Functional Components
    * useState hook
    * Event Handling
    * Basic JSX
    * **React 19 Feature** : use hook for handling promises directly in components.

* **Instructions** : 
  1. Create a component Counter.
  2. Inside Counter, maintain a count state. 
  3. Add two buttons: "Increment" and "Decrement" that modify the count. 
  4. Create an asynchronous function fetchMessageOfTheDay() that returns a promise resolving to a string (e.g., "Hello React 19!"). Simulate a delay with setTimeout. 
  5. In your Counter component, use the use hook to consume the promise from fetchMessageOfTheDay() and display the message. 
  6. Handle loading states (e.g., "Loading message...") and potential errors.

Example (fetchMessageOfTheDay):
```
  function fetchMessageOfTheDay() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("Welcome to React 19!");
    }, 1000);
  });
}
```

## Exercise 2: Basic To-Do List with Form Actions (Conceptual)
**Objective** : Build a simple to-do list where adding a new to-do conceptually uses a "form action" (a new React 19 concept for server interactions).
* **Concepts to practice** :
  * useState for lists 
  * Rendering lists (map)
  * Form handling (controlled components)
  * **React 19 Feature (Conceptual)** : Form Actions for data mutations.

* **Instructions** :
  1. Create a TodoList component. 
  2. Maintain a list of to-do items (strings) in state. 
  3. Display the to-do items. 
  4. Add an input field and a button to add new to-do items. 
  5. **Conceptual** : Imagine your form submission triggers a "form action" that adds the to-do item. For this client-side exercise, simply add it to the local state. Discuss how a real React 19 app might use a server action here. 
  6. Add a button next to each to-do item to delete it.

