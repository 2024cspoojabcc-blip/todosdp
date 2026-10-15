
# MY_TO_DO

A simple and responsive to-do list application built with HTML, CSS, JavaScript, FastAPI, and SQLite.

## Features

- Add new tasks
- Mark tasks as completed
- Edit task titles
- Delete tasks
- Filter tasks by status
- Track task completion progress
- Save frontend tasks in browser local storage

## Project Structure

```text
MY_TO_DO/
├── app/
│   ├── __init__.py
│   ├── main.py
│   └── database.py
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
├── Dockerfile
├── requirements.txt
└── README.md
```

## Run Locally

1. Install Python 3.12 or a compatible Python version.
2. Open a terminal in the project root directory.
3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Start the application:

   ```bash
   python -m uvicorn app.main:app --reload
   ```

5. Open the application in your browser:

   http://127.0.0.1:8000

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tasks` | Get all tasks |
| POST | `/api/tasks` | Create a task |
| PATCH | `/api/tasks/{task_id}` | Update completion status |
| DELETE | `/api/tasks/{task_id}` | Delete a task |

Interactive API documentation is available at:

http://127.0.0.1:8000/docs

## Database

The application uses SQLite. The default database file is `todos.db`.

You can configure its location using the `TODO_DB_PATH` environment variable.

## Docker

Build the image:

```bash
docker build -t my-to-do .
```

Run the container:

```bash
docker run --rm -p 8000:8000 -v todo-data:/data my-to-do
```

Open http://127.0.0.1:8000 in your browser.
