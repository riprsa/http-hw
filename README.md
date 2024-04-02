# Debug Docker container

The goal of this project is to create a small, almost empty Docker container for debugging purposes.

## Overview

While it is possible to use this container as a standalone container, I personally use it with Docker Compose:

```yml
services:
  debug_container:
    image: ghcr.io/riprsa/debug-container:latest
    ports:
      - "80:8081"
    environment:
      # PORT of inner HTTP server. Default value is ":80"
      - PORT=:8081
    # other Compose properties that you would like to uses
```

By default, the container assumes it's ID via `HOSTNAME`. However, you can override it. [Read more](https://docs.docker.com/network/#ip-address-and-hostname)