# HTTP Basic Auth

[HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication)
is an easy way to add username and password login to a service, though it needs
HTTPS to be secure.

Caddy has a [`basicauth` directive] for adding it, which requires a matcher (use `/` for the whole site) and a block of username/password hash pairs. Password hashes can be obtained with `caddy hash-password`.

Here's an example from Caddy's docs:

```Caddyfile
basicauth /secret/* {
	Bob JDJhJDEwJEVCNmdaNEg2Ti5iejRMYkF3MFZhZ3VtV3E1SzBWZEZ5Q3VWc0tzOEJwZE9TaFlZdEVkZDhX
}
```

And here's a reverse-proxy service with basic auth enabled:

```Caddyfile
webdun.nathanielknight.ca {
    reverse_proxy * <ip address of my home server>:<service port>
    basicauth * {
        nknight <password hash that I'm not going to show you even though it would probably be fine if I did>
    }
}
```

[`basicauth` directive]: https://caddyserver.com/docs/caddyfile/directives/basicauth