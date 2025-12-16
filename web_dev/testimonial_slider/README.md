# Testimonial Slider

## Feature Overview

An auto-rotating testimonial carousel showcasing reviews from directors, choreographers, clients, or collaborators. Includes author info with avatars, navigation arrows, dots, and smooth animations.

**Best Used For:**
- Homepage social proof section
- Portfolio credibility building
- Client testimonials
- Reviews from collaborators
- Press quotes

**Visual Features:**
- Auto-rotating slides (every 5 seconds)
- Pause on hover
- Click arrows to navigate
- Click dots to jump to specific testimonial
- Keyboard navigation (arrow keys)
- Smooth slide transitions
- Author info with avatar/photo

---

## How to Customize

### 1. Add/Edit Testimonials

**In `index.html`, duplicate a testimonial card:**

```html
<!-- Copy this entire block -->
<div class="testimonial-card">
    <div class="quote-icon">"</div>
    <p class="testimonial-text">
        "Your testimonial quote goes here. Keep it 2-3 sentences for best visual balance."
    </p>
    <div class="testimonial-author">
        <div class="author-image" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);">
            <span class="author-initial">AB</span>
        </div>
        <div class="author-info">
            <h4 class="author-name">Author Name</h4>
            <p class="author-title">Job Title</p>
            <p class="author-company">Company/Production Name</p>
        </div>
    </div>
</div>
```

**Example:**
```html
<div class="testimonial-card">
    <div class="quote-icon">"</div>
    <p class="testimonial-text">
        "Working with Jordan was transformative for our production.
        Their vision and execution exceeded all expectations."
    </p>
    <div class="testimonial-author">
        <div class="author-image" style="background: linear-gradient(135deg, #fa709a 0%, #fee140 100%);">
            <span class="author-initial">KL</span>
        </div>
        <div class="author-info">
            <h4 class="author-name">Karen Lee</h4>
            <p class="author-title">Casting Director</p>
            <p class="author-company">NBC Universal</p>
        </div>
    </div>
</div>
```

### 2. Use Real Photos Instead of Initials

**Replace author-image div background:**

**From:**
```html
<div class="author-image" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);">
    <span class="author-initial">JD</span>
</div>
```

**To:**
```html
<div class="author-image" style="background-image: url('images/john-davis.jpg'); background-size: cover; background-position: center;">
    <!-- Remove the span with initials -->
</div>
```

### 3. Change Autoplay Speed

**In `index.html` JavaScript section (line 160):**

```javascript
autoplayInterval = setInterval(() => {
    changeTestimonial(1);
}, 5000); // Change 5000 to desired milliseconds (3000 = 3 seconds, 8000 = 8 seconds)
```

**Examples:**
- `3000` = 3 seconds (faster)
- `7000` = 7 seconds (slower)
- Comment out `startAutoplay();` to disable autoplay entirely

### 4. Customize Colors

**Background gradient (`style.css` line 10):**
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
/* Change to match your brand */
```

**Quote icon color (`style.css` line 52):**
```css
color: #667eea; /* Change to your brand color */
```

**Author title color (`style.css` line 119):**
```css
color: #667eea; /* Job title color */
```

**Active dot color (`style.css` line 183):**
```css
background: #667eea; /* Matches brand */
```

**Arrow button colors (`style.css` lines 130-131):**
```css
.slider-arrow {
    background: rgba(102, 126, 234, 0.1); /* Semi-transparent */
}

.slider-arrow span {
    color: #667eea; /* Arrow icon color */
}
```

### 5. Change Section Background

**In `style.css` line 10:**

**Solid color:**
```css
background: #1a1a2e; /* Dark solid */
```

**Different gradient:**
```css
background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%); /* Blue */
```

**Remove background (use on existing page):**
```css
background: transparent;
```

### 6. Adjust Card Appearance

**Card background (`style.css` line 37):**
```css
background: white; /* Change to #f5f5f5 for light gray, etc. */
```

**Border radius (`style.css` line 38):**
```css
border-radius: 20px; /* Make 10px for less rounded, 30px for more */
```

**Padding (`style.css` line 39):**
```css
padding: 3rem 2rem; /* Increase/decrease spacing */
```

---

## HTML Structure

### Required Elements:

```html
<section class="testimonials-section">
    <div class="testimonial-slider">
        <div class="testimonial-track" id="testimonialTrack">
            <!-- Testimonial cards go here -->
            <div class="testimonial-card">...</div>
        </div>

        <!-- Navigation -->
        <button class="slider-arrow left">...</button>
        <button class="slider-arrow right">...</button>
        <div class="slider-dots" id="sliderDots"></div>
    </div>
