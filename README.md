# API-Mock Docker image

Run a api-doc application in docker.

> Document your API in the [API blueprint](http://apiblueprint.org/) format, and API-Mock mocks your routes and sends the responses defined in the api spec.

See more about the application: https://github.com/localmed/api-mock

## Example

api.md

```markdown
# /messages

Retrieve messages

## GET
+ Response 200 (text/plain)

        Hello World!
        Hello Other World


# /messages/{id}
Represents a particular message by it's *id*.

## Retrieve message [GET]
+ Response 200 (text/plain)

        Hello World!

## DELETE MESSAGE DELETE
+ Response 204

# /messages/{id}.json

## Retrieve message in JSON [GET]
+ Response 200 (application/json)

        {"message": "Hello World!"}
```

Run in shell:

```sh
$  docker run -ti --rm -v $PWD/api.md:/usr/src/app/api.md -p 3000:3000 ajnasz/api-mock
```

Then to test by calling a GET request:
```sh
$ curl -v localhost:3000/messages/123
```

There you can see the response

Then to test by calling a DELETE request:
```sh
$ curl -v -X DELETE localhost:3000/messages/123
```
