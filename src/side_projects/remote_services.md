For a service on a remote host, use the following Caddyfile:

```Caddyfile
/etc/caddy/sites/YOURSITE.EXAMPLE.com {
    reverse_proxy ADDRESS_OF_SERVICE
}
```