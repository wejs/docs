# How to install Node.js and We.js in windows 10

## Requirements

### Node.js

1. Go to https://nodejs.org
  * click in **Download for windows** link
  * download and run the install program

### Mysql server

See: http://dev.mysql.com/downloads/mysql/ and follow the instructions

### Graphicsmagick 

See: ftp://ftp.graphicsmagick.org/pub/GraphicsMagick/windows/

## The we.js

In your power shell or other shell run:

First clear cache to skip some permissions error:

```sh
npm cache clear
````

Then install we, yo and generator-wejs:

```sh
npm install we yo generator-wejs -g
```


# Know problems

- `npm run [command]` and `npm test` dont works then use the command `node ./app.js` for run your app
- if return network error in `npm install` command, delete the node_modules folder and reinstall
- if you have a file open in your editor from any submodule or linked module the npm link or npm install commands will return permissions error
