### Container Directory structure

```
/data - data-dir (path for production)
/node_modules (replaced for production )
/app
  /bin
  /data - data-dir (default path, for development)
  /src
```

### Docker cleaning

```bash
docker stop --time 0 $(docker ps)
docker rm -f $(docker ps -a)
docker rmi -f $(docker images -a)
```

### Building
```bash
docker build --no-cache --file docker/Dockerfile \
  --tag ivannikovdev/bitcoin-watcher:latest \
  .
```

### Publishing
```bash
docker push ivannikovdev/bitcoin-watcher:latest
```
