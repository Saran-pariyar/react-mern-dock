# Use a lean base image to minimize image size
FROM node:20-alpine AS builder

# Set the working directory for the build stage
WORKDIR /app

# Copy package files first to leverage Docker build cache
COPY package*.json ./

# Install dependencies using npm install initially to generate package-lock.json
RUN npm install
# If package versions remain unchanged, the subsequent build will reuse the cached layer

# Copy the rest of the project files
COPY . .

# Use a new stage for the production environment
FROM node:20-alpine

# Set the working directory
WORKDIR /app

# Copy the build artifacts from the builder stage
COPY --from=builder /app /app

# Expose the port for development server (adjust if needed)
EXPOSE 5173

# Start the development server
CMD ["npm", "run", "dev"]
