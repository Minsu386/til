----
	#react 

### Objective
- How components can  reference other components
- how this allows us to separate our components into separate files




## Returning Another Component
----

Each [React](React.md) component is responsible for one piece of the interface.
As the application grows in complexity, Components need to be able to interface w/ each other to support the features needed. 

```JavaScript
import React from 'react';

function Picture() {
return <img src"https://content.codecademy.com/courses/React/react_photo-octopus.jpg" />;
}

function Profile() {
	return (
		<>
			<Picture />
			<h1> Name: Octavia</h1>
			<h2>Species: Octopus</h2>
			<h2>Class: Cephalopoda</h2>
		</>
	)
}

export default Profile;
```

The `Picture` component is referenced inside of the `Profile` component. Picture is only responsible for a piece of the profile.

```JavaScript
// Index.js
import React from 'react';
import ReactDOM from 'react-dom/client'; 

import App from './App';  

ReactDOM.createRoot(
  document.getElementById('app')
).render(<App />);
```

```JavaScript
// App.js
import React from 'react';
import HelloWorld from './HelloWorld';  

function App(){
  return <HelloWorld />;
}  

export default App;
```

```JavaScript
// HelloWorld.js
import React from 'react'; 

function HelloWorld(){
  return(<h1>Hello, World!</h1>);
} 

export default HelloWorld;
```

## Review

- A React application can contain multiple components.
- Components can interact with each other by returning instances of each other.
- Components interacting allows them to be broken into smaller components, stored into separate files, and reused when necessary.