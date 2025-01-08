# Exam Title: Basic Task Management System

## Project Description

This project involves creating a basic backend system for managing tasks. The system will allow users to:

- Create, Read, Update, and Delete tasks.
- Filter tasks by their status (To-Do, In Progress, Done).

---

## Setup Instructions
if you encounter an error
```bash
Set-ExecutionPolicy RemoteSigned -Scope Process
```

1. Initialize the Project
   - Open the terminal and create a new directory for the project.

```bash
npm init -y
```

- This command will generate a package.json file with the default configuration.

2. Install Required Dependencies
   - Install the necessary dependencies for the project:

```bash
npm i express nodemon dotenv
```

3. Create the Project Structure
   - Below is the suggested folder structure for the project:

```bash
/task-management
│
├── /controllers           # Logic for handling API requests (CRUD operations)
│   └── taskController.js  # Handles task-related endpoints
├── /models                # Task data model (mock data)
│   └── taskModel.js       # Stores task data in memory
├── /routes                # API routes definition
│   └── taskRoutes.js      # Task CRUD routes
├── .env                   # Environment variables (for settings like port)
├── package.json           # Project metadata and dependencies
├── server.js              # Main server file
└── README.md              # Project documentation and instructions
```

4. Create the `server.js` File
   - This file will serve as the entry point to your application.
   - Set up a simple Express server that listens to requests.
5. Set Up Routes
   - Create routes for managing tasks. The routes will handle creating, reading, updating, and deleting tasks.
6. Set Up Controllers
   - In the `controllers` folder, you will create controller functions to handle the business logic for each API route (task creation, task updates, etc.).
7. Set Up Model

   - In the `models` folder, create a mock model that stores tasks in an in-memory array.

8. Set Up Nodemon for Development
   - Modify the `package.json` to use `nodemon` for running the server in development mode.
     In the `scripts` section of `package.json,` add:

```json
"scripts": {
  "dev": "nodemon server.js"
}
```

- This allows you to start the server with `npm run dev` for automatic restarts during development.

9. Run the Application
   - To start the development server, run the following command:

```bash
npm run dev
```
```bash
http://localhost:3000
```

- The server should now be running on the port specified in your `.env` file (default to 3000 if not specified).

10. Testing the Endpoints

    - Use Postman or any other API testing tool to test the following endpoints:
      - POST `/tasks`: Create a new task.
      - GET `/tasks`: Retrieve all tasks.
      - GET `/task/:status`: Retrieve all tasks or filter by status.
      - PUT `/tasks/:id`: Update an existing task.
      - DELETE `/tasks/:id`: Delete a task by ID.

---

11. Model (models/taskModel.js)

```javascript
const tasks = [
  {
    id: 1,
    title: "Fix login bug",
    description: "Resolve the login issue on the homepage.",
    status: "To-Do",
    due_date: "2025-01-10",
  },
  {
    id: 2,
    title: "Implement feature X",
    description: "Develop feature X for the user dashboard.",
    status: "In Progress",
    due_date: "2025-01-15",
  },
  {
    id: 3,
    title: "Update API documentation",
    description: "Revise the API docs to include new endpoints.",
    status: "Done",
    due_date: "2024-12-20",
  },
  {
    id: 4,
    title: "Fix UI bugs",
    description: "Fix the layout issues on the profile page.",
    status: "To-Do",
    due_date: "2025-01-05",
  },
];

// Export the tasks array for use in the controller
module.exports = { tasks };
```
