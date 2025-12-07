# GitHub Actions Workflows Documentation

## Overview

This project contains 4 GitHub Actions workflows for CI/CD automation.

## Workflows

### 1. CI Pipeline (ci.yml)

**Trigger**: Push to main/develop, PR to main

**Jobs**:
- **Linting Job**: Runs `npm run lint`
- **Testing Job**: Runs `npm test`
- **Build Job**: Runs `npm run build` (depends on lint and test)

### 2. Advanced CI (advanced-ci.yml)

**Trigger**: Push to main/develop, PR to main

**Jobs**:
- **Setup and Test**: Installs dependencies, runs lint and test
- **Code Quality Checks**: Runs linting checks

### 3. Security Audit (security.yml)

**Trigger**: Daily at 2 AM UTC, manual dispatch

**Jobs**:
- **Daily Security Check**: Runs security audit

### 4. Deploy (deploy.yml)

**Trigger**: Push to main, manual dispatch

**Jobs**:
- **Deployment Workflow**: Builds and deploys application

## Best Practices

- All workflows use Node.js 18
- Dependencies are installed before running scripts
- Build job depends on lint and test passing
- Workflows are triggered on push and pull requests
