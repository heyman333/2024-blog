# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Gatsby-based personal tech blog using the `@lekoarts/gatsby-theme-minimal-blog` theme. The blog features MDX content, TypeScript configuration, and is deployed as a static site. The site includes blog posts, an about page, and customized hero/bottom sections.

### Blog Purpose & Writing Style
This is a tech blog project focused on writing long-form content and personal thoughts about software development, technology, and career experiences. All content should be written in Korean using informal/casual tone (평어) rather than formal tone (존댓말).

## Development Commands

### Core Development
- `npm run develop` or `npm start` - Start development server at http://localhost:8000
- `npm run build` - Build production site
- `npm run serve` - Serve built site locally
- `npm run clean` - Clean Gatsby cache and build artifacts

### Special Build Commands
- `npm run develop:cypress` - Development with Cypress support enabled
- `npm run build:cypress` - Production build with Cypress support enabled

## Architecture & Key Concepts

### Gatsby Theme Structure
This project uses Gatsby theme shadowing to customize the base `@lekoarts/gatsby-theme-minimal-blog` theme:

- **Theme Shadowing**: Custom components go in `src/@lekoarts/gatsby-theme-minimal-blog/`
- **Hero Text**: Customized in `src/@lekoarts/gatsby-theme-minimal-blog/texts/hero.mdx`
- **Bottom Section**: Customized in `src/@lekoarts/gatsby-theme-minimal-blog/texts/bottom.mdx`

### Content Structure
- **Blog Posts**: Located in `content/posts/[post-name]/index.mdx`
- **Pages**: Located in `content/pages/[page-name]/index.mdx`
- **Assets**: Images and other assets are co-located with their respective content files

### Content Frontmatter
Blog posts require specific frontmatter:
```mdx
---
title: Post Title
date: YYYY-MM-DD
tags:
  - Tag1
  - Tag2
banner: ./banner.png  # Optional
description: Post description  # Optional
---
```

### Configuration
- **Site Config**: `gatsby-config.ts` contains site metadata, navigation, and plugin configuration
- **TypeScript**: Configured with `jsxImportSource: "theme-ui"` for Theme UI integration
- **Site Metadata**: Includes Korean language (`siteLanguage: 'ko'`) and custom branding

### Key Features
- MDX support for rich content
- Tag/category system
- SEO optimization with sitemap and RSS feed
- PWA manifest configuration
- Google Analytics integration via gatsby-plugin-gtag
- Bundle analysis available with `ANALYSE_BUNDLE=true`

### Customization Patterns
When modifying the blog:
1. Use theme shadowing for component customization
2. Follow existing content structure for new posts/pages
3. Maintain Korean language content style
4. Keep image assets co-located with content
5. Use TypeScript for any custom components

### Static Assets
- Favicon and PWA icons in `/static/` directory
- Banner image (`banner2.png`) used as default site image
- `robots.txt` configured for SEO