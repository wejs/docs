# Plugin Style sheet and Javascript

> Style sheets and client Javascript register and order is avaible for we.js **html** repsonse type.
> 
> With this feature you can register assets with weight and unique names how allows to others plugins add others assets after or before any file

The HTML response have a windows.we object with all client side functions and logic.

## Register a Stylesheet file:

In **plugin.js** file:

```js
    plugin.addCss({
      // weight for use in assets print order
      weight: 5, 

      // Plugin name where this asset is localed
      pluginName: 'we-core',

      // path to you file, 
      // all assets need be inside the **files/public/** folder
      path: 'files/public/jquery.cssemoticons/jquery.cssemoticons.css'
    }
```

## Register a client side javascript file

In **plugin.js** file:

```js
   plugin.addJs({
      // weight for use in assets print order    
      weight: 6, 

      // Plugin name where this asset is localed
      pluginName: 'we-core',

      // all assets need be inside the **files/public/** folder
      path: 'files/public/js/load-image.all.js'
    }
```


## For print the .css e .js file in your template use the:

This functions is used in theme **html.hbs** files:

### Render stylesheet tags

```hbs
{{{render-stylesheet-tags}}}
```

### Render javascript tags

In header:

```hbs
{{{render-javascript-tags 'header'}}}
```

In footer:

```hbs
 {{{render-javascript-tags 'footer'}}}
```

## How to build assets for production

You need to contact and minify all assets after deploy you project for this use the command:

```sh
npm ru build
```

Or 

```sh
gulp build
```

How will run all default gulp tasks for prepare your assets for poduction

## Examples

See in we.js plugins like the we-plugin-file plugin.js file for usage examples: 
https://github.com/wejs/we-plugin-file/blob/master/plugin.js#L232
