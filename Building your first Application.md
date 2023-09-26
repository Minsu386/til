
- mkdir
- cd into dir
- npm init -y
	- create package.json file
- git init
- npm i pg sequelize express
	- 3 libraries you'll need for your application   Postgres, Sequelize, Express.
- npm i nodemon --save-dev
	- 1  for a developer.
- touch server.js

Open server.js with your choice of editor
- code .

Edit package.json script
- can take out test for now
- add in 
	- "start:dev": "nodemon server"
- in terminal
	- npm run start:dev
- in server.js. console.log('hello world') 
	- to test connection

## Start Express Server and Sequelize
----
```JavaScript
const Sequelize = require('sequelize');
const conn = new Sequelize('postgres://localhost/todo_db');
  

const express = require('express');
const app = express();

const port = process.env.PORT || 3000;

app.listen(port, async() => {
	try {
		console.log(`listening on port ${port}`);
		await conn.sync({ force: true}); // will wipe tables in database
		console.log('connected');
	}
	catch(err) {
		console.log(err)
	}
});
```
  
create database 
	can use postico, psql, or command line
	cmdline - `createdb <database>`
	psql - `CREATE DATABASE <database>;`

## Create Data Layer
----
```JavaScript
const Sequelize = require('sequelize');

const conn = new Sequelize('postgres://localhost/todo_db');

  

// Models

const Todo = conn.define('todo', {

// creates columns

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  
  
  

const express = require('express');

const app = express();

  

const port = process.env.PORT || 3000;

  

app.listen(port, async() => {

try {

console.log(`listening on port ${port}`);

await conn.sync({ force: true}); // will wipe tables in database

console.log('--Database connected--');

/* ----- if order of creation is not important, place in promise.all

await Todo.create({ name: 'walk the dog'});

await Todo.create({ name: 'buy chew toy'});

*/

await Promise.all([

Todo.create({ name: 'walk the dog'}),

Todo.create({ name: 'buy chew toy'}),

Todo.create({ name: 'Learn React'}),

Todo.create({ name: 'take out garbage'}),

  

]);

console.log('--Database seeded--');

}

catch(err) {

console.log(err)

}

});
```

`touch .gitignore`  in cmd line to create .gitignore file
`echo node_modules >> .gitignore`  -- ignores the node_module on git status

## Add Routes
----
```JavaScript
const Sequelize = require('sequelize');

const conn = new Sequelize('postgres://localhost/todo_db');

  

// Models

const Todo = conn.define('todo', {

// creates columns

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  
  
  

const express = require('express');

const app = express();

  
  

// Routes

app.get('/', (req, res) => res.redirect('/todos'));

  

app.get('/todos', async(req, res, next) => {

try {

const todos = await Todo.findAll();

// test output with below statement

// res.send(todos);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1>Todos</h1>

<ul>

${

todos.map( todo => {

return `

<li>

<a href='/todos/${todo.id}'>

${todo.name}

</a>

</li>

`

}).join('') // expression not statement do not put a ;

}

</ul>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  
  

const port = process.env.PORT || 3000;

  

app.listen(port, async() => {

try {

console.log(`listening on port ${port}`);

await conn.sync({ force: true}); // will wipe tables in database

console.log('--Database connected--');

/* ----- if order of creation is not important, place in promise.all

await Todo.create({ name: 'walk the dog'});

await Todo.create({ name: 'buy chew toy'});

*/

await Promise.all([

Todo.create({ name: 'walk the dog'}),

Todo.create({ name: 'buy chew toy'}),

Todo.create({ name: 'Learn React'}),

Todo.create({ name: 'take out garbage'}),

  

]);

console.log('--Database seeded--');

}

catch(err) {

console.log(err)

}

});
```

git commit  often. If you add more and your app breaks revert back to known working condition
- `git checkout .`
	anything not comitted , git will get rid of. 

