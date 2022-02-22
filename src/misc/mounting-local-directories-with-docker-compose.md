# Mounting Local Directories with Docker Compose

To mount local directories with Docker Compose for data persistence or to edit
code outside of the container, add a volume mount to your service:

```yaml
version: "3.9"
services:
  <service-name>:
    image: python:slim
    volume:
      - ./in-project:/in-container
      - ~on-host:/in-container
```