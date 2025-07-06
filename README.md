# 📝 express-todo-server

A lightweight and fast Express.js-based REST API for managing a TODO list.  
Tasks are stored locally in a `task.json` file using Node.js's native `fs` module — no database needed.

Built with ❤️ by [@sanjitxdutta](https://github.com/sanjitxdutta)

---

## 🚀 Features

- ✅ Add new tasks
- 📋 View all tasks with summary (done, not done)
- 🔄 Update task status
- ❌ Delete tasks by name
- 💾 Persistent storage using JSON file

---

## 📦 Tech Stack

- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [fs (File System)](https://nodejs.org/api/fs.html)

---

## 📁 Project Structure
```
express-todo-server/
├── index.js
├── package.json
├── package-lock.json
└── task.json
```

---

## 🔧 Setup Instructions

1. **Clone the repo**
```bash
git clone https://github.com/sanjitxdutta/express-todo-server.git
cd express-todo-server
```
2. **Install dependencies**
```bash
npm install
```
3. **Run the server**
```bash
node index.js
```
Server starts at: http://localhost:3000


---

# 📌 API Endpoints - express-todo-server

This document describes all available API endpoints for the **express-todo-server**, a simple task manager built using Node.js and Express with local JSON file storage.

---

## ✅ GET `/`

**Fetch all tasks with summary**

### 🔁 Sample Response:
```json
{
  "TODOS": [
    {
      "id": 1,
      "task": "gym",
      "status": false
    }
  ],
  "totalTask": 1,
  "done": 0,
  "notDone": 1
}
```

---

## ➕ POST `/`

**Add a new task**

### 📤 Request Body:
```json
{
  "task": "study"
}
```

### 📥 Response:
```json
{
  "msg": "Done!"
}
```

---

## 🔄 PUT `/`

**Update the status of a task**

### 📤 Request Body:
```json
{
  "task": "gym",
  "status": true
}
```

### 📥 Response:
```json
{
  "message": "Task updated successfully",
  "updatedTask": {
    "id": 1,
    "task": "gym",
    "status": true
  }
}
```

---

## ❌ DELETE `/?task=taskName`

**Delete a task by its name**

### 🧪 Sample Request:
```
DELETE http://localhost:3000/?task=gym
```

### 📥 Response:
```json
{
  "message": "Task deleted successfully"
}
```

---

## ⚙️ Notes
If task.json doesn't exist, it's automatically created on first run.

All operations persist changes to task.json so data is not lost between restarts.

Task names should be unique to avoid unintended updates/deletes.

---

## 🧠 Future Improvements
 Use task ID instead of name for update/delete

 Add duplicate task name validation

 Add timestamp for created/updated tasks

 Add unit tests and error logging

---
## 📜 License
This project is licensed under the MIT License