## Detail View
----
```JavaScript
const Sequelize = require('sequelize');

const conn = new Sequelize('postgres://localhost/todo_db');

  

// Models

const Todo = conn.define('todo', {

// creates columns

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  
  
  

const express = require('express');

const app = express();

  
  

// Routes

app.get('/', (req, res) => res.redirect('/todos'));

  

app.get('/todos', async(req, res, next) => {

try {

const todos = await Todo.findAll();

// test output with below statement

// res.send(todos);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1>Todos</h1>

<ul>

${

todos.map( todo => {

return `

<li>

<a href='/todos/${todo.id}'>

${todo.name}

</a>

</li>

`

}).join('') // expression not statement do not put a ;

}

</ul>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  

app.get('/todos/:id', async(req, res, next) => {

try {

const todo = await Todo.findByPk(req.params.id);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1><a href='/todos'>Todos</a></h1>

<h2>${todo.name}</h2>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  
  

const port = process.env.PORT || 3000;

  

app.listen(port, async() => {

try {

console.log(`listening on port ${port}`);

await conn.sync({ force: true}); // will wipe tables in database

console.log('--Database connected--');

/* ----- if order of creation is not important, place in promise.all

await Todo.create({ name: 'walk the dog'});

await Todo.create({ name: 'buy chew toy'});

*/

await Promise.all([

Todo.create({ name: 'walk the dog'}),

Todo.create({ name: 'buy chew toy'}),

Todo.create({ name: 'Learn React'}),

Todo.create({ name: 'take out garbage'}),

  

]);

console.log('--Database seeded--');

}

catch(err) {

console.log(err)

}

});
```


## create a form to input new todo
----
```JavaScript
const Sequelize = require('sequelize');

const conn = new Sequelize('postgres://localhost/todo_db');

  

// Models

const Todo = conn.define('todo', {

// creates columns

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  
  
  

const express = require('express');

const app = express();

app.use(express.urlencoded());

  

// Routes

app.get('/', (req, res) => res.redirect('/todos'));

  

app.get('/todos', async(req, res, next) => {

try {

const todos = await Todo.findAll();

// test output with below statement

// res.send(todos);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1>Todos</h1>

<a href='/todos/create'>Create A todo</a>

<ul>

${

todos.map( todo => {

return `

<li>

<a href='/todos/${todo.id}'>

${todo.name}

</a>

</li>

`

}).join('') // expression not statement do not put a ;

}

</ul>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

// Order matters. this create route is more specific then the catch of the /todos/:id route

app.get('/todos/create', async(req, res, next) => {

try {

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1><a href='/todos'>Todos</a></h1>

<form method='POST' action='/todos'>

<input name='name' />

<button>Create</button>

</form>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  

app.get('/todos/:id', async(req, res, next) => {

try {

const todo = await Todo.findByPk(req.params.id);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1><a href='/todos'>Todos</a></h1>

<h2>${todo.name} </h2>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  

app.post('/todos', async(req, res, next) => {

try {

const todo = await Todo.create(req.body);

//res.send(todo); //without middle ware this will not parse

res.redirect(`./todos/${todo.id}`)

}

catch(err) {

next(err)

}

});

  
  

// Error handling

app.use((err, req, res, next) => {

console.log(err);

res.status(500).send(err);

});

  
  

const port = process.env.PORT || 3000;

  

app.listen(port, async() => {

try {

console.log(`listening on port ${port}`);

await conn.sync({ force: true}); // will wipe tables in database

console.log('--Database connected--');

/* ----- if order of creation is not important, place in promise.all

await Todo.create({ name: 'walk the dog'});

await Todo.create({ name: 'buy chew toy'});

*/

await Promise.all([

Todo.create({ name: 'walk the dog'}),

Todo.create({ name: 'buy chew toy'}),

Todo.create({ name: 'Learn React'}),

Todo.create({ name: 'take out garbage'}),

  

]);

console.log('--Database seeded--');

}

catch(err) {

console.log(err)

}

});
```

## Added Categories table / categories to form 
---

