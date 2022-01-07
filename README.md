# Twine Movies API
This project is a code challenge from twine where I should build an API for: movies / person

## Checklist

- [x] Create an API using nodeJS, typescript and express
- [x] Create a model (table) for "Movie"
- [x] Create a model (table) for "Person"
- [x] Create a model (table) for "Role"
- [x] Create a model (table) for the relationship between movie, person and role
- [x] Create an interface for each model
- [x] Create the structure (Controllers, middlewares, models and services)

## Technologies
NodeJS, Typescript,express, Prisma (for MYSQL), JWT, Swagger

I decided to use Typescript insted of Ecmasript because I think it is easier to understand the code once I have used classes for everything an data types. for example: I had to deal with movies information so, I've created a Movies Inferface which holds each type of each property of the movie (id:integer, title:string, release_year:integer)

Talking about the database, I decided to use a relational database because it is easier to deal with the relations between people, movies and roles, so I've created a table for the roles and I've also created a seed to insert the roles into the database because it is not possible to create new roles (you only have 3 possible roles in this challenge). I've created another table for the people, another for the movies and a last one for the users

JWT is used to create users, generate token and authorize users to make POST, PUT and delete requests

## Structure

I tried to build this API using some SOLID principles so I have a class for every specific thing.
I also divided the foldes into controllers and services, basically to separate the responsability of connecting to the database and treating the data.

## Benefits of the structure

Using this structure (Application / Database) and the solid principles, I could make thinks like: allow you to create a new person while creating a movie (if you do not use an ID inside the body but pass the informations "first_name", "last_name" and "aliases", a new person should be created)

## Things I could've made in a better way but I didn't have time because I had a lot of work at the other company
I know there are a lot of things in this API that could be better, like:
- Creating an Error handler class to handle some errors I know that could happen
- Returning right HTTP CODES for every single requests

## How to use:
- Clone the repository
- create a ".env" file in your root directory an put "DATABASE_URL", "PORT", "SALT_KEY" as below
- cofigure the DATABASE_URL with true infromation
   ```
    DATABASE_URL="mysql://user:password@host:port/database?schema=public"
    PORT=3333
    SALT_KEY=Qwedsazxc-cxzdsaewQ
   ```

    use "npm install" to install the dependencies
    use "npm run config-prisma" to configure the database
    use "npm run dev" to run the project

- To make sure the API is running, make a request to "localhost:3333/roles".

The endpoints can be found [here](https://www.postman.com/samdev18/workspace/twine/overview).

I recommend you to first use the "Create User" endpoint

once you create you user, you will retrieve a token, you have to insert this token in the Authorization Bearer token header to make POST, PUT and DELETE requests. 

