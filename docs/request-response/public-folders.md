# Public folders

We.js have **public folders** preconfigured where you can put static files. 

The folder **files/public** it is publicly accessible and all projects, plugins and themes have this folder.

In production enviroment configure your host (Apache, Nginx ...) to serve files directly from public folders. We have some configuration examples in https://wejs.org/docs/we/web-servers .

## How to access in browser?

All project, plugins and themes have an **/files/public** folder where you put your publicly acessible files.

If you put an `image.png` file inside the public folder, it will be acessible in:

### If put in project public folder

Will be accessible in url: `http://localhost:4000/public/project`

### If put in plugin public folder

Will be accessible in url: `http://localhost:4000/public/plugin/[plugin name]/files/image.png` 

### If put in theme public folder

Will be accessible in url: `http://localhost:4000/public/theme/[theme name]/image.png`



Change http://localhost:4000 to your host name
