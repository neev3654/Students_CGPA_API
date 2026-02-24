# Students CGPA API

A simple REST API built with Express.js to manage and retrieve student academic information based on their CGPA (Cumulative Grade Point Average).

## Overview

This API provides endpoints to access student data, calculate statistics, and filter students by various criteria including ID and branch/department.

## Features

- Retrieve all students
- Get individual student details by ID
- Filter students by branch/department
- Calculate average CGPA across all students
- Find the topper (highest CGPA student)
- Count total number of students

## Technologies Used

- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework
- **CORS** - Cross-Origin Resource Sharing middleware
- **Nodemon** - Development tool for auto-restart on file changes

## Installation

1. Clone the repository:
```bash
git clone https://github.com/neev3654/Students_CGPA_API.git
cd Students_CGPA_API
```

2. Install dependencies:
```bash
npm install
```

## Running the Server

To start the server:
```bash
node index.js
```

For development with auto-reload:
```bash
npx nodemon index.js
```

The server will run on **http://localhost:3000**

## API Endpoints

### 1. Health Check
```
GET /
```
Returns a confirmation message that the server is running.

**Response:**
```
Express server is running
```

---

### 2. Get All Students
```
GET /students
```
Retrieves a list of all students with their information.

**Response:**
```json
[
  {
    "id": 1,
    "name": "Aarav Sharma",
    "branch": "CSE",
    "semester": 8,
    "cgpa": 9.3
  },
  ...
]
```

---

### 3. Get Student by ID
```
GET /students/:id
```
Retrieves a specific student by their ID.

**Parameters:**
- `id` (path parameter) - Student ID (integer)

**Response (Success):**
```json
{
  "id": 1,
  "name": "Aarav Sharma",
  "branch": "CSE",
  "semester": 8,
  "cgpa": 9.3
}
```

**Response (Not Found):**
```json
{
  "message": "Student not found"
}
```

---

### 4. Get Students by Branch
```
GET /students/branch/:branchName
```
Retrieves all students from a specific branch/department (case-insensitive).

**Parameters:**
- `branchName` (path parameter) - Branch name (e.g., CSE, IT, ECE, AI, Data Science)

**Response:**
```json
[
  {
    "id": 1,
    "name": "Aarav Sharma",
    "branch": "CSE",
    "semester": 8,
    "cgpa": 9.3
  },
  {
    "id": 4,
    "name": "Meera Iyer",
    "branch": "CSE",
    "semester": 8,
    "cgpa": 9.1
  },
  ...
]
```

---

### 5. Get Topper Student
```
GET /students/topper
```
Retrieves the student with the highest CGPA.

**Response:**
```json
{
  "id": 1,
  "name": "Aarav Sharma",
  "branch": "CSE",
  "semester": 8,
  "cgpa": 9.3
}
```

---

### 6. Get Average CGPA
```
GET /students/average
```
Calculates and returns the average CGPA of all students.

**Response:**
```json
{
  "averageCGPA": 8.51
}
```

---

### 7. Get Total Student Count
```
GET /students/count
```
Returns the total number of students in the database.

**Response:**
```json
{
  "totalStudents": 10
}
```

---

## Sample Data

The API comes with 10 pre-loaded students from various branches:

| ID | Name | Branch | Semester | CGPA |
|---|---|---|---|---|
| 1 | Aarav Sharma | CSE | 8 | 9.3 |
| 2 | Ishita Verma | IT | 7 | 8.9 |
| 3 | Rohan Kulkarni | ECE | 6 | 8.4 |
| 4 | Meera Iyer | CSE | 8 | 9.1 |
| 5 | Kunal Deshmukh | IT | 5 | 7.8 |
| 6 | Ananya Reddy | CSE | 6 | 8.7 |
| 7 | Vikram Patil | ECE | 7 | 8.2 |
| 8 | Priyanka Nair | AI | 4 | 8.8 |
| 9 | Harsh Mehta | Data Science | 5 | 8.0 |
| 10 | Neha Gupta | CSE | 6 | 7.9 |

## Error Handling

The API returns appropriate HTTP status codes:
- **200** - Successful request
- **404** - Resource not found

## Dependencies

```json
{
  "cors": "^2.8.6",
  "express": "^5.2.1",
  "nodemon": "^3.1.14"
}
```

## License

ISC

## Author

[Neev Patel]

---

For more information or to contribute, please visit the [GitHub repository](https://github.com/neev3654/Students_CGPA_API).
