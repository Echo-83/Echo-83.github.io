# Customization Guide

This guide will help you personalize your website with your photo and information.

## Adding Your Profile Photo

### Step 1: Add Your Photo to the Project

1. Choose a good quality profile photo (square format works best, e.g., 500x500px or larger)
2. Name it something simple like `profile.jpg` or `profile.png`
3. Upload it to the `assets/images/` folder in your repository

You can do this in several ways:
- **Via GitHub Web Interface**: 
  - Go to your repository on GitHub
  - Navigate to `assets/images/`
  - Click "Add file" → "Upload files"
  - Drag and drop your photo
  - Commit the changes

- **Via Git Command Line**:
  ```bash
  # Copy your photo to the project
  cp /path/to/your/photo.jpg assets/images/profile.jpg
  
  # Add and commit
  git add assets/images/profile.jpg
  git commit -m "Add profile photo"
  git push
  ```

### Step 2: Update index.html to Use Your Photo

Open `index.html` and find line 213-214 (in the profile-photo section):

**Current code:**
```html
<div class="profile-photo">
  <!-- Replace with your actual photo: <img src="path-to-your-photo.jpg" alt="Profile Photo"> -->
  E
</div>
```

**Replace with:**
```html
<div class="profile-photo">
  <img src="assets/images/profile.jpg" alt="Your Name - Profile Photo" style="width: 100%; height: 100%; object-fit: cover; border-radius: 50%;">
</div>
```

> **Note:** Change `profile.jpg` to match your actual filename if different.

## Updating Personal Information

### LinkedIn URL (Line 226)

**Current:**
```html
<a href="https://linkedin.com/in/your-profile" class="social-link" target="_blank">LinkedIn</a>
```

**Update to:**
```html
<a href="https://linkedin.com/in/YOUR-LINKEDIN-USERNAME" class="social-link" target="_blank">LinkedIn</a>
```

Replace `YOUR-LINKEDIN-USERNAME` with your actual LinkedIn profile username.

### Email Address (Line 227)

**Current:**
```html
<a href="mailto:your.email@example.com" class="social-link">Contact Me</a>
```

**Update to:**
```html
<a href="mailto:your.actual.email@gmail.com" class="social-link">Contact Me</a>
```

Replace with your actual email address.

### GitHub Link

The GitHub link on line 225 is already set to `https://github.com/Echo-83` - verify this is correct or update it if needed.

## Customizing Your Introduction

Edit lines 218-223 to personalize your story:

```html
<p class="intro">
  Hi! I'm [Your Name], and I'm on a mission to master cloud technologies...
  [Customize this to tell your own story]
</p>
```

## Adding Your Achievements

In the "Achievements & Certifications" section (lines 236-257), you can:
- Update the achievement cards with your actual certifications
- Add more badges by copying the badge HTML: `<span class="badge">Your Badge Text</span>`
- Modify descriptions to reflect your actual progress

## Quick Checklist

- [ ] Add profile photo to `assets/images/` folder
- [ ] Update line 213-214 in index.html to reference your photo
- [ ] Update LinkedIn URL (line 226)
- [ ] Update email address (line 227)
- [ ] Verify GitHub link (line 225)
- [ ] Personalize introduction text (lines 218-223)
- [ ] Update achievement cards with your actual accomplishments
- [ ] Test the website locally before pushing changes

## Testing Your Changes

After making changes, you can test locally:

```bash
# Start a simple web server
python3 -m http.server 8080

# Open http://localhost:8080 in your browser
```

Or just push to GitHub and visit your GitHub Pages URL: `https://Echo-83.github.io`

## Need Help?

If you encounter any issues:
1. Double-check file paths are correct
2. Ensure image files are committed to the repository
3. Clear your browser cache if changes don't appear
4. Check the browser console (F12) for any errors
