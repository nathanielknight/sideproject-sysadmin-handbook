# DNS

The DNS configuration for the sideproject server should be pretty straightforward.

The big things you want are:

- An `A` record that points `example.com` to your server, and
- a wildcard `A` record that points `*.example.com` to your server.

You may also have to direct your domain name registrar to point your
domain at your cloud provider's DNS servers; the details will depend on
what services you're using for each.