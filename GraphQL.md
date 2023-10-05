

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

