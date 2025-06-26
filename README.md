# Docmost Deployment

This repository contains configuration files for deploying Docmost to Render.

## Deployment Instructions

### Manual Deployment on Renders

1. In your Render dashboard, create a new Web Service
2. Connect to this GitHub repository
3. Configure the service:
   - **Name**: docmost (or your preferred name)
   - **Environment**: Docker
   - **Region**: Choose your preferred region
   - **Branch**: main
   - **Build Command**: Leave empty
   - **Start Command**: Leave empty
   - **Plan**: Choose your preferred plan

4. Add the following environment variables:
   - `APP_URL`: Your Render app URL (e.g., https://docmost.onrender.com)
   - `APP_SECRET`: a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6q7r8s9t0u1v2w3x4y5z6 (or your own secure string)
   - `DATABASE_URL`: postgresql://docmost:bDsZ6TtSbhAqJW7uAIb3SmilynaaM5vW@dpg-cv304llumphs73a02vdg-a/docmost_vx4c
   - `REDIS_URL`: redis://default:AbaeAAIjcDE3Njk4ZDkyODE0YTQ0YWYyOWFjNGY3ODZmZTdlNmU4N3AxMA@keen-amoeba-46750.upstash.io:6379
   - `NODE_ENV`: production

5. Add a disk:
   - **Name**: docmost-data
   - **Mount Path**: /app/data/storage
   - **Size**: 1 GB (or your preferred size)

6. Set the health check path to: `/api/health`

7. Click "Create Web Service"

## Troubleshooting

If you encounter build issues:

1. Make sure you've selected "Docker" as the environment
2. Verify that the Dockerfile is being used
3. Check that the environment variables are set correctly
4. Ensure the disk is mounted at the correct path.

## First-time Setup

After deployment, please visit your Docmost URL to set up your workspace and create an admin account. 
