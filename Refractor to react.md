We are continuing from the [Building your first Application](Building%20your%20first%20Application.md)

- in db create conn.js
```JavaScript
const Sequelize = require('sequelize');
const conn = new Sequelize('postgres://localhost/todo_db');

module.exports = conn;
```

- in index.js 
	- change const conn to:  `const conn = require('./conn')` 
		- remember, conn my also be called db

- create ToDo.js
	- we will be placing the toDo definition in this file
	- remember to `module.exports = Todo`
- do the same for all other models
- require these models in index.js
	- `const conn = require('./conn');` 

delete routes, require path, change old `app.get('/'`   route to
`app.get('/', (req, res) => res.sendFile(path.join(__dirname, 'index.html')));`

create index.html in root folder

Grab the Try react HTML code from react.dev and paste it into your index.html. this will be our starter and we will manitpulate it and change it to our liking. 

Bable changes jsx into javascript.

all the code inbetween the  between the <script></script> tags cut and paste into a new file, 
	create src folder
	create index.js
		paste the code in this new file

install in root directory
	- npm i webpack webpack-cli @babel/core babel-loader @babel/preset-react --save-dev
	-
create webpage.config.js file and set some parameters .. at a min 
```JavaScript
module.exports = {
module: {
	rules: [
		{
			test: /\.js$/,
			exclude: /node_modules/,
			loader: 'babel-loader',
			options: {
				presets: ['@babel/preset-react']
			}
		}
	]
}

}
```