# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using React, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

*EDIT: Frontend is now written in React with the command to run `npm start`*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
the helper file create_router of the server which calls the createRouter function

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
client is sending requests and receiving data from the server, the server is directing these requests with its routes and interacts with the database to return data.

3. What are the the responsibilities of server.js?
maintaining connections with the db and the client, receiving requests and directing them

4. What are the responsibilities of the `gamesRouter`?
it is actually carrying out the server interactions and returning data in json format

5. What process does the the client (front-end) use to communicate with the server?
it is using the GamesService file to carry out fetch calls via get, post and delete methods

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
optional parameter is an init object which is an object that can be applied to the request. It can have a method, headers, body etc. In this app it is being used to post a newgame object and to delete game objects.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
router.get('/'), post, delete

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
enables node apps to communicate with the mongo db, can handle promises and callbacks as it supports the  javascript api which is asynchronous

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?
its the unique identifier for storage in the db, like id in SQL, which is essential for ensuring that every object in the db is unique and can be targeted individually.

Add to your diagram the dataflow for removing a game.
