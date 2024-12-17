# Responsive Quiz App Using Spring Boot


Here’s a detailed outline of the **`README.md`** content for your project:

---

# Quiz App API (Spring Boot)

## Description
This is a REST API for a Quiz App built using Spring Boot. It provides functionalities for users to:
1. Start a new quiz session.
2. Fetch random multiple-choice questions from a predefined database.
3. Submit answers to questions.
4. View a summary of their progress, including total questions answered and details of correct/incorrect submissions.

---

## Features
- Start a new quiz session.
- Get random questions.
- Submit answers and track correctness.
- View a detailed quiz summary.

---

## Assumptions
- A single user is pre-seeded into the system for simplicity.
- A small set of questions is pre-loaded into the H2 database.
- No user authentication is implemented (all APIs are accessible to anyone).

---

## Prerequisites
- Java 17 or later
- Maven or Gradle
- A code editor or IDE (e.g., IntelliJ IDEA, Eclipse)
- Git installed on your system

---

## How to Run the Project
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Build the project:
   ```bash
   mvn clean install
   ```

3. Run the project:
   ```bash
   mvn spring-boot:run
   ```

4. Access the H2 database console (optional, for debugging purposes):
   - Navigate to: `http://localhost:8080/h2-console`
   - JDBC URL: `jdbc:h2:mem:testdb`
   - Username: `sa`
   - Password: `<leave empty>`

---

## API Endpoints

### 1. **Start a New Quiz Session**
- **Endpoint**: `POST /api/quiz/start`
- **Description**: Initializes a new quiz session for the user.
- **Response**:
  ```json
  {
    "message": "Quiz session started successfully!"
  }
  ```

### 2. **Get a Random Question**
- **Endpoint**: `GET /api/quiz/question`
- **Description**: Fetches a random multiple-choice question from the database.
- **Response**:
  ```json
  {
    "questionId": 1,
    "questionText": "What is the capital of France?",
    "options": ["Paris", "Berlin", "Rome", "Madrid"]
  }
  ```

### 3. **Submit an Answer**
- **Endpoint**: `POST /api/quiz/answer`
- **Description**: Submits an answer for a given question and checks correctness.
- **Request Body**:
  ```json
  {
    "questionId": 1,
    "selectedOption": "Paris"
  }
  ```
- **Response**:
  ```json
  {
    "correct": true,
    "message": "Correct answer!"
  }
  ```

### 4. **Get Quiz Summary**
- **Endpoint**: `GET /api/quiz/summary`
- **Description**: Returns a summary of the quiz session with details of questions answered.
- **Response**:
  ```json
  {
    "totalQuestionsAnswered": 5,
    "correctAnswers": 3,
    "incorrectAnswers": 2
  }
  ```

---

## Database Details
- **H2 Database**: Used as an in-memory database.
- **Schema and Data**:
  - The database is pre-loaded with:
    - A single user.
    - A small set of questions with multiple-choice answers.

---

## Sample Questions in Database
| Question ID | Question Text                          | Options                                   | Correct Answer |
|-------------|----------------------------------------|------------------------------------------|----------------|
| 1           | What is the capital of France?         | Paris, Berlin, Rome, Madrid              | Paris          |
| 2           | Which planet is known as the Red Planet?| Mars, Venus, Earth, Jupiter             | Mars           |

---

## Notes
- Feel free to extend the database schema or add features as needed.
- Contact me for any clarifications or issues at `<your email>`.

---

## Future Enhancements
- Add user authentication.
- Allow multiple users to take quizzes.
- Include a front-end for better user experience.

---

This structure ensures clarity, simplicity, and completeness, making it easy for evaluators to understand and run your project.

### Start Page

![Start Page](https://raw.githubusercontent.com/DevRezaur/spring-boot-quiz-app/main/screenshots/Start%20Page.PNG)

### Quiz Page

![Quiz Page 1](https://raw.githubusercontent.com/DevRezaur/spring-boot-quiz-app/main/screenshots/Quiz%20Page%201.PNG)

![Quiz Page 2](https://raw.githubusercontent.com/DevRezaur/spring-boot-quiz-app/main/screenshots/Quiz%20Page%202.PNG)

### Result Page

![Result Page](https://raw.githubusercontent.com/DevRezaur/spring-boot-quiz-app/main/screenshots/Result%20Page.PNG)

### Score Board

![Score Board](https://raw.githubusercontent.com/DevRezaur/spring-boot-quiz-app/main/screenshots/Score%20Board.PNG)

---

### Have a nice day
