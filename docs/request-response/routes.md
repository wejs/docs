# We.js router

Router is built with Express.js and is compatible with Express.js modules

Plugin or project routes is set in plugin.js files.

## Routes

### Simple route

We have 2 ways to set routes in We.js:

#### 1- set with server/routes/*.json file

Create a `server/routes/*.json` file inside your project or plugin then add your route as object like:

```js
{
  // homepage | default home page
  'get /some-path': {
    // route controller and action is required
    controller: 'main',
    action: 'index',
    // // return user records
    // // this is required for some response formats like JSONApi 
    model: 'user',
  }
}
```

#### 2- set inside one plugin.js file:

```js
  // Set plugin routes
  plugin.setRoutes({
    // homepage | default home page
    'get /some-path': {
      // route controller and action is required
      controller: 'main',
      action: 'index',
      // return user records
      // this is required for some response formats
      model: 'user',
      // // enforces a response format type
      // responseType  : 'json',
      
      // // permission name
      // // Set to true to skip ACL check
      // permission    : 'find_user',

      // //
      // // Settings with we-plugin-view and html response formats:
      // //
  
      // // custom template for this route, by default will use [controller]/[action] as default template
      //template: 'home/index',
      
      // // custom layout for this route 
      // layoutName: 'fullwidth'
    }
  });
```

### Route title localization:

```js
  plugin.setRoutes({
    'get /some-path': {
      controller: 'main',
      action: 'index',
      model: 'user',
      // title method, use i18n for localized titles:
      titleHandler : 'i18n',
      titleI18n: 'user.find'
    }
  })
```

### Route resource

#### Set inside one plugin.js file

Route resource generate all routes for one resource:

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
    "loadCurrentRecord": false, // disable preload current record in context loader
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

    // set custom permission
    // permission: '[string]',

    // // custom template folder for templates in this resources
    // templateFolderPrefix: 'admin/',

    // Custom settings for findAll action, this is optional and you can override all default actions: findAll, create, edit, delete and findOne
    // See https://github.com/wejs/we-core/blob/master/lib/class/Controller.js for default action names
    findAll: {
        
      // // For use one localized string
      // titleHandler: 'i18n',
      // titleI18n: '[i18nstring',

      // // breadcrumb handler method
      // breadcrumbHandler: '[name]',
      
      // // Name of template file without .hbs
      // template: 'somefile/file',
      
      // // Set custom layout for this route
      // layoutName,

      // // Add custom model or controller
      // controller: '[controllerName]',
      // model: '[modelName]',

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
