# Hooks and events

> A list of hooks and events ordered by execution

## On We.js bootstrap

this hooks and events run in we.js load ( bootstrap ) and startServer


#### EVENT we:after:load:plugins
```js
we.events.on('we:after:load:plugins', function (we) {
  // your code here ...
});
```

#### HOOK we:check:requirements
```js
we.hooks.on('we:check:requirements', function (we, done) {
  // your code here ...
  done();
});
```

#### HOOK we:models:before:instance
```js
we.hooks.on('we:models:before:instance', function(we, done) {
  // your code here ...
  done();
});
```

#### HOOK we:models:set:joins
```js
we.hooks.on('we:models:set:joins', function(we, done) {
  // your code here ...
  done();
});
```

#### EVENT we:after:load:controllers
```js
we.events.on('we:after:load:controllers', function(we) {
  // your code here ...
});
```

#### EVENT we:after:load:express
```js
we.events.on('we:after:load:express', function(we) {
  // your code here ...
});
```

#### EVENT we:after:load:passport
```js
we.events.on('we:after:load:passport', function(we) {
  // your code here ...
});
```

#### EVENT we:after:init:i18n
```js
we.events.on('we:after:init:i18n', function(we) {
  // your code here ...
});
```

#### HOOK we:create:default:folders
```js
we.hooks.on('we:create:default:folders', function(we, done) {
  // your code here ...
  done();
});
```

#### HOOK we:before:routes:bind
```js
we.hooks.on('we:before:routes:bind', function(we, done) {
  // your code here ...
  done();
});
```

#### HOOK we:after:routes:bind
```js
we.hooks.on('we:after:routes:bind', function(we, done) {
  // your code here ...
  done();
});
```

#### EVENT we:bootstrap:done
```js
we.events.on('we:bootstrap:done', function(we) {
  // your code here ...
});
```

#### HOOK we:server:before:start
```js
we.hooks.on('we:server:before:start', function(we, done) {
  // your code here ...
  done();
});
```

#### HOOK we:server:after:start
```js
we.hooks.on('we:server:after:start', function(we, done) {
  // your code here ...
  done();
});
```


## On server start

#### HOOK we:server:before:start
```js
we.hooks.on('we:server:before:start', function(we, done) {
  // your code here ...
  done();
});
```

#### EVENT we:server:after:create
```js
we.events.on('we:server:after:create', function(data) {
  var we = data.we; // we.js
  var server = data.server; // express server
  // your code here ...
  done();
});
```

#### HOOK we:server:after:start
```js
we.hooks.on('we:server:after:start', function(we, done) {
  // your code here ...
  done();
});
```


## On resquest process

this hooks and events run in request and response process

#### HOOK we:router:request:before:load:context

```js
we.hooks.on('we:router:request:before:load:context', function (data, done) {
  // var res = data.res;
  // var req = data.req;
  done();
});
```

#### HOOK we:router:request:after:load:context

```js
plugin.hooks.on('we:router:request:after:load:context', function (data, done) {
  // var res = data.res;
  // var req = data.req;
  done();
});
```

#### HOOK we-plugin-menu:after:set:core:menus
Menu plugin is required!

```js
we.hooks.on('we-plugin-menu:after:set:core:menus', function(data, done) {
  // var res = data.res;
  // var req = data.req;
  done();
});
```

#### HOOK we:before:send:okResponse
Run code after res.ok() response:

```js
we.hooks.on('we:before:send:okResponse', function (data, done) {
  // var req = data.req;
  // var res = data.res;
  // var recordOrRecords = data.data;
  done();
});
```

#### HOOK we:before:send:createdResponse
Run code after res.created() response:

```js
we.hooks.on('we:before:send:createdResponse', function (data, done) {
  // var req = data.req;
  // var res = data.res;
  // var recordOrRecords = data.data;
  done();
});
```

#### HOOK we:before:send:updatedResponse
Run code after res.updated() response:

```js
we.hooks.on('we:before:send:updatedResponse', function (data, done) {
  // var req = data.req;
  // var res = data.res;
  // var recordOrRecords = data.data;
  done();
});
```

#### HOOK we:before:send:deletedResponse
Run code after res.deleted() response:

```js
we.hooks.on('we:before:send:deletedResponse', function (data, done) {
  // var req = data.req;
  // var res = data.res;
  done();
});
```

## On render HTML page

### Event: we-html-body-start

```js
we.events.on('we-html-body-start', function (data) {
  var html = data.html; // html text is avaible in html.text, this need be in object to use object attr pointer
  var we = data.we;
  var hbsHelperOptions = data.options; 
});
```

### Event: we:config:getAppBootstrapConfig

```js
we.events.on('we:config:getAppBootstrapConfig', function (data) {
  var configs = data.configs; // client side configs
  var we = data.we;
  var context = data.context; // res.locals
});
```

### Event: we-html-body-end

```js
we.events.on('we-html-body-end', function (data) {
  var html = data.html; // html text is avaible in html.text, this need be in object to use object attr pointer
  var we = data.we;
  var hbsHelperOptions = data.options; 
});
```
