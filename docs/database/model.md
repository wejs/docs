# Models

We.js model is a wrapper of sequelize models how allow one plugin change other plugin model

Related documentation in sequelize docs: http://docs.sequelizejs.com/en/latest/docs/models-definition/ 

## How to create a model?

With we.js yeoman generator!

```sh
yo wejs:model
# then type your model name
```

## Model example

Lets make the post model file with 2 attributes: `title` and `text` and with one association: `creator -> user`

Example file: `server/models/post.js`

```js
/**
 * post
 *
 * @module      :: Model
 * @description :: post model
 *
 */

module.exports = function postModel(we) {
  return model = {
    // define you model here
    // see http://docs.sequelizejs.com/en/latest/docs/models-definition
    definition: {
      title: {
        type: we.db.Sequelize.TEXT, // use sequelize types to set field type
        allowNull: false
      },
      text: {
        type: we.db.Sequelize.TEXT,
        formFieldType: 'html'
      }
    },
    // Associations
    // see http://docs.sequelizejs.com/en/latest/docs/associations
    associations: {
      creator: { type: 'belongsTo', model: 'user' } // suport others sequelize association params
    },
    options: {
      // title field, for default title record pages
      titleField: 'title',
      // Class methods for use with: we.db.models.[yourmodel].[method]
      classMethods: {},
      // record method for use with record.[method]
      instanceMethods: {},
      // Sequelize hooks
      // See http://docs.sequelizejs.com/en/latest/api/hooks
      hooks: {}
    }
  };
};
```