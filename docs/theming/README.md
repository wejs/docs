# We.js theming

> Change the visual and structure of your project in html response (default response)
> 
> Themes can override default plugin templates to change html structures or classes
> 
> We.js theme is npm modules

By default we.js has two kinds of themes, the `app` and `admin` theme.

The admin theme will be used in /admin pages and the app theme will be used in other routes

## HTML, layouts and regions

Theme structure has one `html.hbs` and multiple `layouts` with `regions`

### HTML

The file html.hbs is required in all themes and need to be in `templates/server/html.hbs` 
Inside the html.hbs you will add the <html>, <head> and <body> tags the assets helpers.

#### Assets helpers

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

A layout is `.hbs` files defined in `theme.js` file and is rendered inside the `html.hbs` file. 

To define one region inside layout template use:

```hbs
{{#region 'highlighted'}}{{/region}}
```

#### Regions

Template helper how mark where the widgets will be rendered:

```hbs
{{#region 'highlighted'}}{{/region}}
```

#### Widget

Widget is like blocks with inplace edit and sort.
We.js have a widget API and widget may be get with this API for Single page apps and is rendered in regions for html responses

