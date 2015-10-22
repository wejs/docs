# Command-line interface (CLI)

> We.js cli is a util tool for manage and develop your we.js project

To see all commands after install we cli type `we` in your terminal
 
## Installation

```sh
npm install -g we
```

## Avaible commands

#### version            
Get current we cli version
**Usage:**
```we version```

#### status
Get data about your project like all models and controllers loaded
**Usage:**
```we status```

#### routes
Print all project routes in terminal
**Usage:**
```we routes```

#### console
Start a node.js RELP console with your we.js project loaded as `we` console variable
**Usage:**
```we console```

#### setUserAsAdmin
Set one user as project administrator with userId
**Usage:**
```we setUserAsAdmin 1```
This will set user 1 as administrator

#### uli
Generate one time login url with userId
**Usage:**
```we uli 1```
This will print in console one time login url for user with id 1

#### update
Run pending plugins and project database updates
**Usage:**
```we update```

#### loadLocales
Load plugin default locales in current project
**Usage:**
```we loadLocales```

## Links

We.js cli repository: https://github.com/wejs/we





