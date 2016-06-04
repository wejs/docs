# Heroku configuration

Tips of how to install one We.js project in heroku.

## Requirements:

Install heroku toolbelt: https://toolbelt.heroku.com/ 
Login in heroku toolbelt

## Configuration:

```sh
# add the procfile
echo "web: node app.js" > Procfile
# check if git is inititalized
git init
# add heroku database config on config/database.js
echo "
module.exports.database = {
  prod: {
    uri: process.env.DATABASE_URL,
    dialect: 'postgres',
    protocol: 'postgres'    
  },
  dev: {
    uri: process.env.DATABASE_URL,
    dialect: 'postgres',
    protocol: 'postgres'    
  },
  test: {

  }
} 
" > config/database.js

# commit
git add .
git commit -m "initial commit"

# create your heroku app
heroku create
git push heroku master
heroku ps:scale web=1

# add one database database
heroku addons:create heroku-postgresql:hobby-dev
# view your app
heroku open

```
