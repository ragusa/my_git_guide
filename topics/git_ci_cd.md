
# Automating Git Workflows with CI/CD

## 1. What is CI/CD?
CI (Continuous Integration) and CD (Continuous Deployment or Delivery) automate the process of testing, building, and deploying code, ensuring that every change is tested and deployed reliably.

## 2. CI/CD Pipeline
A typical CI/CD pipeline involves:
- **Commit**: Developers commit changes to a repository.
- **Build**: The system automatically builds the codebase.
- **Test**: Automated tests are run on the code.
- **Deploy**: If tests pass, the code is deployed to production.

## 3. Setting Up CI/CD with GitHub Actions
GitHub Actions allows you to define workflows that run automatically when specific events occur, such as pushing code or creating a pull request.

### 3.1 Create a GitHub Action Workflow
In your repository, create a file named `.github/workflows/ci.yml` with the following content:
```yaml
name: CI Pipeline

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
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.x'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: pytest
```

**Explanation:** This example workflow runs when code is pushed or a pull request is opened on the `main` branch. It sets up a Python environment, installs dependencies, and runs tests.

## 4. Deploying with CI/CD
To deploy automatically, you can add a deployment job to your CI/CD pipeline. Here's an example of deploying a Node.js app using GitHub Actions:
```yaml
deploy:
  runs-on: ubuntu-latest
  needs: build

  steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Set up Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '14.x'

    - name: Install dependencies
      run: npm install

    - name: Deploy to server
      run: ssh user@server "cd /path/to/app && git pull && npm install && pm2 restart all"
```

**Explanation:** This example deploys the app to a server using SSH and restarts the application with `pm2`.

## 5. Benefits of CI/CD
- **Early bug detection**: Automatically testing code with each commit helps catch bugs early.
- **Faster delivery**: Automating deployment allows for faster and more frequent releases.
- **Consistency**: Ensures that code is always deployed in the same manner, reducing the risk of human error.

[Back to README](../README.md)
    