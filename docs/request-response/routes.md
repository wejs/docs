# We.js router

> Router is build with Express.js and is compatible with all Express.js modules

Plugin or project routes is set in plugin.js files.

## Routes

### Simple route

We have 2 forms to set routes in we.js:

#### set with server/routes/*.json file

Create a `server/routes/*.json` file inside your project or plugin then add your route as object like:

```js
{
  // homepage | default home page
  'get /some-path': {
    // route controller and action is required
    controller: 'main',
    action: 'index',
    // // return user records
    // // this is required for some responseTypes
    model: 'user',
  }
}
```

#### set inside one plugin.js file:

```js
  // set plugin routes
  plugin.setRoutes({
    // homepage | default home page
    'get /some-path': {
      // route controller and action is required
      controller: 'main',
      action: 'index',
      // // return user records
      // // this is required for some responseTypes
      model: 'user',

      // // custom template for this route, by default will use the [controller]/[action] as default template
      //template   : 'home/index',
      
      // // custom layout for this route
      // layoutName : 'fullwidth',
    
      // // enforces a response format type
      // responseType  : 'json',
      
      // // permission name
      // // Set to true to skip ACL check
      // permission    : 'find_user'     
    }
  });
```

### Route resource

#### Set inside one plugin.js file

Route resource will generate all routes for one resource:

```
get /[name]/create
get /[name]
get /[name]/:[name]Id
get /[name]/:[name]Id/edit
post /[name]/:[name]Id/edit
put /[name]/:[name]Id
patch /[name]/:[name]Id
get /[name]/:[name]Id/delete
post /[name]/:[name]Id/delete
delete /[name]/:[name]Id
```

##### Example:

To set resource for admin users:

###### With server/resources/*.json

file `server/resources/admin.user.json`:

```json
{
  "name": "user",
  "findAll": {
    "search": {
      "q": {
        "parser": "userSearchQuery",
        "target": {
          "type": "field",
          "field": "id"
        }
      }
    }
  }
}
```

###### Or inside your plugin.js file:

```js
  plugin.setResource({
    
    // // route name prefix, final route name will be admin.user
    // namePrefix: 'admin.',
    
    // route name, this name is used for get controller and model and 
    // in this example will use the user model and controller
    name: 'user',
    // route namespage
    namespace: '/admin',
    
    // // custom template folder for templates in this resources
    // templateFolderPrefix: 'admin/',
    
    // custom settings for findAll routes, this is optional
    findAll: {
      // search API converts query params to internal sequelize.where params     
      search: {
        id:  {
          parser: 'equal',
          target: {
            type: 'field',
            field: 'id'
          }
        },
        email:  {
          parser: 'equal',
          target: {
            type: 'field',
            model: 'user',
            field: 'email'
          }
        },
        fullName:  {
          parser: 'contains',
          target: {
            type: 'field',
            model: 'user',
            field: 'fullName'
          }
        }
      }
    }
  });
```

Will generate:

```
get /admin/user/create
get /admin/user
get /admin/user/:userId
get /admin/user/:userId/edit
post /admin/user/:userId/edit
put /admin/user/:userId
patch /admin/user/:userId
get /admin/user/:userId/delete
post /admin/user/:userId/delete
delete /admin/user/:userId
```

## Links:

Express.js: http://expressjs.com/
