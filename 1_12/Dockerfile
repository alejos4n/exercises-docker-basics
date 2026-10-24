
FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies required to install Node.js
RUN apt-get update && apt-get install -y \
    curl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Install Node.js 16
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app

# Install React application dependencies
COPY package*.json ./
RUN npm install

# Copy application source without modifying it
COPY . .

# Build the React application
RUN npm run build

# Install static file server
RUN npm install -g serve

EXPOSE 5001

# Start the application
CMD ["serve", "-s", "-l", "5001", "build"]
