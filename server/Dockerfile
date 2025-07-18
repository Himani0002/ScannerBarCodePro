# Use official Node image with build tools
FROM node:18-bullseye

# Set working directory
WORKDIR /app

# Install system dependencies for canvas
RUN apt-get update && \
    apt-get install -y build-essential libcairo2-dev libpango1.0-dev libjpeg-dev libgif-dev librsvg2-dev && \
    rm -rf /var/lib/apt/lists/*

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies (rebuilds canvas correctly)
RUN npm install

# Copy the rest of the app
COPY . .

# Expose port
EXPOSE 5000

# Start the server
CMD ["node", "server.js"]
