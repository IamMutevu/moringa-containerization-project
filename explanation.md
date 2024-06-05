# Creating a Basic Micro-service (IP 2 explanation)

## Choice of Base Image

Alpine has been used because of it minimal footprint. Because of this, it is expected that the overall size of the Docker images will 
be reduced

## Docker Directives

The following directives have been used in the Dockerfiles:
- **FROM**: Specifies the base image.
- **WORKDIR**: Sets the working directory in the container.
- **COPY**: Copies files and directories into the container.
- **RUN**: Executes commands inside the container.
- **EXPOSE**: Informs Docker that the container listens on the specified network ports at runtime.
- **CMD**: Provides the command that will be executed when the container starts.

### Implementation
- **Build Stage**: Used npm install --production to only install production dependencies, reducing image size.
- **Multi-Stage Build**: Separates the build environment from the runtime environment, ensuring that only necessary artifacts are carried over to the final image.

## Docker-Compose Networking
- **Bridge Network**: Default Docker network was used to facilitate communication between containers. This network allows containers connected to it to communicate while isolating them from containers not connected to the bridge.
- **Ports**: Application ports are mapped from the container to the host to allow external access. For example, 3000:3000 ensures that the application is accessible through the host's port 3000.


## Git Workflow
Followed the instructions provided in README.md to set up the application and run it. Committed every change and pushed the commit to Github.

### Challenges Encountered

Encountered a challenge when trying to run the application after cloning it from Github. The issue was the node version on my machine. After reinstalling and running npm `npm audit fix --force`, it worked okay

## Screenshots
Below are screenshots of the images pushed to Docker hub.

### Client Image 
![Client Image Screenshot](<client-image.png>)

###
 Backend Image 
![Backed Image Screenshot](<backend-image.png>)

