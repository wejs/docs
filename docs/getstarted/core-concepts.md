# Core Concepts

To get started with We.js, there are a few core concepts you should understood.

## Plugin

**Plug and play** NPM module with suport to database updates and installation, split your code in small plugins for reuse in others projects.

Use plugins to add new features in your project or change default features from others plugins.

If the project have a plugin.js file it will be load as plugin after all plugins. This is a good place to override or change features from others plugins.

## Context Loader

Preload data in res.locals.data related to current request like record (**res.locals.data**) and are avaible in controller.

Context loader runs automaticaly, has one default function and may be overriden in related model. It is required for features like ACL.

## Controller

Get data from database or other provider, process and send to response formatter with response methods.

Every controller is a instance of We.js [controller prototype](https://github.com/wejs/we-core/blob/master/lib/class/Controller.js) and functions in controller is called actions how work like express.js middlewares how receive req, res and next arguments.

## Model

Define your model attributes, joins, model hooks, and custom methods with sequelize API.

## Custom response

Response format is customizable, by default we have the JSON and JSONApi response formats but you can add new formats or change in your `plugin.js` file.
Example: if you request one page with `Accept: application/vnd.api+json` header will receive the data in JSONApi format.

## Permissions and ACL 

Permissions feature and ACL based in `users -> roles -> permissions` how have a administrative page in `/admin/permissions`

Avaible in: [we-plugin-acl](https://github.com/wejs/we-plugin-acl)

## Generators

With the We.js generator you can generate projects, plugins, themes and features like model, resource(CRUD), widgets and more

Powered by yeoman!

Avaible in: [generator-wejs](https://github.com/wejs/generator-wejs)
