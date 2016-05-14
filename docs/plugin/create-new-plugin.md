# Create new plugin

Powered by We.js yeoman generator 

### Generate the plugin structure

```sh
yo wejs:plugin
# then type your plugin Name
```

and the yeoman will generate all plugin structure.

### Install dev dependencies

Enter in plugin folder and tip: 

```sh
npm install
```

### Read and follow your generated plugin README.md

**file:** `[plugin folder]/README.md`

### How to use your new plugin?

Any plugin is one npm module then you may use the npm link or npm install

1- For development or private plugins: Use `npm link` to link the plugin in one We.js project 
2- For public production plugins: Use `npm publish` to publish your plugin and `npm install [pluginName]` in your We.js project

Npm link docs: https://docs.npmjs.com/cli/link