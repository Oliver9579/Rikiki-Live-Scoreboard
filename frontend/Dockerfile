# Use Node 22 image
FROM node:22-alpine

# Set working directory
WORKDIR /app

# Copy package files and install dependencies (cached layer)
COPY package*.json ./
RUN npm install

# Copy frontend source
COPY . .

# Build the React app
RUN npm run build

# Use a lightweight web server to serve static files
RUN npm install -g serve

# Expose port
EXPOSE 5173

# Start the app
CMD ["serve", "-s", "dist", "-l", "5173"]
