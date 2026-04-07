# Betuel S.A. — Website Design Spec
**Date:** 2026-04-06
**Status:** Approved

---

## Overview

A single-page professional website for Betuel S.A., an Argentine IT consulting and software development company. Primary goal: establish a credible web presence for US bank account applications and international client engagement.

**Live domain:** betuelsa.com (GoDaddy DNS → Netlify)
**Language:** English
**Deploy target:** Netlify (static)

---

## Visual Identity

- **Style:** Dark & Technical
- **Background:** `#0f172a` (deep navy)
- **Surface/cards:** `#1e293b`
- **Borders:** `#334155`
- **Accent primary:** `#6366f1` (indigo)
- **Accent secondary:** `#8b5cf6` (violet)
- **Text primary:** `#f1f5f9`
- **Text muted:** `#94a3b8`
- **Text disabled:** `#475569`
- **Typography:** Inter (Google Fonts) for body/UI; monospace for the logo wordmark
- **Gradient CTA:** `linear-gradient(135deg, #6366f1, #8b5cf6)`

---

## Tech Stack

- Pure HTML5 + CSS3 — no JS framework, no build step
- Minimal vanilla JS: mobile nav toggle, smooth scroll
- Netlify Forms for contact form (no backend required)
- `netlify.toml` for deploy configuration
- Google Fonts (Inter) via `<link>` in `<head>`
- Fully responsive (mobile-first)

**Files:**
```
index.html        — single page, all sections
styles.css        — all styles
netlify.toml      — Netlify config
```

---

## Page Structure

### 1. Navigation (fixed top)
- Left: Logo — "BETUEL S.A." in monospace with indigo accent
- Right: Links — About · Services · Team · Contact
- Mobile: hamburger menu that toggles a dropdown
- Background: `#0f172a` with a subtle bottom border, slight blur on scroll

### 2. Hero
- Full-viewport-height section
- Eyebrow label: "SOFTWARE DEVELOPMENT & IT CONSULTING" (small caps, indigo)
- Headline: "Engineering Solutions for Modern Infrastructure"
- Subheadline: "DevOps · Cloud · SRE · Leadership · AI-Driven Operations"
- CTA button: "Get in Touch" → scrolls to contact section
- Footer line: "San Rafael, Mendoza, Argentina · Serving US-based clients"

### 3. About
- Section heading: "About Us"
- Content: Betuel S.A. is an Argentine company providing software development and IT consulting to international clients, primarily in the United States. We engage qualified professionals for each project — covering analysis, design, development, and maintenance — ensuring the right expertise for every engagement.
- Small highlight stats row: e.g., "US-focused" · "Cloud-native" · "Remote-first"

### 4. Services
- Section heading: "Services"
- Two equal-width cards side by side (stack on mobile):

**Card 1 — Infrastructure & DevOps**
- Icon: ⚙ (or SVG gear)
- Title: "Cloud & DevOps Engineering"
- Services list:
  - Cloud infrastructure design & management (AWS, GCP)
  - CI/CD pipeline implementation
  - Monitoring, logging & alerting
  - Site Reliability Engineering (SRE)
  - AI-assisted infrastructure & operations
  - System administration

**Card 2 — Tech Leadership & Talent**
- Icon: ◈ (or SVG people)
- Title: "Tech Leadership Consulting"
- Services list:
  - TAS — Talent Activation System
  - Engineering team restructuring
  - High-performance leadership development
  - Scaleup profitability consulting
  - Technical talent unlocking
  - Executive coaching for tech CEOs

### 5. Team
- Section heading: "Our Team"
- Two cards side by side (stack on mobile):

**Marcelo Aguero**
- Role: CEO & DevOps Lead
- Bio: DevOps and SRE specialist with extensive experience in cloud infrastructure on AWS and GCP. Uses AI tooling to drive infrastructure definition, CI/CD, monitoring, logging, and observability at scale.

**Aurelia Giannattasio**
- Role: Partner & Tech Leadership Consultant
- Bio: Transforms chaotic technical operations into predictable profitability. Through her TAS (Talent Activation System) method, she activates dormant leadership talent within tech teams — helping scaleup CEOs build organizations that execute without depending on them.

### 6. Contact
- Section heading: "Get in Touch"
- Subheading: "Let's work together"
- Netlify Form (attribute: `data-netlify="true"`, name: `"contact"`):
  - Name (text, required)
  - Email (email, required)
  - Message (textarea, required)
  - Submit button: "Send Message"
- Below form: `info@betuelsa.com` · San Rafael, Mendoza, Argentina

---

## Responsiveness

- Nav collapses to hamburger below 768px
- Services and Team cards stack vertically below 640px
- Hero font sizes scale down on mobile
- Minimum font size: 14px

---

## Netlify Configuration (`netlify.toml`)

```toml
[build]
  publish = "."

[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
```

---

## Out of Scope

- CMS or editable content
- Blog or articles section
- Authentication
- Analytics (can be added later with a simple script tag)
- Dark/light mode toggle
