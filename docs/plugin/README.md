# Plugins

> Plug and play npm modules build for extend we.js projects, build one feature and reuse or share with others developers
> 
> You can add Widgets, controllers, routes, models ... every we.js feature can be override or added with plugins

The plugin main file is `plugin.js`

## How to install one plugin?

1. Find plugin in we.js site, npm site, github search or with npm command like:  `npm search we-plugin-`
2. Install with `npm install [pluginName]` like `npm install we-plugin-form`
3. First time when you run your project, We.js will install all we-plugins on project.
3. Start your project and in first project run after install the plugin the we.js will register this plugins and the plugin version for use in database updates.

## How to update?

All plugins is a npm module then you can:

1. use the `npm outdated` to check updates in package.json modules
2. then change the plugin version in your project package.json

