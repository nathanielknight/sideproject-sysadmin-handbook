# Docker Containers



## Back Up a Volume

[Docker Volumes](https://docs.docker.com/storage/volumes/) are a good fit for side-project data.

To save data from a docker volume, you'll need to know:

* the container you want to back up from, and
* the directory where the volume is mounted.

With that, you can run

```shell
docker run --rm --volum
```

See [this section](https://docs.docker.com/storage/volumes/#backup-restore-or-migrate-data-volumes)
of the documentation for details.
