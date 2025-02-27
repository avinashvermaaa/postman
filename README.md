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
