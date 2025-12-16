# Web Dev Features Library

**Modular website components for building performer & creative portfolios**

A collection of self-contained, reusable web features that can be mixed and matched to quickly build impressive portfolio sites. Perfect for dancers, actors, musicians, artists, and other performers looking to showcase their work and book gigs.

---

## 📚 Complete Feature List

### 🎬 Portfolio Essentials

| Feature | Type | Best For | Mobile-Friendly |
|---------|------|----------|-----------------|
| **[video_hero](video_hero/)** | Hero Section | Homepage, landing pages, showcase reels | ✅ |
| **[image_gallery_lightbox](image_gallery_lightbox/)** | Gallery | Photo galleries, headshots, performance photos | ✅ |
| **[testimonial_slider](testimonial_slider/)** | Social Proof | Reviews from directors, choreographers, clients | ✅ |
| **[cta_section](cta_section/)** | Conversion | "Book Me" banners, contact prompts, availability | ✅ |

### ✨ Visual Effects & Animations

| Feature | Type | Best For | Mobile-Friendly |
|---------|------|----------|-----------------|
| **[seamless_loop](seamless_loop/)** | Carousel | Rotating image carousel, continuous loop | ✅ |
| **[scroll_reveal](scroll_reveal/)** | Animation | Content reveals on scroll, fade/slide effects | ✅ |
| **[typing_effect](typing_effect/)** | Animation | Dynamic typing headlines, rotating text | ✅ |
| **[image_hover](image_hover/)** | Interaction | Hover effects, zoom, flip, rotate | ✅ |

### 🎨 Content Display

| Feature | Type | Best For | Mobile-Friendly |
|---------|------|----------|-----------------|
| **[project_cards](project_cards/)** | Content Grid | Project showcases, portfolio pieces | ✅ |
| **[skill_bars](skill_bars/)** | Data Viz | Skills display, progress indicators | ✅ |
| **[hero_section](hero_section/)** | Hero Section | Homepage intro, gradient background | ✅ |

### 🧭 Navigation & Structure

| Feature | Type | Best For | Mobile-Friendly |
|---------|------|----------|-----------------|
| **[hamburger_menu](hamburger_menu/)** | Navigation | Mobile menu, responsive navigation | ✅ |

### 📝 Forms

| Feature | Type | Best For | Mobile-Friendly |
|---------|------|----------|-----------------|
| **[contact_form](contact_form/)** | Form | Contact pages, inquiry forms | ✅ |

---

## 🚀 Quick Start Guide

### 1. Choose Your Features

Browse the features above and pick the ones you need for your site. Each feature is self-contained and works independently.

### 2. Open the Feature

Navigate to the feature folder and open `index.html` in your browser to see a live demo.

### 3. Read the Documentation

Each feature has a `README.md` with:
- How to customize colors, text, images
- HTML structure breakdown
- Integration instructions
- Customization examples

### 4. Copy to Your Site

Follow the integration guide in each README to copy the HTML, CSS, and JavaScript into your project.

---

## 📋 Common Page Layouts

### Homepage (Performer/Creative)
```
┌─────────────────────────────────┐
│  video_hero                     │  ← Performance reel background
├─────────────────────────────────┤
│  About section (custom)         │  ← Bio, headshot
├─────────────────────────────────┤
│  image_gallery_lightbox         │  ← Performance photos
├─────────────────────────────────┤
│  skill_bars / stats             │  ← Years, shows, training
├─────────────────────────────────┤
│  testimonial_slider             │  ← Director reviews
├─────────────────────────────────┤
│  cta_section                    │  ← "Book Me Now"
├─────────────────────────────────┤
│  contact_form                   │  ← Contact info
└─────────────────────────────────┘
```

### Gallery Page
```
┌─────────────────────────────────┐
│  hero_section                   │  ← "My Work" header
├─────────────────────────────────┤
│  image_gallery_lightbox         │  ← Full photo gallery
├─────────────────────────────────┤
│  cta_section                    │  ← "Like what you see?"
└─────────────────────────────────┘
```

### Videos/Reels Page
```
┌─────────────────────────────────┐
│  video_hero                     │  ← Featured reel
├─────────────────────────────────┤
│  project_cards (video grid)     │  ← Multiple reels
├─────────────────────────────────┤
│  cta_section                    │  ← "Let's collaborate"
└─────────────────────────────────┘
```

### Resume/Credits Page
```
┌─────────────────────────────────┐
│  hero_section                   │  ← Name, title
├─────────────────────────────────┤
│  skill_bars                     │  ← Training, skills
├─────────────────────────────────┤
│  Timeline (coming soon)         │  ← Performance history
├─────────────────────────────────┤
│  testimonial_slider             │  ← Recommendations
├─────────────────────────────────┤
│  cta_section                    │  ← Download resume
└─────────────────────────────────┘
```

