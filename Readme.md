# Ecommerce Endpoint Testing 

A repository for some simple functional, integration and performance testing of the REST API endpoints. Test are run through POSTMAN exported as collections and stored here. 

### Schemas

The (folder schemas)[/ecomm-api-tests/tree/master/schemas] stores the json schemas for some of the endpoints. As they are added retrospectively the process is as follows.

Firstly install the (json-schema-generator)[https://www.npmjs.com/package/json-schema-generator] from npm

Then use postman to grab a json endpoint. With the correct and expected json output format it so that it 

- does not contain duplicate named sections 
- does not have any extraneous data (make sure you do this right!)

```bash
$ json-schema-generator INPUT.json -o OUTPUT-schema.json
```

Will produce the schema file. At this point however, this generator does not use ```"additionalProperties": false``` which is really important for us. So add this into each section we need it. Without this, and when running the validator against the schema, it allows extra data that we really want to test against happening. 
