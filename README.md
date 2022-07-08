# serverless-api-d47


AWS: API, Dynamo and Lambda
Create a serverless REST API

### Feature Tasks & Requirements

- Database: DynamoDB
  - 1 Table required
- Routing: API Gateway
  - POST
  - /people - Given a JSON body, inserts a record into the database
  - returns an object representing one record, by its id (##)
  - GET
    - /people - returns an array of objects representing the records in the database
    - /people/## - returns an object representing one record, by its id (##)
  - PUT
  - /people/## - Given a JSON body and an ID (##), updates a record in the database
  - returns an object representing one record, by its id (##)
  - DELETE
  - /people/## - Given an id (##) removes the matching record from the database
  - returns an empty object
- CRUD Operation Handlers: Lambda Functions

### Issues I ran into

I was able to get the GET route functioning but when I tried implementing another route, they both ended up breaking. After doing some research, I think it is because I was not giving the correct inputs to the second route. After seeing that route was broken I started messing around with the first route that was working and ended up breaking that one before realising that this was most likely the problem. I think if I had more time, I would scrap the second route and redo the first one making sure that its inputs were set up correctly like before, and then making sure that I remember to put the correct ones into the other routes.

I took a screenshot of the working GET route from my previous commit and have attached it here:


UML:
<img width="1728" alt="lab 18" src="https://user-images.githubusercontent.com/91757275/163760056-3aec33ba-e409-49bb-b7ee-a58fd82f0b2b.png">

The route for the get is /lab18?test=beau The route for the delete is /lab18/{id}

The get doesn't require anything because it is getting all records. The delete requires the id.

The get route returns all records in an array. The delete route returns no response.
