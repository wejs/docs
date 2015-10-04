# Widget

> HTML blocks how are rendered in html responses or load with widget API

Widgets may be created in plugins or projects

## How create a widget
With yeoman generator-wejs

1. Enter in your project or plugin folder
2. Tip:
```sh
yo wejs:widget
```
3. Then type the widget name

## Widget API

#### Get the widget list:
```
get /api/v1/widget
```

#### Get one widget:
```
get /api/v1/widget/:id([0-9]+)
```
