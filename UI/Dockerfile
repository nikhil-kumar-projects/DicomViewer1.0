# Stage 1: Build Angular App
FROM node:22 AS builder
WORKDIR /App

# Copy package files and install dependencies
COPY dicom-viewer-ui/package*.json ./
RUN npm install

# Copy rest of the application code and build the app
COPY dicom-viewer-ui/ ./
RUN npm run build --prod


# Stage 2: Serve with Nginx
FROM nginx:stable-alpine

# Copy built files from builder stage to Nginx html directory
COPY --from=builder /App/dist/dicom-viewer-ui/browser /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
