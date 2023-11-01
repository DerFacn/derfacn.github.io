# API Documentation

Welcome to the API documentation for our service. Here you will find information on available endpoints, their functionality, and the expected responses.

## Authentication

### POST /auth/signup

**Description:** Allows users to sign up for our service.

**Parameters:**
- `username` (string, required): The username of the user.
- `password` (string, required): The user's password.

**Response:** Upon successful registration, the API will return a JSON response with the following format:
```
{"message": "User created!"}
```

### POST /auth/login

**Description:** Allows users to log in to their account.

**Parameters:**
- `username` (string, required): The username of the user.
- `password` (string, required): The user's password.

**Response:** Upon successful login, the API will set a `Set-Cookie` header and return a status code of 200.

### GET /auth/refresh

**Description:** Accessible only with a valid refresh token. Refreshes the access token.

**Response:** The API will return an updated access token in the user's cookies.

### DELETE /auth/logout

**Description:** Accessible only with a valid refresh token. Clears the user's tokens from cookies.

**Response:** The API will return clean cookies.

## Tasks

### GET /tasks/get-all

**Description:** Retrieves a list of all task IDs.

**Response:** The API will return a list of task IDs in the following format:
```
["...", "...", "..."]
```

### POST /tasks/by-id

**Description:** Retrieves task details by IDs.

**Parameters:**
- `tasks_id` (array of strings, required): An array of task IDs.

**Response:** The API will return a JSON object with task details in the following format:
```
[{"id": ..., "title": ..., "body": ..., "created_at": ...}, {"id": ..., "title": ..., "body": ..., "created_at": ...}]
```

### POST /tasks/create

**Description:** Creates a new task.

**Parameters:**
- `title` (string, required): The title of the task.
- `body` (string, required): The body of the task.

**Response:** Upon successful task creation, the API will return a JSON response with the following format:
```
{"message": "Created!"}
```

### POST /tasks/delete

**Description:** Deletes a task by its ID.

**Parameters:**
- `task_id` (integer, required): The ID of the task to delete.

**Response:** The API will return a JSON response with the following format upon successful deletion:
```
{"message": "Deleted!"}
```

## User Information

### GET /user/info

**Description:** Retrieves user information.

**Response:** The API will return user information in the following format:
```
{"uuid": ..., "username": ..., "created_at": ...}
```
