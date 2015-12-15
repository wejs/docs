# Configuration

> Set default configurations in plugins and overrides in project configs

## Project

Project configuration override default plugin configurations

Example https://github.com/wejs/site/tree/master/config 


### Local project config

The **config/local.js** will override all others configurations then use it for set local configs like database configs

## Plugin

Plugin files have the default configurations for your project, you can see the configuration in plugin and override in your project loca.js file

For set default plugin configurations use the `plugin.setConfigs` in plugin.js file
Example https://github.com/wejs/we-core/blob/master/plugin.js#L10 