# Create a simple resource API

Lets use the generator to make the post resource.

> Tip: Use `we routes` command to list all routes with suport to filters, see options ẁith `we routes -h`

## Make the `post` resource

Lets see how to make a resource with generator-wejs or step by step:

### 1- With resource generator-wejs

This will generate the controller, model and resource routes.

Inside your project or plugin:

```sh
yo wejs:resource post title:string:allowNull=false teaser:text body:text published:boolean
```

> **yo wejs:resource post** generate the post model and **title:string:allowNull=false teaser:text body:text published:boolean** will be model attributes

And done!

TIP: Use `we routes` command to list and filter all routes in your project.

This will make:

```
## API:
post /post # create
get /post # list, find
get /post/:postId # find one
put /post/:postId # update one
delete /post/:postId # delete one

```

And if **we-plugin-view** is installed will generate:

```
## API:
post /post # create
get /post # list, find
get /post/:postId # find one
put /post/:postId # update one
delete /post/:postId # delete one
## pages:
get /post/create
get /post/:postId/edit
post /post/:postId/edit
get /post/:postId/delete
post /post/:postId/delete

```

