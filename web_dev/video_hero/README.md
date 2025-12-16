# Video Hero

## Feature Overview

A full-screen hero section with a looping background video, overlay text, and call-to-action buttons. Perfect for showcasing performance reels, highlight videos, or creating dramatic first impressions.

**Best Used For:**
- Homepage hero section
- Landing pages
- Portfolio showcases
- Performer/creator sites

**Visual Effect:**
- Full-screen background video (loops automatically)
- Dark overlay for text readability
- Animated fade-in content
- Responsive design (video scales properly)
- Fallback gradient if video fails to load

---

## How to Customize

### 1. Replace the Video

**In `index.html` line 13:**
```html
<source src="your-video.mp4" type="video/mp4">
```

**Replace with:**
```html
<source src="path/to/your-performance-reel.mp4" type="video/mp4">
```

**Video Requirements:**
- Format: MP4 (most compatible)
- Recommended size: Under 10MB for fast loading
- Resolution: 1920x1080 or higher
- Aspect ratio: 16:9
- Compress your video for web (use HandBrake or similar)

### 2. Change Text Content

**In `index.html` lines 20-23:**
```html
<h1 class="hero-title">Your Name Here</h1>
<p class="hero-subtitle">Your Title | Your Specialty</p>
<p class="hero-tagline">Your Availability Message</p>
```

**Example:**
```html
<h1 class="hero-title">Jordan Smith</h1>
<p class="hero-subtitle">Actor | Singer | Dancer</p>
<p class="hero-tagline">Available for Film, TV & Theater</p>
```

### 3. Customize Colors

**Video Overlay Darkness (`style.css` line 39):**
```css
background: rgba(0, 0, 0, 0.5); /* 0.3 = lighter, 0.7 = darker */
```

**Primary Button Color (`style.css` line 121):**
```css
.btn-primary {
    background: white;      /* Change to your brand color */
    color: #333;            /* Text color */
}
```

**Secondary Button Color (`style.css` line 132):**
```css
.btn-secondary {
    background: transparent;
    color: white;          /* Change to your brand color */
    border: 2px solid white;
}
```

**Fallback Gradient (`style.css` line 44):**
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
/* Shows if video doesn't load */
```

### 4. Adjust Button Links

**In `index.html` lines 25-26:**
```html
<a href="#contact" class="btn btn-primary">Book Me</a>
<a href="#reel" class="btn btn-secondary">Watch Reel</a>
```

Change `href` to your desired destinations:
- `#contact` → jumps to contact section
- `#gallery` → jumps to gallery section
- `videos.html` → links to another page
- `https://calendly.com/yourname` → external booking link

### 5. Change Animation Speed

**Fade-in duration (`style.css` line 61):**
```css
animation: fadeInUp 1s ease-out; /* Change 1s to 0.5s (faster) or 2s (slower) */
```

**Stagger delays (`style.css` lines 75, 84, 94, 106):**
```css
animation: fadeInUp 1s ease-out 0.2s both; /* Change 0.2s, 0.4s, 0.6s, 0.8s */
```

---

## HTML Structure

### Required Elements:
```html
<section class="video-hero">
    <video class="hero-video">...</video>     <!-- Background video -->
    <div class="video-overlay"></div>         <!-- Dark overlay -->
    <div class="hero-content">                <!-- Main content -->
        <h1 class="hero-title">...</h1>       <!-- Name/headline -->
        <p class="hero-subtitle">...</p>      <!-- Title/role -->
        <div class="hero-buttons">...</div>   <!-- CTA buttons -->
    </div>
</section>
```

### Optional Elements:
```html
<p class="hero-tagline">...</p>               <!-- Additional tagline -->
<div class="scroll-indicator">...</div>       <!-- Scroll down arrow -->
```

---

## Integration Guide

### Copy to Your Page:

1. **Copy the HTML section:**
   - Copy everything from `<section class="video-hero">` to `</section>`
   - Paste where you want the hero to appear (usually at the top of `<body>`)

2. **Copy the CSS:**
   - Copy the entire `style.css` file contents
   - Paste into your main CSS file OR link to it:
     ```html
     <link rel="stylesheet" href="path/to/video-hero-style.css">
     ```

3. **Copy the JavaScript:**
   - Copy the `<script>` tag from `index.html`
   - Paste before your closing `</body>` tag

### Dependencies:
- None! Pure HTML/CSS/JS
- Works standalone or with other features

### Video Hosting Options:
- **Local:** Place video file in same folder
- **CDN:** Use a video hosting service (Vimeo, YouTube background, Cloudflare)
- **Self-hosted:** Upload to your server

---

## Customization Examples

### Example 1: Change Background to Blue Gradient
**In `style.css` line 44:**
```css
background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
```

### Example 2: Make Overlay Lighter (More Video Visible)
**In `style.css` line 39:**
```css
background: rgba(0, 0, 0, 0.3); /* Was 0.5, now 0.3 */
```

### Example 3: Change Button Text
**In `index.html`:**
```html
<a href="#hire-me" class="btn btn-primary">Hire Me</a>
<a href="#portfolio" class="btn btn-secondary">View Portfolio</a>
```

### Example 4: Remove Scroll Indicator
**In `index.html`, delete lines 30-33:**
```html
<!-- Remove this entire block -->
<div class="scroll-indicator">
    ...
</div>
```

### Example 5: Make Video Muted Autoplay (Mobile-Friendly)
Already configured! The video tag includes:
- `autoplay` - Starts automatically
- `muted` - Required for autoplay on mobile
- `loop` - Repeats forever
- `playsinline` - Plays inline on iOS (doesn't go fullscreen)

---

## Performance Tips

1. **Optimize Video:**
   - Compress to under 5-10MB
   - Use H.264 codec for best compatibility
   - Resolution: 1920x1080 is sufficient (4K is overkill)

2. **Mobile Considerations:**
   - Some mobile browsers don't support autoplay
   - Fallback gradient will show instead
   - Consider using a poster image: `<video poster="thumbnail.jpg">`

3. **Loading Speed:**
   - Add `preload="metadata"` to video tag for faster page load
   - Consider lazy loading if hero isn't first on page

---

## Browser Compatibility

✅ Works in all modern browsers:
- Chrome, Firefox, Safari, Edge
- iOS Safari, Chrome Mobile
- Video format: MP4 with H.264 codec (universal support)

⚠️ Fallback:
- If video fails, gradient background shows
- JavaScript automatically detects video errors
