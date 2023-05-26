create new component -
	Search.js
import new component to index patch

Search.js
```JavaScript
import React from 'react';
import {useNavigate} from 'react-router-dom';

const Search = () => {
	const navigate = useNavigate();
	const search = (event) => {
		
	};

	return (
	<div>
		<input placeholder='filter' onChange={ search } />
		
	</div>
);
};

export default Search;


```