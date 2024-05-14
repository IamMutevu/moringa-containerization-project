# Choice of Base Image

Alpine has been used because of it minimal footprint. Because of this, it is expected that the overall size of the Docker images will 
be reduced

# Docker Directives

The following directives have been used in the Dockerfiles:
- **FROM**: Specifies the base image.
- **WORKDIR**: Sets the working directory in the container.
- **COPY**: Copies files and directories into the container.
- **RUN**: Executes commands inside the container.
- **EXPOSE**: Informs Docker that the container listens on the specified network ports at runtime.
- **CMD**: Provides the command that will be executed when the container starts.

