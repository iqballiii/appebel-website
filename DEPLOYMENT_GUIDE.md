# Appebel Website - Complete Deployment Guide

## 📋 Table of Contents
1. [Quick Start](#quick-start)
2. [GitHub Pages Deployment](#github-pages-deployment)
3. [API Integration Setup](#api-integration-setup)
4. [Customization Guide](#customization-guide)
5. [Testing](#testing)

---

## 🚀 Quick Start

You have all the files needed to deploy! Here's what you received:
- `index.html` - Main website file (ready to deploy)
- `README.md` - Project documentation
- `.gitignore` - Git ignore rules
- `DEPLOYMENT_GUIDE.md` - This file

---

## 📦 GitHub Pages Deployment (FREE Hosting)

### Step 1: Create GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the "+" icon → "New repository"
3. Name it: `appebel-website`
4. Make it **Public**
5. **DO NOT** initialize with README (we already have one)
6. Click "Create repository"

### Step 2: Upload Your Files

**Option A: Using GitHub Web Interface (Easiest)**

1. On your new repository page, click "uploading an existing file"
2. Drag and drop these files:
   - `index.html`
   - `README.md`
   - `.gitignore`
   - `DEPLOYMENT_GUIDE.md`
3. Write commit message: "Initial commit - Appebel website"
4. Click "Commit changes"

**Option B: Using Git Command Line**

```bash
# Navigate to your project folder
cd /path/to/your/project

# Initialize git repository
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit - Appebel website"

# Add remote (replace YOUR-USERNAME)
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/appebel-website.git

# Push to GitHub
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" in the left sidebar
4. Under "Source":
   - Branch: Select `main`
   - Folder: Select `/ (root)`
5. Click "Save"
6. Wait 1-2 minutes for deployment

### Step 4: Access Your Website

Your website will be live at:
```
https://YOUR-USERNAME.github.io/appebel-website/
```

Example: If your GitHub username is `johndoe`, your site will be:
```
https://johndoe.github.io/appebel-website/
```

---

## 🔌 API Integration Setup

The website currently runs in **TEST MODE**. Form submissions are logged to the browser console but not sent anywhere.

### Current Status:
```javascript
const API_CONFIG = {
    endpoint: 'https://your-api-domain.com/api/contact',
    enabled: false  // 👈 Currently in test mode
};
```

### Option 1: Use Formspree (Recommended for Quick Setup)

**Formspree is FREE for up to 50 submissions/month**

1. Go to [formspree.io](https://formspree.io)
2. Sign up for free account
3. Create a new form
4. Copy your form endpoint (looks like: `https://formspree.io/f/xyzabc123`)
5. Open `index.html` in a text editor
6. Find the `API_CONFIG` section (around line 840)
7. Update it:

```javascript
const API_CONFIG = {
    endpoint: 'https://formspree.io/f/YOUR_FORM_ID',  // 👈 Replace with your actual ID
    enabled: true  // 👈 Change to true
};
```

8. Save and push changes to GitHub
9. Test the form - you'll receive submissions via email!

### Option 2: Your Own Backend API

If you have your own backend API:

1. Create an endpoint that accepts POST requests with this JSON structure:
```json
{
    "name": "User Name",
    "email": "user@example.com",
    "subject": "Subject Line",
    "message": "Message content",
    "timestamp": "2026-02-04T10:30:00.000Z"
}
```

2. Update the `API_CONFIG`:
```javascript
const API_CONFIG = {
    endpoint: 'https://your-api.com/api/contact',
    enabled: true
};
```

### Option 3: EmailJS

1. Sign up at [emailjs.com](https://www.emailjs.com)
2. Follow their [integration guide](https://www.emailjs.com/docs/)
3. Replace the entire form submission code with EmailJS code

---

## 🎨 Customization Guide

### 1. Replace Logo Emoji

Current logo is a music note emoji (🎵). To use your real logo:

1. Open `index.html`
2. Find this section (around line 100):
```html
<div class="logo-icon">🎵</div>
```

3. Replace with image:
```html
<div class="logo-icon">
    <img src="your-logo.png" alt="Appebel Logo" style="width: 100%; height: 100%; border-radius: 12px;">
</div>
```

4. Upload `your-logo.png` to your repository

### 2. Add Real App Screenshots

1. Prepare 3 screenshots (recommended size: 1170x2532 pixels - iPhone size)
2. Name them: `screenshot1.png`, `screenshot2.png`, `screenshot3.png`
3. Upload to your repository
4. Open `index.html`, find screenshot placeholders (around line 150):

```html
<!-- Replace this: -->
<div class="screenshot-placeholder">App Screenshot 1</div>

<!-- With this: -->
<img src="screenshot1.png" alt="App Screenshot 1" style="width: 100%; height: 100%; object-fit: cover; border-radius: 24px;">
```

### 3. Update App Store Links

Find the download buttons (around line 130):

```html
<!-- Replace the # with real links -->
<a href="https://apps.apple.com/app/idYOUR_APP_ID" class="btn btn-primary">
    <span>📱</span>
    Download on App Store
</a>
<a href="https://play.google.com/store/apps/details?id=YOUR_PACKAGE_NAME" class="btn btn-primary">
    <span>🤖</span>
    Get it on Google Play
</a>
```

### 4. Change Colors (Optional)

Find CSS variables at the top of `index.html` (around line 15):

```css
:root {
    --color-primary: #FF3B7F;      /* Main pink color */
    --color-secondary: #6B4EFF;    /* Purple color */
    --color-accent: #00D9FF;       /* Cyan color */
    /* Change these to match your brand */
}
```

### 5. Update Contact Information

Find and replace:
- `support@appebel.com` → Your real email
- `privacy@appebel.com` → Your privacy contact email

---

## 🧪 Testing

### Test Locally (Before Deploying)

1. Open `index.html` directly in your browser
2. Click all navigation links - they should scroll smoothly
3. Open FAQ items - they should expand/collapse
4. Submit the contact form - you should see a notification
5. Check browser console (F12) - form data should be logged

### Test After Deployment

1. Visit your GitHub Pages URL
2. Test all functionality
3. Check form submission
4. Verify all links work
5. Test on mobile devices

### Browser Console Testing

When the form is in test mode, submissions are logged:

```
=== FORM SUBMISSION (Test Mode) ===
API Endpoint: https://your-api-domain.com/api/contact
Form Data: {
    name: "Test User",
    email: "test@example.com",
    subject: "Test Subject",
    message: "Test message",
    timestamp: "2026-02-04T..."
}
===================================
```

---

## 🔗 Using Your Website for App Store Submission

### For Apple App Store Connect:

1. **Support URL**: 
   ```
   https://YOUR-USERNAME.github.io/appebel-website/#support
   ```

2. **Privacy Policy URL**: 
   ```
   https://YOUR-USERNAME.github.io/appebel-website/#privacy
   ```

3. **Marketing URL** (Optional): 
   ```
   https://YOUR-USERNAME.github.io/appebel-website/
   ```

### For Google Play Console:

- Same URLs as above work perfectly!

---

## 📞 Need Help?

### Common Issues:

**Issue**: Website not appearing after enabling GitHub Pages
- **Solution**: Wait 2-5 minutes, then refresh. GitHub Pages can take time to build.

**Issue**: Images not loading
- **Solution**: Make sure image files are in the same directory as `index.html` and file names match exactly (case-sensitive).

**Issue**: Form not submitting
- **Solution**: Check browser console (F12) for errors. Make sure `enabled: true` in API_CONFIG.

**Issue**: Custom domain not working
- **Solution**: In GitHub Pages settings, add your custom domain and update DNS records.

---

## ✅ Pre-Deployment Checklist

Before going live, make sure you've:

- [ ] Uploaded all files to GitHub
- [ ] Enabled GitHub Pages in repository settings
- [ ] Tested the website locally
- [ ] Updated API endpoint (or kept in test mode)
- [ ] Replaced logo emoji with real logo (optional)
- [ ] Added real app screenshots (optional)
- [ ] Updated App Store/Play Store links
- [ ] Updated contact email addresses
- [ ] Tested all links and navigation
- [ ] Checked on mobile devices

---

## 🎉 You're All Set!

Your website is now ready for:
- ✅ App Store submission
- ✅ Play Store submission  
- ✅ User support and contact
- ✅ Privacy policy compliance
- ✅ Professional marketing presence

Good luck with your app launch! 🚀