### Contact Page
```
┌─────────────────────────────────┐
│  hero_section                   │  ← "Get In Touch"
├─────────────────────────────────┤
│  contact_form                   │  ← Contact form
├─────────────────────────────────┤
│  Social media links             │  ← Instagram, TikTok, etc.
└─────────────────────────────────┘
```

---

## 🎨 Customization & Theming

### Global Color Palette

Most features use this consistent color scheme:

```css
/* Primary Gradient */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Primary Color */
--primary: #667eea;

/* Dark Backgrounds */
--dark: #1a1a2e;
--dark-alt: #0f0c29;

/* Light Backgrounds */
--light: #f5f5f5;
--white: #ffffff;

/* Text Colors */
--text-dark: #333;
--text-light: #666;
```

### How to Apply Your Brand Colors

**Method 1: Find & Replace**
1. Open all CSS files
2. Find `#667eea` (primary purple)
3. Replace with your brand color
4. Find `#764ba2` (secondary purple)
5. Replace with your accent color

**Method 2: CSS Variables (Recommended)**

Add this to the top of your main CSS file:

```css
:root {
    --primary-color: #YOUR_COLOR_HERE;
    --secondary-color: #YOUR_ACCENT_COLOR;
    --text-color: #333;
    --background: #f5f5f5;
}
```

Then update each feature's CSS to use variables:
```css
/* Instead of */
background: #667eea;

/* Use */
background: var(--primary-color);
```

### Typography

Standard font stack across all features:
```css
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
```

**To change globally:**
```css
body {
    font-family: 'Your Font', sans-serif;
}
```

**Popular performer site fonts:**
- Modern: `'Poppins', sans-serif`
- Elegant: `'Playfair Display', serif`
- Bold: `'Montserrat', sans-serif`
- Clean: `'Inter', sans-serif`

---

## ⚡ Performance Optimization

### Image Optimization

**For Photos/Galleries:**
- Format: JPEG (smaller file size)
- Max width: 1920px
- Quality: 70-85%
- Tools: TinyPNG, Squoosh, ImageOptim

**For Thumbnails:**
- Create smaller versions (500px wide)
- Load thumbnails in grid, full-size in lightbox

**For Background Images:**
- Compress aggressively (under 500KB)
- Use WebP format when possible

### Video Optimization

**For video_hero:**
- Max size: 5-10MB
- Format: MP4 (H.264 codec)
- Resolution: 1920x1080 max
- Length: 10-30 seconds (loop it)
- Tools: HandBrake, Clipchamp

**For performance reels:**
- Host on YouTube/Vimeo when possible
- Embed instead of self-hosting
- Use poster images for better loading

### Loading Speed Tips

1. **Lazy Loading:**
   ```html
   <img src="photo.jpg" loading="lazy" alt="Description">
   ```

2. **Minimize CSS/JS:**
   - Combine multiple CSS files into one
   - Remove unused styles

3. **Use CDN for images:**
   - Cloudinary, Imgix, or similar
   - Automatic optimization and responsive images

---

## 📱 Mobile Responsiveness

All features are mobile-friendly with a breakpoint at **768px**.

### Testing Checklist

- [ ] Test on actual phone (not just browser resize)
- [ ] Tap targets are min 44x44px
- [ ] Text is readable (min 16px font size)
- [ ] Images load properly
- [ ] Videos play on mobile (muted autoplay)
- [ ] Forms are easy to fill out
- [ ] Navigation works smoothly
- [ ] No horizontal scrolling

### Mobile-Specific Tips

**For video_hero:**
- Some mobile browsers block autoplay
- Fallback gradient shows instead
- Test on iOS Safari and Chrome

**For image_gallery_lightbox:**
- Swipe gestures would enhance UX
- Consider adding touch event handlers

**For hamburger_menu:**
- Essential for mobile navigation
- Test open/close animations

---

## 🔧 Integration Tips

### Combining Multiple Features

**1. CSS Organization:**
```html
<head>
    <!-- Option A: One file per feature -->
    <link rel="stylesheet" href="css/video-hero.css">
    <link rel="stylesheet" href="css/gallery.css">
    <link rel="stylesheet" href="css/testimonials.css">

    <!-- Option B: Combined (recommended) -->
    <link rel="stylesheet" href="css/main.css">
</head>
```

**2. JavaScript Organization:**
```html
<body>
    <!-- Your HTML -->

    <!-- Option A: Inline (current setup) -->
    <script>
        // Gallery code
        // Testimonial code
        // etc.
    </script>

    <!-- Option B: External files -->
    <script src="js/gallery.js"></script>
    <script src="js/testimonials.js"></script>
</body>
```

**3. Avoid ID Conflicts:**

If using multiple features, ensure unique IDs:
```html
<!-- Gallery -->
<div id="galleryLightbox"></div>

<!-- Video Modal -->
<div id="videoModal"></div>

<!-- NOT -->
<div id="modal"></div> <!-- Don't reuse generic IDs -->
```

