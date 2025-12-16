# Image Gallery with Lightbox

## Feature Overview

A responsive image gallery grid that opens images in a fullscreen lightbox modal when clicked. Includes navigation arrows, keyboard controls, and smooth animations.

**Best Used For:**
- Portfolio photo galleries
- Performance photos
- Headshots collection
- Behind-the-scenes galleries
- Any image showcase

**Visual Features:**
- Responsive grid layout (adapts to screen size)
- Hover zoom effect on thumbnails
- Click to open fullscreen lightbox
- Previous/Next navigation arrows
- Keyboard navigation (arrow keys, ESC to close)
- Image captions
- Smooth fade and zoom animations

---

## How to Customize

### 1. Add Your Images

#### Method A: Using Background Images (Simple)

**In `index.html`, replace gradient with image:**

**From:**
```html
<div class="gallery-image" style="background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);">
```

**To:**
```html
<div class="gallery-image" style="background-image: url('images/photo1.jpg');">
```

#### Method B: Using `<img>` Tags (Recommended)

**Replace the gallery-image div with:**
```html
<div class="gallery-item" onclick="openLightbox(0)">
    <img src="images/photo1.jpg" alt="Performance shot" class="gallery-image">
    <div class="gallery-overlay">
        <span class="view-icon">+</span>
    </div>
</div>
```

**Then in `style.css`, change `.gallery-image` to:**
```css
.gallery-image {
    width: 100%;
    height: 300px;
    object-fit: cover; /* Crops image to fit */
    display: block;
}
```

### 2. Update Image Data in JavaScript

**In `index.html` lines 104-114, update the images array:**

```javascript
const images = [
    { src: 'images/performance1.jpg', caption: 'Opening Night - Hamilton' },
    { src: 'images/headshot.jpg', caption: 'Professional Headshot' },
    { src: 'images/rehearsal.jpg', caption: 'Rehearsal Day 1' },
    // Add more images...
];
```

**Important:** The number of gallery items in HTML must match the number of items in the `images` array!

### 3. Add or Remove Images

**To add a new image:**

1. Add HTML gallery item:
```html
<div class="gallery-item" onclick="openLightbox(9)"> <!-- Update index -->
    <div class="gallery-image" style="background-image: url('images/new-photo.jpg');">
        <div class="gallery-overlay">
            <span class="view-icon">+</span>
        </div>
    </div>
</div>
```

2. Add to JavaScript array:
```javascript
{ src: 'images/new-photo.jpg', caption: 'New Photo Description' },
```

**To remove an image:**
- Delete the corresponding `<div class="gallery-item">` in HTML
- Delete the corresponding line in the `images` array
- Update all `onclick="openLightbox(X)"` indexes to match

### 4. Customize Grid Layout

**In `style.css` line 33:**

```css
/* 3 columns on desktop, adjusts automatically */
grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
```

**For specific column counts:**
```css
/* Always 4 columns */
grid-template-columns: repeat(4, 1fr);

/* Always 2 columns */
grid-template-columns: repeat(2, 1fr);

/* 5 columns, minimum 250px wide */
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
```

### 5. Change Image Height

**In `style.css` line 53:**
```css
height: 300px; /* Change to 250px, 400px, etc. */
```

### 6. Customize Colors

**Overlay darkness (`style.css` line 76):**
```css
background: rgba(0, 0, 0, 0.6); /* 0.3 = lighter, 0.8 = darker */
```

**Plus icon color (`style.css` line 87):**
```css
color: white; /* Change to any color */
font-size: 4rem; /* Size of the + */
```

**Lightbox background (`style.css` line 98):**
```css
background: rgba(0, 0, 0, 0.95); /* Almost black */
```

---

## HTML Structure

### Required Elements:

```html
<!-- Gallery Section -->
<section class="gallery-section">
    <div class="gallery-grid">
        <div class="gallery-item" onclick="openLightbox(0)">
            <div class="gallery-image">...</div>
            <div class="gallery-overlay">...</div>
        </div>
        <!-- Repeat for each image -->
    </div>
</section>

<!-- Lightbox Modal -->
<div class="lightbox" id="lightbox">
    <span class="close-lightbox">×</span>
    <span class="lightbox-arrow left">‹</span>
    <span class="lightbox-arrow right">›</span>
    <div class="lightbox-content">
        <img class="lightbox-image" id="lightboxImage">
        <div class="lightbox-caption" id="lightboxCaption"></div>
    </div>
</div>
```

