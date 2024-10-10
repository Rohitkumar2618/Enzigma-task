

# To-Do List Application (MEAN Stack)

This is a simple To-Do List application built using the **MEAN (MongoDB, Express, Angular, Node.js)** stack. The application allows users to perform CRUD (Create, Read, Update, Delete) operations on tasks, with fields such as assigned users, status, due date, priority, and comments. The backend is powered by Node.js, Express, and MongoDB, while Angular manages the frontend.

## Features

- **Create, Read, Update, Delete (CRUD)** operations for tasks.
- Task model with fields like `AssignedTo`, `Status`, `DueDate`, `Priority`, and `Comments`.
- Server-side validation using Mongoose.
- Modular structure with separate routes, controllers, models, and database configuration.
- Global error handling middleware for catching exceptions.
- **Frontend Integration** with Angular, built using [Angular CLI](https://github.com/angular/angular-cli) version 18.2.7.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14+)
- [MongoDB](https://www.mongodb.com/) (either locally or using a cloud solution like MongoDB Atlas)
- [Angular CLI](https://angular.dev/tools/cli) (v18.2.7+)

## Installation

### Backend Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/todo-app.git
   cd todo-app/backend
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Set up MongoDB**:

   - You can either run MongoDB locally or use MongoDB Atlas.
   - If using MongoDB locally, make sure it’s running on `mongodb://localhost:27017/todo`.

4. **Start the backend server**:

   ```bash
   node server.js
   ```

5. The backend server will be running on `http://localhost:5000`. You can interact with the API using Postman or other API testing tools.

### Frontend Setup

1. **Navigate to the frontend directory**:

   ```bash
   cd ../frontend
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Run the frontend development server**:

   ```bash
   ng serve
   ```

4. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## API Endpoints

- **GET /api/tasks** - Get all tasks
- **POST /api/tasks** - Create a new task
- **PUT /api/tasks/:id** - Update an existing task by ID
- **DELETE /api/tasks/:id** - Delete a task by ID

### Sample Request

**POST /api/tasks**

```json
{
  "assignedTo": "User 1",
  "status": "In Progress",
  "dueDate": "2024-12-10",
  "priority": "Low",
  "comments": "This task is good"
}
```

### Sample Response

```json
{
  "_id": "5f8f8f8f8f8f8f8f8f8f8f8",
  "assignedTo": "User 1",
  "status": "In Progress",
  "dueDate": "2024-12-10T00:00:00.000Z",
  "priority": "Low",
  "comments": "This task is good",
  "createdAt": "2024-10-01T12:34:56.789Z",
  "updatedAt": "2024-10-01T12:34:56.789Z",
  "__v": 0
}
```

## Project Structure Explanation

### Backend

- **`server.js`**: The entry point of the application, handles middleware, routing, and error handling.
- **`config/db.js`**: Configures and connects to the MongoDB database.
- **`models/Task.js`**: Defines the Mongoose schema for the `Task` object.
- **`controllers/taskController.js`**: Contains the logic for handling the CRUD operations for tasks.
- **`routes/taskRoutes.js`**: Defines the API routes and maps them to the corresponding controller functions.
- **`middlewares/errorHandler.js`**: Middleware for handling application-wide errors.

### Frontend

- **Angular CLI**: Use commands like `ng generate` to scaffold components, services, or modules.
- **Development server**: Run `ng serve` to start the frontend at `http://localhost:4200/`.
- **Build**: Run `ng build` to generate the production-ready build in the `dist/` directory.
- **Testing**: Use `ng test` for unit tests (Karma) and `ng e2e` for end-to-end testing.

## Error Handling

All errors are caught and handled gracefully using the global error handler located in `middlewares/errorHandler.js`. The error handler returns a standard error response with a 500 status code and a descriptive message.

## Future Improvements

- **Authentication**: Add user authentication and authorization using JWT.
- **Search and Filter**: Add search and filter capabilities for tasks.
- **Pagination**: Implement pagination for large sets of tasks.
- **Enhanced Frontend**: Refine the Angular frontend for a smoother user experience.

## Contributing

Feel free to fork the repository, make updates, and create pull requests if you want to contribute to this project.

## License

This project is open-source and available under the [MIT License](LICENSE).
