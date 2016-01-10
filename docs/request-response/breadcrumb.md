# Breadcrumb API

## Default breadcrumbs:

See: https://github.com/wejs/we-core/blob/master/lib/router/breadcrumb.js

## Set breadcrumb with breadcrumb function handler:

Function handlers are avaible in `we.router.breadcrumb.middlewares['name']`

```js
  plugin.setResource({
    name: 'post',
    findOne: {
      breadcrumbHandler: 'findOne'
    }
  });
```

## Set breadcrumb with custom function:

plugin.js file:

```js
  plugin.setResource({
    name: 'post',
    findOne: {
      breadcrumbHandler: function findOneBreadcrumb(req, res, next) {
        if (!res.locals.group) return next();

        res.locals.breadcrumb =
          '<ol class="breadcrumb">'+
            '<li> <a href="/">'+res.locals.__('Home')+'</a></li>'+
            '<li href="/group/'+res.locals.group.id+'">'+res.locals.group.name+'</li>'+
            '<li class="active">'+res.locals.__(res.locals.resourceName + '.find')+'</li>'+
          '</ol>';

        next();
      }
    }
  });
```
