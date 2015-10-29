# Url alias

> Override default express routes with custom routes for make slugs or clean urls and define model functions how automaticaly generate url alias for your records

Avaible in we-core v0.3.98+

code: https://github.com/wejs/we-core/blob/master/lib/router/alias.js 

## Model url alias generator

This method rund on record create and update and needs to return a object with **alias** and **target** attributes.

Set **urlAlias** method in your **model options.classMethods** like the we.js core user model in https://github.com/wejs/we-core/blob/master/server/models/user.js#L206

Example:

```js
  // --- your modele file ...

      options: {
        classMethods: {
          // returns an url alias
          urlAlias: function urlAlias(record) {
            return {
              alias: '/'+ we.i18n.__('user') +'/' + record.id + '-'+  we.utils
                .string( record.username || record.displayName ).slugify().s,
              target: '/user/' + record.id,
            }
          }
        }
      },
  // ---
```

## Url alias in admin

Use the **/admin/urlAlias** page for manage all alias in your system

## Template helpers

### {{link-to-record}}

Generate link for sequelize record.

Usage: 
```hbs
{{#link-to-record record=record class="btn btn-default"}}Text inside the link{{/link-to-record}}
```

Code: https://github.com/wejs/we-core/blob/master/server/helpers/link-to-record.js

### {{link-to}}

Resolve and generate link for related route name

Usage:
```hbs
{{#link-to 'routeName' class="btn btn-default"}}Text inside the link{{/link-to}}
```

code: https://github.com/wejs/we-core/blob/master/server/helpers/link-to.js

## Functions

Url alias feature module is avaible in **we.router.alias** and have this helper methods:

### we.router.alias.forPath

Check if path have a alias and if exists return the alias or null

Usage:

```js
 var path = '/user/1';
 var aliasOrNUll = we.router.alias.forPath(path);
```

code: https://github.com/wejs/we-core/blob/master/lib/router/alias.js#L108

### we.router.alias.resolvePath

Check if path have alias and return the alias or the path

Usage:
```js
 var path = '/user/1';
 var alias = we.router.alias.resolvePath(path);
```
code: https://github.com/wejs/we-core/blob/master/lib/router/alias.js#L122


