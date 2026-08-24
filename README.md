# Conference Website Template

This repository contains a **Jekyll** static site template designed for academic conferences. It uses the **Chulapa** remote theme (`dieghernan/chulapa`) and is configured for **GitHub Pages** deployment.

The template is data-driven: all conference content lives in `_data/*.yml` files, while layouts, includes, and CSS handle structure and styling. This makes it easy to customize for different conferences without modifying template code.

---

## Part 1: Getting Started

### What is this template?
This is a complete, ready-to-use website template for academic conferences. It includes:

- **7 custom layouts** for different content types (programme, speakers, committee, papers, registration, etc.)
- **Data-driven architecture** — all content is in `_data/*.yml` files, not hardcoded in layouts
- **Responsive design** with mobile-first breakpoints
- **Cross-cutting components** (navbar, footer, headers) configurable via `_config.yml`
- **No build scripts required** — uses standard Jekyll/Bundler commands

The site is structured as a **conference website**, not a blog. It has no posts collection — only static pages with permalinks.

### Prerequisites

| Requirement | Version | Installation |
|------------|---------|--------------|
| Ruby | `>= 3.0` | `rbenv install 3.1.2` / `rvm install 3.1.2` |
| Jekyll | `~> 3.10` | `gem install jekyll bundler` |
| Bundler | `~> 2.6` | `gem install bundler` |

> **Note on macOS:** You may need `xcode-select --install` for build tools, and `brew install ruby` if Ruby is not present.

### Install in Local

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-org/your-conference-website.git
   cd your-conference-website
   ```

2. **Install dependencies:**
   ```bash
   bundle install
   ```

3. **Start the development server:**
   ```bash
   # Standard local development
   bundle exec jekyll serve --livereload

   # With local Chulapa gem (see Configuration below)
   bundle exec jekyll serve --config _config.dev.yml --livereload
   ```

4. **Visit** `http://localhost:4000` to see the site.

### Configuration

All site configuration lives in **`_config.yml`**. Key sections, using the config structure as example:

#### Site Metadata
```yaml
title: "Conference Name"
subtitle: "Conference Subtitle"
email: "contact@conference.org"
description: >-
  Conference description.

conference:
  name: "Conference Name"
  edition: "Edition Year"
  acronym: "CONF YEAR"
  year: 202X
  location: "City, Country"
  dates: "Month n-m, 202X"
  topic: "Conference Topic"

markdown: kramdown

remote_theme: "dieghernan/chulapa"
```

#### Navbar
```yaml
navbar:
  style: dual        # "fab", "dual", or default Bootstrap style
  brand:
    title: "Conference Name"
    img: "./assets/images/conference-logo.svg"
    url: /
  nav:
    - title: Home
      url: /
    - title: Submissions
      child:
        - title: Why Submit?
          url: /why-submit/
        - title: Paper Track
          url: /regular-paper-track/
        - title: PhD Forum
          url: /phd-forum/
    - title: Programme
      child:
        - title: Programme Overview
          url: /programme-overview/
        - title: Accepted Papers
          url: /accepted-papers/
        - title: Speakers
          url: /invited-speakers/
        - title: Social Programme
          url: /social-programme/
    - title: Organization
      child:
        - title: Chairs
          url: /chairs/
    - title: Attending
      child:
        - title: Venue & Travel
          url: /venue-and-travel/
        - title: Registration
          url: /registration/
    - title: Submission System
      url: https://cmt3.research.microsoft.com/CONF202X/
      target: _blank
```

#### Colors & Fonts
```yaml
googlefonts:
  - url: "https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;600;700&display=swap"
  - url: "https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap"
  - url: "https://fonts.googleapis.com/css2?family=Lekton:ital,wght@0,400;0,700;1,400&display=swap"

chulapa-skin:
  skin: "graymor"
  vars:
    body-color: "#000"
    body-bg: "#fff"
    footer-chulapa-bg-color: "#000"
    footer-chulapa-text-color: "#fff"
    navbar-chulapa-bg-color: "#000"
    navbar-chulapa-text-color: "#fff"
    primary: "#000"
    link-color: "#e87722"
    link-hover-color: "#e87722"
    link-decoration: "underline"
    headings-font-family: "open sans, sans-serif"
```

#### Footer
```yaml
footer:
  links:
    - label: "Bluesky"
      icon: "fab fa-bluesky"
      url: "https://bsky.app/profile/conference.bsky.social"
    - label: "LinkedIn"
      icon: "fab fa-linkedin"
      url: "https://www.linkedin.com/groups/conference/"
    - label: "Facebook"
      icon: "fab fa-facebook"
      url: "httpswww.facebook.com/conference/"
  copyright: "20XX - Conference Name"
```

#### Build Config for Localserver
The project includes **`_build_config.yml`** for building to a `localserver/` folder:

```bash
bundle exec jekyll build --config _config.yml,_build_config.yml
```

This outputs to `localserver/` with `pure_relative_paths: true`, enabling the site to work when served from arbitrary directories or opened via `file://`.

---

## Part 2: Site Structure

### Directory Overview

```
.
├── _config.yml              # Main site configuration
├── _config.dev.yml          # Dev config: uses local Chulapa gem
├── _build_config.yml        # Build config: outputs to localserver/
├── _data/                   # Data files (see below)
├── _includes/               # Reusable components (headers, footer, navbar)
├── _layouts/                # Page layouts (7 custom layouts)
├── _pages/                  # Jekyll pages collection
├── assets/
│   ├── css/custom.scss      # Design system (~1200 lines SCSS)
│   ├── images/              # Conference photos, logos, placeholders
│   ├── js/                  # lunr.js search, sidebar renderer
│   └── charts/              # Optional chart data
├── Gemfile / Gemfile.lock   # Ruby dependencies
├── 404.html                 # Custom error page
└── README.md                # This file
```

