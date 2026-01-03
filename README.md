[SeaweedFS](https://github.com/seaweedfs/seaweedfs) Playground.

# Launch containers

```shell
$ docker compose up -d
```

## Web Interfaces

### Master

Visit `http://127.0.0.1:9333/`.

### Filer

Visit `http://127.0.0.1:8888/`

### Admin

Visit `http://localhost:23646/`.

## Container

### Weed Shell

```shell
$ docker compose exec seaweedfs-playground-master weed shell
```
