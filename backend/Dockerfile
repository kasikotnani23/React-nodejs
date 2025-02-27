# Use lightweight Node.js Alpine image
FROM node:18-alpine

# Maintainer information
LABEL maintainer="kasikotnani@gmail.com"

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json (if exists) to install dependencies
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy rest of the application code
COPY . .

# Expose port 5000
EXPOSE 5000

# Start the Node.js application
CMD ["npm", "start"]
