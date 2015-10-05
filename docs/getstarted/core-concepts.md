# Core Concepts

> To get started with We.js, there are a few core concepts you should understand.

## Plugin

A plug and play NPM module with suport to database updates and installation, split your code in small plugins for reuse in others projects.

Use plugin to add new features for your project or change default features from others plugins.

If the project have a plugin.js file it will be load as plugin after all plugins then is a good place the override or change plugin features.

## Themes

A theme is responsible for visual, html and css of your project

Make themes for your project in html response. By default every we.js project have 2 themes, 1 for admin and 1 for app.

## Controllers

Process the data from database and send to response formater with response methods.

## Models

Define your model attributes, joins, model hooks, and custom methods with sequelize API.

## Custom responses

Response format is customizable, by default we have the HTML and JSON responses but you can extend or change in your `plugin.js` file

## Permissions and ACL

Build in permissions feature and ACL based in `users -> roles -> permissions` how have a administrative page in `/admin/permissions`

## Layouts, regions and widgets

HTML responses have the layouts, regions and widgets feature

Define the layouts and regions in your theme and then add widgets in regions of the page with edit in place API

