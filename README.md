🟢 📌 TASK: Create a Small Student API (GET + POST)

Your students must build two APIs:

✨ Task 1 — Create a GET API
API Route:
GET /students

Response:

Return a list of 3 students in JSON format:

[
  { "id": 1, "name": "Rahul", "age": 20 },
  { "id": 2, "name": "Ayesha", "age": 21 },
  { "id": 3, "name": "Sohail", "age": 22 }
]

✨ Task 2 — Create a POST API
API Route:
POST /add-student

Requirements:

Postman will send data like this:

{
  "name": "New Student",
  "age": 19
}

Response:

Return:

{
  "message": "Student added successfully",
  "receivedData": {
    "name": "New Student",
    "age": 19
  }
}

✨ Task 3 — Use Postman to test both APIs
For GET:

Set method to GET

Hit: http://localhost:3000/students

For POST:

Set method to POST

URL: http://localhost:3000/add-student

Body → raw → JSON

Send:

{
  "name": "Ali",
  "age": 18
}

🟦 BONUS (OPTIONAL) — Task 4

Create another GET API:

GET /student/:id


Example:

GET /student/2


Return:

{
  "id": 2,
  "name": "Ayesha",
  "age": 21
}

🟣 Full Code Starter Template

Give them this starter code or ask them to write from scratch:

const express = require("express");
const app = express();

app.use(express.json());

// Task 1
app.get("/students", (req, res) => {
    res.json([
        { id: 1, name: "Rahul", age: 20 },
        { id: 2, name: "Ayesha", age: 21 },
        { id: 3, name: "Sohail", age: 22 }
    ]);
});

// Task 2
app.post("/add-student", (req, res) => {
    res.json({
        message: "Student added successfully",
        receivedData: req.body
    });
});

app.listen(3000, () => console.log("Server running on port 3000"));
