# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh


# Web Development Bootcamp - Day 6

## Topics Covered

### 1. Event Handlers in React
- **onChange Event Handler**:
  - Used to handle changes in form inputs.
  - Example:
    ```jsx
    <input type="text" placeholder='Enter the task here' value={Newtask} onChange={Inputchange} />
    ```

- **onClick Event Handler**:
  - Used to handle button clicks and other clickable elements.
  - Example:
    ```jsx
     <button onClick={Onsubmit}>Add</button>
    ```

### 2. Firestore Database Structure
- **Firestore**:
  - A NoSQL database by Firebase.
  - Documents and Collections are used to store data.
  - Collections contain multiple documents, each identified by a unique ID.

### 3. useEffect Hook
- **useEffect**:
  - A hook that allows you to perform side effects in functional components.
  - Example:
    ```jsx
    import { useEffect } from 'react';

    useEffect(() => {
      // Code to run on component mount
    }, []);
    ```

### 4. Retrieving Documents from Firestore
- **getDocs Module**:
  - Used to retrieve documents from a collection.
  - Example to get documents from the "taskscollection":
    ```javascript
    import { getDocs, collection } from "firebase/firestore";
    import { db } from "./firebase-config"; // Make sure to import your firestore config

    useEffect(() =>{
     const gettasks = async() => {
       const data = await getDocs(taskref)
       const filtereddata = data.docs.map(doc => ({...doc.data(),id:doc.id}))
       setTasks(filtereddata)
     }

     gettasks()
});
    };
    ```

## Summary
Today, we delved into essential React event handlers (`onChange` and `onClick`), explored the structure of the Firestore database, and learned how to use the `useEffect` hook for side effects. We also practiced retrieving documents from a Firestore collection using the `getDocs` module.
