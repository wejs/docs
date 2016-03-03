# Run with cluster module

> In we.js v1.0 you can run multiple instances of we.js using Cluster module of node.js

### Change your app.js file to:

```js
var cluster = require('cluster');

if(cluster.isMaster) {
  var numWorkers = require('os').cpus().length;

  console.log('Master cluster setting up ' + numWorkers + ' workers...');

  for(var i = 0; i < numWorkers; i++) {
      cluster.fork();
  }

  cluster.on('online', function(worker) {
      console.log('Worker ' + worker.process.pid + ' is online');
  });

  cluster.on('exit', function(worker, code, signal) {
      console.log('Worker ' + worker.process.pid + ' died with code: ' + code + ', and signal: ' + signal);
      console.log('Starting a new worker');
      cluster.fork();
  });
} else {
  /**
   * Main app file, load we-core and start the app
   */

  // start the we.js core
  var We = require('we-core');
  // instantiate an new app
  var app = new We();

  app.go(function (err) {
    if (err) return console.error(err);
  });
}

```
