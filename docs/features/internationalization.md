# i18n

>We.js have node i18n module and you can ise it as:

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
