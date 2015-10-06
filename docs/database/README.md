# Database and ORM and session database

> We.js use Sequelize as Object-relational mapping (ORM) with extra steps for allow model extensions in plugins

> Current We.js database feature only suport SQL databases ('mysql'|'mariadb'|'sqlite'|'postgres'|'mssql') 

> For user session we.js projects use the express-session

## Important variables

In project execution default connection is avaible at `we.db.defaultConnection` and all models is avaible in `we.db.models`

## Database configuration

By default all projects have 3 database connection configurations how is selected by enviroment.
Ex: if you are in dev enviroment it will start the default database connections with we.config.database.dev configuration

For all options see: http://sequelize.readthedocs.org/en/latest/api/sequelize/#class-sequelize

### Mysql

Build in mysql suport and the session configuration is automatically set with database settings and the default configuration for mysql is:

file: `config/local.js`

```js
  // ...
  database: {
    prod: {
      dialect: 'mysql',
      database: 'databaseName',
      username: 'databaseUser',
      password: 'password'
    },
    dev: {
      dialect: 'mysql',
      database: 'databaseName',
      username: 'databaseUser',
      password: 'password'
    },
    test: {
      dialect: 'mysql',
      database: 'databaseName',
      username: 'databaseUser',
      password: 'password'
    }
  }
  // ...
```

### PostgreSQL 

For suport with postgreSQL you need we-core v0.3.89+

To configure the postgreSQL database you need to:

1. Install **pg** and **pg-hstore** in your project:
```js
npm install --save pg pg-hstore
```
2. Configure the project **config/local.js**:
```js
  // ...
  database: {
    prod: {
      dialect: 'postgres',
      database: 'databaseName',
      username: 'databaseUser',
      password: 'password'
    },
    dev: {
      dialect: 'postgres',
      database: 'databaseName',
      username: 'databaseUser',
      password: 'password'
    }
  },
  // ...
```
3. Configure a session store
  We-core mysql session store is disabled then you need to configure you session store.
  See the session store page