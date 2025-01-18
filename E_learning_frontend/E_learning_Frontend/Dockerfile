# Use an official Node.js runtime for building the Angular app
FROM node:18 AS build

# Set the working directory in the container
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire Angular app and build it
COPY . .
RUN npm run build --prod

# Use an Nginx image to serve the built Angular app
FROM nginx:alpine
COPY --from=build /app/dist/ELEARN_PFA/usr/share/nginx/html
