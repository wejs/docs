# Responses

> Custom response functions extends express.js response object (res) with extra functions like res.ok or res.updated

## Core responses:

### res.ok() send a 200 response
Use for simple success responses or find and findAll responses

```js
res.ok();
```

### res.notFound send a 404 response
Use for show the not found page

```js
res.notFound(msg);
```


### res.forbidden send a 403 response
Use for send the forbidden page

```js
res.forbidden(msg);
```

### res.serverError send a 403 response
Use for send the error page

```js
res.serverError(err);
```

### res.badRequest send a 400 response
Use for send the bad request page

```js
res.badRequest(msg);
```

### res.queryError send a 400 or 403 response
Use in sequelize `.catch` callback for parse database errors and for html requests will reload the form with erro messages

```js
we.db.models.user.findOne()
//.then(...)
.catch(res.queryError);
```


### res.goTo a core redirect how use flash for deals with session messages
Use for redirects

```js
res.goTo(responseStatus, pathOrUrl);
```

## Record responses:

### res.created() send a 201 response with suport to core redirecTo
Use after create a record

```js
res.created();
```

### res.updated() send a 200 response with suport to core redirecTo
Use after update a record

```js
res.updated();
```

### res.deleted() send a 204 response with suport to core redirecTo
Use after delete a record

```js
res.deleted();
```
