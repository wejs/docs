# Security

> We.js have some build in security features like ACL, CORS or text sanitizer

## Cross-Origin Resource Sharing (CORS)

Build in node-cors middleware

### Settings for all routes:

Ìn your project **config/local.js** file
```js
module.exports = {
  // .... others configs
  security: {
    // see https://github.com/expressjs/cors#configuration-options for  all CORS configuration options
    // This may be override by every route configs
    CORS: {
      // block all CORS requests by default
      origin: function(origin, cb){ cb(null, false) },
      // default methods
      methods: ['GET', 'OPTIONS'],
      allowedHeaders: ['Content-Type', 'Authorization', 'Accept']
    }
  }
  // .... others configs
}
```

### Settings only in one route:

```js
    'get /event/:eventId([0-9]+)/register': {
      name          : 'event_register',
      titleHandler  : 'i18n',
      titleI18n: 'event.register',
      controller    : 'cfregistration',
      action        : 'register',
      model         : 'cfregistration',
      permission    : 'find_event',
      CORS          : {
        // see https://github.com/expressjs/cors#configuration-options for  all CORS configuration options
        // block all CORS requests by default
        origin: function(origin, cb){ cb(null, false) },
        // default methods
        methods: ['GET', 'OPTIONS'],
        allowedHeaders: ['Content-Type', 'Authorization', 'Accept']        
      }
    },
```

## Access control list (ACL)

For ACL see: http://wejs.org/docs/we/request-response.acl

## Sanitizer

> Configured npm `sanitize-html` module 
> 
> **Automatically sanitize all model attributes**, if you don't need to sanitize one model add the `skipSanitizer: true` in your model field attribute

In runtime the sanitizer is avaible at `we.sanitizer` 
   
### Methods

#### we.sanitizer.sanitize

```js
we.sanitizer.sanitize('a strange text <a href="#" javascript="alert(\'HI\')">IO</a>)');

// By defalt will return:
// 'a strange text <a href="#">IO</a>)'
```

#### we.sanitizer.sanitizeAllAttr

```js
we.sanitizer.sanitizeAllAttr({
    attr1: 'Hi <span invalidAttr="asdasd"></span>',
    attr2: 'Umm <asaskdak>Strange!</alskdkka>'
});

// By defalt will return:
// { attr1: 'Hi ', attr2: 'Umm Strange!' }
```
