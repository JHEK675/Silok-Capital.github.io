# Silok-Capital Portfolio Website

A modern, responsive single-page portfolio website showcasing professional projects, skills, and contact information. Built with vanilla HTML, CSS, and JavaScript—no build system or dependencies required.

**Live Site:** [https://JHEK675.github.io](https://JHEK675.github.io)

## 🎯 Features

- **Smooth Scroll Navigation**: Seamless anchor-based navigation with active link highlighting
- **Responsive Design**: Mobile-first approach with breakpoints at 768px and 480px
- **Scroll Animations**: Intersection Observer API for fade-in effects on project cards and skills
- **Modern Gradient UI**: Consistent purple gradient theme (#667eea to #764ba2)
- **Zero Dependencies**: Pure HTML5, CSS3, and vanilla JavaScript—deploy directly to GitHub Pages
- **Accessibility**: Semantic HTML structure with proper meta tags and alt text support

## 🚀 Quick Start

### No Installation Needed
Simply clone or fork this repository and customize the content:

```bash
git clone https://github.com/JHEK675/Silok-Capital.github.io.git
cd Silok-Capital.github.io
```

Open `index.html` in your browser to preview locally.

## 📁 Project Structure

```
.
├── index.html        # Main HTML file with all sections
├── styles.css        # Responsive styling with CSS variables
├── script.js         # Interactive features (navigation, animations)
└── README.md         # This file
```

## 🎨 Customization Guide

### 1. Update Personal Information
Edit `index.html`:
- **Line 7**: Update `<title>` and meta description
- **Lines 18-20**: Change logo/name in navbar
- **Lines 32-33**: Update hero section heading and subtitle
- **Lines 46-50**: Replace About section content
- **Lines 66-94**: Modify project cards (title, description, tags, links)
- **Lines 113-130**: Update skills categories and items
- **Lines 139-144**: Update contact section and social media links
- **Line 149**: Update copyright year/name

### 2. Change Color Scheme
Edit `styles.css` (`:root` section, lines 12-21):
```css
--primary-color: #667eea;      /* Main gradient start */
--secondary-color: #764ba2;    /* Main gradient end */
--text-dark: #333;             /* Text color */
--text-light: #666;            /* Secondary text */
--bg-light: #f8f9fa;           /* Section backgrounds */
--bg-dark: #1a1a1a;            /* Footer background */
```

### 3. Customize Animation Behavior
In `script.js`, adjust IntersectionObserver settings:
- **Line 35**: `threshold: 0.1` — controls when animation triggers (0-1, lower = earlier)
- **Line 36**: `rootMargin: '0px 0px -50px 0px'` — offset for animation trigger
- **Lines 44-46**: Modify `.project-card` animation properties
- **Lines 51-53**: Modify `.skill-category` animation properties

### 4. Add Project Cards
Duplicate a project card block in `index.html` (lines 63-79):
```html
<div class="project-card">
    <div class="project-image" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);"></div>
    <h3>Project Name</h3>
    <p>Project description</p>
    <div class="project-tags">
        <span class="tag">Technology</span>
    </div>
    <a href="#" class="project-link">View Project →</a>
</div>
```

### 5. Add New Sections
1. Add section to `index.html`:
   ```html
   <section id="section-id" class="section-name">
       <div class="container">
           <!-- Your content -->
       </div>
   </section>
   ```
2. Add navbar link: `<li><a href="#section-id">Label</a></li>`
3. Create styles in `styles.css` with 80px padding
4. If scroll animation needed, add observer logic in `script.js`

## 🎬 Features in Detail

### Navigation
- Fixed sticky navbar with gradient logo text
- Active link highlighting based on scroll position (offset by -200px for sticky nav)
- Smooth scrolling to anchor links (no page reload)

### Animations
- Hero section text fades in on page load with staggered timing
- Project cards and skill categories fade in as they scroll into view
- Buttons have hover effects with transform and shadow changes

### Responsive Breakpoints
| Breakpoint | Changes |
|-----------|---------|
| 768px and below | Nav gaps reduce, grids switch to single column, heading sizes decrease |
| 480px and below | Smaller fonts, compact navbar spacing, mobile-optimized layout |

## 📤 Deployment

### Deploy to GitHub Pages
1. **Enable GitHub Pages** in repository settings (Settings → Pages)
2. **Set source** to main branch, root directory
3. **Push changes** to main branch—site auto-deploys
4. **Access** at `https://[username].github.io`

### Custom Domain (Optional)
1. Create `CNAME` file in root with your domain
2. Configure DNS records to point to GitHub Pages

## 🛠️ Technologies Used

- **HTML5**: Semantic markup with proper meta tags
- **CSS3**: Flexbox, CSS Grid, custom properties, media queries
- **JavaScript (ES6+)**: DOM manipulation, Intersection Observer API
- **GitHub Pages**: Free hosting and deployment

## 📋 Browser Support

- Chrome/Edge (Latest)
- Firefox (Latest)
- Safari (Latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🚀 Performance Tips

- All images should be optimized (use WebP or compressed PNG/JPEG)
- Keep project descriptions concise for better mobile display
- Test animations at different scroll speeds in DevTools
- Verify responsive design at 768px and 480px breakpoints

## 💡 Common Issues & Solutions

**Smooth scroll not working?**
- Ensure `scroll-behavior: smooth` is set on `html` (styles.css, line 25)

**Animations not triggering?**
- Check IntersectionObserver threshold and rootMargin values
- Verify elements have the correct classes (`.project-card`, `.skill-category`)
- Disable browser cache in DevTools and check console for errors

**Navigation links not highlighting?**
- Confirm section IDs match anchor href values exactly
- The -200px offset accounts for sticky navbar; adjust if needed

## 📝 License

© 2026 John Doe. All rights reserved.

---

**Need help?** Review the [Copilot Instructions](.github/copilot-instructions.md) for AI-assisted development guidelines.
