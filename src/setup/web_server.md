# Web Server

Caddy is the web server we'll use to accept web requests, direct traffic to our projects,
serve static files, and generate TLS certificates.

## Installation

Instructions for installing it are [here](https://caddyserver.com/docs/install#debian-ubuntu-raspbian).

## Configuration

The main directory for Caddy's configuration should be in `/etc/caddy/`. The main configuration file
is `/etc/caddy/Caddyfile`. Replace it's contents with:

```caddyfile
import sites/*
```

The vanilla server-wide configuration is good enough for us, and we can do
overrides on a per-site basis.

We'll describe how to configure individual projects in a later section.
