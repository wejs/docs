# Generate a blog project

Lets make the blog project ...

Install graphicsmagick dependency http://www.graphicsmagick.org/ (optional for we-plugin-file and blog project). Check in your package manager

With yeoman generator-wejs:

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
     |  ~  |     |   Generate one testable  |
   __'.___.'__   |      we.js project!      |
 ´   `  |° ´ Y ` '--------------------------'

? Your blog name: blogname
```

Note: if you want something simple its possible to make a simple app with `yo wejs:app` 

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
we go
```

### For load default locales run:

This will load all default locales from plugins and save this locales in your project.

```sh
we loadLocales
```
