# Use nginx as the base image
FROM node:14-alpine

#Set working directory
WORKDIR /client/app

# Copy built frontend files to nginx default directory
COPY package*.json ./

#Install dependencies
RUN npm install

#Copy the rest of the application code from root to workdir
COPY . .

# Expose port 3000 for the client
EXPOSE 3000
