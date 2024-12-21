# Docker HEALTHCHECK

Docker's `HEALTHCHECK` instruction tells Docker how to test a container to check that it is still working. This can help you ensure that your application is running correctly and take action if it is not.

## Usage

To add a health check to your Dockerfile, use the `HEALTHCHECK` instruction followed by the options and the command to run. For example:

```dockerfile
HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://localhost/ || exit 1
```

### Options

- `--interval`: Time between running the check (default: 30s).
- `--timeout`: Time before considering the check to have failed (default: 30s).
- `--retries`: Consecutive failures needed to consider the container unhealthy (default: 3).

### Example

Here is an example of a Dockerfile with a health check:

```dockerfile
FROM nginx:alpine

HEALTHCHECK --interval=30s --timeout=10s --retries=3 CMD curl -f http://localhost/ || exit 1

COPY . /usr/share/nginx/html
```

In this example, Docker will run the `curl -f http://localhost/` command every 30 seconds. If the command fails or takes longer than 10 seconds, it will be retried up to 3 times before marking the container as unhealthy.

## Checking Container Health

You can check the health status of a container using the `docker ps` command. The status will be shown in the `STATUS` column.

```sh
docker ps
```

## Conclusion

Using `HEALTHCHECK` in your Dockerfile can help you ensure that your application is running correctly and take action if it is not. It is a simple yet powerful feature to improve the reliability of your Docker containers.
