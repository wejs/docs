# We.js theming

Change the visual and structure of your project in html response (default response)
 
Themes can override default plugin templates to change html structures or CSS class
 
We.js theme is a npm module

By default we.js has two kinds of themes, the **app** and **admin** theme.

The admin theme will be used in /admin pages and the app theme will be used in other routes

Avaible in: **we-plugin-view**

## HTML, layouts and regions

Theme structure has one `html.hbs` and multiple `layouts` with `regions`

### HTML

The file html.hbs is required in all themes and need to be in **templates/server/html.hbs**
Inside the html.hbs you will add the `<html>`, `<head>` and `<body>` tags the assets helpers.

#### Asset helpers

Template helpers where you will add 
```hbs
<head>
  {{!-- render metadata tags --}}   
  {{{render-metadata-tags}}}
  {{!-- render css head tags --}}
  {{{render-stylesheet-tags}}}
  {{!-- render .js head tags like jquery --}}  
  {{{render-javascript-tags 'header'}}}
</head>
<body>
 {{!-- template event, plugins may use this for add code --}}
 {{we-event event="we-html-body-start"}}
 {{!-- layoutHtml print the theme layouts --}}
 {{{layoutHtml}}}
 {{!-- javascript bootstrap configs --}}
 {{{render-bootstrap-config}}}
 {{!-- render footer javascript tags --}}
 {{{render-javascript-tags 'footer'}}}
 {{!-- render components html like widget modal --}}
 {{{render-client-component-templates}}}
 {{!-- template event, plugins may use this for add code --}}
 {{we-event event="we-html-body-end"}}
</body>
```

#### Layouts

A layout is **.hbs** files defined in **theme.js** file and is rendered inside the **html.hbs** file. 

To define one region inside layout template use:

```hbs
{{#region 'highlighted'}}{{/region}}
```

#### Regions

Template helper how mark where the widgets will be rendered:

```hbs
{{#region 'highlighted'}}{{/region}}
```

#### Widgets

The widget is like blocks with inplace edit and sort.
We.js have a widget API and widgets may be get with this API for single page apps


## Configuration

Every theme have a theme.js file with configurations where you will define how layouts and regions will be avaible.

#### Example: 

```js
module.exports = {
  // theme config
  configs: {
    // theme email template configs
    emailTemplates: {
      // path to email templates
      path: 'templates/email',
    },
    // the theme javascript file
    // This javascript file will be added after plugin and project .js files
    javascript: 'files/public/script.js',
    // the theme css file
    // This css will be added after project and plugin CSS and dont are minified with others CSS
    stylesheet: 'files/public/style.css'
  },
  // Theme layouts
  // List and configure all avaible layouts for this theme
  layouts: {
    // The default layout, REQUIRED!
    'default': {
      // complete sys path to .hbs file for use as layout
      template: __dirname + '/templates/server/layouts/default-layout.hbs',
      // regions avaible in this layout
      regions: {
        highlighted: {
          // readable region name
          name: 'Highlighted'
        },
        sidebar: {
          name: 'Sidebar'
        }
      }
    },
    // A custom layout, you can use a diferente layout for home page or other page, but need to set this layout in route configs with layoutName: '' config
    'home': {
      template: __dirname + '/templates/server/layouts/home.hbs',
      regions: {
        highlighted: {
          name: 'Highlighted'
        },
        afterContent: {
          name: 'After content'
        }
      }
    },
  },
  widgets: {}
};

```

