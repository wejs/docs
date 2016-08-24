# Access control list (ACL)

Role-based access control (RBAC) feature from we-core-acl npm module.

Check if current user have access to one route based in roles and permissions

Avaible in: **we-plugin-acl**

## How We.js ACL works?

1. In we.js Bootstrap:
  We.js load all roles and permissions in memory in we.js bootstrap
2. In request
  1. Load current user
  2. Load current user roles
  3. Check if user roles have access to current route and send a 500 or continue with the request to controller. 

## Configuration

Commands avaible in We.js cli:

```
acl:role:add [options] <roleName>                     Add one role if not exists
acl:role:export [options]                             Export all project roles to file or log
acl:role:permission:add|arpa <roleName> <permission>  Add one permission in role
acl:role:permission:rm|arpr <roleName> <permission>   Remove one permission in role
acl:role:rm <roleName>                                Remove one role, this dont remove system roles
acl:user:role:add <userId> <roleName>                 Add one role in user
acl:user:role:rm <userId> <roleName>                  Remove one role in user
```

Example, for add role administrator to user with id 1:

```sh
we acl:user:role:add 1 'administrator'
```

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

## Permission management with we-plugin-view

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