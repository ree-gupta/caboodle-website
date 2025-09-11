# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site for "Cake Caboodle" - a gourmet cake business. The website showcases the company's cakes and allows customers to order via WhatsApp. It uses the "up-business-theme" from GitLab as a submodule.

## Essential Commands

### Development
- `hugo server` - Start local development server with live reload
- `hugo server -D` - Include draft content in development server
- `hugo --buildDrafts` - Build site including draft content

### Build and Deploy
- `hugo` - Build production site (outputs to `./public/`)
- `hugo --minify` - Build minified production site (used by CI/CD)

### Content Management
- `hugo new content/post/example.md` - Create new blog post
- `hugo new content/homepage/section.md` - Create new homepage section

## Architecture

### Site Structure
- **config.yaml** - Main Hugo configuration with site settings, menus, social links
- **content/** - Markdown content files organized by section
  - `homepage/` - Homepage sections (about.md, work.md, etc.)
  - `post/` - Blog posts
  - `_index.md` - Main page content
- **data/home/** - YAML data files for homepage sections (hero.yaml, services.yaml, portfolio.yaml, testimonials.yaml, etc.)
- **themes/up-business-theme/** - Git submodule containing the theme
- **layouts/partials/** - Custom layout overrides
  - `head/` - Custom head elements
  - `shared/` - Shared components like header
- **assets/** - Site assets and images
- **static/** - Static files served directly
- **public/** - Generated site (git-ignored, auto-built)

### Theme Integration
- Uses "up-business-theme" as Git submodule from GitLab
- Theme provides business/landing page layout with sections for hero, services, portfolio, testimonials
- Custom layouts in `layouts/partials/` override theme defaults
- Site data in `data/home/` configures theme sections

### Content Model
- Homepage content is split between `content/homepage/` markdown files and `data/home/` YAML files
- Blog posts go in `content/post/` with front matter for metadata
- Navigation menus configured in config.yaml under `menus` section
- Social media links and contact info in config.yaml `params` section

## Deployment

### GitHub Actions
- Automatic deployment to GitHub Pages via `.github/workflows/hugo.yml`
- Uses Hugo v0.123.7 extended version
- Builds on push to main branch
- Includes git submodule checkout for theme

### Domain Configuration
- Custom domain: cakecaboodle.in (configured in CNAME file)
- Base URL set to https://cakecaboodle.in/ in config.yaml

## Common Tasks

### Updating Content
- Modify YAML files in `data/home/` to update homepage sections
- Edit `config.yaml` to change site-wide settings, menus, contact info
- Add new blog posts in `content/post/` directory

### Theme Updates
- Theme is a git submodule, update with: `git submodule update --remote themes/up-business-theme`
- Always test locally after theme updates

### Asset Management
- Logo and images go in `assets/images/`
- Hugo processes and optimizes images automatically
- Generated image resources appear in `resources/_gen/images/`

## Key Files to Know

- **config.yaml**: Site configuration, menus, social links, business info
- **data/home/hero.yaml**: Homepage hero section with main messaging
- **data/home/services.yaml**: Services/offerings section
- **data/home/portfolio.yaml**: Product showcase/gallery
- **layouts/partials/shared/header.html**: Custom header layout
- **.github/workflows/hugo.yml**: CI/CD pipeline configuration