# Artists and Albums

## Overview

We have been tasked with building an archive of all the best music and providing it to our users. We need to compile a database that will keep track of our favorite musicians and all of their work. For this job we need to build out an API that we can access to build out an application using JavaScript and AJAX.

## Structure

### Artists

Each `Artist` will need:

-   [] `name`
-   [] `albums`
-   [] `recordLabel`

### Albums

Each `Album` will need:

-   [] `albumName`
-   [] `releaseDate`
-   [] `songs`
-   [] `genre`
-   [] `coverImage`

### Songs

Each `Song` will need:

-   [] `songName`
-   [] `length`
-   [] `lyrics`
-   [] `videoUrl` (optional)
-   [] `rating`

## Tasks

We are going to want our users to be able to interact with information on our database so we will need to include inputs that will be able to add, update, and delete `Artist`s, `Album`s, and `Song`s from our database. We will need a page to display each piece of data that we're interacting with so, for example, we will need a page to display all `Artist`s. When we click an `Artist`, we will see a page that lists all of their `Album`s. When we click and `Album` we will see all `Song`s. Finally, when we click a `Song` we will see everything associated with that `Song`.

Users should also be able to add comments to `Song`s as well as `Album`s.

Users should be able to update lyrics similar to being able to update entries on wikis.

Design a robust, responsive frontend so our users have an intuitive, enjoyable experience.

## Stretch

### Band

Each `Band` will need:

-   [] `bandName`
-   [] `artists`
-   [] `albums`
-   [] `merchandise`

Users should be able to add comments to `Band`s

### Ratings

Make ratings interactive by letting users leave a rating for a given song and then displaying the `Song`s rating as the average of ratings left by users.
