# Request order and limit in lists

We.js have an build in suport for set query order and limit with query params

## Limit

<p>Limit is set with **limit** query param.<br>
Example: If you have 200 post records in database and want get only 20 records per request then you can use the request:</p>

```
http://[host]/post?limit=20
```

> Query limit dont returns more than **we.config.queryMaxLimit** limit configuration that is set to 300 records by default

## Sort / Ordering

Ordering may be set with:

- **order** query param
  Example: `http://[host]/post?order=title ASC`
- **sort** query param
  Example: `http://[host]/post?sort=title ASC`
- **sort** with **sortDirection** query params
  Example: `http://[host]/post?sort=title&sortDirection=ASC`  