```JavaScript
const Sequelize = require('sequelize');

const conn = new Sequelize('postgres://localhost/todo_db');

  

// Models - creates tables

const Todo = conn.define('todo', {

// creates columns

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  

const Category = conn.define('category', {

name: {

type: Sequelize.STRING,

allowNull: false,

validate: {

notEmpty: true

}

}

});

  

// create relationship between our models

Todo.belongsTo(Category);

Category.hasMany(Todo);

  

const express = require('express');

const app = express();

app.use(express.urlencoded());

  

// Routes

app.get('/', (req, res) => res.redirect('/todos'));

  

app.get('/todos', async(req, res, next) => {

try {

const todos = await Todo.findAll({

// includes allows us to access category data

include: [Category]

});

// test output with below statement

// res.send(todos);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1>Todos</h1>

<a href='/todos/create'>Create A todo</a>

<ul>

${

todos.map( todo => {

return `

<li>

<a href='/todos/${todo.id}'>

${todo.name}

</a>

(${todo.category.name})

</li>

`

}).join('') // expression not statement do not put a ;

}

</ul>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

// Order matters. this create route is more specific then the catch-all of the /todos/:id route

app.get('/todos/create', async(req, res, next) => {

try {

const categories = await Category.findAll();

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1><a href='/todos'>Todos</a></h1>

<form method='POST' action='/todos'>

<input name='name' />

<select name='categoryId'>

${

categories.map(category => {

return `

<option value='${category.id}'>${category.name}</option>

`;

}).join('')

}

</select>

<button>Create</button>

</form>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  

app.get('/todos/:id', async(req, res, next) => {

try {

const todo = await Todo.findByPk(req.params.id);

res.send(`

<html>

<head>

<title>Todos</title>

</head>

<body>

<h1><a href='/todos'>Todos</a></h1>

<h2>${todo.name} </h2>

</body>

</html>

`);

}

catch(err) {

next(err);

}

});

  

app.post('/todos', async(req, res, next) => {

try {

const todo = await Todo.create(req.body);

//res.send(todo); //without middle ware this will not parse

res.redirect(`./todos/${todo.id}`)

}

catch(err) {

next(err)

}

});

  
  

// Error handling

app.use((err, req, res, next) => {

console.log(err);

res.status(500).send(err);

});

  
  

const port = process.env.PORT || 3000;

  

app.listen(port, async() => {

try {

console.log(`listening on port ${port}`);

await conn.sync({ force: true}); // will wipe tables in database

console.log('--Database connected--');

/* ----- if order of creation is not important, place in promise.all

await Todo.create({ name: 'walk the dog'});

await Todo.create({ name: 'buy chew toy'});

*/

const categories = await Promise.all([

Category.create({ name: 'pets'}),

Category.create({ name: 'learning'}),

Category.create({ name: 'chores '}),

]);

// Deconstruct the category tags from categories const

const [pets, learning, chores] = categories;

// to use category with the task, add category as a 2nd parameter.

await Promise.all([

Todo.create({ name: 'walk the dog', categoryId: pets.id}),

Todo.create({ name: 'buy chew toy', categoryId: pets.id}),

Todo.create({ name: 'Learn React', categoryId: learning.id}),

Todo.create({ name: 'take out garbage', categoryId: chores.id}),

  

]);

console.log('--Database seeded--');

}

catch(err) {

console.log(err)

}

});
```

## Refractor - Seperate Data layer
----
- Create db folder
`mkdir db`
- create index.js file
- `touch index.js`

- Copy server.js content into index.js. 
- Delete Express content
- export your models and the connection to the database
-

in Server.js
- remove the sequelize code that we moved to db>index.js
- bring in the exported db>index.js code
	- `const {conn, Todo, Category } = require('./db');`
- transfer the seeding of our data to the db>index.js file
- add the seed data in our require('./db') statement

in db/index.js
- create a function for seed data
- export seed data

[Refractor to react](Refractor%20to%20react.md)