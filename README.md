![React Cover Image](image/React.png) 
# React 19 Exercises
These exercises are designed to help you practice with React 19, incorporating its new features and best practices.

# Beginner Level
These exercises focus on fundamental React concepts, with a touch of React 19's new capabilities like the ``use`` hook for promises and server components (conceptual).

## Exercise 1: Simple Counter with ``use`` for Async Data
**Objective** : Create a basic counter-application that also displays a "message of the day" fetched asynchronously using the ``use`` hook.
* **Concepts to practice** : 
    * Functional Components
    * ``useState`` hook
    * Event Handling
    * Basic JSX
    * **React 19 Feature** : ``use`` hook for handling promises directly in components.

* **Instructions** : 
  1. Create a component ``Counter``.
  2. Inside ``Counter``, maintain a ``count`` state. 
  3. Add two buttons: "Increment" and "Decrement" that modify the ``count``. 
  4. Create an asynchronous function ``fetchMessageOfTheDay()`` that returns a promise resolving to a string (e.g., "Hello React 19!"). Simulate a delay with ``setTimeout``. 
  5. In your ``Counter`` component, use the ``use`` hook to consume the promise from ``fetchMessageOfTheDay()`` and display the message. 
  6. Handle loading states (e.g., "Loading message...") and potential errors.

Example ```fetchMessageOfTheDay```:
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
  * ``useState`` for lists 
  * Rendering lists (``map``)
  * Form handling (controlled components)
  * **React 19 Feature (Conceptual)** : Form Actions for data mutations.

* **Instructions** :
  1. Create a ``TodoList`` component. 
  2. Maintain a list of to-do items (strings) in state. 
  3. Display the to-do items. 
  4. Add an input field and a button to add new to-do items. 
  5. **Conceptual** : Imagine your form submission triggers a "form action" that adds the to-do item. For this client-side exercise, simply add it to the local state. Discuss how a real React 19 app might use a server action here. 
  6. Add a button next to each to-do item to delete it.

# Intermediate Level
These exercises delve deeper into React 19 features like Server Components, Asset Loading, and more complex state management.

## Exercise 3: Blog Post Viewer with Server Components (Conceptual) and Asset Loading
**Objective** : Create a blog post viewer. Imagine the main blog post content is a Server Component, and client-side interactions (like comments) are handled by Client Components. Also, explore asset loading.

* **Concepts to practice** :
  * Component composition (mixing Client and Server Components conceptually)
  * Conditional rendering 
  * Props drilling vs. Context API 
  * **React 19 Features** : Server Components (conceptual), Asset Loading (e.g., preloading images/fonts).

* **Instructions** :

1. **Conceptual Server Component** : Create a ``BlogPostContent`` component. Imagine this component is rendered on the server and receives ``postData`` as props. It simply displays the title, author, and content. 
2. **Client Component** : Create a ``CommentsSection`` component. This component will handle adding and displaying comments. It should use ``useState`` for comments and an input field for new comments. 
3. Main App Component: In your ``App`` component:
   * Render ``BlogPostContent`` (passing mock ``postData``). 
   * Render ``CommentsSection``. 
   * **Asset Loading** : Think about how you would use React 19's asset loading capabilities. For instance, if your blog post had a hero image, you could conceptually use ``preload`` or ``preinit`` directives. Simulate this by adding a ``<link rel="preload" href="image.jpg" as="image">`` in your HTML (or discuss how React 19 would manage this).

## Exercise 4: Data Table with ``useOptimistic`` for Instant UI Updates
**Objective** : Build a data table where updating a row (e.g., marking an item as "completed") provides an instant UI update using ``useOptimistic``, even before the actual server response.

**Concepts to practice** :
  * Managing arrays of objects in state 
  * Mapping data to table rows 
  * Asynchronous operations (simulated API calls)
  * **React 19 Feature** : ``useOptimistic`` hook.

