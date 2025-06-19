# Website Customization Guide

This guide explains how to easily customize your optimized marketing website.

## Quick Start

All main customization options are available in the `js/config.js` file. Simply modify the values there to customize your website.

## 1. Company Information

Update your company details in the `CONFIG.company` object:

```javascript
company: {
    name: "Your Company Name",
    tagline: "Your Tagline",
    email: "your-email@company.com",
    phone: "+1 234 567 8900",
    location: "Your City, Country",
    website: "https://yourwebsite.com",
    linkedIn: "https://linkedin.com/company/yourcompany"
}
```

## 2. Form Configuration

Set up your contact form in the `CONFIG.form` object:

```javascript
form: {
    scriptURL: 'your-google-apps-script-url', // Your form submission endpoint
    thankYouPage: 'https://yourwebsite.com/thank-you', // Redirect after submission
    fields: {
        name: { required: true, label: "Your Name" },
        email: { required: true, label: "Your Email" },
        company: { required: false, label: "Company Name" }
    }
}
```

## 3. Color Themes

### Using Pre-built Themes

Switch between themes by changing the `activeTheme` value:

```javascript
activeTheme: 'default' // Options: 'default', 'blue', 'green'
```

### Creating Custom Themes

Add a new theme to the `CONFIG.themes` object:

```javascript
themes: {
    // ... existing themes
    red: {
        neon: "#ff4444",
        purple: "#cc0000",
        dark: "#1a0000",
        white: "#ffffff"
    }
}
```

Then set `activeTheme: 'red'`

### Dynamic Theme Switching

You can change themes programmatically:

```javascript
// In browser console or your custom scripts
changeTheme('blue');  // Switch to blue theme
changeTheme('green'); // Switch to green theme
```

## 4. Services & Content

### Updating Services

Modify the `CONFIG.services` array:

```javascript
services: [
    {
        number: 1,
        title: "Your Service Title",
        description: "Your service description"
    },
    // Add more services...
]
```

### Updating "Why Choose Us" Reasons

Modify the `CONFIG.reasons` array:

```javascript
reasons: [
    {
        number: 1,
        title: "Your Reason Title",
        description: "Your reason description"
    },
    // Add more reasons...
]
```

## 5. Visual Customization

### CSS Custom Properties

All colors, fonts, and spacing are controlled by CSS custom properties in `css/styles.css`:

```css
:root {
    /* Colors - automatically updated by themes */
    --neon: #ddf344;
    --purple: #382bf0;
    --dark: #191919;
    --white: #ffffff;
    
    /* Typography */
    --font-family: 'Arial', sans-serif;
    --font-size-base: 1rem;
    --font-size-4xl: 4.5rem;
    
    /* Spacing */
    --spacing-sm: 1rem;
    --spacing-lg: 2rem;
    --spacing-3xl: 6rem;
}
```

### Animation Settings

Adjust animation speeds in `CONFIG.animations`:

```javascript
animations: {
    scrollOffset: 100, // Trigger point for scroll animations
    floatingSpeed: 20, // Background floating elements speed
    brandScrollSpeed: 20, // Brand logo scroll speed
    shimmerSpeed: 7 // Hero title shimmer effect speed
}
```

## 6. Content Updates

### Text Content

Update text directly in the HTML file (`index.html`). Key sections:

- Hero title and subtitle
- Section headings and descriptions
- Footer content
- Modal content

### Images

Replace images in the `images/` folder:

- `mente3.png` - Logo
- `mrtaco.PNG`, `milkshake.JPG`, `codigo-min.png` - Brand logos

Update image references in the HTML or `CONFIG.brands` array.

## 7. Advanced Customization

### Adding New Sections

1. Add HTML structure in `index.html`
2. Add corresponding CSS in `css/styles.css`
3. Add any interactive behavior in `js/main.js`

### Custom JavaScript

Add custom functionality by extending the `WebsiteManager` class in `js/main.js`:

```javascript
// Add new methods to WebsiteManager class
setupCustomFeature() {
    // Your custom code here
}
```

### SEO Optimization

Update meta tags in the HTML `<head>` section:

```html
<title>Your Page Title</title>
<meta name="description" content="Your page description">
<meta name="keywords" content="your, keywords, here">
```

## 8. Development Tips

### Browser Console Tools

Open browser console (F12) and try:

```javascript
// Change theme
changeTheme('blue');

// Update configuration
updateConfig({ activeTheme: 'green' });

// Access the main website manager
websiteManager.openModal(); // Open contact modal
websiteManager.closeModal(); // Close contact modal
```

### File Structure

```
/
├── index.html          # Main HTML file
├── css/
│   └── styles.css      # All styles (organized and optimized)
├── js/
│   ├── config.js       # Configuration and customization
│   └── main.js         # Main functionality
├── images/             # Image assets
└── CUSTOMIZATION_GUIDE.md # This guide
```

## 9. Performance Optimization

The optimized code includes:

- ✅ Modular CSS with custom properties
- ✅ Optimized JavaScript with classes
- ✅ Lazy loading animations
- ✅ Responsive design
- ✅ Accessible markup
- ✅ SEO-friendly structure

## 10. Browser Support

This code supports all modern browsers:
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

For older browsers, consider adding polyfills if needed.

## Need Help?

The code is designed to be self-documenting. Check the browser console for helpful messages and available commands when you load the page.
