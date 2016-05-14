# Field types

Reusable templates for build form field types

Avaible with [we-plugin-form](https://github.com/wejs/we-plugin-form)

### How to register:

Form field types is simple templates added in `server/templates/forms/` folder

### Example

File: `server/templates/forms/email.hbs` :
```hbs
<input id="{{fieldId}}" name="{{name}}" type="email" class="form-control" placeholder="{{t placeholder}}" {{fieldAttrs}} value="{{value}}">
```

Is usable in model form as:

todo model file: server/models/todo.js
```js
module.exports = function TodoModel(we) {
  return model = {
    definition: {
      email: {
        type: we.db.Sequelize.STRING,
        allowNull: false,
        formFieldType: 'email' // < will use the forms/email.hbs template 
      },     
    }
  }
}
```

## Avaible variables in form field template

- locals: same as res.locals
- values: object with filled values, use for edit or error pages
- fieldOptions: field configurations from model or jdon form field

for see others values use the `{{log this}}` helper in your template

## Links

- Core form fields: https://github.com/wejs/we-plugin-form/tree/master/server/templates/forms 
