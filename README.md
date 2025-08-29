# Temporaio Ruby SDK Experiments

## Potential deadlock issue with v0.6.0

Reproducing https://github.com/temporalio/sdk-ruby/issues/330

Ruby script: [./temporalio_worker](./temporalio_worker)

Make sure to run `docker compose down` after each run to reset db.

### v0.6.0

Script used v0.6.0 client by default.

To reproducer run:

```shell
docker compose down
docker compose up
```

You can open temporal web UI to check progress at:
http://localhost:28080

### v0.5.0

You use docker compose override to run script with v0.5.0 SDK, which doesn't experience the issue.

```shell
docker compose down
docker compose -f docker-compose.yml -f docker-compose.v05.yml up
```

