# Sentry in Docker

## Environment
```bash
$ cat /etc/redhat-release
CentOS Linux release 7.7.1908 (Core)

$ docker --version
Docker version 1.13.1, build 7f2769b/1.13.1

$ docker-compose --version
docker-compose version 1.24.1, build 4667896b

$ docker images --format "{{.Repository}}:{{.Tag}}"
docker.io/redis:5.0.6-alpine
docker.io/sentry:9.1.2
docker.io/postgres:11.5-alpine
```

