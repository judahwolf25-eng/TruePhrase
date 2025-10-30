# Deployment Guide: TruePhrase to GitHub + Vercel

Follow these steps to make your website public on GitHub and Vercel.

## Step 1: Push to GitHub

### Option A: Using GitHub Web Interface

1. Go to [github.com](https://github.com) and sign in
2. Click the "+" icon in the top right → "New repository"
3. Name it `grindset` or `truephrase`
4. Make it **Public**
5. **Don't** initialize with README, .gitignore, or license
6. Click "Create repository"

### Option B: Using Git Command Line

```bash
# Initialize git repository (if not already done)
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: TruePhrase website"

# Add your GitHub repository as remote (replace YOUR_USERNAME with your actual GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/grindset.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 2: Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in (use GitHub to log in)
2. Click "Add New..." → "Project"
3. Import your GitHub repository (`grindset` or whatever you named it)
4. Vercel will auto-detect the project settings:
   - Framework: Other (static HTML)
   - Build Command: (leave empty or use: `echo 'No build needed'`)
   - Output Directory: `.` (just period)
5. Click "Deploy"
6. Wait 1-2 minutes for deployment

## Step 3: Get Your Live URL

After deployment, you'll get a URL like:
- `https://grindset-xyz123.vercel.app`
- You can also set a custom domain in Vercel settings

## Step 4: Update README (Optional)

Update the README.md to include your actual Vercel URL.

## Important Notes

### Security Warning ⚠️

Your `index.html` contains exposed API keys:
- **Supabase Key**: Currently visible in the code
- **Google Gemini API Key**: Currently visible in the code

For production:
- Consider using environment variables in Vercel
- Go to Vercel Dashboard → Your Project → Settings → Environment Variables
- Add keys as environment variables
- Update your HTML to reference these

### Files Included

These files will be deployed:
- ✅ `index.html` - Your main website
- ✅ `package.json` - Node configuration
- ✅ `vercel.json` - Vercel configuration
- ✅ `README.md` - Project documentation
- ✅ `.gitignore` - Git ignore rules

These files will NOT be deployed (excluded by .gitignore):
- ❌ `node_modules/` - Node modules (not needed for static site)

## Troubleshooting

### If Vercel deployment fails:
- Make sure `index.html` is in the root directory
- Check that `vercel.json` has correct configuration
- Look at Vercel build logs for specific errors

### If the site loads but doesn't work:
- Check browser console for JavaScript errors
- Verify API keys are still valid
- Check that Supabase database exists and has proper permissions

## Next Steps

1. ✅ Push to GitHub
2. ✅ Deploy to Vercel
3. 🔗 Share your live URL
4. 🔒 Consider securing API keys with environment variables
5. 📝 Add custom domain (optional)

## Support

If you run into issues:
- Check Vercel deployment logs
- Check GitHub repository settings
- Verify all files are committed and pushed

Good luck! 🚀

