api.md

```markdown
# /messages/{id}

## GET
+ Response 200 (text/plain)

        Hello World!

## DELETE
+ Response 204

```

Run in shell:

```sh
$  docker run -ti --rm -v $PWD/api.md:/app/api.md -p 3000:3000 ajnasz/api-mock
```

Then to test:

```sh
$ curl -v localhost:3000/messages/123
$ curl -X DELETE localhost:3000/messages/123
```
