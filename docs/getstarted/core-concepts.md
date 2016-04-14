# Core Concepts

> To get started with We.js, there are a few core concepts you should understood.

## Plugin

Plug and play NPM module with suport to database updates and installation, split your code in small plugins for reuse in others projects.

Use plugin to add new features in your project or change default features from others plugins.

If the project have a plugin.js file it will be load as plugin after all plugins. This is a good place to override or change features from others plugins.

## Context Loader

Preload data in res.locals related to current request like record (res.locals.data) in findOne, edit or update actions and are avaible in res.locals.data.

## Controller

Get data from database or other provider, process and send to response formatter with response methods.

Every controller is a instance of We.js [controller prototype](https://github.com/wejs/we-core/blob/master/lib/class/Controller.js) and functions in controller is called actions how work like express.js middlewares how receive req, res and next arguments.

## Model

Define your model attributes, joins, model hooks, and custom methods with sequelize API.

## Custom response

Response format is customizable, by default we have the HTML and JSON responses but you can extend or change in your `plugin.js` file

## Permissions and ACL

Build in permissions feature and ACL based in `users -> roles -> permissions` how have a administrative page in `/admin/permissions`

## Theme

A theme is responsible for visual, html and css of your project.

Make themes for your project with html response content. By default every we.js project have 2 themes, 1 for administration and 1 for app.

## Layouts, regions and widgets

HTML response format have layouts, regions and widgets parts

Define the layouts and regions in your theme and then add widgets in regions of the page with widgets edit in place API

Widget API is avaible for single page applications with API calls, use it to build dynamic dashboards or page blocks

## Generators

With the We.js generator you can generate projects, plugins, themes and features like model, resource(CRUD), widgets and more

Powered by yeoman!
