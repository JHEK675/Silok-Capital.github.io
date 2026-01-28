# Copilot Instructions - Silok-Capital Portfolio

## Project Overview
This is a single-page static portfolio website deployed via GitHub Pages. The site is a modern, responsive showcase featuring smooth scroll navigation, intersection observer animations, and CSS Grid/Flexbox layouts. No build system or dependencies—pure HTML/CSS/JavaScript.

## Architecture & Key Patterns

### File Organization
- **index.html**: Single-page with semantic sections (home, about, projects, skills, contact)
- **styles.css**: Mobile-first responsive CSS using CSS custom properties (--primary-color, --secondary-color, etc.) at `:root`
- **script.js**: DOM manipulation for interactive features (smooth scroll, active nav highlighting, scroll animations)

### Color & Design System
Located in `styles.css`:
- Primary gradient: `--primary-color: #667eea` + `--secondary-color: #764ba2`
- Spacing uses consistent padding (80px for sections, 1.5rem for cards)
- All transitions use `--transition: all 0.3s ease`
- Shadows are centralized: `--shadow: 0 10px 30px rgba(0, 0, 0, 0.1)`

### Component Patterns
- **Cards** (.project-card): Hover effect uses `transform: translateY(-10px)` with shadow enhancement
- **Buttons** (.cta-btn, .contact-btn): 12px 30px padding, 50px border-radius, white/gradient backgrounds
- **Tags** (.tag): Rounded pills with 4px 12px padding, #f0f0f0 background, primary color text
- **Grids**: `grid-template-columns: repeat(auto-fit, minmax(XXXpx, 1fr))` for responsive layouts

## JavaScript Conventions

### Key Features in script.js
1. **Smooth Scroll Navigation**: Prevents default anchor behavior, uses `scrollIntoView({behavior: 'smooth'})`
2. **Active Nav Highlighting**: Intersection detection with offset (-200px) to account for sticky navbar
3. **Scroll Animations**: Uses IntersectionObserver API with threshold 0.1, animates elements from `opacity: 0; transform: translateY(20px)` → visible
4. **Target Elements**: `.project-card` and `.skill-category` are animated on scroll

### Animation Convention
All scroll-triggered animations:
- Initial state: `opacity: 0; transform: translateY(20px); transition: all 0.6s ease`
- Trigger: IntersectionObserver fires `isIntersecting` → `opacity: 1; transform: translateY(0)`

## Responsive Design Strategy
Breakpoints in `styles.css`:
- **768px**: Medium devices (nav gaps reduce, grids → single column for contact)
- **480px**: Mobile (fonts shrink, nav gaps compress)
- Use `max-width` media queries, never mobile-first overrides

## Common Tasks

### Adding a New Section
1. Add `<section id="section-name" class="section-name">` to index.html
2. Add link to navbar: `<li><a href="#section-name">Label</a></li>`
3. Create `.section-name` styles in styles.css (80px padding, centered content)
4. If animated on scroll: add `observer.observe(element)` logic to script.js for elements needing fade-in

### Updating Colors
- Change `:root` CSS variables—all components inherit automatically
- Use only `var(--primary-color)`, `var(--secondary-color)`, `var(--text-dark)`, `var(--text-light)`, `var(--bg-light)` for consistency

### Adding Interactive Features
- Use vanilla JavaScript only (no frameworks)
- Leverage `document.querySelectorAll()` + `addEventListener()`
- Always provide smooth transitions (`transition: var(--transition)`)
- Test IntersectionObserver threshold and rootMargin for correct trigger points

## Testing & Deployment
- No build step: deploy directly to GitHub Pages
- Test responsive behavior at 768px and 480px breakpoints
- Verify scroll animations in DevTools (Disable cache + slow down animations if needed)
- Check that all anchor links scroll to correct section with proper offset
