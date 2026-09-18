# Student Notes CRUD Micro-App

## Student Details

**Name:** Sree Lasya Muvva  
**Student ID:** 2026204009  
**Course:** Full-Stack Cloud Architectures  
**Lab Activity:** MERN Stack CRUD App  

**GitHub Repository:** https://github.com/sreelasyamuvva/notes-app

---

## Project Description

A full-stack Student Notes CRUD application developed using the MERN stack.

The application allows users to:

- Create notes
- View all notes
- Delete notes
- View note creation dates with times
- Update the UI without refreshing the browser

---

## Technology Stack

### Frontend
- React
- Vite
- Axios

### Backend
- Node.js
- Express.js
- CORS

### Database
- MongoDB
- Mongoose

---

## Database Configuration

The application connects to the local MongoDB database:

`mongodb://localhost:27017/notes_db`

---

## API Endpoints

### Create Note

`POST /api/notes`

Creates and stores a new note.

### Get All Notes

`GET /api/notes`

Retrieves all notes in descending chronological order.

### Delete Note

`DELETE /api/notes/:id`

Deletes a note using its MongoDB ID.

---

## Project Structure

```text
notes-app/
├── .gitignore
├── README.md
├── screenshots/
│   ├── ui-preview.png
│   └── delete-action.png
├── server/
│   ├── config/
│   │   └── db.js
│   ├── models/
│   │   └── Note.js
│   ├── routes/
│   │   └── noteRoutes.js
│   ├── package.json
│   └── server.js
└── client/
    ├── index.html
    ├── vite.config.js
    ├── package.json
    └── src/
        ├── App.jsx
        ├── main.jsx
        └── index.css