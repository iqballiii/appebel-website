# Appebel - Event Management App Website

Official website for Appebel mobile application, featuring app information, support, and privacy policy.

## 🌐 Live Website

Visit: [https://iqballiii.github.io/appebel-website](https://iqballiii.github.io/appebel-website/)

## 📱 About Appebel

Appebel is your personal event companion for managing festivals, concerts, and live events. Features include:

- Event schedule management
- Favorite artists tracking
- Smart notifications and reminders
- Personalized profiles
- Multi-language support

## 🚀 Deployment Instructions

### Deploy to GitHub Pages:

1. Create a new repository on GitHub named `appebel-website`
2. Clone this repository locally
3. Push the code to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Appebel website"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/appebel-website.git
   git push -u origin main
   ```
4. Go to repository Settings → Pages
5. Under "Source", select `main` branch
6. Click "Save"
7. Your site will be live at `https://YOUR-USERNAME.github.io/appebel-website/`

## 🔧 API Integration

The contact form is ready for API integration. To enable:

1. Open `index.html` (or `appebel-website-v2.html`)
2. Find the `API_CONFIG` section in the JavaScript
3. Replace the endpoint with your actual API URL
4. Set `enabled: true`

### Example API Endpoints You Can Use:

**Option 1: Your Own Backend**
```javascript
const API_CONFIG = {
    endpoint: 'https://your-api.com/api/contact',
    enabled: true
};
```

**Option 2: Formspree (Free)**
1. Sign up at [formspree.io](https://formspree.io)
2. Create a new form
3. Use the endpoint:
```javascript
const API_CONFIG = {
    endpoint: 'https://formspree.io/f/YOUR_FORM_ID',
    enabled: true
};
```

**Option 3: EmailJS (Free)**
Follow [EmailJS documentation](https://www.emailjs.com/docs/) for setup

## 📝 Customization

### Update Branding:
- Replace emoji logo (🎵) with your actual logo image
- Add real app screenshots to replace placeholders
- Update colors in CSS `:root` variables

### Update Contact Information:
- Change email addresses in the Contact section
- Update support email links

### Add App Store Links:
- Replace download button `href="#"` with actual App Store URLs

## 📄 Pages Included

- **Home**: Hero section with app overview
- **Features**: Detailed feature showcase
- **Support**: Contact form and FAQ
- **Privacy Policy**: Complete privacy policy
- **Contact**: Contact information

## 🛠️ Built With

- HTML5
- CSS3 (Custom animations and gradients)
- Vanilla JavaScript
- Google Fonts (Righteous, DM Sans)

## 📧 Support

For support, email support@appebel.com

## 📜 License

© 2026 Appebel. All rights reserved.
