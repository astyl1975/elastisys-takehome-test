# Use an Alpine-based Node.js image
FROM node:24-alpine
# Set the working directory inside the container
WORKDIR /app
# Copy package.json and package-lock.json
COPY package*.json ./
# Install application dependencies
RUN npm install
RUN npm install ejs
# Copy the rest of the application source code
COPY . .
# Expose port 3000 to the outside world

# Optionally run as non-root user
# RUN addgroup -S appgroup && adduser -S appuser -G appgroup
# RUN chown -R appuser:appgroup /app
# USER appuser

EXPOSE 3000
# Command to run the application
# CMD ["node", "bin/www.js"]
CMD ["npm", "start"]

