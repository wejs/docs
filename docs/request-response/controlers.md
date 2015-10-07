# Controllers

> Controllers are where you get data from models and run response functions for send data to user in differents formats.
> Same as MVC controller
> All controllers is an instance of Controller prototype: https://github.com/wejs/we-core/blob/master/lib/class/Controller.js

> Functions defined in controller is called actions and every route access a controller.action and all actions works like express middlewares which recieves resquest, response and next params.

> Single record routes have the record preloaded in context middleware and is avaible in controller as res.locals.record


Example: https://github.com/wejs/we-core/blob/master/server/controllers/user.js