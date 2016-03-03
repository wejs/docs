# Create a simple resource API

> For create a We.js resource API in your project you need to create one model, one controller and set the resouce

## Lets make the `post` resource

> Lets see how to make a resource with generator-wejs or step by step:

### 1- With resource generator-wejs

This will generate the controller, model and resource routes.

Inside your project or plugin:
```sh
yo wejs:resource post
```

And done!

### 2- Step by step without the generator-wejs

#### Create a model

With yeoman!

1- Create the model file
```sh
yo wejs:model post
```

2- Set your model attributes in model.definition

Open the model file in your editor `server/models/post.js` and add:

```js
// ...
    definition: {
      title: {
        type: we.db.Sequelize.TEXT,
        allowNull: false
      },
      text: {
        type: we.db.Sequelize.TEXT,
        formFieldType: 'html'
      }
      // ...
   }
// ...
```

save your file

#### 2 Create an controller

Create the file `server/controllers/post.js` with:

```js 
module.exports = {};
```

All controllers are an instance of: https://github.com/wejs/we-core/blob/master/lib/class/Controller.js

And have all default controller actions.

#### 3 Set route resource

Open the `plugin.js`file inside your project folder and add:

```js
  // by default the url will be /post
  plugin.setResource({
    name: 'post'
  });
```

This will make:

```
get /post/create
get /post
get /post/:postId
get /post/:postId/edit
post /post/:postId/edit
get /post/:postId/delete
post /post/:postId/delete
```

### Done 

Now to see your resource start the project with `npm run dev` , open your browser and access `/post/create` to access your form and `/post` to access your list;

After publish your project don't forget to configure your project permissions in `/admin/permissions` page



