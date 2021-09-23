"let me see my first version to be late deleted" Follow Mulesoft recommended approach to design an effective
APIs.
MuleSoft advocates API specification-driven (contract-first API
design and RAML
fragments)
 Start by creating the API specification, ideally in the form of a
RAML
definition
 API versioning and where to expose what elements of an API’s
version
 between Enterprise Data Model and Bounded Context Data
Models
 Simulate interaction with the API based on the API specification
 Gather feedback from potential future API consumers
 Publish documentation and API-related assets, including the RAML
definition of the API
 Only then implement the API
 This is the approach we will follow to deliver the project.
Mulesoft B21 Project #1
B21 Page 3
CraftSoft Mulesoft Batch 21 trainee
Prepare an API that has five endpoints.
1. GET /api/notes
2. GET /api/notes/{noteId}
3. POST /api/notes
4. PUT /api/notes/{noteId}
5. DELETE /api/notes/{noteId}
Use your local MySQL database while the fourth consumes data from
an external API.The fours endpoints will be:
1. This will list all notes in the notes_app table. UpdatedAt field
should not return null. Check null
2. This will return the record where the noteId field is equal to the
uri parameter “noteId”. UpdatedAt field should not return null.
Check null
3. This will add new note to the notes_app table with id, title,
content, createdAt and updatedAt. These fields should be
provided in the body of the post call. You may develop the
json format any way you think is best.
Prerequisite for question number 4:
(Go to: https://www.zip-codes.com/zip-code-api.asp and
create a free account to get a key. Please provide a fake user
identity: I repeat don’t provide your real name, address, phone
number)
4. GET:
localhost:8081/project1/zipcode/zip=[somezipcode]?key=[som
ekey] – This endpoint will consume the zip codes variable from
the query string and use that to gather data from the following
external API:
Mulesoft B21 Project #1
B21 Page 4
Sample
https://api.zipcodes.com/ZipCodesAPI.svc/1.0/GetZipCodeDet
ails/90210?key=DEMOAPIKEY
The full zip code location at the end of the example will be
replaced with the value in the your key (once you registered in
the website) query string parameter. This endpoint will either
return all of the data provided by the external api or just the
“current” object, specified by the “content” query string
parameter.
MySQL database
 Host: localhost
 Port: 3306
 Username: xx
 Password: xx
 Database name: notes_app
 Table name: notes
Table info:
 Column names: id, title, content, createdAt, updatedAt
 id field is an integer and auto_increment
 title and content fields are varchar
 createdAt and updatedAt are timestamps