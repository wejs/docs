# Response formater

Extendable response formaters for format your response after send to client

To change the response formater set the extension like `/user.json`  in your url or Accept header

## Options for select the response content type (responseType)

Lets get the json version of the content:

#### Usage with extension in url:

`[url].json`

#### Usage with accept header:

```
GET /docs/we HTTP/1.1
Host: localhost:4000
Accept: application/json
```

#### Usage with query params:

`[url]?responseType=json`

## How to add a custom response formater?

1. Add it in your plugin plugins.js file:
   ```js
   // wait to load all plugins and configs
   plugin.events.on('we:after:load:plugins', function (we){
     // then add it with we.responses.addResponseFormater and set the extension, in this example we use the csv
     we.responses.addResponseFormater('csv', function (req, res){
        // format the response and send it to browser
        // util variables:
        // res.locals.model == current model for this request
        // res.locals.data == data to send, may be one array or object
        
        // after format run res.send with formated data
        res.send(formatedData);
     });
   });

   ```
