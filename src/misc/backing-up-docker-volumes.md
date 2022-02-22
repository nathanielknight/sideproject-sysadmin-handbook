# Backing up Docker Volumes

Managed docker volumes are an easy way to persist data between container restarts,
but it can be nerve-wracking to risk data-loss when performing other Docker operations
(such as updating a service to use a new image).

To backup docker data we'll create an ephemeral container with two mounts: one 
that contains the data we want to back up and one that maps to somewhere safe on the host.
Then we run a command (e.g. `tar`) to create the backup.

This process is from the Docker docs
[here](https://docs.docker.com/storage/volumes/#back-up-a-volume).

Here's an example:

```shell
docker run --rm -it -v $(pwd):/backup --volumes-from <container-to-backup> ubuntu <backup cmd>
```

Docker Compose services can be backed up this way as well, as those containers will show up in Docker.