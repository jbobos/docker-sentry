# Sentry in Docker

## Quick start
```bash
# start containers - redis, postgres, sentry web, cron and worker
docker-compose up -d
# show logs of sentry containers
# note: it might take up to a few minutes to start sentry
docker-compose logs -f web cron worker
```

```bash
# create a super user only at the first time
docker-compose exec web sentry createuser --email admin@domain.com --password admin --superuser
```

## Testing
```bash
# install sentry sdk
pip install --upgrade sentry-sdk==0.12.3
```

```python
# open the following page to find your own DSN
# http://localhost:9000/settings/sentry/projects/internal/install/python/
import sentry_sdk
sentry_sdk.init("http://0657400d61d4459b9537f7a32e7fc8f1@localhost:9000/1")
division_by_zero = 1 / 0

# open the following page to see your issues
# http://localhost:9000/sentry/internal/
```

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

