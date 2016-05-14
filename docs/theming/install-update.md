# Installation and updates

We.js theme is npm modules

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
      '[yout theme name]',
      'we-theme-admin-default'
    ],
    app: '[yout theme name]',
    admin: 'we-theme-admin-default'
};
```

## Updates

Use the NPM commands

1. npm outdated to check if have updates
```sh
npm outdated
```
2. Ànd update the project version in `package.json` file