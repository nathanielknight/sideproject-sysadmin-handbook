# Web Server

Caddy is the web server we'll use to accept web requests, direct traffic to our projects,
serve static files, and generate TLS certificates.

## Installation

Instructions for installing it are [here](https://caddyserver.com/docs/install#debian-ubuntu-raspbian).

I ended up using [xcaddy](https://github.com/caddyserver/xcaddy) to do a custom build with the
[caddy-lf](https://github.com/mholt/caddy-l4) plugin, but the default might be enough.


## Configuration

The main directory for Caddy's configuration should be in `/etc/caddy/`. The main configuration file
is `/etc/caddy/Caddyfile`. Replace it's contents with:

```caddyfile
import sites-enabled/*
```


## Static Sites

To serve a static site:

1. Upload its contents somewhere on the server.
1. Add a file for it in `/etc/cadd/sites`

```caddyfile
SITE_DOMAIN {
    file_server
    root * PATH_TO_CONTENT
}
```