### Optional Elements:
```html
<h2>Gallery Title</h2>
<p class="gallery-subtitle">Subtitle text</p>
```

---

## Integration Guide

### Copy to Your Page:

1. **Copy HTML:**
   - Copy the gallery section AND the lightbox modal
   - Paste anywhere in your `<body>`

2. **Copy CSS:**
   - Copy entire `style.css` contents
   - Paste into your main CSS file

3. **Copy JavaScript:**
   - Copy the entire `<script>` section
   - Paste before closing `</body>` tag
   - **Important:** Make sure the `images` array is updated with your image paths!

### Dependencies:
- None! Pure HTML/CSS/JS
- No jQuery or external libraries needed

### Image File Organization:
```
your-site/
├── index.html
├── style.css
└── images/
    ├── photo1.jpg
    ├── photo2.jpg
    ├── photo3.jpg
    └── ...
```

---

## Customization Examples

### Example 1: Make Gallery 4 Columns
**In `style.css` line 33:**
```css
grid-template-columns: repeat(4, 1fr);
```

### Example 2: Square Images Instead of Rectangles
**In `style.css` line 53:**
```css
height: 300px; /* Make same as width */
/* Or use aspect-ratio: 1 / 1; for perfect squares */
```

### Example 3: Remove Captions
**In `index.html`, delete line 104:**
```html
<!-- Delete this line -->
<div class="lightbox-caption" id="lightboxCaption">Image 1 of 9</div>
```

### Example 4: Change Hover Effect
**In `style.css` line 62:**
```css
/* Instead of zoom, try: */
.gallery-item:hover .gallery-image {
    transform: scale(1.05) rotate(2deg); /* Zoom + tilt */
}
```

### Example 5: Auto-Close Lightbox After 10 Seconds
**Add to JavaScript:**
```javascript
let autoCloseTimer;

function openLightbox(index) {
    currentImageIndex = index;
    document.getElementById('lightbox').style.display = 'flex';
    updateLightboxImage();
    document.body.style.overflow = 'hidden';

    // Auto-close after 10 seconds
    autoCloseTimer = setTimeout(closeLightbox, 10000);
}

function closeLightbox() {
    clearTimeout(autoCloseTimer);
    // ... rest of close function
}
```

---

## Keyboard Controls

When lightbox is open:
- **Right Arrow** → Next image
- **Left Arrow** → Previous image
- **ESC** → Close lightbox

---

## Performance Tips

1. **Optimize Images:**
   - Resize large images to max 1920px wide
   - Use JPEG for photos (smaller file size)
   - Use PNG for graphics with transparency
   - Compress images (TinyPNG, Squoosh)

2. **Lazy Loading:**
   Add `loading="lazy"` to img tags:
   ```html
   <img src="photo.jpg" loading="lazy">
   ```

3. **Thumbnail Generation:**
   - Use smaller versions for gallery grid
   - Load full-size only in lightbox
   - Example: `photo-thumb.jpg` (grid) vs `photo-full.jpg` (lightbox)

4. **Many Images (50+):**
   - Consider pagination or infinite scroll
   - Load images in batches
   - Use thumbnail CDN (Cloudinary, Imgix)

---

## Accessibility

Current accessibility features:
- Keyboard navigation (arrow keys, ESC)
- Click outside image to close
- Alt text support (add to `<img>` tags)

**To improve accessibility, add:**
```html
<div class="lightbox" role="dialog" aria-label="Image gallery lightbox">
    <span class="close-lightbox" aria-label="Close lightbox">×</span>
    <!-- ... -->
</div>
```

---

## Browser Compatibility

✅ Works in all modern browsers:
- Chrome, Firefox, Safari, Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

⚠️ CSS Grid support required (IE11 not supported)

---

## Common Issues & Solutions

**Problem:** Lightbox doesn't open
- **Solution:** Check that `onclick="openLightbox(X)"` indexes match array length

**Problem:** Images don't show in lightbox
- **Solution:** Verify image paths in the `images` array are correct

**Problem:** Grid looks weird on mobile
- **Solution:** Check responsive CSS media queries are included

**Problem:** Can't scroll page after closing lightbox
- **Solution:** JavaScript sets `overflow: hidden` - make sure `closeLightbox()` resets it
