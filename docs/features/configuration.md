# Configuration

Set default configurations in plugins and overrides in project configs

## Project

Project configuration override default plugin configurations

Example https://github.com/wejs/site/tree/master/config 

Project configurations is set in **config/** folder and every file will be parsed and merged in we.config

Example:

For set i18n configuration you can add one file in project config/ folder with:

```js
module.exports.i18n = {
  // Which locales are supported?
  locales: ['en-us'],
  defaultLocale: 'en-us'
};
```

And will be parsed to we.config.i18n

**config/local.js** files are loaded after all files and can override other configs

### Local project config

The **config/local.js** will override all others configurations then use it for set local configs like database configs

## Plugin

Plugin files have the default configurations for your project, you can see the configuration in plugin and override in your project loca.js file

For set default plugin configurations use the `plugin.setConfigs` in plugin.js file
Example https://github.com/wejs/we-core/blob/master/plugin.js#L10 