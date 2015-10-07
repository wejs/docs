# Security

> We.js have some build in security features like ACL, CORS or text sanitizer

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
