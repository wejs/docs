# Models

We.js model is a wrapper of sequelize models and allows plugin changes with hooks in model definition before set it in sequelize.

Related documentation in sequelize docs: http://docs.sequelizejs.com/en/latest/docs/models-definition/ 

## How to create a model?

With we.js yeoman generator!

Create one empty model:

```sh
yo wejs:model post
```

With model attribute in generation:

```sh
# create the post model with title, bodu and published attributes
yo wejs:model post title:string:allowNull=false body:text published:boolean
```

With associations:

```sh
# create the post model with title attibute and creator association, associated with user
yo wejs:model post title:string creator:belongsTo:user
```

## Model example

Example below is created with command:

```sh
yo wejs:model post title:string:allowNull=false body:text published:boolean creator:belongsTo:user
```

Example file: `server/models/post.json`

```json
{
  "attributes": {
    "title": {
      "type": "STRING",
      "allowNull": false
    },
    "body": {
      "type": "TEXT"
    },
    "published": {
      "type": "BOOLEAN"
    }
    
  },
  "associations": {
    "creator": {
      "type": "belongsTo",
      "model": "user"
    }
    
  },
  "hooks": {
    "afterCreate": []
  }
}
```
