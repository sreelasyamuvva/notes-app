# Student Notes CRUD Micro-App

## Student Details

**Name:** Sree Lasya Muvva  
**Student ID:** 2026204009 
**Course:** Full-Stack Cloud Architectures  
**Lab Activity:** MERN Stack CRUD App  

**GitHub Repository:** https://github.com/sreelasyamuvva/notes-app

---

## 1. Project Description

The Student Notes CRUD Micro-App is a full-stack web application developed using the MERN stack.

The application allows users to:

- Create new notes
- View all existing notes
- Delete notes
- View the date and time when a note was created
- Update the user interface without manually refreshing the browser

The application follows a decoupled two-tier architecture consisting of a React frontend and an Express/Node.js backend connected to MongoDB using Mongoose.

---

## 2. Technology Stack

### Frontend

- React
- Vite
- Axios
- React Hooks (`useState`, `useEffect`)

### Backend

- Node.js
- Express.js
- CORS

### Database

- MongoDB
- Mongoose

---

## 3. Database Configuration

The application uses a local MongoDB database.

MongoDB connection string:

```text
mongodb://localhost:27017/notes_db
```

The database is named:

```text
notes_db
```

---

## 4. Mongoose Schema

Each note is stored using the following schema:

```text
title     : String, required
content   : String, required
createdAt : Date, default Date.now
```

The `createdAt` field is automatically populated with the current date and time when a note is created.

---

## 5. REST API Endpoints

### POST /api/notes

Creates a new note.

**Request body:**

```json
{
  "title": "Sample Note",
  "content": "This is a sample note."
}
```

**Response:**

Returns the created note with HTTP status:

```text
201 Created
```

---

### GET /api/notes

Retrieves all notes from MongoDB.

Notes are ordered by `createdAt` in descending order, so the newest notes appear first.

**Response:**

```text
200 OK
```

---

### DELETE /api/notes/:id

Deletes a note using its MongoDB `_id`.

**Response:**

```text
200 OK
```

If the note does not exist:

```text
404 Not Found
```

---

## 6. Project Structure

```text
notes-app/
│
├── .gitignore
├── README.md
│
├── screenshots/
│   ├── ui-preview.png
│   └── delete-action.png
│
├── server/
│   ├── config/
│   │   └── db.js
│   │
│   ├── models/
│   │   └── Note.js
│   │
│   ├── routes/
│   │   └── noteRoutes.js
│   │
│   ├── package.json
│   ├── package-lock.json
│   └── server.js
│
└── client/
    ├── index.html
    ├── vite.config.js
    ├── package.json
    ├── package-lock.json
    │
    └── src/
        ├── App.jsx
        ├── main.jsx
        └── index.css
```

---

## 7. Step-by-Step Setup Instructions

### Step 1: Clone the Repository

Clone the GitHub repository:

```bash
git clone https://github.com/sreelasyamuvva/notes-app.git
```

Navigate into the project directory:

```bash
cd notes-app
```

---

### Step 2: Start MongoDB

Make sure the local MongoDB service is running.

The application connects to:

```text
mongodb://localhost:27017/notes_db
```

---

### Step 3: Install Backend Dependencies

Open a terminal and navigate to the server directory:

```bash
cd server
```

Install the required dependencies:

```bash
npm install
```

---

### Step 4: Start the Backend Server

Start the Express server:

```bash
npm start
```

The backend server runs on:

```text
http://localhost:5000
```

The terminal should display messages indicating that the server is running and MongoDB is connected.

---

### Step 5: Open a Second Terminal

Keep the backend terminal running.

Open another terminal and navigate to the client directory:

```bash
cd notes-app/client
```

---

### Step 6: Install Frontend Dependencies

Install the required frontend dependencies:

```bash
npm install
```

---

### Step 7: Start the React Development Server

Run:

```bash
npm run dev
```

The Vite development server runs on:

```text
http://localhost:5173
```

---

### Step 8: Open the Application

Open a browser and visit:

```text
http://localhost:5173
```

The Student Notes application will be displayed.

---

## 8. Application Usage

### Creating a Note

1. Enter a title in the Note Title field.
2. Enter the note content.
3. Click the **Add Note** button.
4. The note is sent to the backend using an Axios POST request.
5. The note is stored in MongoDB.
6. The newly created note appears in the notes list without refreshing the page.

---

### Viewing Notes

When the application loads, React's `useEffect` hook sends a GET request to:

```text
GET /api/notes
```

The retrieved notes are stored in React state and displayed on the page.

Each note displays:

* Title
* Content
* Creation date and time
* Delete button

---

### Deleting a Note

1. Click the **Delete** button on a note.
2. The application sends a DELETE request to:

```text
DELETE /api/notes/:id
```

3. The backend deletes the note from MongoDB.
4. The frontend updates its local state.
5. The deleted note disappears from the interface without requiring a browser refresh.

---

## 9. Defensive UI States

The application implements loading and empty states.

### Loading State

While notes are being retrieved from the backend, the application displays:

```text
Loading notes...
```

### Empty State

When there are no notes, the application displays:

```text
No notes yet — add one above!
```

---

## 10. CORS Configuration

The Express backend uses the CORS middleware to allow requests from the React frontend.

The backend includes:

```javascript
app.use(cors());
```

The backend also parses JSON request bodies using:

```javascript
app.use(express.json());
```

---

## 11. Error Handling

The backend includes error handling for:

* MongoDB connection failures
* Failed API requests
* Missing notes during deletion

The frontend also handles errors during Axios requests and implements loading and empty states.

---

## 12. Screenshots

### UI Preview

The `ui-preview.png` screenshot provides visual proof of the application successfully displaying at least two notes.

### Delete Action

The `delete-action.png` screenshot provides visual proof of a successful note deletion. It shows the application after deletion along with the browser DevTools Network tab displaying the successful:

```text
DELETE /api/notes/:id
200 OK
```

---

## 13. Running the Application

The application requires two terminals.

### Terminal 1 — Backend

```bash
cd notes-app/server
npm install
npm start
```

Backend URL:

```text
http://localhost:5000
```

### Terminal 2 — Frontend

```bash
cd notes-app/client
npm install
npm run dev
```

Frontend URL:

```text
http://localhost:5173
```

MongoDB must also be running locally.

---

## 14. GitHub Repository

The complete project source code is available at:

[https://github.com/sreelasyamuvva/notes-app](https://github.com/sreelasyamuvva/notes-app)