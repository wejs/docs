# Database and ORM

> We.js use Sequelize as Object-relational mapping (ORM) with extra steps for allow model extensions in plugins

> Current We.js database feature only suport SQL databases ('mysql'|'mariadb'|'sqlite'|'postgres'|'mssql') 

## Important variables

In project execution default connection is avaible at `we.db.defaultConnection` and all models is avaible in `we.db.models`

## Database configuration

By default all projects have 3 database connection configurations how is selected by enviroment.
Ex: if you are in dev enviroment it will start the default database connections with we.config.database.dev configuration

For all options see: http://sequelize.readthedocs.org/en/latest/api/sequelize/#class-sequelize

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
