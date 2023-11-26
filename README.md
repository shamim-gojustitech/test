# Exammer API

- [Exammer API](#exammer-api)
- [Students Section](#students-section)
  - [Profile](#profile)
    - [1. Create a New Student](#1-create-a-new-student)
    - [2. Get Student Details by ID](#2-get-student-details-by-id)
    - [3. Get a List of All Students](#3-get-a-list-of-all-students)
    - [4. Update Student Information by ID](#4-update-student-information-by-id)
    - [5. Delete a Student by ID](#5-delete-a-student-by-id)
  - [Exam](#exam)
    - [1. Get Exam Details by ID](#1-get-exam-details-by-id)
    - [2. Get a List of All Exams](#2-get-a-list-of-all-exams)
  - [Results](#results)
    - [1. Get All Results for a Specific Student](#1-get-all-results-for-a-specific-student)
    - [2. Get All Results for a Specific Exam](#2-get-all-results-for-a-specific-exam)
    - [3. Get Result of a Specific Student in a Specific Exam](#3-get-result-of-a-specific-student-in-a-specific-exam)
    - [4. Remove Result by Student ID and Exam ID](#4-remove-result-by-student-id-and-exam-id)
    - [5. Get All Results](#5-get-all-results)
    - [6. Get Leaderboard for a Specific Exam](#6-get-leaderboard-for-a-specific-exam)
    - [7. Get All-Time Leaderboard](#7-get-all-time-leaderboard)
  - [Exam](#exam-1)
    - [1. Submit Exam](#1-submit-exam)
    - [2. Remove Exam Submission](#2-remove-exam-submission)
    - [3. Get Student Submissions by Exam](#3-get-student-submissions-by-exam)
- [Teachers Section](#teachers-section)
  - [Profile](#profile-1)
    - [1. Create a New Teacher](#1-create-a-new-teacher)
    - [2. Get Teacher Details by ID](#2-get-teacher-details-by-id)
    - [3. Get a List of All Teachers](#3-get-a-list-of-all-teachers)
    - [4. Update Teacher Information by ID](#4-update-teacher-information-by-id)
    - [5. Delete a Teacher by ID](#5-delete-a-teacher-by-id)
  - [Classroom](#classroom)
    - [1. Create a New Classroom](#1-create-a-new-classroom)
    - [2. Get Classroom Details by ID](#2-get-classroom-details-by-id)
    - [3. Get a List of All Classrooms](#3-get-a-list-of-all-classrooms)
    - [4. Update Classroom Information](#4-update-classroom-information)
    - [5. Delete Classroom](#5-delete-classroom)
    - [6. Add Teacher to Classroom](#6-add-teacher-to-classroom)
    - [7. Remove Teacher from Classroom](#7-remove-teacher-from-classroom)
    - [8. Add Student to Classroom](#8-add-student-to-classroom)
    - [9. Remove Student from Classroom](#9-remove-student-from-classroom)
    - [10. Get All Students in a Classroom](#10-get-all-students-in-a-classroom)
  - [Question](#question)
    - [1. Create a New Question](#1-create-a-new-question)
    - [2. Get Question Details by ID](#2-get-question-details-by-id)
    - [3. Get a List of All Questions](#3-get-a-list-of-all-questions)
    - [4. Update Question Information](#4-update-question-information)
    - [5. Delete Question](#5-delete-question)
  - [Exam](#exam-2)
    - [1. Create a New Exam](#1-create-a-new-exam)
    - [2. Get Exam Details by ID](#2-get-exam-details-by-id)
    - [3. Get a List of All Exams](#3-get-a-list-of-all-exams)
    - [4. Update Exam Information](#4-update-exam-information)
    - [5. Delete Exam](#5-delete-exam)
  - [Results](#results-1)
    - [1. Get All Results for a Specific Student](#1-get-all-results-for-a-specific-student-1)
    - [2. Get All Results for a Specific Exam](#2-get-all-results-for-a-specific-exam-1)
    - [3. Get Result of a Specific Student in a Specific Exam](#3-get-result-of-a-specific-student-in-a-specific-exam-1)
    - [4. Remove Result by Student ID and Exam ID](#4-remove-result-by-student-id-and-exam-id-1)
    - [5. Get All Results](#5-get-all-results-1)
    - [6. Get Leaderboard for a Specific Exam](#6-get-leaderboard-for-a-specific-exam-1)
    - [7. Get All-Time Leaderboard](#7-get-all-time-leaderboard-1)

# Students Section

## Profile

### 1. Create a New Student

- **Endpoint:** `student/profile/create`
- **Method:** `POST`
- **Description:** `Creates a new student with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "username": "john_doe123",
    "password": "password123",
    "email": "john.doe@example.com",
    "picture": "https://example.com/john_doe.jpg",
    "dateOfBirth": "1990-01-01",
    "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
    "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]
  }
  ```
- **Response Format:** `application/json`
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
      "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
      "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]
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

- **Endpoint:** `student/profile/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific student by ID.`
- **URL Parameters:** - `id`: Student's ID (Example: `student/profile/101`)
- **Response Format:** `application/json`
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
      "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
      "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]
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

- **Endpoint:** `student/profile/find/all ❌`
- **Method:** `GET`
- **Description:** `Gets a list of all students.`
- **Response Format:** `application/json`
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
        "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
        "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]
      },
      {
        "id": 124,
        "firstName": "Jane",
        "lastName": "Smith",
        "username": "jane_smith456",
        "email": "jane.smith@example.com",
        "picture": "https://example.com/jane_smith.jpg",
        "dateOfBirth": "1992-02-02",
        "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
        "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]
      }
    ]
    ```
  - **Error Code:** No specific error handling for this endpoint.
  <hr>

### 4. Update Student Information by ID

- **Endpoint:** `student/profile/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific student by ID.`
- **URL Parameters:** - `id`: Student's ID (Example: `student/profile/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "firstName": "Updated",
    "lastName": "Doe",
    "username": "updated_doe123",
    "password": "updated_password123",
    "email": "updated.doe@example.com",
    "picture": "https://example.com/updated_doe.jpg",
    "dateOfBirth": "1990-01-01",
    "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
    "exams": ["ObjectID(exam)", "ObjectID(exam)"],  
  }
  ```
- **Response Format:** `application/json`
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
      "classrooms": ["ObjectID(classroom)", "ObjectID(classroom)"],
      "exams": ["ObjectID(exam)", "ObjectID(exam)", "ObjectID(exam)"]    
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
- **URL Parameters:** - `id`: Student's ID (Example: `student/profile/delete/101`)
- **Response Format:** `application/json`
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

// more to be done

## Exam

### 1. Get Exam Details by ID

- **Endpoint:** `student/exam/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific exam by ID.`
- **URL Parameters:** - `id`: Exam's ID (Example: `student/exam/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "name": "Midterm Exam",
      "classroom": "ObjectID(classroom)",
      "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Exam not found"
    }
    ```
    <hr>

### 2. Get a List of All Exams

- **Endpoint:** `student/exam/find/all`
- **Method:** `GET`
- **Description:** `Gets a list of all exams.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(exam)",
        "name": "Midterm Exam",
        "classroom": "ObjectID(classroom)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
      },
      {
        "id": "ObjectID(exam)",
        "name": "Final Exam",
        "classroom": "ObjectID(classroom)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
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

## Results

### 1. Get All Results for a Specific Student

- **Endpoint:** `student/results/find/student/:studentId`
- **Method:** `GET`
- **Description:** `Retrieve all results for a specific student.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/student/results/student/123`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 85,
        "exam": {
          "id": "ObjectID(exam)",
          "name": "Math Exam"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified student"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Get All Results for a Specific Exam

- **Endpoint:** `student/results/find/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve all results for a specific exam.`
- **URL Parameters:**
  - `examId`: Exam's ID (Example: `/student/results/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)"
        "score": 85,
        "student": {
          "id": "ObjectID(exam)",
          "firstName": "John",
          "lastName": "Doe"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 3. Get Result of a Specific Student in a Specific Exam

- **Endpoint:** `student/results/find/student/:studentId/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve the result of a specific student in a specific exam.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/student/results/student/123`)
  - `examId`: Exam's ID (Example: `/student/results/student/123/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(result)",
      "score": 85,
      "student": {
        "id": "ObjectID(student)",
        "firstName": "John",
        "lastName": "Doe"
      },
      "exam": {
        "id": "ObjectID(exam)",
        "name": "Math Exam"
      }
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Result not found for the specified student and exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Remove Result by Student ID and Exam ID

- **Endpoint:** `student/results/remove/student/:studentId/exam/:examId`
- **Method:** `DELETE`
- **Description:** `Remove a result for a specific student in a specific exam.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/student/results/student/123`)
  - `examId`: Exam's ID (Example: `/student/results/student/123/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Result removed successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Result not found for the specified student and exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 5. Get All Results

- **Endpoint:** `student/results/find/all`
- **Method:** `GET`
- **Description:** `Retrieve a list of all results.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 85,
        "student": {
          "id": "ObjectID(student)",
          "firstName": "John",
          "lastName": "Doe"
        },
        "exam": {
          "id": "ObjectID(exam)",
          "name": "Math Exam"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 6. Get Leaderboard for a Specific Exam

- **Endpoint:** `student/results/leaderboard/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve the leaderboard for a specific exam, sorted by score in descending order.`
- **URL Parameters:**
  - `examId`: Exam's ID (Example: `/student/results/leaderboard/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 95,
        "student": {
          "id": "ObjectID(student)",
          "firstName": "Alice",
          "lastName": "Wonder"
        }
      }
      // ... other leaderboard entries
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 7. Get All-Time Leaderboard

- **Endpoint:** `student/results/leaderboard/all-time`
- **Method:** `GET`
- **Description:** `Retrieve the all-time leaderboard, sorted by total score in descending order.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "student": {
          "id": "ObjectID(result)",
          "firstName": "John",
          "lastName": "Doe"
        },
        "totalScore": 320
      }
      // ... other leaderboard entries
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

## Exam

### 1. Submit Exam

- **Endpoint:** `/exam/submit/:examId`
- **Method:** `POST`
- **Description:** `Submits an exam for a specific student.`
- **URL Parameters:**
  - `examId`: Exam ID (Example: `/exam/submit/101`)
- **Request Format:** `application/json`
  ```json
  {
    "studentId": "ObjectID(student)",
    "questionIds": ["q1", "q2", "q3"],
    "answers": ["option1", "option2", "option3"]
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "submission": {
        "_id": "submission123",
        "student": "ObjectID(student)",
        "exam": "ObjectID(exam)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"],
        "answers": ["option1", "option2", "option3"]
      },
      "result": {
        "_id": "result123",
        "student": "ObjectID(student)",
        "exam": "ObjectID(exam)",
        "score": 2
      }
    }
    ```
  - **Error Code:** `500 Internal Sever Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Remove Exam Submission

- **Endpoint:** `/exam/remove/:examId`
- **Method:** `DELETE`
- **Description:** `Removes an exam submission for a specific student.`
- **URL Parameters:**
  - `examId`: Exam ID (Example: `/exam/remove/101`)
- **Request Format:** `application/json`
  ```json
  {
    "studentId": "ObjectID(student)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Exam removed successfully"
    }
    ```
  - **Error Code:** `500 Internal Sever Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 3. Get Student Submissions by Exam

- **Endpoint:** `/exam/submit/find/:examId`
- **Method:** `GET`
- **Description:** `Gets a student's submissions for a specific exam.`
- **URL Parameters:**
  - `examId`: Exam ID (Example: `/exam/remove/101`)
- **Request Format:** `application/json`
  ```json
  {
    "studentId": "ObjectID(student)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "_id": "submission123",
        "student": "ObjectID(student)",
        "exam": "ObjectID(exam)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"],
        "answers": ["option1", "option2", "option3"]
      }
      // ... other submissions
    ]
    ```
  - **Error Code:** `500 Internal Sever Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

# Teachers Section

## Profile

### 1. Create a New Teacher

- **Endpoint:** `teacher/profile/create`
- **Method:** `POST`
- **Description:** `Creates a new teacher with the provided information.`
- **Request Format:** `application/json`
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
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID()",
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

- **Endpoint:** `teacher/profile/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific teacher by ID.`
- **URL Parameters:** - `id`: Teacher's ID (Example: `teacher/profile/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(teacher)",
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

- **Endpoint:** `teacher/profile/find/all ❌`
- **Method:** `GET`
- **Description:** `Gets a list of all teachers.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(teacher)",
        "firstName": "John",
        "lastName": "Doe",
        "username": "john_doe123",
        "email": "john.doe@example.com",
        "picture": "https://example.com/john_doe.jpg"
      },
      {
        "id": "ObjectID(teacher)",
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

- **Endpoint:** `teacher/profile/update/:id ❌`
- **Method:** `PUT`
- **Description:** `Updates information for a specific teacher by ID.`
- **URL Parameters:** - `id`: Teacher's ID (Example: `teacher/profile/update/101`)
- **Request Format:** `application/json`
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
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(teacher)",
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
- **URL Parameters:** - `id`: Teacher's ID (Example: `teacher/profile/delete/101`)
- **Response Format:** `application/json`
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

- **Endpoint:** `teacher/classroom/create`
- **Method:** `POST`
- **Description:** `Creates a new classroom with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "name": "Classroom A",
    "teacher": "ObjectID(teacher)",
    "students": ["ObjectID(student)", "ObjectID(student)"]
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific classroom by ID.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/find/all ❌`
- **Method:** `GET`
- **Description:** `Gets a list of all classrooms.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(classroom)",
        "name": "Classroom A",
        "teacher": {
          // Teacher details
        },
        "students": [
          // List of student details
        ]
      },
      {
        "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/update/:id ❌`
- **Method:** `PUT`
- **Description:** `Updates information for a specific classroom by ID.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "name": "Updated Classroom A",
    "teacher": "ObjectID(classroom)",
    "students": ["ObjectID(student)"]
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a classroom by ID.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/update/101`)
- **Response Format:** `application/json`
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

- **Endpoint:** `teacher/classroom/add/teacher/:id`
- **Method:** `PUT`
- **Description:** `Adds a teacher to a classroom.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/add/teacher/101`)
- **Request Format:** `application/json`
  ```json
  {
    "teacherId": "ObjectID(teacher)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/remove/teacher/:id ❌`
- **Method:** `PUT`
- **Description:** `Removes a teacher from a classroom.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/remove/teacher/101`)
- **Request Format:** `application/json`
  ```json
  {
    "teacherId": "ObjectID(teacher)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(teacher)",
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

- **Endpoint:** `teacher/classroom/add/student/:id`
- **Method:** `PUT`
- **Description:** `Adds a student to a classroom.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/add/student/101`)
- **Request Format:** `application/json`
  ```json
  {
    "studentId": "ObjectID(student)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/remove/student/:id`
- **Method:** `PUT`
- **Description:** `Removes a student from a classroom.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/add/student/101`)
- **Request Format:** `application/json`
  ```json
  {
    "studentId": "ObjectID(student)"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(classroom)",
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

- **Endpoint:** `teacher/classroom/students/:id`
- **Method:** `GET`
- **Description:** `Gets a list of all students in a specific classroom.`
- **URL Parameters:** - `id`: Classroom's ID (Example: `teacher/classroom/students/101`)
- **Response Format:** `application/json`
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

- **Endpoint:** `teacher/question/create`
- **Method:** `POST`
- **Description:** `Creates a new question with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "text": "What is the capital of France?",
    "options": ["Berlin", "Paris", "Madrid", "London"],
    "correctOption": "Paris"
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(question)",
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

- **Endpoint:** `teacher/question/find/:id`
- **Method:** `GET`
- **Description:** `Gets information about a specific question by ID.`
- **URL Parameters:** - `id`: Question's ID (Example: `teacher/question/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(question)",
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

- **Endpoint:** `teacher/question/find/all`
- **Method:** `GET`
- **Description:** `Gets a list of all questions.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(question)",
        "text": "What is the capital of France?",
        "options": ["Berlin", "Paris", "Madrid", "London"],
        "correctOption": "Paris"
      },
      {
        "id": "ObjectID(question)",
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

- **Endpoint:** `teacher/question/update/:id`
- **Method:** `PUT`
- **Description:** `Updates information for a specific question by ID.`
- **URL Parameters:** - `id`: Question's ID (Example: `teacher/question/update/101`)
- **Request Format:** `application/json`
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
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(question)",
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

- **Endpoint:** `teacher/question/delete/:id`
- **Method:** `DELETE`
- **Description:** `Deletes a question by ID.`
- **URL Parameters:** - `id`: Question's ID (Example: `teacher/question/delete/101`)
- **Response Format:** `application/json`
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

## Exam

### 1. Create a New Exam

- **Endpoint:** `teacher/exam/create`
- **Method:** `POST`
- **Description:** `Creates a new exam with the provided information.`
- **Request Format:** `application/json`
  ```json
  {
    "name": "Midterm Exam",
    "classroom": "ObjectID(classroom)",
    "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `201 Created`
    ```json
    {
      "id": "ObjectID(exam)",
      "name": "Midterm Exam",
      "classroom": "ObjectID(classroom)",
      "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
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
- **URL Parameters:** - `id`: Exam's ID (Example: `teacher/exam/find/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(exam)",
      "name": "Midterm Exam",
      "classroom": "ObjectID(classroom)",
      "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
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
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(exam)",
        "name": "Midterm Exam",
        "classroom": "ObjectID(classroom)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
      },
      {
        "id": "ObjectID(exam)",
        "name": "Final Exam",
        "classroom": "ObjectID(classroom)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
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
- **URL Parameters:** - `id`: Exam's ID (Example: `teacher/exam/update/101`)
- **Request Format:** `application/json`
  ```json
  {
    "name": "Updated Midterm Exam",
      "classroom": "ObjectID(classroom)",
      "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
      "Updated Question ID 1",
      "Updated Question ID 2",
      "Updated Question ID 3"
    ]
  }
  ```
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(")Exam ID",
      "name": "Updated Midterm Exam",
        "classroom": "ObjectID(classroom)",
        "questions": ["ObjectID(question)", "ObjectID(question)", "ObjectID(question)"]
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
- **URL Parameters:** - `id`: Exam's ID (Example: `teacher/exam/delete/101`)
- **Request Format:** No request body required.
- **Response Format:** `application/json`
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

## Results

### 1. Get All Results for a Specific Student

- **Endpoint:** `teacher/results/find/student/:studentId`
- **Method:** `GET`
- **Description:** `Retrieve all results for a specific student.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/teacher/results/student/123`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 85,
        "exam": {
          "id": "ObjectID(exam)",
          "name": "Math Exam"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified student"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 2. Get All Results for a Specific Exam

- **Endpoint:** `teacher/results/find/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve all results for a specific exam.`
- **URL Parameters:**
  - `examId`: Exam's ID (Example: `/teacher/results/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 85,
        "student": {
          "id": "ObjectID(student)",
          "firstName": "John",
          "lastName": "Doe"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 3. Get Result of a Specific Student in a Specific Exam

- **Endpoint:** `teacher/results/find/student/:studentId/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve the result of a specific student in a specific exam.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/teacher/results/student/123`)
  - `examId`: Exam's ID (Example: `/teacher/results/student/123/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "id": "ObjectID(result)",
      "score": 85,
      "student": {
        "id": "ObjectID(student)",
        "firstName": "John",
        "lastName": "Doe"
      },
      "exam": {
        "id": "ObjectID(exam)",
        "name": "Math Exam"
      }
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Result not found for the specified student and exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 4. Remove Result by Student ID and Exam ID

- **Endpoint:** `teacher/results/remove/student/:studentId/exam/:examId`
- **Method:** `DELETE`
- **Description:** `Remove a result for a specific student in a specific exam.`
- **URL Parameters:**
  - `studentId`: Student's ID (Example: `/teacher/results/student/123`)
  - `examId`: Exam's ID (Example: `/teacher/results/student/123/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    {
      "message": "Result removed successfully"
    }
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "Result not found for the specified student and exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 5. Get All Results

- **Endpoint:** `teacher/results/find/all`
- **Method:** `GET`
- **Description:** `Retrieve a list of all results.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 85,
        "student": {
          "id": "ObjectID(student)",
          "firstName": "John",
          "lastName": "Doe"
        },
        "exam": {
          "id": "ObjectID(exam)",
          "name": "Math Exam"
        }
      }
      // ... other results
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 6. Get Leaderboard for a Specific Exam

- **Endpoint:** `teacher/results/leaderboard/exam/:examId`
- **Method:** `GET`
- **Description:** `Retrieve the leaderboard for a specific exam, sorted by score in descending order.`
- **URL Parameters:**
  - `examId`: Exam's ID (Example: `/teacher/results/leaderboard/exam/101`)
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "id": "ObjectID(result)",
        "score": 95,
        "student": {
          "id": "ObjectID(student)",
          "firstName": "Alice",
          "lastName": "Wonder"
        }
      }
      // ... other leaderboard entries
    ]
    ```
  - **Error Code:** `404 Not Found`
    ```json
    {
      "error": "No results found for the specified exam"
    }
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>

### 7. Get All-Time Leaderboard

- **Endpoint:** `teacher/results/leaderboard/all-time`
- **Method:** `GET`
- **Description:** `Retrieve the all-time leaderboard, sorted by total score in descending order.`
- **Response Format:** `application/json`
  - **Success Code:** `200 OK`
    ```json
    [
      {
        "student": {
          "id": "ObjectID(student)",
          "firstName": "John",
          "lastName": "Doe"
        },
        "totalScore": 320
      }
      // ... other leaderboard entries
    ]
    ```
  - **Error Code:** `500 Internal Server Error`
    ```json
    {
      "error": "Internal Server Error"
    }
    ```
    <hr>
