# Heroku configuration

Tips of how to install one We.js project in heroku.

Example: https://github.com/wejs-examples/blog-heroku

## Requirements:

Install heroku toolbelt: https://toolbelt.heroku.com
Login in heroku toolbelt

## Configuration:

Install yeoman and the we.js generator if you haven't already
```sh
npm install -g yo
npm install -g generator-wejs
```

Use the we.js generator to generate the heroku configuration:

```sh
yo wejs:heroku
```

## commit

```
git add .
git commit -m "initial commit"
```

## create your heroku app

```sh
heroku create
git push heroku master
heroku ps:scale web=1
```

## add one database database

```sh
heroku addons:create heroku-postgresql:hobby-dev
## view your app
heroku open
```

