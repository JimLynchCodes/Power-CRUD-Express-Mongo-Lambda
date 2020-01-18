# Power-CRUD-Express-Mongo-Lambda
Example of an awesome database CRUD api in node.js!

# Tips


### Use A Consistent (Preferably Plural) Naming For Endpoints

There is a great discussion of this topic in [this stack overflow post](https://stackoverflow.com/questions/6845772/rest-uri-convention-singular-or-plural-name-of-resource-while-creating-it), and I have found this to be the concesus- use a consistent, usually plural name for your endpoints.


### Think In Terms Of Your Collections (And The GET Route)
Apis that interact with databases must think in terms of collections. In MongoDB they are actually named collections, but relational tables are in the end just a collection of rows. An extremely common pattern is for the base GET route to return the full collection and the GET route with some argument after the "/" would instruct the api to get the item of the collections.

GET  /orders        -> gets all orders
GET  /orders/123    -> gets the order with id of 123

If you use a singular name for your resource then it can be confusing for consumers of your api. "Does /order return one order and /orders return all orders? Is everything just /order? Why does /order return the entire list of orders?" These are all questions consumers of your api will be wondering if you use singularly named routes, whereas if you use plural routes no one will ask you anything about your api because they are not super confused.


## Core CRUD Routes

## GET
  - takes an id and returns the item with that id.
  - base route (no id) that returns a (potentially filtered / paginated) list if items.
  
## POST
  - takes a new item payload, inserts the new item into the collection.

## PUT
  - takes an id and new item payload, updates the item with that id to be the new payload.

## DELETE
  - takes an id and deletes the item with that id.

---

## Use Serverless Framework For Unparalled Developer Experience & Deployment Flexibility
With the Serverless cli you can scaffold out serverless functions for _any_ cloud provider, _any_ programming language... it's pretty great! The serevrless.yaml file it much more succint and pleasant to deal with than raw AWS SAML. 

## Automatic Swagger Generation
Great for learning and understanding and api- automatically generated from the code.

## End-To-End Testing With SuperTest
Gives you confidence you endpoints work every time you deploy!

## Load Testing
It's good to do although with serverless kind of unnecessary.

## Unit Testing
If your api has any logic at all, you should test it.

## Enterprise-Level Monitoring Tools
Lumigo and Espagon.

## CI / CD
Helps large projects move wuickly and accurately.

## JSON:API
The [JSON:API](https://jsonapi.org/) spec is a well though-out (although very opinionated) guide that makes a lot of decisions for you in how you should structure the response, pagination & filtering, linked to different resources, etc. Although I don't necessarily recommend following this guide in the strictest possible sense, I think can be a great inspiration for any backend developer in _one possible_ approach for designing the api at hand.
