# Design With Vibhu - High-Performance Clean Landing Page Template

## 1. Template Overview
- **Template Name:** Design With Vibhu - Portfolio & Art Director Landing Page
- **Source File:** `designwithvibhu.com/index.html`
- **Template Purpose:** A completely self-contained, high-performance, and sequentially organized template extracted from the original `designwithvibhu.com/index.html`. All required CSS, JavaScript, fonts, vector graphics (SVG), and responsive image assets are organized cleanly without altering a single pixel of the visual UI, typography, spacing, or animation.

---

## 2. Key Code Structure & Performance Optimizations

1. **Direct Image Rendering (Zero Lag / No Blank Boxes)**:
   - Replaced all WordPress/Theme placeholder `src="data:image/svg+xml..."` dummy SVGs with the direct local image paths in `src` and `srcset`.
   - Enabled native browser `loading="lazy"` on all 20 lazyloaded images (hero graphic, portfolio works 1–8, promotional banners, e-book).
   - **Result:** Images and hero visuals appear instantaneously without waiting for JavaScript execution.

2. **Extracted Heavy Inline Styles (48% HTML Size Reduction)**:
   - Extracted 136 KB of inline Elementor styles into `assets/css/elementor/page-styles.css`.
   - Extracted 10 KB of WordPress global base styles into `assets/css/theme/wordpress-base.css`.
   - Reduced `index.html` file size from **321 KB down to 164 KB**, allowing fast DOM streaming and browser stylesheet caching.

3. **Removed Unused & Render-Blocking Overhead**:
   - Eliminated synchronous external calls to Google Tag Manager (`googletagmanager.com/gtag/js`).
   - Removed the 5-second Adobe Typekit timeout script (`liquid-typekit-js-before`) that was causing a 5000ms delay.
   - Removed WordPress internal speculation rules and dead RSS/oEmbed endpoint tags.
   - Removed Google SiteKit analytics event tracking overhead.

4. **100% Sequential Execution Pipeline**:
   - Reorganized `<head>` into 7 strict, textbook logical sections:
     - `<!-- 1. META & DOCUMENT CONFIGURATION -->` (Charset, Viewport, Compatibility, Mobile)
     - `<!-- 2. SEO & SOCIAL METADATA -->` (Title, Description, Robots, Canonical, OpenGraph, Twitter, Schema JSON-LD)
     - `<!-- 3. FAVICONS & DEVICE ICONS -->` (Theme color, Favicons 32x32, 192x192, Apple Touch Icons, Tile Image)
     - `<!-- 4. RESOURCE PRELOADS (FONTS & ASSETS) -->` (ITC Avant Garde & LQD Essentials)
     - `<!-- 5. STYLESHEETS (VENDOR, THEME, ELEMENTOR & GOOGLE FONTS) -->`
     - `<!-- 6. HEAD INLINE STYLES -->` (Liquid base inline, Lazyload fallback, Custom CSS, Dynamic theme styling)
     - `<!-- 7. HEAD SCRIPTS -->` (jQuery Core, jQuery Migrate, liquidParams global configuration)
   - Reorganized `<header>` (`#header`) into clean, modular landmarks:
     - `<!-- [A] HEADER SCOPED STYLES (ELEMENTOR TEMPLATE 18) -->` (Properly formatted & indented CSS)
     - `<!-- [B] DESKTOP NAVIGATION BAR -->`
       - 1. Site Logo Brand Container (`elementor-widget-image`)
       - 2. Primary Navigation Menu Container (`elementor-widget-ld_custom_menu` with Portfolio, Courses, About, Contact)
       - 3. Header Action / CTA Button Container (`elementor-widget-ld_button` with "New Course")
     - `<!-- [C] MOBILE NAVIGATION SECTION -->`
       - Mobile Header Bar (Navbar Toggle Button & Brand Logo)
       - Mobile Navigation Drawer / Collapsible Menu (`mobile-navbar-collapse`)
   - Reorganized body sections with clear semantic landmarks:
     - `<!-- SECTION 6.1: HERO BANNER -->`
     - `<!-- SECTION 6.2: CLIENT LOGOS & BRAND SHOWCASE -->`
     - `<!-- SECTION 6.3: SELECTED WORKS / PORTFOLIO -->`
     - `<!-- SECTION 6.4: "DESIGN LIKE A PRO" BANNER -->`
   - Grouped and sequenced footer scripts logically: **Vendor Core &rarr; Theme Core Engine &rarr; Elementor Runtime & Interactive Handlers**.

---

## 3. Folder Structure
```text
template/
│
├── index.html                                 # Clean, organized & optimized HTML (164 KB)
├── README.md                                  # Complete template documentation & instructions
└── assets/
    ├── css/                                   # 27 Total CSS Files & Skins
    │   ├── vendor/                            # bootstrap-optimize, fresco, lqd-essentials, extendify
    │   ├── theme/                             # wordpress-base, design.css, typography.css, child-hub-style, liquid-merged-styles
    │   ├── elementor/                         # page-styles.css (136 KB), frontend, widget styles, motion-fx, keyframe animations
    │   └── fresco-skins/                      # sprite.svg, sprite.png
    │
    ├── js/                                    # 31 Total JS Files (sequentially ordered execution)
    │   ├── vendor/                            # jQuery, GSAP, ScrollTrigger, FastDOM, Flickity, etc.
    │   ├── theme/                             # theme.min.js, liquid-typekit.js
    │   └── elementor/                         # webpack.runtime, frontend modules, pro frontend, handlers
    │
    ├── fonts/                                 # Custom Fonts
    │   ├── ITC-AVANT-GARDE-GOTHIC-LT-MEDIUM.woff
    │   └── lqd-essentials.woff2
    │
    ├── images/                                # 81 Total Raster Images (WebP, PNG, JPG)
    │   ├── LOGO.png, Favicon, Hero portraits, Backgrounds, Work items, Testimonials & thumbnails
    │
    └── svg/                                   # 9 Vector Assets
        ├── page-bg-5.svg, Client logos (1-6), Instagram icon
```

---

## 4. How to Run Locally

```bash
# Using Node.js
npx -y serve d:/C/Rohit/designwithvibhu.com/template -p 3000

# Using Python
cd d:/C/Rohit/designwithvibhu.com/template
python -m http.server 8000
```
Then navigate to `http://localhost:3000` (or `http://localhost:8000`) in your browser.
