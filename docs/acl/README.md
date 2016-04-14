# Access control list (ACL)

> We.js core have a build in ACL feature how check if current user have access to one route based in roles and permissions

## How We.js ACL works?

1. In we.js Bootstrap:
  We.js load all roles and permissions in memory in we.js bootstrap
2. In request
  1. Load current user
  2. Load current user roles
  3. Check if user roles have access to current route and send a 500 or continue with the request to controller. 

## Configuration

ACL feature is disabled by default in your config/local.js file for fast project develo.pment

file: *config/locals.js*
```js
module.exports: {
  // ... others project configs ...
  
  // acl configs
  acl: {
    // set to false for enable acl feature. ACL is disabled by default
    disabled: true 
  },
  
  // ... others project configs ...
};
```

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
{{#can permission='do_something' roleNames=req.userRoleNames}}
  can
{{else}}
  cant
{{/can}}
```