# Use an official Node.js Alpine image
FROM node:14.21.3

# Set the working directory
WORKDIR /usr/src/app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install Bower globally
RUN npm install -g bower

# Copy other necessary files
COPY . .

# Change to the src directory and run Bower install
WORKDIR /usr/src/app/src
#RUN bower install node --trace-deprecation
RUN bower install --allow-root /bin/bash
 
# Go back to the root directory and run npm install
WORKDIR /usr/src/app
RUN npm install

# Expose the port the app runs on
EXPOSE 9090

# Command to run the application
CMD ["npm", "start"]

