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


# EPIC_2 : Categorize questions

**As** AI developer 
**I want** categorize training questions according to predefined topics 
**To** structure the learning process in a better way and increase the accuracy of the model

### Assumptions

It is assumed that the training model does not have questions categorized according to predefined topics

### Validations

- How are the questions currently organized? Under what criteria?
- Do you have categories and/or subcategories to classify the questions?
- Based on the history of questions, what are the most common topics?
- Have you previously tried to implement categorization of questions? If so, how did you do it and what was the result?

## REQUIREMENTS

## Functional Requirements

### EPIC_2_REQ_01:

**As** AI developer
**I want** to define a clear and structured list of topics to categorize questions
**To** improve the organization, retrieval, and classification of training data

#### Purpose

The system should provide a predefined, structured list of topics to categorize training questions efficiently

### Tasks

#### Task_01: Create a predefined list of topics and subtopics based on the subject matter

**_Solution_**

```bash
defineTopicList(topics: list<string>) → boolean
```

```bash
assignTopicToQuestion(questionId: int, topicId: int) → boolean
```

**_Outcome_**

- Ensures consistency, improves data organization, and enhances the accuracy of the AI model by grouping related questions under well-defined topics.


#### Task_02: Store and manage the topic list in a structured format

**_Solution_**

```bash
storeTopicList(topics: list<object>) → boolean
```

```bash
updateTopic(topicId: int, newName: string, parentTopicId: int) → boolean
```

```bash
getTopicList() → list<object>
```

_**Outcome**_

- Efficient storage and retrieval of topic lists in a structured format

### EPIC_2_REQ_02:

**As** AI developer
**I want** to ensure that the model classifies questions correctly
**To** improve the accuracy and consistency of topic categorization.

####  Purpose

Ensure that the model correctly classifies questions into predefined categories, improving structured learning and optimizing training accuracy.

### Tasks

#### Task_01: Implement an evaluation mechanism to measure and validate the model’s classification accuracy

**_Solution_**

```bash
preprocessQuestion(questionText: string) → string
```

```bash
extractFeatures(questionText: string) → vector
```

```bash
classifyQuestion(questionText: string) → topicId
```

```bash
evaluateModel(predictions: list<int>, groundTruth: list<int>) → dict
```

_**Outcome**_

- Automated classification enabling real-time assignment of questions to correct topics.

### EPIC_2_REQ_03:

**As** AI developer
**I want** the system to provide an interface for categorizing training questions
**To** streamline the organization and management of the training dataset

#### Purpose

Provide an interface that allows users to categorize training questions efficiently, ensuring structured organization and better learning outcomes.

### Tasks

#### Task_01: Design and implement a graphical user interface (GUI) for categorizing and reviewing training questions

**_Solution_**

```bash
renderCategoryInterface(containerId: string) → void
```

```bash
assignCategoryToQuestion(questionId: int, categoryIds: list<int>) → boolean
```

```bash
fetchQuestionsByCategory(categoryId: int) → list<object>
```

```bash
updateQuestionCategory(questionId: int, categoryIds: list<int>) → boolean
```

**_Outcome_**

- User-friendly interface for efficiently categorizing training questions.

## System Requirements

### EPIC_2_REQ_04:

**As** AI developer
**I want** to implement a system that organizes and stores queries in a searchable and efficient 
**To** make them easily searchable and efficient

#### Purpose

Implement a system that efficiently organizes and stores training questions, ensuring fast retrieval, categorization, and searchability to support structured learning and model training.

### Tasks

#### Task_01: Implement Database Functions for Question Storage and Retrieval

**_Solution_**

```bash
storeQuestion(questionText: string, categoryId: int) → int
```

```bash
searchQuestions(query: string, categoryId: int, limit: int, offset: int) → list<object>
```

```bash
updateQuestion(questionId: int, questionText: string, categoryId: int) → boolean
```

```bash
deleteQuestion(questionId: int) → boolean
```

**_Outcome_**

- Structured and efficient storage of questions.
- CRUD operations for question management ensuring flexibility.

#### Task_02: Develop API for Managing Questions

_**Solution**_

**API Endpoints**

- Create Question: _**POST /questions**_ 
- Search Questions: _**GET /questions?query=text&category=1**_ 
- Update Question: **_PUT /questions/:id_** 
- Delete Question: **_DELETE /questions/:id_** 

_**Outcome**_

- Efficient categorization for structured organization.
- External accessibility for question management via API.


# EPIC_3: Ensure that the data used is “balanced”

**As** AI developer 
**I want** Investigate the data used to train the model to identify possible unbalanced or biased data 
**To** ensure that the model is accurate and optimal

### Assumptions

It is assumed that there is no system to identify if there is any bias or “unbalance” in the data used for training.

### Validations

- How do you perform mass data collection?
- Do you currently have a system for identifying and depuration of the data?
- Have you identified any technical challenges when using web scraping? Describe.
- How do you currently handle the process of frequent data updates? Does it require additional infrastructure?
- Have you faced any security risks due to the use of web scraping? Explain.
- What kind of biases are considered most critical?
- Which biases can be omitted and under which criteria?
- Have you tried to implement a system that identifies and classifies data biases according to their impact? If so, how did you do it and what was the result?
