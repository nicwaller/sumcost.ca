# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for SumCost.ca - a Canadian tax calculator that helps users determine the true cost of purchases including income tax, CPP, EI, and sales tax. The entire application is contained in a single HTML file with embedded CSS and JavaScript.

## Architecture

- **Single-page application**: Everything is contained in `index.html`
- **No build process**: Static HTML/CSS/JavaScript that can be served directly
- **No dependencies**: Pure vanilla JavaScript with no external libraries
- **GitHub Pages hosting**: Uses CNAME file for custom domain

## Key Components

- **Tax calculation engine**: Embedded JavaScript with Canadian federal and provincial tax brackets, CPP/EI calculations
- **Province-specific sales tax**: GST/PST/HST rates for all Canadian provinces and territories
- **URL state management**: Form state is preserved in URL hash for sharing calculations
- **Responsive design**: Mobile-optimized with appropriate input types for iOS keyboards

## Development Commands

Since this is a static site with no build process:
- **Local development**: Open `index.html` directly in browser or use any local web server
- **No testing framework**: Manual testing required
- **No linting/formatting**: Pure HTML/CSS/JS without tooling

## Social Media Assets

- `ogpreview.jpg`: Open Graph image for social media previews
- `twitter-card-image.jpg`: Twitter card image
- Both images should maintain aspect ratios when updated