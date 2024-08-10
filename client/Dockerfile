# syntax=docker/dockerfile:1

# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Dockerfile reference guide at
# https://docs.docker.com/go/dockerfile-reference/

# Want to help us make this template better? Share your feedback here: https://forms.gle/ybq9Krt8jtBL3iCk7

ARG NODE_VERSION=20.13.1

FROM node:${NODE_VERSION}-alpine

# Use production node environment by default.
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install any needed packages
RUN npm install

RUN npx vite --version

# Copy the current directory contents into the container at /app
COPY . .

# Build the app for production
RUN npm run build

# Expose port 5173 (default Vite dev server port)
EXPOSE 5173

# Command to run the app
CMD ["npm", "run", "dev", "--", "--host"]