Docker image for [phpmetrics](https://github.com/phpmetrics/PhpMetrics)

## Quick start

```sh
docker run --rm \
    --user $(id -u):$(id -g) \
    --volume $PWD:/project \
    pboissinot/phpmetrics:master [<options>]
```

## Usage with docker compose:

You can add it as a service in your `compose.yaml` file

```
# compose.yaml:
services:
  phpmetrics:
    build: pboissinot/phpmetrics:master
    # add a profile key to disable the start on up/start command
    profiles:
        - donotstart
    volumes:
        - .:/project
    command: phpmetrics --report-html=build/phpmetrics src
```

Then, use it with the command `docker compose run --rm phpmetrics`
