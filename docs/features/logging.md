# Logging

Log functions is avaible at **we.log** powered by winston

```js
// logs by log level
we.log.error('message');
we.log.warn('message');
we.log.info('message');
we.log.debug('message');
we.log.verbose('message');
```


## Log configuration and custom transporters:

Log is configurable with winston module configuration in project **config/log.js** file.

Example:

```js
var winston = require('winston');

module.exports.log = {
  level: 'info' ,
  colorize: true,
  timestamp: true,
  json: true,
  stringify: true,
  prettyPrint: true,
  depth: 5,
  showLevel: true,
  transports: [
    new (winston.transports.File)({
      filename: 'files/app.log'
    })
  ]
}
```

## Links:

- Winston reporitory: https://github.com/winstonjs/winston
