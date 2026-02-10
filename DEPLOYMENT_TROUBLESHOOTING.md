# GitHub Pages Deployment Troubleshooting Guide

## Issue: Website not showing recent changes

If you've made changes to your website but they're not showing up on the live site, follow this troubleshooting guide.

## Quick Fixes (Try These First)

### 1. Clear Your Browser Cache
The most common reason for not seeing changes is browser caching.

**Chrome/Edge:**
1. Press `Ctrl+Shift+Delete` (Windows) or `Cmd+Shift+Delete` (Mac)
2. Select "Cached images and files"
3. Click "Clear data"
4. **OR** simply do a hard refresh: `Ctrl+F5` (Windows) or `Cmd+Shift+R` (Mac)

**Firefox:**
1. Press `Ctrl+Shift+Delete` (Windows) or `Cmd+Shift+Delete` (Mac)
2. Select "Cache"
3. Click "Clear Now"
4. **OR** hard refresh: `Ctrl+F5` (Windows) or `Cmd+Shift+R` (Mac)

**Safari:**
1. Go to Safari > Preferences > Advanced
2. Enable "Show Develop menu"
3. Go to Develop > Empty Caches
4. **OR** hard refresh: `Cmd+Option+R`

### 2. Check Which Branch GitHub Pages is Using

For a repository named `username.github.io` (like this one), GitHub Pages should automatically deploy from the `main` branch.

To verify:
1. Go to your repository on GitHub
2. Click on "Settings"
3. Scroll down to "Pages" section (left sidebar)
4. Under "Source", verify it's set to deploy from the `main` branch
5. The URL should show: `https://Echo-83.github.io`

### 3. Verify Your Changes Are on the Main Branch

Your changes must be on the `main` branch to be deployed:

```bash
# Check which branch you're on
git branch

# If you're not on main, switch to it
git checkout main

# Pull the latest changes
git pull origin main

# Check if your changes are there
git log --oneline -5
```

### 4. Check GitHub Actions Deployment Status

GitHub Pages uses GitHub Actions to build and deploy your site:

1. Go to your repository on GitHub
2. Click the "Actions" tab
3. Look for "pages build and deployment" workflows
4. Check if the latest run was successful (green checkmark)
5. If it failed (red X), click on it to see the error details

## Common Issues and Solutions

### Issue: Changes committed to a different branch

**Solution:** You need to merge your changes to the `main` branch:

```bash
# Switch to main branch
git checkout main

# Merge your feature branch (replace 'your-branch-name' with actual branch)
git merge your-branch-name

# Push the changes
git push origin main
```

### Issue: GitHub Pages deployment failed

**Solution:** Check the Actions tab for error details. Common causes:
- Invalid HTML syntax
- Missing files that are referenced in the HTML
- File size too large (max 1GB for entire repository)

### Issue: Changes not showing after 5+ minutes

**Possible causes:**
1. Browser cache (try incognito/private mode)
2. Changes not on main branch
3. Deployment hasn't finished yet
4. CDN cache (GitHub Pages uses a CDN, which can take a few minutes to update globally)

**Solution:**
- Wait 5-10 minutes for CDN to update
- Try accessing from an incognito window
- Try accessing from a different device/network

## Deployment Timeline

After pushing to main branch:
1. **Immediate**: GitHub receives your push
2. **~30 seconds**: GitHub Actions workflow starts
3. **~1-2 minutes**: Build and deployment completes
4. **~2-5 minutes**: CDN cache updates globally
5. **Total**: Expect changes to appear within 5-10 minutes max

## How to Force a Fresh Deployment

If you want to trigger a fresh deployment:

1. Make a small change to any file (even just a comment)
2. Commit and push to main:
   ```bash
   git add .
   git commit -m "Force redeploy"
   git push origin main
   ```
3. Watch the Actions tab for the deployment to complete

## Verifying Your Current Setup

Run these commands to check your current state:

```bash
# Check current branch
git branch

# Check latest commits
git log --oneline -5

# Check remote branches
git branch -r

# Check if you have uncommitted changes
git status
```

## Current Status of This Repository

✅ **Photo Added**: `assets/images/rand_alaidi.jpg` exists  
✅ **Colors Updated**: Purple gradient background implemented  
✅ **HTML Updated**: Profile photo is properly linked in index.html  
✅ **Main Branch**: All changes are on the main branch  

The website **should** be working correctly at: https://Echo-83.github.io

If it's not showing for you, it's almost certainly a **browser cache issue**. Try:
1. Hard refresh: `Ctrl+F5` or `Cmd+Shift+R`
2. Open in incognito/private mode
3. Clear your browser cache completely

## Need More Help?

If none of these solutions work:
1. Check the [GitHub Pages documentation](https://docs.github.com/en/pages)
2. Verify your repository is public (private repos need GitHub Pro for Pages)
3. Check if there are any GitHub status issues at [githubstatus.com](https://www.githubstatus.com/)
