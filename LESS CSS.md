#css #style #frontend 


less css

install globally on your machine
	- sudo npm i -g less 

root dir 
	- `mkdir less`
		- `touch index.less`


index.less -- tetst your less first
```less
*{
	margin: 0;
	box-sizing: border-bo;
}

html {
	background-color: aquarmarine
}
```


less css watch compiler
- `npm i less-watch-compiler`

package.json
add "watchless": "less-watch-compiler  src dist" where src and dist are the src of the folder that contains less files and dist folder contains output css files

`less-watch-compiler` <root folder> <dist> index.less

- src folder index.js
	add link to stylesheet
	 dist/index.css


less folder  components
	index.less - main gathering point of your other .less files.  you import them here.
	main.less -- main css style of your site.
		@import "main"
	nav.less -- 



Today task
Style todo with less



[Frontend](Frontend)

