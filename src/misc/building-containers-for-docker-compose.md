# Building Containers for Docker Compose

This section describes how to build custom containers for
[Docker Compose](https://docs.docker.com/compose/).

Docker Compose is often used to give users an easy way to run apps that have
dependencies. For example, an app might provide a container with its own code,
but need a separate database or cache, each of which is provided as a service in
the `docker-compose.yml` file.

This section describes how to create a container from a `Dockerfile` instead of
from an upstream image.

In the service's definition in `docker-compose.yml` file, we specify a
[`build`](https://docs.docker.com/compose/compose-file/compose-file-v3/#build)
object instead of an `image`:


```yaml
version: "3.9"
services:
  <service name>:
    image: <this is the *name* of the built image; docker won't go find this image elsewhere>
    build:
      context: <path to a dir or git repo with a Dockerfile>
      dockerfile: <name of dockerfile (if not "Dockerfile")>
```
