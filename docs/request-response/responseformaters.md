# Response formater

> Extentable response formaters how format your response after send to client

> To change the response formater set `responseType=[type]` like `responseType=json` as query param in your url

## Core responses:

### HTML (default)

#### Usage with accept header:
```
GET /docs/we HTTP/1.1
Host: localhost:4000
Accept: application/json
```

#### Usage with query params:
`[url]?responseType=html`

### JSON

#### Usage with accept header:
```
GET /docs/we HTTP/1.1
Host: localhost:4000
Accept: application/json
```
#### Usage with query params:
`[url]?responseType=json`


## How to add a custom response formater?

1. Add it in we.config.responseTypes
   in `plugin.js` file
   ```js

   ```

    // map reponseType response types
    responseTypes: ['html', 'json'],