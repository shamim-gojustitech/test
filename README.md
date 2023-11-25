# Exammer API

## Students

### 1. Create a New Student

- **Endpoint:** `student/profile/create`
- **Method:** `POST`
- **Description:** `Creates a new student with the provided information.`
- **Request Format:** `json`
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "username": "john_doe123",
    "password": "password123",
    "email": "john.doe@example.com",
    "picture": "https://example.com/john_doe.jpg",
    "dateOfBirth": "1990-01-01",
    "classrooms": ["Math", "Science"]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": 123,
      "firstName": "John",
      "lastName": "Doe",
      "username": "john_doe123",
      "email": "john.doe@example.com",
      "picture": "https://example.com/john_doe.jpg",
      "dateOfBirth": "1990-01-01",
      "classrooms": ["Math", "Science"]
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Username or email already exists"
    }
    ```
    <hr>

### 2. Get Student Details by ID

- **Endpoint:** `student/profile/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific student by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "firstName": "John",
      "lastName": "Doe",
      "username": "john_doe123",
      "email": "john.doe@example.com",
      "picture": "https://example.com/john_doe.jpg",
      "dateOfBirth": "1990-01-01",
      "classrooms": ["Math", "Science"]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Student not found"
    }
    ```
    <hr>

### 3. Get a List of All Students

- **Endpoint:** `student/profile/all`
- **Method:** `GET`
- **Description:** `Gets a list of all students.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": 123,
        "firstName": "John",
        "lastName": "Doe",
        "username": "john_doe123",
        "email": "john.doe@example.com",
        "picture": "https://example.com/john_doe.jpg",
        "dateOfBirth": "1990-01-01",
        "classrooms": ["Math", "Science"]
      },
      {
        "id": 124,
        "firstName": "Jane",
        "lastName": "Smith",
        "username": "jane_smith456",
        "email": "jane.smith@example.com",
        "picture": "https://example.com/jane_smith.jpg",
        "dateOfBirth": "1992-02-02",
        "classrooms": ["History", "English"]
      }
    ]
    ```
  - **Error Code:** No specific error handling for this endpoint.
  <hr>

### 4. Update Student Information by ID

- **Endpoint:** `student/profile/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific student by ID.`
- **Request Format:** `json`
  ```json
  {
    "firstName": "Updated",
    "lastName": "Doe",
    "username": "updated_doe123",
    "password": "updated_password123",
    "email": "updated.doe@example.com",
    "picture": "https://example.com/updated_doe.jpg",
    "dateOfBirth": "1990-01-01",
    "classrooms": ["History", "English"]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "firstName": "Updated",
      "lastName": "Doe",
      "username": "updated_doe123",
      "email": "updated.doe@example.com",
      "picture": "https://example.com/updated_doe.jpg",
      "dateOfBirth": "1990-01-01",
      "classrooms": ["History", "English"]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Student not found"
    }
    ```
    <hr>

### 5. Delete a Student by ID

- **Endpoint:** `student/profile/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a student by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Student deleted successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Student not found"
    }
    ```
    <hr>

## Teachers

### 1. Create a New Teacher

- **Endpoint:** `teacher/profile/create`
- **Method:** `POST`
- **Description:** `Creates a new teacher with the provided information.`
- **Request Format:** `json`
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "username": "john_doe123",
    "password": "password123",
    "email": "john.doe@example.com",
    "picture": "https://example.com/john_doe.jpg"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": 123,
      "firstName": "John",
      "lastName": "Doe",
      "username": "john_doe123",
      "email": "john.doe@example.com",
      "picture": "https://example.com/john_doe.jpg"
    }
    ```
  - **Error Code:** `400 Bad Request`
    ```json
    {
      "error": "Username or email already exists"
    }
    ```
    <hr>

### 2. Get Teacher Details by ID

- **Endpoint:** `teacher/profile/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific teacher by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "firstName": "John",
      "lastName": "Doe",
      "username": "john_doe123",
      "email": "john.doe@example.com",
      "picture": "https://example.com/john_doe.jpg"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Teacher not found"
    }
    ```
    <hr>

### 3. Get a List of All Teachers

