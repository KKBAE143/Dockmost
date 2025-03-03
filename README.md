# Docmost Deployment

This repository contains configuration files for deploying Docmost to Render.

## Deployment Instructions

### Option 1: Deploy to Render using the Blueprint

1. Click the "Deploy to Render" button below:

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

2. This will use the `render.yaml` file to set up your Docmost instance.

### Option 2: Manual Deployment

1. Fork this repository
2. In your Render dashboard, create a new Web Service
3. Connect to your GitHub repository
4. Select "Docker" as the environment
5. Set the following environment variables:
   - `APP_URL`: Your Render app URL (e.g., https://docmost.onrender.com)
   - `APP_SECRET`: A secure random string
   - `DATABASE_URL`: Your PostgreSQL connection string
   - `REDIS_URL`: Your Redis connection string
   - `NODE_ENV`: production
6. Add a disk with mount path: `/app/data/storage`
7. Deploy the service

## Configuration

Update the `render.yaml` file to customize your deployment:

- Update the `APP_URL` to match your Render URL
- Set a strong `APP_SECRET`
- Update the `REDIS_URL` with your Upstash Redis password
- Adjust the disk size as needed

## First-time Setup

After deployment, visit your Docmost URL to set up your workspace and create an admin account. 