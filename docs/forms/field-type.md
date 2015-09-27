# Field types

> Reusable templates for build form field types

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

## Links

- All core form fields see https://github.com/wejs/we-plugin-form/tree/master/server/templates/forms 