**Instructions** :
1. Create a ``DataTable`` component. 
2. Initialize some mock data (e.g., an array of objects with ``id``, ``name``, ``status``). 
3. Render this data in a table. 
4. Add a button or checkbox next to each row to toggle its ``status`` (e.g., "pending" to "completed"). 
5. When the button is clicked:
   * Immediately update the UI to reflect the new status using ``useOptimistic``. 
   * Simulate an asynchronous API call (e.g., ``setTimeout`` for 2 seconds) that would confirm the update. 
   * If the simulated API call fails, revert the optimistic update.

``useOptimistic`` **Hint** :
```
import { useOptimistic } from 'react';

function MyComponent() {
  const [optimisticValue, setOptimisticValue] = useOptimistic(
    initialValue,
    (state, newValue) => newState
  );

  // ...
  // Call setOptimisticValue to update the UI optimistically
  // Then perform the actual async operation
}

```

# Professional Level
These exercises challenge you with more complex scenarios, integrating multiple React 19 features and considering performance and architecture.

## Exercise 5: E-commerce Product Page with Server Components, ``use``, and Asset Graph
**Objective** : Design a product page for an e-commerce site. The core product details come from a Server Component. Related products are fetched using ``use``. Consider how React 19's Asset Graph optimizations would apply.

* **Concepts to practice** :
  * Advanced component architecture (deep understanding of Client/Server Component boundaries)
  * Efficient data fetching with ``use``
  * Error boundaries for robust UIs 
  * **React 19 Features** : Server Components, ``use`` hook, Asset Graph (conceptual application).

* **Instructions** :
  1. Conceptual Server Component (``ProductDetails``): Imagine this component fetches and displays detailed product information (name, description, price, images). It's designed to be a Server Component. 
  2. Client Component (``AddToCartButton``): A simple button that adds the product to a cart. This must be a Client Component. 
  3. Client Component (``RelatedProducts``): This component fetches a list of related products asynchronously. Use the use hook to fetch this data. Handle loading and error states. 
  4. Main ProductPage Component:
     * Render ``ProductDetails`` (conceptually passed from the server). 
     * Render ``AddToCartButton``. 
     * Render ``RelatedProducts``. 
     * Implement an Error Boundary around ``RelatedProducts`` to gracefully handle fetching failures. 
  5. Asset Graph Discussion: Discuss how React 19's ability to understand the "asset graph" (which assets are needed by which components) would optimize the loading of images, fonts, and scripts for this product page, ensuring only necessary resources are loaded.

## Exercise 6: Real-time Collaborative Document Editor with Form Actions and ``useOptimistic``
**Objective** : Create a simplified collaborative document editor where users can type, and changes are synced. Use Form Actions for saving, and ``useOptimistic`` for immediate local updates.

* **Concepts to practice** :
  * Real-time updates (simulated or with a mock WebSocket)
  * Debouncing input for efficient saving 
  * Complex state management for text content 
  * **React 19 Features** : Form Actions (for saving), ``useOptimistic`` (for local text updates).

* **Instructions** :
1. Create a ``DocumentEditor`` component. 
2. Maintain the document content (a string) in state. 
3. Display a ``textarea`` where users can type. 
4. ``useOptimistic`` **for typing** : As the user types, immediately update the ``textarea`` content using ``useOptimistic``. 
5. **Form Action for saving** : When the user stops typing for a short period (debounce), or explicitly clicks a "Save" button, trigger a "form action" (conceptually). This action should simulate saving the document content to a server.
   * Simulate the server saving with a setTimeout. 
   * On successful save, confirm the optimistic update. 
   * On failure, revert the optimistic update and show an error message.
6. Real-time collaboration (conceptual): Imagine a second user making changes. Discuss how you would integrate a WebSocket or similar mechanism to receive updates from other users and merge them into the local document, potentially requiring careful handling of ``useOptimistic`` states.