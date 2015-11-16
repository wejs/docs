# Web servers and proxy

> You can host multiple apps in same server and every app need be in diferent port. For handle this we use one web server with proxy like nginx or apache how proxy requests from http or https port to internal app port

> Tested with NGINX and Apache

##  NGINX server configuration

### Example:

Lets configure the virtual host for **http://example.com** where then We.js app is runnig in **127.0.0.1:6000** inside same server in **/var/wejs/apps/example.com** folder

```
# the IP(s) on which your We.js server is running. in this example is host 127.0.0.1 and port 6000.
upstream app_example.com {
    server 127.0.0.1:6000;
    keepalive 8;
}

# the nginx server instance
server {
    listen 0.0.0.0:80;
    server_name example.com;
    # nginx http access log
    access_log /var/log/nginx/example.com.log;
    
    ##
    ### Static file configuration for project in localhost
    ##
    
    ##
    # Project public static files
    ##
    location /public/project {
      expires 1d;
      add_header Cache-Control "public";
      alias /var/wejs/apps/example.com/files/public;
    }

    ##
    # Themes public static files
    ##
    location ~ ^/public/theme/(?<name>[A-Za-z0-9_-]+)/(?<p>.*)$ {
      expires 1d;
      add_header Cache-Control "public";
      alias /var/wejs/apps/example.com/node_modules/$name/files/public/$p;
    }

    ##
    # Plugins public static files
    ##
    location ~ ^/public/plugin/(?<name>[A-Za-z0-9_-]+)/files/(?<p>.*)$ {
      expires 1d;
      add_header Cache-Control "public";
      alias /var/wejs/apps/example.com/node_modules/$name/files/public/$p;
    }
    ## END static config

    # pass the request to the node.js server with the correct headers
    # and much more can be added, see nginx config options
    location / {
      proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header Host $http_host;
      proxy_set_header X-NginX-Proxy true;

      proxy_pass http://app_example.com/;
      proxy_redirect off;

      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection "upgrade";

    }
 }
```


### Apache
TODO!