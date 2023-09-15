# Use an official Node.js runtime as a parent image
# set the base image to build from 
FROM node:alpine

# Set the working directory to /app
WORKDIR /app

COPY package.json .
COPY package-lock.json ./

# Install app dependencies
RUN npm install

# Copy the application code to /app
COPY . .


# Expose the port that the application is listening on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]
