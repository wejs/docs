# Generate a blog project

> With yeoman:

```sh
yo wejs:blog
```
We.js ask you for the name of your project

```sh
     _-----_
    |       |    .--------------------------.
    |--(o)--|    |     We.js simple blog    |
   `---------´   |  project generator! |o/  |
    ( _´U`_ )    |            |o/           |
    /___A___\    |                          |
     |  ~  |     |   generate one testable  |
   __'.___.'__   |      we.js project!      |
 ´   `  |° ´ Y ` '--------------------------'

? Your blog name: blogname
```

Or if you want something simple its possible to make a simple app with `yo wejs:app` 

### Enter in your project folder
```sh
cd we-project-blog-blogname
```
### Install npm dependencies:

```sh
npm install
```

### Configure your database:

Edit ```config/local.js``` file and change database configuration to your database.

### Start the project with:

```sh
npm run dev
```


### For load default locales run:

This will load all default locales from plugins and save this locales in your project.

```sh
we loadLocales
```



