## Documentation

```markdown
# FastAPI ToDo API

This is a basic RESTful API built with FastAPI and SQLite, which allows users to manage a simple "To-Do List" application.
```
```
## Features

- Create, read, update, and delete todo items
- Store todo items in a SQLite database
- Automatic Swagger documentation at `/docs`
```
```
## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yashaskhot/todo_app_fastapi.git
   ```

2. Change to the project directory:

   ```bash
   cd todo_app_fastapi
   ```

3. Create a virtual environment and activate it:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

4. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

5. Run the application:

   ```bash
   uvicorn todo_app.main:app --reload
   ```

   The application will start running on `http://localhost:8000`.

## API Endpoints

The API provides the following endpoints:

- `POST /todos/`: Create a new todo item
- `GET /todos/`: Retrieve a list of all todo items
- `GET /todos/{todo_id}`: Retrieve a specific todo item by its ID
- `PUT /todos/{todo_id}`: Update a specific todo item by its ID
- `DELETE /todos/{todo_id}`: Delete a specific todo item by its ID

You can explore the API documentation at `http://localhost:8000/docs`.

## Database Schema

The application uses a SQLite database to store the todo items. The database schema consists of a single table named `todos` with the following fields:

- `id`: Integer, primary key, auto-incrementing
- `title`: Text, the title of the todo item
- `description`: Text, the description of the todo item
- `completed`: Boolean, indicates whether the todo item is completed or not

## Folder Structure

The project has the following folder structure:

```
todo_app/
├── __init__.py
├── database.py
├── schemas.py
└── main.py
requirements.txt
```

- `todo_app/database.py`: Defines the SQLAlchemy models and database connection.
- `todo_app/schemas.py`: Contains the Pydantic models for request and response validation.
- `todo_app/main.py`: Defines the FastAPI application and the API endpoints.
- `requirements.txt`: Lists the required Python packages.

## Usage with Postman

You can use Postman to interact with the API. Here's a step-by-step guide:

1. Start the application: `uvicorn todo_app.main:app --reload`
2. Open Postman and create requests for the various API endpoints.


1. **Create a new Todo:**
   - Open Postman and create a new request.
   - Set the request type to `POST` and the URL to `http://localhost:8000/todos/`.
   - In the `Body` tab, select `raw` and `JSON` as the format.
   - Add the following JSON data:
     ```json
     {
       "title": "Learn FastAPI",
       "description": "Complete the FastAPI tutorial",
       "completed": false
     }
     ```
   - Click the `Send` button to create a new todo item.

2. **Get all Todos:**
   - Create a new request and set the request type to `GET`.
   - Set the URL to `http://localhost:8000/todos/`.
   - Click the `Send` button to retrieve all the todo items.

3. **Get a specific Todo:**
   - Create a new request and set the request type to `GET`.
   - Set the URL to `http://localhost:8000/todos/1` (replace `1` with the ID of the todo item you want to retrieve).
   - Click the `Send` button to get the details of the specific todo item.

4. **Update a Todo:**
   - Create a new request and set the request type to `PUT`.
   - Set the URL to `http://localhost:8000/todos/1` (replace `1` with the ID of the todo item you want to update).
   - In the `Body` tab, select `raw` and `JSON` as the format.
   - Update the JSON data as needed, for example:
     ```json
     {
       "title": "Learn FastAPI and SQLAlchemy",
       "description": "Complete the tutorial and build a project",
       "completed": true
     }
     ```
   - Click the `Send` button to update the todo item.

5. **Delete a Todo:**
   - Create a new request and set the request type to `DELETE`.
   - Set the URL to `http://localhost:8000/todos/1` (replace `1` with the ID of the todo item you want to delete).
   - Click the `Send` button to delete the todo item.