### File Structure Recommendation

```
your-site/
├── index.html
├── gallery.html
├── videos.html
├── contact.html
├── css/
│   ├── main.css          (combined from all features)
│   └── reset.css         (normalize styles)
├── js/
│   ├── gallery.js
│   ├── testimonials.js
│   └── menu.js
├── images/
│   ├── photos/
│   ├── headshots/
│   └── thumbnails/
└── videos/
    └── reel.mp4
```

---

## 🎯 Use Case: Commercial Dancer Portfolio

**Goal:** Book Broadway shows, tours, music videos, commercials

**Essential Pages:**
1. **Homepage** - video_hero + about + testimonials + cta
2. **Gallery** - image_gallery_lightbox (headshots, performance photos)
3. **Videos** - Video reels grid
4. **Resume** - Training, experience, credits
5. **Contact** - contact_form + booking info

**Key Features:**
- video_hero with performance reel
- image_gallery_lightbox for headshots
- testimonial_slider for director reviews
- cta_section for "Book Me" prompts
- contact_form for inquiries

**Priority:**
1. Make it easy to see your work (photos/videos)
2. Build credibility (testimonials, credits)
3. Make booking simple (clear CTAs, contact form)

---

## 🚧 Upcoming Features (Batch 2)

Coming soon to complete the library:

- **stats_counter** - Animated counting numbers (years, shows, awards)
- **timeline** - Career history, training, performances
- **video_grid** - Multiple video showcase
- **split_section** - 50/50 image + bio/about
- **parallax_section** - Parallax scrolling photos
- **masonry_gallery** - Pinterest-style image grid
- **text_reveal_animation** - Dramatic text effects
- **social_feed** - Instagram/TikTok embed showcase

---

## ❓ FAQ

### Can I use these for commercial projects?
Yes! These features are free to use for personal and commercial projects.

### Do I need to credit this library?
Not required, but appreciated!

### Can I modify the code?
Absolutely! These are templates - customize them to fit your needs.

### Do these work with WordPress/Wix/Squarespace?
The HTML/CSS can be integrated into custom themes, but may require adaptation for page builders.

### What if I need help?
Each feature has detailed documentation in its README.md file. Read through the customization examples first.

### Can I sell websites built with these features?
Yes! Use them to build client sites.

---

## 📞 Support & Resources

**Documentation:**
- Each feature folder has a detailed `README.md`
- Customization examples included
- Integration guides provided

**Testing:**
- Open `index.html` in each folder for live demo
- Test in multiple browsers
- Check mobile responsiveness

**Tools:**
- Image optimization: [TinyPNG](https://tinypng.com), [Squoosh](https://squoosh.app)
- Video compression: [HandBrake](https://handbrake.fr)
- Font pairing: [FontPair](https://fontpair.co)
- Color schemes: [Coolors](https://coolors.co)
- Gradient generator: [cssgradient.io](https://cssgradient.io)

---

## 🎓 Learning Resources

**HTML/CSS Basics:**
- [MDN Web Docs](https://developer.mozilla.org)
- [CSS-Tricks](https://css-tricks.com)
- [Web.dev](https://web.dev/learn/css/)

**JavaScript:**
- [JavaScript.info](https://javascript.info)
- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

**Responsive Design:**
- [Responsive Web Design Basics](https://web.dev/responsive-web-design-basics/)
- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

---

## 📊 Feature Compatibility Matrix

| Feature | Video Support | Image Support | Animation | JavaScript | Responsive |
|---------|--------------|---------------|-----------|------------|------------|
| video_hero | ✅ | ✅ (fallback) | ✅ | ⚠️ (minimal) | ✅ |
| image_gallery_lightbox | ❌ | ✅ | ✅ | ✅ | ✅ |
| testimonial_slider | ❌ | ✅ | ✅ | ✅ | ✅ |
| cta_section | ❌ | ✅ (bg) | ✅ | ❌ | ✅ |
| seamless_loop | ❌ | ✅ | ✅ | ❌ | ✅ |
| scroll_reveal | ❌ | ❌ | ✅ | ✅ | ✅ |
| typing_effect | ❌ | ❌ | ✅ | ✅ | ✅ |
| image_hover | ❌ | ✅ | ✅ | ❌ | ✅ |
| project_cards | ❌ | ✅ | ✅ | ❌ | ✅ |
| skill_bars | ❌ | ❌ | ✅ | ❌ | ✅ |
| hero_section | ❌ | ❌ | ✅ | ❌ | ✅ |
| hamburger_menu | ❌ | ❌ | ✅ | ✅ | ✅ |
| contact_form | ❌ | ❌ | ✅ | ❌ | ✅ |

---

**Last Updated:** December 2024
**Total Features:** 13 (+ 8 coming soon)
**Status:** Production Ready ✅
