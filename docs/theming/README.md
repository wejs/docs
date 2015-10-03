# We.js theming

> Change the visual and structure of your project in html reponses (default reponse)
> 
> Themes can override default plugin templates to change html structures or classes

By default we.js have 2 themes, the `app` and `admin` theme.

The admin theme will be used in /admin pages and the app theme will be used in others routes

## How to install a theme:

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



