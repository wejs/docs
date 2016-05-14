# i18n

We.js have the i18n module ready to use which multi language suport. 

By default it run based on locales folder config/locales/ folder.

## How to configure

Example: https://github.com/wejs/site/blob/master/config/i18n.js

## Usage

#### Global
Default locale config
```js
we.i18n.__('string');
```

#### Request localization
Use user profile settings as i18n locale

##### In controller:
```js
req.__('string');
```

##### In template
```hbs
{{t 'string' variable1='' var2=''}}
```

## How to load default locales?

Ẁith we.js cli:

```sh
we loadLocales
```
