# Reviews Site, Full Stack

## Overview

Return to your reviews site from the [previous exercise](../reviews-site) (or create another). All requirements from the previous project still apply. If these aren't present, you will lose points.

## Creating a new repository from an existing one

If you are continuing with your reviews site from the previous exercise, create a new branch for the project. Inside of your project directory in your command line, type the following: `git checkout -b new-branch-name`. (replace 'new-branch-name' with an actual descriptive name)

You can now look at the branches you have with `git branch` and you can switch between branches with `git checkout branch-name` (Make sure to `git add .` and `git commit -m "whatever your message is"` first!)

We're going to add categories to reviews. Each category will have one or more reviews (a one to many relationship). Each review will be assigned to one category (a many to one relationship).

Also, we're going to JPA-enable your site so that it writes/reads from an H2 database.

## Tasks

Feel free to use appropriate class names other than `Review` and `Category`, but these instructions will refer to `Review` and `Category`.

*   Add the following dependencies to `build.gradle` (or use [Spring Initializr](https://start.spring.io/) to create a new `build.gradle`)
    *   [ ] JPA (spring-boot-starter-data-jpa)
    *   [ ] H2
*   Create a `Category` class that:
    *   [ ] is a JPA entity.
    *   [ ] contains an instance variable referencing the `Review`s it contains.
    *   [ ] configures an appropriate JPA relationship to its reviews.
*   Update the `Review` class such that:
    *   [ ] it is a JPA entity.
    *   [ ] configures a JPA relationship to its associated category.
    *   [ ] allows for a description/content/body longer than 255 characters.
*   Update your view (templates/html/css) such that:
    *   [ ] there is a page that lists review categories, each of which links to the (details) page for a specific category.
    *   [ ] there is a page that lists the reviews for a chosen category, each of which links to the (details) page for a specific review.
    *   [ ] each review detail page has a link to the page for its category.

### Stretch Tasks

#### Tags

*   [ ] Create a `Tag` entity.
*   [ ] Update `Review` so that it can have tags associated with it. A review can have many tags, a tag can be assigned to many reviews.
*   [ ] Display tags on the review details page.
*   [ ] Create a page that displays links to all of the reviews associated with a given tag.

##### Stretchier

*   [ ] Style your tags list template as a _tag cloud_, making tags which appear more often larger and/or bolder and those that appear less often smaller and/or lower weight.
*   [ ] Allow creation and deletion of tags from a review using `<form>` and `<button>` elements along with the appropriate controller method(s).

## Grading

Find the rubric [here](./rubric.md).

### Tips

#### Start with the known specifics

Start with mapping and displaying your `Review`s. Add `Category`s to them after you've gotten that working.

#### Mapping out URLs, Model attributes, view template names, etc

It is good practice to map things out and think them through, using plural and singular names appropriately, or you'll likely be well confused.

Your names, etc will be different, but hopefully this helps with some of the confusion I've seen around naming and what is in the model for a specific view. I'll append model and view to names to help clarify, though we usually wouldn't do this in the wild. Create your _own_ table that maps these things out:

| Page Intent                                                           | URL (mapped via @RequestMapping) | Description of model attribute             | Model Attribute       | Retrieved via  | View will display                                                                      | View Template name   |
| --------------------------------------------------------------------- | -------------------------------- | ------------------------------------------ | --------------------- | -------------- | -------------------------------------------------------------------------------------- | -------------------- |
| Categories List                                                       | /categories                      | an `Iterable` of all `Category` objects    | "categoriesModel"     | repo `findAll` | list of categories                                                                     | "categoriesView"     |
| Category details, including a list of reviews for the chosen category | /category?id=42                  | the `Category` object associated with `id` | "singleCategoryModel" | repo `findOne` | category detail and list of reviews for that category, each of which links to a review | "singleCategoryView" |
| Review details                                                        | /review?id=86                    | the `Review` object associated with `id`   | "reviewModel"         | repo `findOne` | review details                                                                         | "reviewView"         |

#### String fields longer than 255 characters

For instance variables that hold things like descriptions, which may be longer than 255 characters, you will need to indicate that this should be stored in a CLOB (Character Large OBject). To do, this use the `@Lob` annotation on your instance variable, like so:

```java
@Lob
private String description;
```

See [LOBs, BLOBs, CLOBs and Serialization](https://en.wikibooks.org/wiki/Java_Persistence/Basic_Attributes#LOBs.2C_BLOBs.2C_CLOBs_and_Serialization) in the Java Persistence wikibook.
