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