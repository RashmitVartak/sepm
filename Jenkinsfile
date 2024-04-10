#!/bin/bash

# Ensure Node.js is installed
NODE_VERSION=$(node -v)
if [ -z "$NODE_VERSION" ]; then
    echo "Node.js is not installed. Please install Node.js."
    exit 1
fi

# Install npm packages for frontend
cd frontend && npm install
if [ $? -ne 0 ]; then
    echo "Failed to install npm packages for frontend."
    exit 1
fi

# Build frontend
npm run build
if [ $? -ne 0 ]; then
    echo "Failed to build frontend."
    exit 1
fi

# Install npm packages for backend
cd ../backend && npm install
if [ $? -ne 0 ]; then
    echo "Failed to install npm packages for backend."
    exit 1
fi

# Build backend
npm run build
if [ $? -ne 0 ]; then
    echo "Failed to build backend."
    exit 1
fi

# Deploy to IIS
cp -r RASHMIT/Sites/prac # Copy frontend build to Apache web server directory

# Make sure to replace '/path/to/backend/directory' with the correct path for your backend
