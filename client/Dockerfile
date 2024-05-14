# Stage 1: Build the application
FROM node:14-alpine as builder

# Set the working directory in the build stage
WORKDIR /app

# Copy package.json and package-lock.json (if available)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the application
RUN npm run build

# Stage 2: Setup the runtime environment
FROM node:14-alpine

# Set the working directory in the runtime stage
WORKDIR /app

# Only copy the build artifacts and necessary files from the build stage
COPY --from=builder /app/build ./build
COPY --from=builder /app/node_modules ./node_modules

# Expose the port the container will run on
EXPOSE 3000

# Command to run the application
CMD [ "npm", "start" ]
