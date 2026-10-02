# Task Manager Backend Components

Express routes and JavaScript controllers for a task management application. This repository contains the backend components for listing, creating, completing, and deleting tasks.

## Implemented behavior

- List tasks stored in memory.
- Create tasks with a required title and optional description.
- Mark an existing task as completed.
- Delete tasks and return an empty success response.
- Return validation and not-found responses where implemented.

## Route definitions

These paths are defined in `taskRoutes.js`; their final URL prefix depends on how the router is mounted in an Express application.

| Method | Path | Behavior |
| --- | --- | --- |
| GET | `/tasks` | List all tasks |
| POST | `/tasks` | Create a task |
| PUT | `/tasks/:id` | Mark a task as completed |
| DELETE | `/tasks/:id` | Delete a task |

Example creation body:

```json
{
  "title": "Document the API",
  "description": "Explain the task endpoints"
}
```

## Technologies

JavaScript, Node.js, and Express. The package also declares CORS and Nodemon dependencies.

## Repository structure

- `taskController.js` — task operations, validation, and in-memory storage.
- `taskRoutes.js` — Express route definitions.
- `index.js` — current entry file; prints the Node.js version.
- `package.json` — dependencies and development scripts.

## Current status

This is a collection of backend components, not yet a standalone running API. The package scripts reference `src/index.js`, which is absent, and the router imports a controller from a directory that is not present in this repository. Running the API requires wiring an Express server, enabling JSON body parsing, mounting the router, and aligning those paths.

Tasks are held in process memory and are lost when the server restarts. Authentication, persistent storage, and automated tests are not included.
