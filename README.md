# DevOps

This project is a minimal setup to **trigger a GitHub Actions workflow** and earn the **DevOps Guru** badge on GitHub.

## What's Inside

- A simple HTML page (`index.html`)
- A GitHub Actions workflow (`.github/workflows/main.yml`)
- Clean project structure
- Ready for GitHub Pages deployment

## GitHub Actions Workflow

The workflow runs on every push or pull request to the `main` branch.

```yaml
name: CI Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'

    - name: Say hi
      run: echo "Hello from GitHub Actions!"
