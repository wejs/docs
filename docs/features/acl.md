# Access control list (ACL)

> We.js core have a build in ACL feature how check if current user have access to one route based in roles and permissions

## How We.js ACL works?

1. In we.js Bootstrap:
  We.js load all roles and permissions in memory in we.js bootstrap
2. In request
  1. Load current user
  2. Load current user roles
  3. Check if user roles have access to current route and send a 500 or continue with the request to controller. 

## Permission management

We.js core have a administrative interface in **/admin/permissions** route for set role permissions and **admin/user/:userId/roles** for set user roles

## ACL methods

We.js ACL object is avaible at **we.acl** and user roles is avaible in **req.userRoleNames**

##### You can check user access with:

```js
we.acl.canStatic('do_something', req.userRoleNames);
```

## Related template helpers
 
```hbs
{{#can permission='do_something' roles=req.userRoleNames}}
  can
{{else}}
  cant
{{/can}}
```
