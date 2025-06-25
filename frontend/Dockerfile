# Use the latest official Node.js image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files first for caching layer
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the app
COPY . .

# Expose React dev server port (3000 for CRA, 5173 for Vite)
EXPOSE 3000

# Run the app in development mode
CMD ["npm", "start"]