### Data Files (`_data/`)

All conference content lives in these YAML files. To update content, edit the relevant file — no layout changes needed. The field structure shown below uses the existing config as reference but is generic:

| File | Content Structure | Purpose |
|------|------------------|---------|
| `dates.yml` | Array of `{label, date, display}` | Conference deadlines and milestones |
| `speakers.yml` | Array of `{name, affiliation, photo, talk_title, talk_abstract, website}` | Invited speakers |
| `committee.yml` | Array of `{name, affiliation, photo, bio, role}` | Organizing committee |
| `papers.yml` | Array of `{title, authors, type, id}` | Accepted papers |
| `program.yml` | Day/session structure with times, types, titles | 3-day programme |
| `registration.yml` | `{early_deadline, categories[{name, early, late, note}], registration_url, includes}` | Pricing and fees |
| `social_programme.yml` | Array of `{title, date, time, venue, description, bus_info, image}` | Social events |
| `faqs.yml` | Array of `{question, answer}` | Frequently asked questions |
| `sponsors.yml` | Array of `{name, logo, url, tier}` | Sponsor organizations |

### Pages (`_pages/`)

All pages use the `_pages/` Jekyll collection with `permalink: /:path`. The 11 page types are:

| Page | Layout | Header Type | Purpose |
|------|--------|-------------|---------|
| **Home** | `default-full` | `hero` | Homepage with hero image, key data, sponsors |
| **Why Submit** | `default` | `ida` | Persuasive copy about conference submission |
| **Paper Track** | `default` | `ida` | Submission guidelines and important dates |
| **PhD Forum** | `default` | `ida` | PhD Forum description and guidelines |
| **Programme Overview** | `programme` | `ida` | Tabbed 3-day schedule |
| **Accepted Papers** | `papers` | `ida` | Paper list with search/filter |
| **Invited Speakers** | `speakers` | `ida` | Speaker cards with modal popups |
| **Social Programme** | `default-full` | `ida` | Event cards with images |
| **Chairs** | `committee` | `ida` | Committee member cards with modals |
| **Registration** | `registration-table` | `ida` | Pricing table and registration |
| **Venue & Travel** | `default` | `ida` | Venue, travel, accommodation info |

### Cross-Cutting Elements

#### Menu (Navbar)
Configure via `_config.yml` under `navbar.nav`. Supports dropdowns with `child:` nesting. Active page highlighting via URL matching. External links get a `fa-external-link-alt` icon automatically.

#### Footer
Configure via `_config.yml` under `footer.links` and `footer.copyright`. Three-column layout: "About", "Contacts" (email + social icons), logo + copyright. Social icons use Font Awesome from `site.footer.links`.

#### Headers
Each page sets `header_type` in its front matter. Six types available:

| Type | Description |
|------|-------------|
| `hero` | Full-width background image with centered title/subtitle |
| `ida` | Conference-styled header with title, subtitle |
| `splash` | Like `ida` but with dark gradient overlay |
| `hero` | Large hero banner with overlay, `display-4` heading |
| `base` | Centered text header with optional background image |
| `image` | Full-width image with text overlay below |
| `post` | Blog-post style header with image and metadata |

Set `header_white: true` for white text on dark backgrounds.

#### Favicon & Images
All favicons and the site manifest are configured in **`_includes/custom/custom_head.html`**. To replace:

1. Place new images in `assets/images/` (or update paths)
2. Edit `custom_head.html` to update `apple-touch-icon`, `favicon-32x32.png`, `favicon-16x16.png`, `site.webmanifest`, `safari-pinned-tab.svg`, `favicon.ico`, and `theme-color`

---

## Part 3: Using as a GitHub Template

### How to use this template

1. **Click "Use this template"** on GitHub to create a new repository
2. **Update conference metadata** — edit these fields in `_config.yml`:
   - `conference.name`, `conference.edition`, `conference.year`
   - `footer.copyright`: Update the year and name
   - `navbar.brand.title` and `img`: Your conference logo and title
   - Navbar links: Update URLs and titles for your page structure

3. **Update data files** in `_data/` — replace the example entries with your conference's actual data. No layout changes needed for most content updates. Key data files to populate:
   - `dates.yml` — conference deadlines
   - `speakers.yml` — invited speakers (if applicable)
   - `committee.yml` — organizing committee (if applicable)
   - `papers.yml` — accepted papers (if applicable)
   - `program.yml` — 3-day schedule (if applicable)
   - `registration.yml` — pricing and fees (if applicable)
   - `social_programme.yml` — social events (if applicable)
   - `faqs.yml` — frequently asked questions
   - `sponsors.yml` — sponsor organizations (if applicable)

4. **Customize branding**:
   - Replace `assets/images/conference-logo.svg` with your logo
   - Update Google Fonts URLs in `_config.yml` if using different fonts
   - Modify `assets/css/custom.scss` for color/design changes specific to your conference

5. **Deploy to GitHub Pages**:
   - Push to `main` branch
   - Go to **Settings → Pages** → Select branch `main` / `/(root)`
   - The site builds automatically via the `github-pages` gem (configured in `Gemfile`)

6. **For local development**:
   - Use `bundle exec jekyll serve --config _config.dev.yml --livereload`
   - This uses the local `chulapa-jekyll` gem instead of the remote theme

### Screenshots

Build the site locally first (`bundle exec jekyll serve`), then capture a screenshot, or view the live site at the GitHub Pages URL after deployment.

---

## Credits

- **Theme:** Chulapa (`dieghernan/chulapa`) — remote theme for Jekyll
- **License:** MIT (or specify your license)

---

*Conference website template. For questions or contributions, open an issue on the GitHub repository.*