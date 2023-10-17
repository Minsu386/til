![](Pasted%20image%2020230531200435.png)




## Modules
----

`module.export` 
- initially an empty object
- Assign it the data you want to expose
- a `require` of this file ('module') will return its `module.exports`

## Require
----
`require`
- Finds a file
- Executes it
- Imports that file's exports



## Express & Async
----

### [Express](Express)

```JavaScript
const express = require('express')
const app = express()

app.get('/', (req, res, next) => {
	res.send(`<h1>Welcome to the main page</h1>`)
})

app.get('/about', (req,res, next) => {
	res.send(`<h1>Welcome to the about page</h1>`)
})

app.listen(3000)
```
you will also need to install express via [NPM](NPM)
`npm i express`

Start fresh	 
```zsh
mkdir expressDemo && cd $_
npm init -y
git init

touch server.js
npm i nodemon --save-dev

```

in package.json add this line  in the "scripts: {
 "start:dev": "nodemon server"
}"

to start
`npm run start:dev`

## [Express](Express) & [Sequelize](Sequelize.md) [Backend](Backend.md)
____




