# puaa-docker
puaa dockerfile repo

Runs the test OAuth server with a pre-configured test client.

See
  - https://gitlab.com/romk/puaa
  - https://cloud.docker.com/repository/docker/romk/puaa


## Build
```
docker build -t puaa .
```

## Run
```
docker run -it -p 8000:8000 puaa
```

With a custom uaa.yml
```
docker run -it -p 8000:8000 -v <HOST PATH TO THE uaa.yml>:/etc/uaa.yml puaa
```

### Get test client token
```
curl -sS http://localhost:8000/oauth/token -u test:test -d grant_type=client_credentials
```

### Get a list of JWT keys
```
curl -sS http://localhost:8000/token_keys
```

## License
MIT
