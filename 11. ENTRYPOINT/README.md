# Dockerfile for ENTRYPOINT Instruction

```dockerfile
# Use ubuntu as base Docker Image
FROM ubuntu

# OCI Labels
LABEL org.opencontainers.image.authors="Ariful Islam"
LABEL org.opencontainers.image.title="ENTRYPOINT Instruction in Docker"
LABEL org.opencontainers.image.description="Illustrating the use of the ENTRYPOINT instruction"
LABEL org.opencontainers.image.version="1.0"

# Always run the echo command as the entrypoint
ENTRYPOINT ["echo", "Ariful"]
```

## Difference between CMD and ENTRYPOINT

- **CMD**:
    - The `CMD` instruction provides defaults for an executing container.
    - It can be overridden by passing arguments to `docker run`.
    - Example:
        ```dockerfile
        CMD ["echo", "Hello World"]
        ```

- **ENTRYPOINT**:
    - The `ENTRYPOINT` instruction configures a container that will run as an executable.
    - It cannot be overridden as easily as `CMD`.
    - Example:
        ```dockerfile
        ENTRYPOINT ["echo", "Hello World"]
        ```

In summary, `CMD` is used to provide default commands and arguments for a container, while `ENTRYPOINT` is used to set up a container to run as a specific executable.