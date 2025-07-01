

# mutation
----
## Add (post)
```JSON
mutation {
	addUser(firstName: "Phillip", age: 39) {
		id
		firstName
		age
	}
} 
```

## Delete (delete)
----
```JSON
mutation {
	deleteUser(id: "23")
}
```

## Update/Edit (patch)
----
```JSON
mutation  {
	updateUser(id: "23", firstName: "john") {
		id
		firstName
		age
	}
}
```


React App how does it it work with the GraphQL server?
	In between the react app and the GraphQL server are two different important pieces of technology
		1. Apollo Provider
		2. Apollo Store

The Apollo store communicates directly w/ the GraphQL server and store data that comes back from it.
	Client side repo of all the data that is coming back from the GraphQL server

The integration layer between the Store and our actual React application is the Apollo provider
	Provides data to our react app
	The provider will take data from the store and inject it into our app


GraphQL + React Strategy
1. Id data required
2. Write query in Graphiql (for practice) and in component file
3. Bond query + components
4. access data


Mutation Variable remember "dollar sign, type name, dollar sign'

## mutation w/ variable
```graphql
mutation LikeLytric($id: ID) {
	likeLyric(id: $id)
}
```


