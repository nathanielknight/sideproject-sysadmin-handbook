# Deploying projects


## Static files

Static files can be deployed with [RSync](https://en.wikipedia.org/wiki/Rsync):

```shell
rsync -avz $SOURCE $DEST
```

Note that it must be installed on the host as well as the computer you're
deploying from.
