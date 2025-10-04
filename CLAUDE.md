# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

PlainAdmin is a free and open-source Vanilla JS admin dashboard template based on Bootstrap 5. It's a static frontend template with no backend framework - built with vanilla JavaScript (no jQuery), Bootstrap 5, and SCSS for styling.

## Development Commands

### Install Dependencies
```bash
yarn install
```

### Development Server
```bash
gulp
```
Runs the default Gulp task which:
- Compiles SCSS files from `assets/scss/` to `assets/css/`
- Starts BrowserSync development server on default port
- Watches for changes in HTML files and JavaScript files in `assets/js/`
- Auto-reloads browser on changes

### Manual SCSS Compilation
The SCSS files are automatically compiled by the default gulp task, but you can reference the source:
- Source SCSS: `assets/scss/main.scss` (entry point)
- Compiled CSS: `assets/css/main.css`

## Architecture

### File Structure
- **HTML Pages**: Root-level `.html` files for each page (index.html, signin.html, tables.html, etc.)
- **Styles**: `assets/scss/` contains modular SCSS organized by component/feature
- **Scripts**: `assets/js/` contains vanilla JavaScript files and third-party libraries
- **Build Tool**: `gulpfile.js` handles SCSS compilation and development server

### SCSS Architecture
The styles use a modular approach with `assets/scss/main.scss` as the entry point that imports:
- Variables and mixins (`_variables.scss`, `_mixin.scss`)
- Common/default styles (`_common.scss`, `_default.scss`)
- Component-specific styles organized in subdirectories (buttons/, cards/, forms/, etc.)
- Layout styles (sidebar, header, preloader)

### JavaScript Structure
- **main.js**: Core functionality including:
  - Preloader handling
  - Header scroll effects
  - Sidebar toggle functionality
  - Overlay interactions
- **Chart/plugin files**: Separate JS files for specific features (Chart.min.js, fullcalendar.js, jvectormap.min.js, etc.)
- **Page-specific scripts**: Inline scripts in HTML files for page-specific chart configurations and initializations

### Template Components
Each HTML page follows a consistent structure:
1. Sidebar navigation (`sidebar-nav-wrapper`)
2. Main wrapper containing:
   - Header with menu toggle, search, notifications, messages, and profile dropdown
   - Section with page content
   - Footer
3. All pages load the same CSS and core JS files, with page-specific scripts added inline

## Key Development Notes

- This is a static template with no build process beyond SCSS compilation
- All interactions are handled with vanilla JavaScript
- Bootstrap 5 components are used throughout
- Icon libraries: LineIcons and Material Design Icons
- Charts use Chart.js library
- Calendar uses FullCalendar library
- Maps use jsVectorMap library
