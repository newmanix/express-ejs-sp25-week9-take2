FROM node:18

# Install Git, MongoDB, and curl for testing
RUN apt-get update && apt-get install -y git mongodb curl

# Install Mongo Express globally
RUN npm install -g mongo-express

# Set working directory
WORKDIR /workspace

# Copy local app files into container
COPY . .

# Install app dependencies
RUN npm install

# Expose ports:
# - 3000: Node/Express app
# - 27017: MongoDB
# - 8081: Mongo Express
EXPOSE 3000 27017 8081

# Start MongoDB, Mongo Express, and Node app
CMD mongod --fork --logpath /var/log/mongodb.log && \
    mongo-express --url mongodb://localhost:27017 & \
    npm start
