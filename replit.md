# Portfolio Website

## Overview

This is a static portfolio website built with vanilla HTML, CSS, and JavaScript. It serves as a professional showcase for displaying projects, skills, experience, and personal information. The site features a responsive design with smooth scrolling navigation, animated elements on scroll, and a mobile-friendly hamburger menu. A simple Python HTTP server is included for local development.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Single-Page Application (SPA) Design**
- Static HTML structure with anchor-based navigation (#home, #about, #skills, #experience, #projects)
- No framework dependency - uses vanilla JavaScript for interactivity
- Rationale: Simplicity and performance for a portfolio site that doesn't require complex state management or dynamic content rendering

**Responsive Design Pattern**
- Mobile-first CSS approach using flexbox/grid layouts
- Hamburger menu for mobile navigation
- CSS custom properties (CSS variables) for consistent theming
- Pros: Easy to maintain, works across all devices, no build step required
- Cons: More manual work for complex responsive behaviors compared to CSS frameworks

**Animation and Interactivity**
- Intersection Observer API for scroll-triggered animations
- Elements fade in and slide up when entering viewport (opacity and translateY transforms)
- Smooth scroll behavior enabled via CSS
- Navbar shadow effect changes on scroll
- Rationale: Modern, performant animations without relying on external animation libraries

**Navigation System**
- Fixed position navbar that stays visible while scrolling
- Dynamic shadow effect based on scroll position
- Mobile hamburger menu toggles navigation visibility
- Auto-close menu on link click for better UX
- Alternatives considered: Sticky positioning (chosen fixed for better control)

### Styling Architecture

**CSS Variable System**
- Centralized color scheme and design tokens in `:root`
- Colors: Primary (#6366f1 indigo), Secondary (#8b5cf6 purple), neutral grays
- Reusable shadow definitions (--shadow, --shadow-lg)
- Pros: Easy theme modifications, consistent design system, no preprocessor needed
- Cons: Limited browser support for very old browsers (IE11)

**Component-Based Styling**
- Each section (hero, about, skills, etc.) has self-contained styles
- Utility classes for common patterns (container, section-title, btn)
- Transition properties defined for smooth state changes

### Development Server

**Python HTTP Server**
- Simple HTTP server running on port 5000
- Custom request handler disables caching (Cache-Control headers)
- Binds to 0.0.0.0 for accessibility in containerized environments
- Rationale: Lightweight development server with no dependencies beyond Python standard library
- Alternatives: Node.js http-server, Python's built-in module (chosen for zero npm dependencies)

## External Dependencies

### Runtime Dependencies
- **None** - The application runs entirely on vanilla web technologies (HTML5, CSS3, ES6+ JavaScript)

### Development Dependencies
- **Python 3.x** - Required to run the local development server (server.py)
- Uses only Python standard library modules (http.server, socketserver)

### Browser APIs Used
- **Intersection Observer API** - For scroll-triggered animations
- **DOM APIs** - Event listeners, classList manipulation, style modifications
- **CSS Custom Properties** - For theming and design system

### Third-Party Services
- **None currently integrated** - Portfolio is self-contained with no external API calls, analytics, or third-party scripts

### Asset Dependencies
- No external fonts (uses system font stack)
- No external CSS frameworks or icon libraries
- All styling is custom-built in styles.css
