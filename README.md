### README: Todo Application

---

## Overview

This project is a simple Todo application built using React. It allows users to add, update, delete, and toggle the completion status of tasks. The application utilizes React's Context API for state management, making it easy to manage and share state across different components.

### Features

1. **Add Todo**: Users can add new tasks to their todo list.
2. **Update Todo**: Users can edit existing tasks.
3. **Delete Todo**: Users can remove tasks from the list.
4. **Toggle Completion**: Users can mark tasks as complete or incomplete.
5. **Persistent State**: Todos are stored in `localStorage`, so the list is preserved even after refreshing the page.

---

### 1. **Adding a Todo**

- **Feature**: Users can add a new todo by typing in the input field and pressing the "Add" button.
- **Logic**: 
  - The `addTodo` function in `App.js` is used to add a new todo to the list. 
  - The function generates a unique ID using `Date.now()` and combines it with the todo text and a `completed` status (set to `false` by default). 
  - The new todo is then added to the beginning of the existing `todos` array using the `setTodos` function.

### 2. **Updating a Todo**

- **Feature**: Users can edit the text of an existing todo.
- **Logic**: 
  - In `TodoItem.js`, when the edit button (✏️) is clicked, the `isTodoEditable` state is toggled to allow editing the text field.
  - Once the user makes changes and clicks the save button (📁), the `editTodo` function is called, which updates the specific todo item in the `todos` array by matching the `id`.
  - The `updateTodo` function in `App.js` is responsible for replacing the old todo with the updated one.

### 3. **Deleting a Todo**

- **Feature**: Users can delete a todo from the list.
- **Logic**: 
  - The `deleteTodo` function in `App.js` filters out the todo with the matching `id` from the `todos` array.
  - This function is triggered by the delete button (❌) in the `TodoItem.js` component.

### 4. **Toggling Todo Completion**

- **Feature**: Users can mark a todo as completed or uncompleted.
- **Logic**: 
  - The `toggleComplete` function in `App.js` toggles the `completed` status of a todo item. 
  - When a checkbox is clicked, the `toggleComplete` function is triggered, updating the `completed` property of the corresponding todo item.
  - The todo item's appearance (e.g., background color, text style) changes based on its completion status.

### 5. **Persistent State with localStorage**

- **Feature**: The application remembers the todo list even after a page refresh.
- **Logic**: 
  - On initial load (`useEffect` with an empty dependency array), the application checks `localStorage` for saved todos and sets them in the state if found.
  - Every time the `todos` array changes, a `useEffect` hook updates the `localStorage` with the new state. This ensures that todos persist across page reloads.

---

## Getting Started

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/todo-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd todo-app
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Run the application:
   ```bash
   npm start
   ```

### Usage

1. Type a task in the input field and click "Add" to create a new todo.
2. Click on the checkbox to toggle the completion status of a todo.
3. Edit a todo by clicking the edit button (✏️), modifying the text, and saving (📁).
4. Delete a todo by clicking the delete button (❌).

### Customization

- You can customize the appearance of the application by editing the `App.css` file.
- Modify the logic in `TodoContext.js` to change how todos are managed globally.
