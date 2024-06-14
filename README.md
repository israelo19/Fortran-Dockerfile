# Fortran Dockerfile

This Dockerfile allows you to set up a Docker container with Fortran ready to use. Fork this repository and/or add your own images to your container to customize it according to your needs.
@Israel Ogwu

## Prerequisites

Before getting started, make sure you have the following installed:

- Docker

## Setup

1. Choose a Linux distribution and version for your container. In this example, we're using Alpine Linux version 3.20.

2. Familiarize yourself with the following Docker commands:
  - `FROM`: Creates a layer from a base image.
  - `COPY`: Copies files from the source to the destination.
  - `RUN`: Executes a command in a new image layer.
  - `CMD`: Specifies the default command to run when a container is launched.
  - `EXPOSE`: Documents which ports are exposed by the container.

## Dockerfile

Here's the Dockerfile used in this example:

```Dockerfile
FROM alpine:3.20
RUN apk add --no-cache bash bash-doc bash-completion
RUN apk add --no-cache musl-dev 
RUN apk add --no-cache gfortran gdb make
RUN apk add --no-cache nano
```

## This Dockerfile sets up an Alpine Linux container with the following components:

- Bash shell and related packages
- Musl development libraries
- GNU Fortran compiler (gfortran)
- GDB debugger
- Make build tool
- Nano text editor

Feel free to modify the Dockerfile to include any additional packages or configurations you need for your Fortran development environment.

### Building the Docker Image
- To build the Docker image, navigate to the directory containing the Dockerfile and run the following command:
  ```
  docker build -t fortran-alpine
  ```
  This command will build the Docker image and tag it as fortran-alpine.
### Running the Docker Container
To run the Docker container based on the fortran-alpine image, use the following command:
```
docker run -it --rm fortran-alpine
```
This command will start the container in interactive mode, allowing you to access the shell prompt inside the container.
The `--rm` flag ensures that the container is automatically removed when you exit it.
You can now start using Fortran within the container!

Enjoy your Fortran development environment in Docker! `:)`
