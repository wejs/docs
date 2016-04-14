# Cron tasks

> With We.js cron feature you can set functions to run with linux cron or other task manager after some time
> 
> May be add inside project or plugin

# How to add

To add a cron function you need to create the `cron.js` file inside your project or plugin folder

#### Example File

file `cron.js`

```js
module.exports = function (we, done) {
  // do something ...
  // database is avaible at we.db
  // then call done();
  done();
};
```

## How to run

Cron functions run with we cli `we cron` command

#### How to run with local we cli install

1. first install the cli localy *or* inside your project:

    ```sh
    npm install we
    ```

2. then run the we cli cron command with:
    ```sh
    node node_modules/.bin/we cron
    ```

#### How to run with a global we cli install

Inside the project folder tip:

```sh
we cron
```
