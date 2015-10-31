# Gulp tasks

> Default We.js projects have a defalt gulp tasks powered by we-gulp-tasks-default npm module
> 
> You can change the default gulp tasks, add or remove from your project

See https://github.com/wejs/we-gulp-tasks-default for all tasks

## Installation

This feature is installed by default in we.js projects but you can change or install it if not is avaible in your project

1- Install the npm packages in your we.js project:
```sh
npm install --save gulp we-gulp-tasks-default
```

2- Add in your gulpfile.js

File: gulpfile.js

```js
var we = require('we-core');
var projectFolder = process.cwd();
var gulp = require('gulp');
var weGulpTasks = require('we-gulp-tasks-default');

weGulpTasks(we, gulp, projectFolder, function doneTask() {
  we.exit(function(){
    process.exit();
  });
});
```

## Avaible tasks:

### Build task

Generate concat and minify your project assets and prepare assets files to use in production enviroment

Usage:

```sh
npm run build
```