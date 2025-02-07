# Use official Node.js 20 image
FROM node:20.6.0

# Set working directory
WORKDIR /app

# Install pnpm globally
RUN npm install -g pnpm

# Copy package files and install dependencies
COPY package.json pnpm-lock.yaml ./
RUN pnpm install --frozen-lockfile

# Copy the rest of the app files
COPY . .

# Generate Prisma Client
RUN pnpm prisma generate

# Expose backend port
EXPOSE 3000

# Start the application
CMD ["pnpm", "start"]
