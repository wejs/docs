# Installation and updates

We.js theme is npm modules

To enable theme feature install: **we-plugin-view**

## Installation

### Download:
```sh
# install the theme
npm install [theme npm name]
```

### Configure

In your project:

**File:** [project]/config/themes.js
```js
module.exports.themes = {
    enabled: [
      // load and enable in node_modules folder:
      '[your theme name]',
      // load and enable in custom folder:
      {
        name: '[your theme name]',
        themeFolder: process.cwd()+'/server/themes/black-onepage-business-template'
      }
    ],
    app: '[your theme name]'
};
```

## Updates

Use the NPM commands

1. npm outdated to check if have updates
```sh
npm outdated
```
2. Ànd update the project version in `package.json` file