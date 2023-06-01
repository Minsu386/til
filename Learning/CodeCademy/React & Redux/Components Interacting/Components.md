----
	#react 

### Objective
- How components can  reference other components
- how this allows us to separate our components into separate files




## Returning Another Component
----

Each [[React]] component is responsible for one piece of the interface.
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