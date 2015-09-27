# Model form

> Auto generate a html form from model attributes.

### How to:

In template use the `form-model` helper:

```hbs
{{{form-model model record validationError}}}
```

For docs and code of this helper see: https://github.com/wejs/we-plugin-form/blob/master/server/helpers/form-model.js

### Example:

todo model file: server/models/todo.js
```js
module.exports = function TodoModel(we) {
  return model = {
    definition: {
      text: {
        type: we.db.Sequelize.STRING,
        allowNull: false,
        formFieldType: 'text' // < will use the forms/text.hbs template 
      },
      done: {
        type: we.db.Sequelize.BOOLEAN,
        defaultValue true,
        formFieldType: 'boolean' // < will use the forms/boolean.hbs template 
      }      
    }
  }
}
```

If we use the `{{{form-model 'todo' record validationError}}}` in one template will generate one form with 2 fields:
-  1 input type text
-  1 input type checkbox

For all core form fields see https://github.com/wejs/we-plugin-form/tree/master/server/templates/forms 