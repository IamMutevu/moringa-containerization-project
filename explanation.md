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

## Implementation

# Git Workflow

## Challenges Encountered

Encountered a challenge when trying to run the application after cloning it from Github. The issue was the node version on my machine. After reinstalling and running npm `npm audit fix --force`, it worked okay

# Screenshots
Below are screenshots of the images pushed to Docker hub.

## Client Image 
![Client Image Screenshot](<client-image.png>)

## Backend Image 
![Backed Image Screenshot](<backend-image.png>)

