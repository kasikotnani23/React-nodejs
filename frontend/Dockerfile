# Build stage
FROM node:18-alpine AS build

# Maintainer info
LABEL maintainer="kasikotnani@gmail.com"

# Set working directory
WORKDIR /app

# Copy package.json & package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all files and build the React app
COPY . .
RUN npm run build

# -----------------------------------------
# Production stage: Serve with Nginx
# -----------------------------------------
FROM nginx:alpine

# Copy the built React app to Nginx's serving directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 (default for Nginx)
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
