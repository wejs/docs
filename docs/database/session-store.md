# Session store

A database for store user sessions and temporary data. 
By default it will try to use the mysql database

We.js use the **express-session** npm module and is compatible with session stores like **connect-redis**

Express session: https://github.com/expressjs/session

## How to configure:

In your project:

1. Install you session store npm module.
2. Configure in your **config/local.js** project configuration file:
file: config/local.js

```js
// require the session store npm module
var SessionStore = require('express-mysql-session');

module.exports: {
  // -- others configs
  session: {
    store: new SessionStore({
      // pass the session store settings, see the session store docs
      host: 'localhost',
      port: 3306,
      user: 'username',
      password: 'password',
      database: 'databasename'
    }),
    // others settings ...
    resave: true,
    saveUninitialized: true
  },
    // -- others configs
}
```

## Example config with Redis as session store

### 1- install dependencies

```sh
npm install --save redis connect-redis express-session
```

### 2- Configure your local.js

File: *config/local.js*

```js
var session = require('express-session');
var RedisStore = require('connect-redis')(session);
var redis = require('redis');

// change host and port to your redis cfgs:
var redisHost = 'localhost';
var redisPort = 6379;

//CREATE REDIS CLIENT
var redisClient = redis.createClient({
  host: redisHost,
  port: redisPort
});


// then inside your module exports:
module.exports = {
   //... others configs
   
   // you app session configs:
   session: {
    secret: 'someSecretText',
    store: new RedisStore({
      // pass the session store settings, see the session store docs
      client: redisClient,
      host: redisHost,
      port: redisPort,
      ttl: 31557600, // 1 year, this is set by secconds
      // db: 50
    }),
    resave: false, // don't save session if unmodified
    saveUninitialized: false
  },

  // others configs ...
};

```


