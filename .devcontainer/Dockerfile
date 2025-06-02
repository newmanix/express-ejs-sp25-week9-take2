FROM node:18

# Install Git, MongoDB, and curl (curl is optional, but often useful)
RUN apt-get update && apt-get install -y git mongodb curl

# Install Mongo Express globally via npm
RUN npm install -g mongo-express

# Set working directory inside container
WORKDIR /workspace

# Expose application ports (Node app, MongoDB, Mongo Express)
EXPOSE 3000 27017 8081
