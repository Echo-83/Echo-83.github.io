# Echo-83.github.io

Welcome to my Cloud Certifications & Learning Journey website! 🚀

This is my personal documentation hub for cloud certifications (Azure, AWS, and more), where I share comprehensive study guides, resources, and insights to help both myself and others preparing for certification exams.

## 🌐 Live Website

Visit: [https://Echo-83.github.io](https://Echo-83.github.io)

## 📋 Quick Start - Personalize Your Website

### 1. Add Your Profile Photo
- Upload your photo to the `assets/images/` folder
- Name it `profile.jpg` (or any name you prefer)
- See [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md) for detailed instructions

### 2. Update Your Personal Information
Open `index.html` and update:
- **LinkedIn URL** (line ~229): Replace `your-profile` with your LinkedIn username
- **Email** (line ~230): Replace `your.email@example.com` with your actual email
- **Introduction text** (line ~218-223): Personalize your story

### 3. Add Your Photo to the Page
In `index.html` around line 212-218:
- Uncomment the `<img>` tag
- Remove the "E" placeholder
- Update the path if you used a different filename

## 📚 Project Structure

```
Echo-83.github.io/
├── index.html              # Main landing page
├── assets/
│   └── images/            # Your photos and images go here
├── CUSTOMIZATION_GUIDE.md  # Detailed customization instructions
└── README.md              # This file
```

## 🎯 Future Pages

The website is structured to add course-specific pages:
- `azure.html` - Microsoft Azure certification guide
- `aws.html` - AWS certification guide
- `resources.html` - Additional study materials

Each course page will have topic-specific sub-pages for detailed content.

## 📖 Documentation

For detailed instructions on customizing your website, see:
- [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md) - Step-by-step personalization guide
- [assets/images/README.md](assets/images/README.md) - Image guidelines

## 🛠️ Local Development

To preview changes locally:

```bash
# Start a local web server
python3 -m http.server 8080

# Open http://localhost:8080 in your browser
```

## 📝 Contributing to Your Own Site

1. Make your changes to the HTML files
2. Test locally using the command above
3. Commit and push to GitHub
4. Changes will appear on your GitHub Pages site automatically

## 🔧 Troubleshooting

If your changes aren't showing on the live website:
- See [DEPLOYMENT_TROUBLESHOOTING.md](DEPLOYMENT_TROUBLESHOOTING.md) for a complete guide
- Most common cause: **browser cache** - try a hard refresh (`Ctrl+F5` or `Cmd+Shift+R`)
- Ensure changes are on the `main` branch
- Check the Actions tab for deployment status

---

**Building knowledge, one topic at a time.** 💡
