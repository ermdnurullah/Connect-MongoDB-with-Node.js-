# Connect MongoDB with Node.js Using Mongoose
```
connect-mongodb-with-node-js-using-mongoose
```
In this tutorial,  You will get the best and common way to Connect MongoDB with Node.js using Mongoose. Even you will get the mongoose script for MongoDB connection and will also learn a simple way to use it.

All the pieces of information on mongoose are provided in simple speaking language. So, It is also easy to understand. Hence, It is necessary to know the given information before stabilizing the MongoDB database connection.

Node.js - MongoDB Connection Using Mongoose

Mongoose:

Mongoose is an object modeling of MongoDB.
It is mainly used with Node.js to manipulate & retrieve the MongoDB data.
It provides the best solution to model our application data based on Schema.
Even, We can easily develop our application data using its built-in query building, type casting, validation, business logic hooks & more.
You will know more about mongoose through the following official documentation URL

Read Mongoose Doc

Basic Configuration

Before getting started with Node.js MongoDB Connection, you must do the following things

You must install MongoDB on your computer.
Even, You must install Node.js or Express Application.
After Installing Express Application, You will get the following folder structure
myapp/
  |__bin/
  |__node_modules/
  |__public/
  |__routes/
  |__views/
  |__database.js
  |__package-lock.json
  |__package.json


Install the Mongoose Module

First of all, Install the Mongoose  in the Express App folder  myapp through the following command.

npm install mongoose
Create a MongoDB Database

Create a MongoDB database through the following steps:-

Install MongoDB Compass on your computer.
Open MongoDB Compass & create a test database.
Create a database URL for localhost as

URL syntax -

mongodb://localhost:27017/databaseName

URL Example -

mongodb://localhost:27017/test

The next step will learn you to connect MongoDB with Node.js using the above database URL.

Connect MongoDB with Node.js using Mongoose

To connect MongoDB with Node.js, you have to configure it according to the following steps -

Create database.js file in the root folder of the express application.
Include Mongoose module
call connection method with the localhost port & database name
Call on method with connection variable
At last, export the connection

File Name - database.js

var mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/test', {useNewUrlParser: true});
var conn = mongoose.connection;
conn.on('connected', function() {
    console.log('database is connected successfully');
});
conn.on('disconnected',function(){
    console.log('database is disconnected successfully');
})
conn.on('error', console.error.bind(console, 'connection error:'));
module.exports = conn;

Now you can use the script of the above file anywhere in your application. But make sure that your database name is already created in the mongo compass. If you miss anything in this script, it will not work and produce an error.

Use Node.js MongoDB Connection Script

You can use database.js file in multiple files by including them with require() the module.

Suppose that you have to use database.js the file in routes/index.js, you will have to include it as  require('../database');

This example is enough to understand the MongoDB connection. Now, you can easily set up it and make a lightweight application.

I have shared various tutorials related to MongoDB on this website, you can implement them for your better understanding of Mongo connection with Node.js.

My Suggestion

Dear developers, I hope you have understood the above script, Now you are able to stabilize the Node.js MongoDB connection.

I will share more tutorials on Node.js/Express asap. So, Continue to visit this website.If you have any doubts or questions. You can directly ask me through the below comment box.
