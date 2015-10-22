# Session store

> A database for store user sessions, by default we.js try to use the mysql database
> We.js use the **express-session** npm module the have suport to compatible session stores like **connect-redis**

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