</section>

<script>
    <!-- JavaScript code -->
</script>
```

### Optional Elements:
```html
<h2>Section Title</h2>
<p class="section-subtitle">Section description</p>
```

---

## Integration Guide

### Copy to Your Page:

1. **Copy HTML:**
   - Copy entire `<section class="testimonials-section">` to `</section>`
   - Paste where you want testimonials (usually mid-page or before contact)

2. **Copy CSS:**
   - Copy entire `style.css` contents
   - Paste into your main CSS file
   - **Note:** Adjust `body` styles if integrating into existing page

3. **Copy JavaScript:**
   - Copy entire `<script>` section
   - Paste before closing `</body>` tag

### Dependencies:
- None! Pure HTML/CSS/JS
- No jQuery or external libraries

### Integration Tips:
- Remove `body` gradient if placing on existing page
- Adjust `.testimonials-section` max-width to fit your design
- Can change text color to black if using on light background

---

## Customization Examples

### Example 1: Disable Autoplay
**In JavaScript:**
```javascript
// Comment out or remove this line at the bottom:
// startAutoplay();
```

### Example 2: Show 2 Testimonials at Once (Desktop)
**In `style.css` line 49:**
```css
.testimonial-card {
    min-width: 50%; /* Was 100%, now shows 2 at a time */
    /* Note: You'll need to adjust navigation logic too */
}
```

### Example 3: Remove Navigation Arrows
**In `index.html`, delete lines 90-96:**
```html
<!-- Delete this block -->
<button class="slider-arrow left" onclick="changeTestimonial(-1)">
    <span>&#10094;</span>
</button>
<button class="slider-arrow right" onclick="changeTestimonial(1)">
    <span>&#10095;</span>
</button>
```

### Example 4: Change Quote Icon
**In `index.html` line 21:**
```html
<div class="quote-icon">❝</div>  <!-- Different quote style -->
<!-- Or remove entirely for cleaner look -->
```

### Example 5: Add Star Ratings
**In `index.html`, add after testimonial-text:**
```html
<div class="rating">
    ★★★★★
</div>
```

**In `style.css`, add:**
```css
.rating {
    color: #ffd700; /* Gold stars */
    font-size: 1.5rem;
    margin: 1rem 0;
}
```

---

## JavaScript Functions

### Key Functions:

- `changeTestimonial(direction)` - Navigate prev/next (-1 or 1)
- `goToTestimonial(index)` - Jump to specific slide
- `updateSlider()` - Updates position and active dot
- `startAutoplay()` - Begins auto-rotation
- `resetAutoplay()` - Restarts autoplay timer

### Keyboard Controls:
- **Right Arrow** → Next testimonial
- **Left Arrow** → Previous testimonial

### Mouse Interactions:
- **Hover on slider** → Pauses autoplay
- **Mouse leave** → Resumes autoplay
- **Click arrows** → Navigate
- **Click dots** → Jump to slide

---

## Performance Tips

1. **Image Optimization:**
   - Use small images for author photos (100x100px max)
   - Compress images (TinyPNG)
   - Use WebP format for smaller file sizes

2. **Lazy Loading:**
   If you have many testimonials (10+), only load visible ones initially

3. **Testimonial Length:**
   - Keep quotes 2-4 sentences (150-300 characters)
   - Longer quotes may need height adjustment

---

## Accessibility

Current features:
- Keyboard navigation (arrow keys)
- Semantic HTML (section, button elements)
- Pause on hover (user control)

**To improve accessibility:**

```html
<div class="testimonial-slider" role="region" aria-label="Customer testimonials">
    <button class="slider-arrow left" aria-label="Previous testimonial">...</button>
    <button class="slider-arrow right" aria-label="Next testimonial">...</button>
</div>
```

**Add ARIA live region:**
```html
<div class="testimonial-track" aria-live="polite">...</div>
```

---

## Browser Compatibility

✅ Works in all modern browsers:
- Chrome, Firefox, Safari, Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

⚠️ CSS Flexbox required (IE11 partially supported)

---

## Common Issues & Solutions

**Problem:** Slides don't advance
- **Solution:** Check that JavaScript is included and IDs match (`testimonialTrack`, `sliderDots`)

**Problem:** Dots don't show
- **Solution:** JavaScript creates dots dynamically - ensure `<div id="sliderDots">` exists

**Problem:** Autoplay doesn't pause on hover
- **Solution:** Check that `.testimonial-slider` class is on correct element

**Problem:** Too much/too little space between slides
- **Solution:** Adjust `.testimonial-card` padding in CSS

**Problem:** Images don't show
- **Solution:** Check image paths in `background-image: url(...)` are correct
