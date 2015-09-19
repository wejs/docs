#Request and response

We.js request and response have 3 steps: **Receive / parse**, **Process** and **Send** the response

- Receive the request
  - Set default vars
  - Set custom response functions
  - Set express engine configs
  - Set response layout
  - Load morgan debuger ( dev or test env )
  - Body parser middleware
  - Cookie parser middleware
  - Session store middleware ( todo remove from token requests )
  - Set flash messages ( todo remove from token requests )
  - Run CORS Middleware
  - Run passport middlewares
  - if are a public file request the file from public folders
  - if are admin, return with admin page
  - Run the we.url middleware
  - Set i18n configs
- Process the request
  - Run context loader middleware
  - Run ACL middleware
  - Run Group ACL middleware (group plugin)
  - Run upload middleware ( if in current route config )
  - Run controller
- Send the response
  - Run send response middleware
  - Run the response formater method
  - Send the formated response to user
