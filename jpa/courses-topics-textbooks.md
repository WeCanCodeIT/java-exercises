# JPA enabled courses-topics-textbooks

## Objectives

-   Wire up a JPA enabled web application that will control entities for courses, topics and textbooks
-   Introduction to test driving a JPA enabled app
-   Develop an understanding of the annotations used to create the proper entity relationships

## Setup

Use the [Spring Initializr](https://start.spring.io) to create a `courses-topics-textbooks-jpa` project, including the following dependencies:

-   Devtools
-   Web
-   Thymeleaf
-   JPA
-   H2

## The Project Explanation

Schools in session! We want to create a listing of courses that students can choose from this semester. We also want to create the topics that will be covered as well as the required texts for each course. All of this information should be kept in a relational database so that we can not only keep track of it but persist it in our application. We need to use TDD to test drive the creation of all necessary components.

## Entities

### The `Course` Table

A list of `Course`s

| id  | name                              | description   |
| --- | --------------------------------- | ------------- |
| 1   | "Intro to Java"                   | "description" |
| 2   | "Intro to the Spring Framework    | "description" |
| 3   | "Advanced Software Design"        | "description" |
| 4   | "Introduction to HTML, CSS, & JS" | "description" |

### The `Topic` Table

A `Topic` can exist in multiple different `Course`s since we build on material through them.

| id  | topic    | `Course` |
| --- | -------- | -------- |
| 1   | Java     | 1, 2, 3  |
| 2   | Spring   | 2, 3     |
| 3   | TDD      | 3, 4     |
| 4   | Frontend | 4        |

### The `Textbook` Table

A `Textbook` has a name and and can be utilized in a number of different `Course`s.

| id  | title                      | `Course` |
| --- | -------------------------- | -------- |
| 1   | Head First Java            | 1        |
| 2   | Head First Design Patterns | 3        |
| 3   | Clean Code                 | 2, 3, 4  |
| 4   | Intro to JPA               | 2        |
| 5   | JavaScript: The Good Parts | 4        |

## Backend

### Repository

Next, we need to build out `Repository`s to be able to store entities in our actual databases. Remeber what type of `Object` a `Repository` should be. Also, think about how many we will need.

### Populator

Following the `Repository`, we need a way to add `Course`s, `Topic`s, and `Textbook`s. So we need to build a `Populator` to add elements to their respective `Repository`.

### Controller

Finally, we need a way to link our backend and frontend so that we can pass this data between the two. Our `Controller` should house methods that route to a page for all `Course`s as well as to an individual `Course`. Optionally, you can include a route to a homepage as well. This should target the `/` location in our browser.

## Frontend

### HTML

We will need to create `Thymeleaf` templates for each view in our `templates` directory. Make sure your semantics are correct for all information.

### CSS

Add `CSS` for layout and styling of your `HTML` elements.

### JS

Optionally, include some `JS` to make this information interactive. Maybe by filtering `Topics` or `Textbooks`? Or adding a dropdown menu for navigation.

## TDD

### The tests to build out this application

These test should be added in conjunction to other frontend testing you should already be familiar with in Spring and JS.

We will write the following unit tests to drive the creation of this project:

-   save and load a topic
-   generate a topic id
-   save and load a course
-   save a textbook to a particular course
-   establish course to topics relationship
-   establish topic to courses relationship
-   find courses for a topic
-   find courses for a particular topic id
