# Use an official Node.js runtime as a parent image
FROM node:16-alpine as builder

# Set the working directory to /app
WORKDIR /app

COPY package.json .

# Install app dependencies
RUN npm install

# Copy the application code to /app
COPY . .

RUN npm run build

#Stage2

FROM nginx:1.19.0
WORKDIR  /usr/share/nginx/html
COPY --from=build /app/build /usr/share/nginx/html 

# Expose the port that the application is listening on
EXPOSE 3000

# Start the application
CMD ["nginx", "-g", "daemon off;"]
