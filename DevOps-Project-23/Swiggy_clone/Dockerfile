# Use Node.js 16 from AWS Public ECR
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

# ✅ Install production server
RUN npm install -g serve

# Expose port
EXPOSE 3000

# ✅ FIXED: use production server
CMD ["serve", "-s", "build", "-l", "3000"]
