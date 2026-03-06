# Vercel Deployment Guide

## Setup for Vercel Deployment

### Prerequisites
- Vercel account (https://vercel.com)
- Git repository (GitHub, GitLab, or Bitbucket)

### Step 1: Push to Git

```bash
git init
git add .
git commit -m "Add Vercel deployment config"
git push origin main
```

### Step 2: Deploy to Vercel

**Option A: Using Vercel CLI**
```bash
npm i -g vercel
vercel
```
Follow the prompts to link your project and deploy.

**Option B: Using Vercel Dashboard**
1. Go to https://vercel.com/new
2. Select your Git repository
3. Vercel will auto-detect the Python app
4. Click "Deploy"

### Step 3: Environment Variables (if needed)

If you need environment variables:
1. Go to Project Settings → Environment Variables
2. Add any required variables
3. Redeploy

### Local Development

To test locally before deploying:

```bash
# Install dependencies
pip install -r requirements.txt

# Run locally
python main.py
```

The app will be available at `http://localhost:7860`

### Notes

- The `vercel.json` config routes all requests to `api/index.py`
- `api/index.py` exports the Gradio ASGI app
- Vercel will automatically install dependencies from `requirements.txt`
- Python 3.9+ is supported by default on Vercel

### Troubleshooting

- **Build fails**: Check that all dependencies in `requirements.txt` are compatible
- **App doesn't load**: Check Vercel logs at `https://vercel.com/account/projects`
- **File upload issues**: Vercel has a 50MB limit on function payloads; files must be under limit
