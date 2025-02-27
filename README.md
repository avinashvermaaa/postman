# Postman API Challenge 
* Request methods
```
GET           Retrieve data (Read)
POST          Send data (Create)
PUT/PATCH     Update data (Update)
PUT           usually replaces an entire resource, whereas PATCH usually is for partial updates
DELETE	      Delete data (Delete)
```
* Response status codes
![image](https://github.com/user-attachments/assets/5151cc47-757e-43f4-ba4c-515a618cd9a1)

# Request  Parameters

* variables :-
`{{variableName}}` -> variableName  and select "Collection" as the scope, then click Set variable.
`example :- https://library-api.postmanlabs.com    {{baseURL}}`

* Query Parametes :- `?` `key=value` ->
  single-> (https://website/photos?orientation=landscape)
  multiple ->(https://website/photos?orientation=landscape&size=500x400)
` example :- https://library-api.postmanlabs.com/books?genre=fiction`

* path parametes :- `/:id`
  `example :- {{baseURL}}/books/:id`
  `in params -> path variables -> id = 29cd820f-82f9-4b45-a7f4-0924111b5b89`

# Sending data with POST
* add a book
```
body -> raw -> json { as RESTApi accepts json as body}
{
  "title": "book",
  "author": "avinash",
  "genre": "fiction",
  "yearPublished": 2025
}
```
* add an authorization 
``` req. method POST
in headers tab -> api-key = postmanrulz
in body tab -> raw -> json
{
  "title": "postmanwa",
  "author": "avinash",
  "genre": "fiction",
  "yearPublished": 2025
}
{
    "id": "bd681e02-b583-49c8-8a1c-d53f2d8d7c1a",
    "title": "postmanwa",
    "author": "avinash",
    "genre": "fiction",
    "yearPublished": 2025,
    "checkedOut": false,
    "isPermanentCollection": false,
    "createdAt": "2025-02-27T21:26:44.314Z"
}
```