- **Endpoint:** `teacher/profile/all`
- **Method:** `GET`
- **Description:** `Gets a list of all teachers.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": 123,
        "firstName": "John",
        "lastName": "Doe",
        "username": "john_doe123",
        "email": "john.doe@example.com",
        "picture": "https://example.com/john_doe.jpg"
      },
      {
        "id": 124,
        "firstName": "Jane",
        "lastName": "Smith",
        "username": "jane_smith456",
        "email": "jane.smith@example.com",
        "picture": "https://example.com/jane_smith.jpg"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Update Teacher Information by ID

- **Endpoint:** `teacher/profile/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific teacher by ID.`
- **Request Format:** `json`
  ```json
  {
    "firstName": "Updated",
    "lastName": "Doe",
    "username": "updated_doe123",
    "password": "updated_password123",
    "email": "updated.doe@example.com",
    "picture": "https://example.com/updated_doe.jpg"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "firstName": "Updated",
      "lastName": "Doe",
      "username": "updated_doe123",
      "email": "updated.doe@example.com",
      "picture": "https://example.com/updated_doe.jpg"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Teacher not found"
    }
    ```
    <hr>

### 5. Delete a Teacher by ID

- **Endpoint:** `teacher/profile/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a teacher by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Teacher deleted successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Teacher not found"
    }
    ```
    <hr>

## Classroom

### 1. Create a New Classroom

- **Endpoint:** `classroom/create`
- **Method:** `POST`
- **Description:** `Creates a new classroom with the provided information.`
- **Request Format:** `json`
  ```json
  {
    "name": "Classroom A",
    "teacher": "teacherId123",
    "students": ["studentId1", "studentId2"]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": 123,
      "name": "Classroom A",
      "teacher": {
        // Teacher details
      },
      "students": [
        // List of student details
      ]
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Get Classroom Details by ID

- **Endpoint:** `classroom/findId/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific classroom by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "name": "Classroom A",
      "teacher": {
        // Teacher details
      },
      "students": [
        // List of student details
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 3. Get a List of All Classrooms

- **Endpoint:** `classroom/find/all`
- **Method:** `GET`
- **Description:** `Gets a list of all classrooms.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": 123,
        "name": "Classroom A",
        "teacher": {
          // Teacher details
        },
        "students": [
          // List of student details
        ]
      },
      {
        "id": 124,
        "name": "Classroom B",
        "teacher": {
          // Teacher details
        },
        "students": [
          // List of student details
        ]
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Update Classroom Information

- **Endpoint:** `classroom/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific classroom by ID.`
- **Request Format:** `json`
  ```json
  {
    "name": "Updated Classroom A",
    "teacher": "updatedTeacherId",
    "students": ["newStudentId"]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "name": "Updated Classroom A",
      "teacher": {
        // Updated teacher details
      },
      "students": [
        // List of updated student details
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 5. Delete Classroom

- **Endpoint:** `classroom/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a classroom by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Classroom deleted successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 6. Add Teacher to Classroom

- **Endpoint:** `classroom/add/teacher`
- **Method:** `PUT`
- **Description:** `Adds a teacher to a classroom.`
- **Request Format:** `json`
  ```json
  {
    "classroomId": "classroomId123",
    "teacherId": "newTeacherId"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "classroomId123",
      "name": "Classroom A",
      "teacher": {
        // Updated teacher details
      },
      "students": [
        // List of student details
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 7. Remove Teacher from Classroom

- **Endpoint:** `classroom/remove/teacher`
- **Method:** `PUT`
- **Description:** `Removes a teacher from a classroom.`
- **Request Format:** `json`
  ```json
  {
    "classroomId": "classroomId123",
    "teacherId": "teacherIdToRemove"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "classroomId123",
      "name": "Classroom A",
      "teacher": {
        // Updated teacher details (without the removed teacher)
      },
      "students": [
        // List of student details
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 8. Add Student to Classroom

- **Endpoint:** `classroom/add/student`
- **Method:** `PUT`
- **Description:** `Adds a student to a classroom.`
- **Request Format:** `json`
  ```json
  {
    "classroomId": "classroomId123",
    "studentId": "newStudentId"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "classroomId123",
      "name": "Classroom A",
      "teacher": {
        // Teacher details
      },
      "students": [
        // List of updated student details
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 9. Remove Student from Classroom

- **Endpoint:** `classroom/remove/student`
- **Method:** `PUT`
- **Description:** `Removes a student from a classroom.`
- **Request Format:** `json`
  ```json
  {
    "classroomId": "classroomId123",
    "studentId": "studentIdToRemove"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "classroomId123",
      "name": "Classroom A",
      "teacher": {
        // Teacher details
      },
      "students": [
        // List of updated student details (without the removed student)
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

### 10. Get All Students in a Classroom

- **Endpoint:** `classroom/students/:classroomId`
- **Method:** `GET`
- **Description:** `Gets a list of all students in a specific classroom.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        // Student details
      },
      {
        // Another student details
      }
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Classroom not found"
    }
    ```
    <hr>

## Question

### 1. Create a New Question

- **Endpoint:** `question/create`
- **Method:** `POST`
- **Description:** `Creates a new question with the provided information.`
- **Request Format:** `json`
  ```json
  {
    "text": "What is the capital of France?",
    "options": ["Berlin", "Paris", "Madrid", "London"],
    "correctOption": "Paris"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": 123,
      "text": "What is the capital of France?",
      "options": ["Berlin", "Paris", "Madrid", "London"],
      "correctOption": "Paris"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Get Question Details by ID

- **Endpoint:** `question/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific question by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "text": "What is the capital of France?",
      "options": ["Berlin", "Paris", "Madrid", "London"],
      "correctOption": "Paris"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Question not found"
    }
    ```
    <hr>

### 3. Get a List of All Questions

- **Endpoint:** `question/find/all`
- **Method:** `GET`
- **Description:** `Gets a list of all questions.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": 123,
        "text": "What is the capital of France?",
        "options": ["Berlin", "Paris", "Madrid", "London"],
        "correctOption": "Paris"
      },
      {
        "id": 124,
        "text": "Who wrote Romeo and Juliet?",
        "options": ["Shakespeare", "Hemingway", "Tolstoy", "Jane Austen"],
        "correctOption": "Shakespeare"
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Update Question Information

- **Endpoint:** `question/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific question by ID.`
- **Request Format:** `json`
  ```json
  {
    "text": "Updated question text?",
    "options": [
      "Updated option 1",
      "Updated option 2",
      "Updated option 3",
      "Updated option 4"
    ],
    "correctOption": "Updated option 2"
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": 123,
      "text": "Updated question text?",
      "options": [
        "Updated option 1",
        "Updated option 2",
        "Updated option 3",
        "Updated option 4"
      ],
      "correctOption": "Updated option 2"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Question not found"
    }
    ```
    <hr>

### 5. Delete Question

- **Endpoint:** `question/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a question by ID.`
- **Request Format:** `No request body required.`
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Question deleted successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Question not found"
    }
    ```
    <hr>

# Exams

### 1. Create a New Exam

- **Endpoint:** `teacher/exam/create`
- **Method:** `POST`
- **Description:** `Creates a new exam with the provided information.`
- **Request Format:** `json`
  ```json
  {
    "name": "Midterm Exam",
    "classroom": "Classroom ID",
    "questions": ["Question ID 1", "Question ID 2", "Question ID 3"]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "Exam ID",
      "name": "Midterm Exam",
      "classroom": "Classroom ID",
      "questions": ["Question ID 1", "Question ID 2", "Question ID 3"]
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Get Exam Details by ID

- **Endpoint:** `teacher/exam/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific exam by ID.`
- **Request Format:** No request body required.
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "Exam ID",
      "name": "Midterm Exam",
      "classroom": "Classroom ID",
      "questions": ["Question ID 1", "Question ID 2", "Question ID 3"]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Exam not found"
    }
    ```
    <hr>

### 3. Get a List of All Exams

- **Endpoint:** `teacher/exam/find/all`
- **Method:** `GET`
- **Description:** `Gets a list of all exams.`
- **Request Format:** No request body required.
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "Exam ID 1",
        "name": "Midterm Exam",
        "classroom": "Classroom ID",
        "questions": ["Question ID 1", "Question ID 2", "Question ID 3"]
      },
      {
        "id": "Exam ID 2",
        "name": "Final Exam",
        "classroom": "Classroom ID",
        "questions": ["Question ID 4", "Question ID 5", "Question ID 6"]
      }
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Update Exam Information

- **Endpoint:** `teacher/exam/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific exam by ID.`
- **Request Format:** `json`
  ```json
  {
    "name": "Updated Midterm Exam",
    "classroom": "Updated Classroom ID",
    "questions": [
      "Updated Question ID 1",
      "Updated Question ID 2",
      "Updated Question ID 3"
    ]
  }
  ```
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "Exam ID",
      "name": "Updated Midterm Exam",
      "classroom": "Updated Classroom ID",
      "questions": [
        "Updated Question ID 1",
        "Updated Question ID 2",
        "Updated Question ID 3"
      ]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Exam not found"
    }
    ```
    <hr>

### 5. Delete Exam

- **Endpoint:** `teacher/exam/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes an exam by ID.`
- **Request Format:** No request body required.
- **Response Format:** `json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Exam deleted successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Exam not found"
    }
    ```
    <hr>
