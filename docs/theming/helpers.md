# Template helpers

> Helpers is a handlebars functions which allow to do some logic in functions and reuse in templates

See more information about handlebars and helpers in: http://handlebarsjs.com/

Helpers can be created in plugin or project and the helers folder is `server/helpers/*.hbs`

## How to create a helper

With yeoman generator-wejs!

1. Enter in your project or plugin folder
2. use the `yo wejs:helper` command

```sh
yo wejs:helper
```

## Core helpers

### can helper

Check if role name list have one permission how allows do something

Usage:

```hbs
  {{#can permission=permissionName roles=req.userRoleNames}}
    can
  {{else}}
    cant
  {{/can}}
```

### If condition helper

Check if v1 is equal to v2

Usage:

```hbs
  {{#ifCond v1 v2}}
      v1 is equal to v2
  {{else}}
      v1 is not equal to v2
  {{/ifCond}}
```

### Is array

Check if a variable is array

Usage:

```hbs
  {{#isArray array}}
      is array
  {{else}}
      not array
  {{/isArray}}
```

## Is pair

Check if one number is pair 0, 2, 4 ... n

Usage:

```hbs
  {{#isPair number}}
    is pair/even
  {{else}}
    is odd
  {{/isPair}}
```

## Link to record

Generate a html link for database record

Usage:

```hbs
  {{#link-to-record record=record class="btn btn-default"}}Text inside the link{{/link-to-record}}
```

## Link to

Resolve and generate a html link with route name and params

```hbs
{{#link-to 'routeName' class="btn btn-default"}}Text inside the link{{/link-to}}
```

## Paginate

Generate a paginationn for we.js router lists

Usage: 

```hbs
 {{paginate count=metadata.count limit=query.limit currentPage=query.page req=req}}
```

## t - localization helper

Localize / translate a string with current user locale

Usage: 

```hbs
{{t 'string'}}
```


## We Contains

Check if the array contains a value

Usage:

```hbs
  {{#we-contains array value}}
      {{array}} contains {{value}}
  {{else}}
      {{array}} not contains {{value}}
  {{/we-contains}}
```

## Date

Print date in custom formats

Usage:

```hbs
{{we-date date format locals=locals}}
```

## Event

A mark how allows to extend current HTML with node.js events.

Usage:

```hbs
 {{we-event event="we-html-body-start"}}
```


## We grid

Calc and generate html grids

Usage:

```hbs
{{#we-grid items=array cols=colCount}}each item html{{/we-grid}}
```

## Strip tags

Remove all tags from text and print it

Usage: 

```hbs
{{we-strip-tags text='' maxLength=170}}
```
