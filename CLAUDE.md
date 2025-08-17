# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based website for the AthenaK Summer School 2026, built using the Freelancer theme. The site is a static portfolio-style website designed for a physics/astronomy summer school at Penn State.

## Architecture

- **Jekyll Static Site**: Uses Jekyll 4.x with Liquid templating
- **Theme Structure**: Based on the Freelancer Bootstrap theme with modular includes
- **Layout System**: Single `default.html` layout with component includes
- **Content Structure**: Portfolio projects stored as markdown posts in `_posts/`
- **Styling**: Bootstrap + custom CSS with FontAwesome icons
- **Contact Forms**: Configurable contact system (static via formspree.io, disqus, or PHP)

## Key Components

- `_layouts/default.html`: Main page template that assembles all components
- `_includes/`: Modular components (nav, header, portfolio grid, about, contact, footer, modals)
- `_posts/`: Portfolio project entries with frontmatter metadata
- `_config.yml`: Site configuration including colors, contact settings, and social links
- `css/`, `js/`: Static assets for Bootstrap and custom styling/behavior

## Common Development Commands

### Build and Serve
```bash
# Install dependencies
bundle install

# Build the site
bundle exec jekyll build

# Serve locally with auto-rebuild
bundle exec jekyll serve

# Test the built site
rake test
```

### Testing
```bash
# Run HTML validation tests
rake test
```

The test task builds the site and runs HTMLProofer to validate links and HTML structure.

## Configuration

- Site settings in `_config.yml` control theme colors, contact form type, social links, and metadata
- Contact form behavior controlled by `contact` setting: "static" (formspree), "disqus", or default PHP
- Portfolio projects added as markdown files in `_posts/` with required frontmatter
- Color scheme customizable via hex codes in `_config.yml`

## Content Management

Portfolio projects use this frontmatter structure:
```yaml
---
layout: default
modal-id: [unique number]
date: [YYYY-MM-DD]
img: [filename in img/portfolio/]
alt: [alt text]
project-date: [display date]
client: [client name]
category: [category]
description: [project description]
---
```

## Deployment

Site is configured for GitHub Pages deployment at `https://dradice.github.io/athenak-summer-school/`.
