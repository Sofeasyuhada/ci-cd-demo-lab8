name: CI/CD Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    # Checkout repository
    - name: Checkout Code
      uses: actions/checkout@v3

    # Set up Node.js environment
    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '16' # Specify your Node.js version

    # Install dependencies
    - name: Install Dependencies
      run: npm install

    # Run tests
    - name: Run Tests
      run: npm test

    # Build project (if applicable)
    - name: Build Project
      run: npm run build

  deploy:
    runs-on: ubuntu-latest
    needs: build

    steps:
    # Checkout repository
    - name: Checkout Code
      uses: actions/checkout@v3

    # Deploy application (example deployment script)
    - name: Deploy to Server
      run: |
        echo "Deploying application..."
        # Replace with actual deployment commands
        ssh user@server 'bash deploy-script.sh'
