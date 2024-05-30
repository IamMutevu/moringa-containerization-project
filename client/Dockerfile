# Stage 1: Build the application
FROM node:14-alpine as builder
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY . .
RUN npm run build
# Remove development files
RUN rm -rf src tests node_modules_dev

# Stage 2: Setup the runtime environment
FROM node:14-alpine
WORKDIR /app
COPY --from=builder /app/build ./build
COPY --from=builder /app/node_modules ./node_modules
EXPOSE 3000
CMD ["npm", "start"]