# JSON form

> Auto generate a html form from JSON file
### How to:

#### First register the json form:

json form: server/forms/login.json
```json
{
  "title": "auth.login.title", // i18N title
  "method": "post", // default form method
  "action": "/login", // form action, will post to /login
  "fields": {
    "email": {
      "type": "email", // templates/forms/email.hbs template
      "allowNull": false
    },
    "password": {
      "type": "password", // templates/forms/password.hbs template
      "allowNull": false
    },
    "persistent": {
      "type": "boolean" // templates/forms/boolean.hbs template
    }
  },
  "actions": { // actions ... may have multiple actions
    "submit": {
      "type": "submit"
    }
  }
}
```


#### Then use it:

In template use the `form` helper:

```hbs
{{{form formName record validationError}}}
```

For docs and code of this helper see: https://github.com/wejs/we-plugin-form/blob/master/server/helpers/form.js
