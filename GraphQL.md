

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

