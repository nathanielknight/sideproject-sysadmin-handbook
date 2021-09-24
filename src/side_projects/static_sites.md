# Static Sites

This section describes how to deploy static websites. It doesn't get in to how
you generate the content, but should work with any system that outputs a bunch
of HTML, CSS, JavaScript, and other files into a directory that gets served as a
website (e.g. hand-written HTML, static site generators, compiled React sites).

It presumes that you're using version control or something similar to manage
your data, so it doesn't describe how to back up your static site.

## Setup

You'll need somewhere on your server to store the files. I like to have a
non-admin user with a directory-per-website named for the site.

```shell
/home/nknight/an.example.ca/
/home/nknight/another.example.com/
```

You'll also need a Caddy file for your site.

```Caddyfile
/etc/caddy/sites/YOURSITE.EXAMPLE.COM
YOURSITE.EXAMPLE.COM {
    file_server
    root * /PATH/TO/CONTENT/FOR/YOUR/SITE
}
```

## Deploying Changes

If you've prepared the files for your static site there are *many* ways to
upload them to the server.

To copy the contents of `source_dir` to `destination_dir` on a remote `host`, run:

```shell
rsync -avz source_dir/ user@host:path/to/target_dir/
```

Note that:

* **The trailing slashes are important**
  (as described in [`rsync`'s manual page](https://linux.die.net/man/1/rsync)).
* `rsync` must be installed on the *host* as well as the computer you're
  deploying from.
* You need to be able to SSH to the remote host.
