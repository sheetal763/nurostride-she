# Deploy to Hugging Face Spaces

## Steps to Deploy

### 1. Create a Hugging Face Account
Go to https://huggingface.co and sign up if you don't have an account.

### 2. Create a New Space
1. Visit https://huggingface.co/spaces
2. Click "Create new Space"
3. Fill in the form:
   - **Space name**: `emg-classifier` (or any name you prefer)
   - **License**: Choose one (e.g., "MIT")
   - **Select the Space SDK**: Choose **Gradio**
   - **Visibility**: Public (or Private if you prefer)
4. Click "Create Space"

### 3. Push Your Code to the Space

The easiest way is to use git. Hugging Face Spaces will show you instructions, but here's the quick version:

```bash
cd c:\Users\sheet\Downloads\pedaloo

# Initialize git if not already done
git init
git add .
git commit -m "Initial commit - EMG classifier"

# Add Hugging Face remote (replace YOUR-USERNAME)
git remote add hf https://huggingface.co/spaces/YOUR-USERNAME/emg-classifier

# Push to Hugging Face
git push hf main
```

### 4. Done!
Your app will automatically build and deploy. You can monitor the build progress on the Space page.

## File Structure for Hugging Face Spaces

The important file is:
- **`app.py`** — Entry point (Hugging Face automatically runs this)
- **`requirements.txt`** — Dependencies (Hugging Face auto-installs these)

That's it! No need for `vercel.json` or the `api/` folder for Hugging Face Spaces.

## Why Hugging Face Spaces is Better for Gradio

✅ Designed specifically for Gradio apps  
✅ No build issues with complex dependencies  
✅ Automatic deployment on git push  
✅ Free tier with generous limits  
✅ Easy to update — just push to git  
✅ Built-in version control  
✅ No serverless cold start issues  

## Accessing Your App

Once deployed, your app will be available at:
```
https://huggingface.co/spaces/YOUR-USERNAME/emg-classifier
```

## Updates

To update your app:
```bash
git add .
git commit -m "Update description"
git push hf main
```

Spaces will automatically rebuild and redeploy!
