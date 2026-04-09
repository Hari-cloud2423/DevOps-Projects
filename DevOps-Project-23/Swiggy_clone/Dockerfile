# Use Node.js 16 from AWS Public ECR (NO rate limit)
FROM public.ecr.aws/docker/library/node:16

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy app code
COPY . .

# Build React app
RUN npm run build

# Expose port
EXPOSE 3000

# Start app
CMD ["npm", "start"]
