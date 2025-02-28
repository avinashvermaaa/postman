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

* variables :- Reuse values to keep your work DRY (Don’t Repeat Yourself)
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

* Use POSTMAN Auth instead!
```
delete the previous api-key -> save -> go to your collection {Postman Api challenge -> authorization -> (autz type ) = api key -> add api-key = value -> save and re run POST request
```
* Scripting
```
Scripting in Postman
  Postman allows you to add automation and dynamic behaviors to your collections with scripting.
  Postman will automatically execute any provided scripts during two events in the request flow:

  Immediately before a request is sent: pre-request script (Pre-request Script of Scripts tab).
  Immediately after a response comes back: post-response script (Post-response of Scripts tab).

scripts tab -> post-response tab ->
for example :-can access the JSON response body from an API with: 
pm.response.json()
```
```
scripts tab -> post-response tab ->
  // save the "id" value from the response to a variable named "id"
  const id = pm.response.json().id
  // save the id as a collection variable named "id"
  pm.collectionVariables.set("id", id)


fetch data only id -> create/ update the id variable
{{id}} variable is created and can be used in 'get book by id' request -> {{baseURL}}/books/:id
```

