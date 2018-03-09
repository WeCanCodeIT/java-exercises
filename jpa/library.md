# Library Pair Programming/ Mobbing Activity

## Objectives

- Students will use **Object Relational Mapping (ORM)** to connect entities together 
- Students will become familiar with the tools of the CRUD Repository
- Students will create data to test by @Override of the run method of CommandLineRunner
- Students will complete this activity in a pair-programming setting or mobbing where one is always "driving" and one is "directing"
- Students will create the following relationships:
  -`@OneToMany`
  -`@ManyToOne`
  -`@ManyToMany`


## Setup

Use the [Spring Initializr](https://start.spring.io) to create a `library-jpa` project, including the following dependencies:
- Thymeleaf
- JPA
- H2
- Devtools

## The Project Explanation

Libraries categorize books by `Genre`. A `Book` can only belong to one `Genre` in our Library. Some of our authors are busy and they have written multiple books. An `Author` can also share duties, so multiple authors can write a single book. 

### The `Genre` Table

|genre|
|----|
|Fiction|
|Non Fiction|

### The `Author` Table

|firstName|lastName|
|----|--------|
|Kathy|Sierra|
|Bert|Bates|
|Elisabeth|Freeman|
|Clifford|Stoll|

### The `Book` Table

|genre|title|authors|
|----|--------|---|
|Non Fiction|Head First Design Patterns|Kathy Sierra, Bert Bates|
|Non Fiction|Head First Java|Kathy Sierra, Elisabeth Freeman|
|Fiction|The Cukoo's Egg|Clifford Stoll|

### Determine your relationships

- One of our tables has a `@OneToMany` relationship.
- One of our tables has a `@ManyToMany` relationship.
- One of our tables has both a `@ManyToOne` and a `@ManyToMany` relationship.

## Build out the necessary files

- An `@Entity` class for each table
- A repository for each table
- One or more `@Controller`s that handles requests
- Each response should be a view rendered by one of the Thymeleaf templates `genres.html`, `authors.html`, or `books.html`
- A populator to populate the database

### Hints

- The `@OneToMany` relationship will need to be `mappedBy`
- The non-owning side of your `@ManyToMany` relationship will need to be `mappedBy`. Remember that in the case of a simple many-to-many relationship, deciding the "owning" side is arbitrary, chosen for convenience based on context.
- In addition any other needful parameters, your `Book` constructor should handle multiple authors. It should look similar to this:

  ```java
  public Book(Foo foo, Bar bar, FooBar ... fooBar){
      this.foo = foo;
      this.bar = bar;
      this.fooBar = new HashSet<>(Arrays.asList(fooBar));
  }
  ```
- Remember, you can perform concatentation in Thymeleaf using the `+` operator. Use single quotes (`'`) to enclose Strings if you used double quotes (`"`) to enclose your `th:text` attribute value (or vice versa):
  ```xml
  <p th:text="${'Name: ' + item.firstName + ' ' + item.lastName}" />
  ```
- Or… Use literal substitutions:
  ```xml
  <p th:text="|Name: ${item.firstName} ${item.lastName}|" />
  ```

- Your view for `Genre` will simply list the genres.
- Your view for `Author` will simply list the names of our authors.
- Your view for `Book` will display genre, title, and author.