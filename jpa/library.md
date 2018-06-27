# Library Pair Programming Activity

## Objectives

-   Wire up a JPA enabled web application that will control entities for courses, topics and textbooks
-   Students will use **Object Relational Mapping (ORM)** to connect entities together
-   Students will complete this activity in a pair-programming setting where one is always "driving" and one is "directing"
-   Students will create the following relationships:
    -   `@OneToMany`
    -   `@ManyToOne`
    -   `@ManyToMany`

## Setup

Use the [Spring Initializr](https://start.spring.io) to create a `library-restructure` project, including the following dependencies:

-   Devtools
-   Web
-   Thymeleaf
-   JPA
-   H2

## The Project Explanation

The Columbus Metropolitan Library has gotten so overwhelmed with new material that they have just totally lost track of all of their books. Today we are going to help them by making a system that they can use to input and track books by authors or genre.

## Entities

You are encouraged to expand these tables with more options.

### The `Genre` Table

| id  | genre       |
| --- | ----------- |
| 1   | Fiction     |
| 2   | Non Fiction |
| 3   | Mystery     |
| 4   | Technology  |

### The `Author` Table

| id  | firstName  | lastName |
| --- | ---------- | -------- |
| 1   | Kathy      | Sierra   |
| 2   | Bert       | Bates    |
| 3   | Elisabeth  | Freeman  |
| 4   | Clifford   | Stoll    |
| 5   | Steven D.  | Levitt   |
| 6   | Stephen J. | Dubner   |

### The `Book` Table

| id  | title                      | authors | genre |
| --- | -------------------------- | ------- | ----- |
| 1   | Head First Design Patterns | 1, 2    | 4     |
| 2   | Head First Java            | 1, 3    | 4     |
| 3   | The Cukoo's Egg            | 4       | 1     |
| 4   | Freakonomics               | 5, 6    | 2     |

## Backend

### Repository

Next, we need to build out `Repository`s to be able to store entities in our actual databases. Remeber what type of `Object` a `Repository` should be. Also, think about how many we will need.

### Populator

Following the `Repository`, we need to build out our databases tables. So we need a `Populator` to add elements to their respective `Repository`.

### Controller

We are going to add routes to _all_ books, _a_ book, _all_ authors, _all_ genres, and home ("/"). Home should redirect you to the route for _all_ books.

## Frontend

### HTML

We will need to create `Thymeleaf` templates for each view in our `templates` directory. Make sure your semantics are correct for all information. Add navigation to the `<header>` element on all pages to navigate around your application.

### CSS

Add appropriate `CSS` for layout and styling of your `HTML` elements.

### JS

Optionally, include some `JS` to make this information interactive. It is _cough cough_ **heavily** suggested you add some **useful** `JS`. Look to examples in previous projects and creatively use `JS`.

## TDD

### The tests to build out this application

Make sure to appropriately test your `Java` (to include Spring elements) and `JS` (So please include Jasmine where it is appropriate). Look back at previous projects to see examples of what you should be doing.

Time to roll the dice...
