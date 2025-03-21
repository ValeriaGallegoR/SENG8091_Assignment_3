# EPIC_1 : Separate questions and answers

**As** AI developer
**I want** separate training questions from answers 
**To** facilitate the ability to evaluate and validate knowledge thus identifying areas for improvement

### Assumptions

Assume that the training model does not currently have a separate question and answer structure.

### Validations

- Describe how the training model is currently managed
- Are the questions separated from the answers?
- How do you differentiate questions from answers? Explain how you identify and what format you use.
- What are the criteria for separating questions from answers?
- How to identify that the answers correspond to the questions?
- Have you previously tried to implement this mechanism? If so, how did you do it and what was the result?

## REQUIREMENTS

## Functional Requirements

### EPIC_1_REQ_01:

**As** AI developer
**I want** to define a format for storing data that separates questions and answers
**To** improve data organization

#### Purpose

Define a format for storing data where questions and answers are clearly separated to ensure structured organization, easy retrieval, and efficient data management.

### Tasks

#### Task_01: Implement a data structure that distinctly separates questions and answers

**_Solution_**

```bash
storeQuestion(questionText: string) → questionId
```

```bash
storeAnswer(questionId: int, answerText: string) → answerId
```

```bash
getQuestionById(questionId: int) → string
```

```bash
getAnswersByQuestionId(questionId: int) → list<string>
```

_**Outcome**_

- A structured and normalized data format ensuring a clear separation between questions and answers.
- Efficient retrieval through unique identifiers (**id**, **question_id**).

### EPIC_1_REQ_02:

**As** AI developer
**I want** the system to establish a mechanism to link questions to the correct answers
**To** ensure that each question is matched with the correct answer

#### Purpose

Establish a mechanism to link questions with their correct answers, ensuring data integrity and efficient retrieval.

### Tasks

#### Task_01: Implement a function to create and store associations between questions and their corresponding answers

_**Solution**_

```bash
linkAnswerToQuestion(questionId: int, answerId: int) → boolean
```

```bash
getCorrectAnswerByQuestionId(questionId: int) → string
```

```bash
validateAnswer(questionId: int, answerId: int) → boolean
```

_**Outcome**_

- Clear linkage between questions and their correct answers through unique identifiers (**question_id**).

### EPIC_1_REQ_03:

**As** a AI developer
**I want** to have a graphical interface 
**To** manage training questions and answers

#### Purpose

Develop a graphical interface (GUI) that allows users to create, update, delete, and manage questions and answers efficiently.

### Tasks

#### Task_01: Develop a graphical interface to manage the questions and answers

**_Solution

Frontend_**

- QuestionForm: Form for adding/editing questions
- AnswerForm: Form for adding/editing answers
- QuestionList: Displays a list of questions
- AnswerList: Displays associated answers

_**Outcome**_

- Interactive GUI for managing questions and answers

## System Requirements

### EPIC_1_REQ_04:

**As** AI developer
**I want** the system to be optimized to handle large data sets of training questions and answers
**To** ensure fast data processing, minimize latency and support scalability.

#### Purpose

Optimize system performance to efficiently handle large datasets of training questions and answers, ensuring fast retrieval, storage, and processing.

### Tasks

#### Task_01: Implement performance optimizations to handle large volumes of training data efficiently

**_Solution_**

```bash
fetchQuestionsPaginated(limit: int, offset: int) → list<object>
```

```bash
cacheQuestionData(questionId: int) → boolean
```

```bash
batchInsertAnswers(answers: list<object>) → boolean
```

```bash
optimizeDatabaseIndexes() → void
```

_**Outcome**_

- Faster query execution through indexing and optimized queries.
- Reduced database load with caching and asynchronous processing.

### EPIC_1_REQ_05:

**As** AI developer
**I want** to develop a REST or GraphQL API for CRUD operations on questions and answers
**To** enable efficient management, retrieval and modification of training data in the system

#### Purpose

Develop a REST or GraphQL API to enable CRUD (Create, Read, Update, Delete) operations for managing questions and answers, allowing seamless interaction between the frontend and the backend.

### Tasks

#### Task_01: Develop a REST API or GraphQL API for CRUD operations on questions and answers

**_Solution

Backend_**

```bash
createQuestionWithAnswers(questionText: string, answers: list<string>) → object
```

```bash
getQuestionWithAnswers(questionId: int) → object
```

```bash
updateQuestionAnswer(questionId: int, questionText: string, answers: list<object>) → boolean
```

```bash
deleteQuestionWithAnswers(questionId: int) → boolean
```

_**Outcome**_

- RESTful or GraphQL API enables easy management of questions and answers.
- Scalability to support complex CRUD operations and filtering.