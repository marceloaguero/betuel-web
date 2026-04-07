# Betuel S.A. Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a professional single-page website for Betuel S.A. deployable to Netlify at betuelsa.com.

**Architecture:** Three-file static site — `index.html` (all sections and markup), `styles.css` (all styles, mobile-first), `netlify.toml` (deploy config + security headers). No build step, no JS framework. Netlify Forms handles the contact form server-side.

**Tech Stack:** HTML5, CSS3 (custom properties), vanilla JS (< 30 lines), Google Fonts (Inter), Netlify Forms, Netlify static hosting.

---

## File Map

| File | Responsibility |
|------|---------------|
| `index.html` | All page markup: nav, hero, about, services, team, contact |
| `styles.css` | All styles: CSS variables, reset, layout, components, responsive |
| `netlify.toml` | Netlify publish dir, security response headers |

---

## Task 1: Netlify config and HTML skeleton

**Files:**
- Create: `netlify.toml`
- Modify: `index.html` (replace existing)

- [ ] **Step 1: Write `netlify.toml`**

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

- [ ] **Step 2: Replace `index.html` with the full skeleton**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Betuel S.A. — Software development and IT consulting. DevOps, Cloud Infrastructure, SRE, and Tech Leadership services for US-based clients.">
  <title>Betuel S.A. — Software Development & IT Consulting</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <!-- NAVIGATION -->
  <nav class="nav" id="nav">
    <div class="nav__inner">
      <a href="#" class="nav__logo">BETUEL <span>S.A.</span></a>
      <button class="nav__toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
      <ul class="nav__links" id="navLinks">
        <li><a href="#about">About</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#team">Team</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero" id="home">
    <div class="hero__inner">
      <p class="hero__eyebrow">Software Development &amp; IT Consulting</p>
      <h1 class="hero__headline">Engineering Solutions for<br>Modern Infrastructure</h1>
      <p class="hero__sub">DevOps &middot; Cloud &middot; SRE &middot; Leadership &middot; AI&#8209;Driven&nbsp;Operations</p>
      <a href="#contact" class="btn btn--primary">Get in Touch</a>
      <p class="hero__location">San Rafael, Mendoza, Argentina &mdash; Serving US&#8209;based clients</p>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="section" id="about">
    <div class="container">
      <p class="section__label">About Us</p>
      <h2 class="section__title">An Argentine company built for global delivery</h2>
      <p class="section__body">
        Betuel S.A. is an Argentine software development and IT consulting firm dedicated to serving international clients, primarily in the United States. We pair senior strategic leadership with a network of qualified professionals engaged for each engagement — covering analysis, design, development, and maintenance — so every project gets exactly the right expertise.
      </p>
      <div class="pills">
        <span class="pill">US&#8209;focused</span>
        <span class="pill">Cloud&#8209;native</span>
        <span class="pill">Remote&#8209;first</span>
        <span class="pill">AI&#8209;driven</span>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <section class="section section--alt" id="services">
    <div class="container">
      <p class="section__label">Services</p>
      <h2 class="section__title">Two areas of deep expertise</h2>
      <div class="cards">

        <div class="card">
          <div class="card__icon">&#9881;</div>
          <h3 class="card__title">Cloud &amp; DevOps Engineering</h3>
          <p class="card__sub">Infrastructure &amp; Site Reliability</p>
          <ul class="card__list">
            <li>Cloud infrastructure design &amp; management (AWS, GCP)</li>
            <li>CI/CD pipeline implementation &amp; optimization</li>
            <li>Monitoring, logging &amp; alerting systems</li>
            <li>Site Reliability Engineering (SRE) practices</li>
            <li>AI&#8209;assisted infrastructure &amp; operations</li>
            <li>System administration &amp; automation</li>
          </ul>
        </div>

        <div class="card">
          <div class="card__icon">&#10070;</div>
          <h3 class="card__title">Tech Leadership Consulting</h3>
          <p class="card__sub">Leadership &amp; Talent Development</p>
          <ul class="card__list">
            <li>TAS &mdash; Talent Activation System</li>
            <li>Engineering team restructuring</li>
            <li>High&#8209;performance leadership development</li>
            <li>Scaleup profitability consulting</li>
            <li>Technical talent unlocking</li>
            <li>Executive coaching for tech CEOs</li>
          </ul>
        </div>

      </div>
    </div>
  </section>

  <!-- TEAM -->
  <section class="section" id="team">
    <div class="container">
      <p class="section__label">Our Team</p>
      <h2 class="section__title">Senior leadership, qualified teams</h2>
      <div class="cards">

        <div class="card card--team">
          <div class="card__avatar">MA</div>
          <h3 class="card__name">Marcelo Aguero</h3>
          <p class="card__role">CEO &amp; DevOps Lead</p>
          <p class="card__bio">
            DevOps and SRE specialist with deep expertise in cloud infrastructure on AWS and GCP. Leverages AI tooling to drive infrastructure-as-code, CI/CD pipelines, observability stacks, and operational automation at scale.
          </p>
        </div>

        <div class="card card--team">
          <div class="card__avatar">AG</div>
          <h3 class="card__name">Aurelia Giannattasio</h3>
          <p class="card__role">Partner &amp; Tech Leadership Consultant</p>
          <p class="card__bio">
            Transforms chaotic technical operations into predictable profitability. Through her TAS (Talent Activation System) method, she activates dormant leadership potential within tech teams — helping scaleup CEOs build self-sufficient organizations that execute and grow without bottlenecking on the founder.
          </p>
        </div>

      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section section--alt" id="contact">
    <div class="container container--narrow">
      <p class="section__label">Contact</p>
      <h2 class="section__title">Let's work together</h2>
      <p class="section__body">
        Ready to modernize your infrastructure or unlock your team's leadership potential? Send us a message and we'll get back to you within one business day.
      </p>

      <form class="form" name="contact" method="POST" data-netlify="true" netlify-honeypot="bot-field">
        <input type="hidden" name="form-name" value="contact">
        <p class="form__honeypot">
          <label>Don't fill this out: <input name="bot-field"></label>
        </p>
        <div class="form__row">
          <label class="form__label" for="name">Name</label>
          <input class="form__input" type="text" id="name" name="name" required placeholder="Your name">
        </div>
        <div class="form__row">
          <label class="form__label" for="email">Email</label>
          <input class="form__input" type="email" id="email" name="email" required placeholder="your@email.com">
        </div>
        <div class="form__row">
          <label class="form__label" for="message">Message</label>
          <textarea class="form__input form__input--textarea" id="message" name="message" required placeholder="Tell us about your project or challenge..." rows="5"></textarea>
        </div>
        <button class="btn btn--primary btn--full" type="submit">Send Message</button>
      </form>

      <div class="contact-info">
        <a href="mailto:info@betuelsa.com" class="contact-info__item">info@betuelsa.com</a>
        <span class="contact-info__sep">&middot;</span>
        <span class="contact-info__item">San Rafael, Mendoza, Argentina</span>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="footer">
    <div class="container">
      <p>&copy; <span id="year"></span> Betuel S.A. All rights reserved.</p>
    </div>
  </footer>

  <script src="app.js"></script>
</body>
</html>
```

- [ ] **Step 3: Verify skeleton in browser**

Open `index.html` in a browser (File → Open, or `python3 -m http.server 8080` and visit http://localhost:8080). Expect: unstyled but complete structure, all 6 sections visible, no broken tags.

- [ ] **Step 4: Commit**

```bash
git init  # only if repo not initialized
git add index.html netlify.toml
git commit -m "feat: add HTML skeleton and Netlify config"
```

---

## Task 2: CSS foundation — variables, reset, typography

**Files:**
- Create: `styles.css`

- [ ] **Step 1: Create `styles.css` with variables and reset**

```css
/* =============================================
   CSS CUSTOM PROPERTIES
   ============================================= */
:root {
  --bg:           #0f172a;
  --surface:      #1e293b;
  --border:       #334155;
  --accent:       #6366f1;
  --accent-2:     #8b5cf6;
  --text:         #f1f5f9;
  --text-muted:   #94a3b8;
  --text-faint:   #475569;
  --gradient:     linear-gradient(135deg, #6366f1, #8b5cf6);

  --font-sans:    'Inter', system-ui, -apple-system, sans-serif;
  --font-mono:    'Courier New', Courier, monospace;

  --radius:       8px;
  --radius-sm:    4px;

  --nav-h:        64px;

  --space-xs:     0.5rem;
  --space-sm:     1rem;
  --space-md:     1.5rem;
  --space-lg:     2.5rem;
  --space-xl:     4rem;
  --space-2xl:    6rem;
}

/* =============================================
   RESET
   ============================================= */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: var(--nav-h);
}

body {
  font-family: var(--font-sans);
  background-color: var(--bg);
  color: var(--text);
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
}

img, svg { display: block; max-width: 100%; }

ul { list-style: none; }

a {
  color: inherit;
  text-decoration: none;
}

button {
  font-family: inherit;
  cursor: pointer;
  border: none;
  background: none;
}
```

- [ ] **Step 2: Reload browser**

Expect: page background is `#0f172a` (deep navy), text is light, font is Inter (or system fallback if fonts haven't loaded yet).

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add CSS custom properties and reset"
```

---

## Task 3: Navigation styles

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Append nav styles to `styles.css`**

```css
/* =============================================
   NAVIGATION
   ============================================= */
.nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  height: var(--nav-h);
  background-color: rgba(15, 23, 42, 0.95);
  border-bottom: 1px solid var(--border);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
}

.nav__inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 var(--space-md);
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav__logo {
  font-family: var(--font-mono);
  font-size: 1rem;
  font-weight: 700;
  letter-spacing: 0.15em;
  color: var(--text);
}

.nav__logo span {
  color: var(--accent);
}

.nav__links {
  display: flex;
  gap: var(--space-lg);
}

.nav__links a {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--text-muted);
  transition: color 0.2s;
}

.nav__links a:hover {
  color: var(--text);
}

/* Hamburger button — hidden on desktop */
.nav__toggle {
  display: none;
  flex-direction: column;
  gap: 5px;
  padding: 4px;
}

.nav__toggle span {
  display: block;
  width: 22px;
  height: 2px;
  background-color: var(--text);
  transition: transform 0.2s, opacity 0.2s;
  border-radius: 2px;
}

/* Mobile nav */
@media (max-width: 640px) {
  .nav__toggle {
    display: flex;
  }

  .nav__links {
    display: none;
    position: absolute;
    top: var(--nav-h);
    left: 0;
    right: 0;
    flex-direction: column;
    background-color: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: var(--space-sm) 0;
    gap: 0;
  }

  .nav__links.is-open {
    display: flex;
  }

  .nav__links a {
    display: block;
    padding: var(--space-sm) var(--space-md);
    font-size: 1rem;
  }
}
```

- [ ] **Step 2: Verify nav in browser**

Expect: fixed dark nav at top with "BETUEL S.A." logo (S.A. in indigo) and 4 nav links. On mobile width (< 640px), links are hidden and a hamburger icon appears. Clicking the hamburger does nothing yet (JS comes later).

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add navigation styles"
```

---

## Task 4: Hero section styles

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Append hero styles to `styles.css`**

```css
/* =============================================
   HERO
   ============================================= */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: calc(var(--nav-h) + var(--space-xl)) var(--space-md) var(--space-2xl);
  background: radial-gradient(ellipse at 60% 0%, rgba(99,102,241,0.12) 0%, transparent 70%),
              var(--bg);
}

.hero__inner {
  max-width: 700px;
  margin: 0 auto;
  text-align: center;
}

.hero__eyebrow {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: var(--space-md);
}

.hero__headline {
  font-size: clamp(2rem, 5vw, 3.25rem);
  font-weight: 700;
  line-height: 1.15;
  color: var(--text);
  margin-bottom: var(--space-md);
}

.hero__sub {
  font-size: clamp(0.875rem, 2vw, 1.125rem);
  color: var(--text-muted);
  margin-bottom: var(--space-lg);
  letter-spacing: 0.04em;
}

.hero__location {
  font-size: 0.8rem;
  color: var(--text-faint);
  margin-top: var(--space-md);
}

/* =============================================
   BUTTONS
   ============================================= */
.btn {
  display: inline-block;
  padding: 0.75rem 2rem;
  border-radius: var(--radius-sm);
  font-size: 0.9375rem;
  font-weight: 600;
  transition: opacity 0.2s, transform 0.2s;
}

.btn:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}

.btn--primary {
  background: var(--gradient);
  color: #fff;
}

.btn--full {
  display: block;
  width: 100%;
  text-align: center;
}
```

- [ ] **Step 2: Verify hero in browser**

Expect: full-viewport hero with subtle indigo radial glow, large headline, muted subheadline with dots, indigo gradient CTA button, and faint location text below. Content is centered.

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add hero and button styles"
```

---

## Task 5: Section layout and About styles

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Append section and about styles to `styles.css`**

```css
/* =============================================
   SHARED SECTION LAYOUT
   ============================================= */
.section {
  padding: var(--space-2xl) var(--space-md);
}

.section--alt {
  background-color: rgba(30, 41, 59, 0.4);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

.container--narrow {
  max-width: 640px;
}

.section__label {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent);
  margin-bottom: var(--space-sm);
}

.section__title {
  font-size: clamp(1.5rem, 3vw, 2.25rem);
  font-weight: 700;
  color: var(--text);
  margin-bottom: var(--space-md);
  line-height: 1.2;
}

.section__body {
  font-size: 1.0625rem;
  color: var(--text-muted);
  max-width: 680px;
  line-height: 1.75;
  margin-bottom: var(--space-lg);
}

/* =============================================
   PILLS (About highlights)
   ============================================= */
.pills {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-xs);
}

.pill {
  display: inline-block;
  padding: 0.375rem 0.875rem;
  background-color: rgba(99, 102, 241, 0.12);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 999px;
  font-size: 0.8125rem;
  font-weight: 500;
  color: var(--accent);
}
```

- [ ] **Step 2: Verify About section in browser**

Expect: About section visible below hero with indigo label, large title, body paragraph, and 4 indigo pill badges (US-focused, Cloud-native, Remote-first, AI-driven).

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add section layout, about, and pill styles"
```

---

## Task 6: Services and Team card styles

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Append card styles to `styles.css`**

```css
/* =============================================
   CARDS (Services + Team)
   ============================================= */
.cards {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-md);
}

@media (max-width: 640px) {
  .cards {
    grid-template-columns: 1fr;
  }
}

.card {
  background-color: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: var(--space-lg);
  transition: border-color 0.2s;
}

.card:hover {
  border-color: var(--accent);
}

/* Service cards */
.card__icon {
  font-size: 1.5rem;
  margin-bottom: var(--space-sm);
  color: var(--accent);
}

.card__title {
  font-size: 1.125rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.25rem;
}

.card__sub {
  font-size: 0.8125rem;
  color: var(--accent-2);
  font-weight: 500;
  margin-bottom: var(--space-md);
}

.card__list {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.card__list li {
  font-size: 0.9375rem;
  color: var(--text-muted);
  padding-left: 1rem;
  position: relative;
}

.card__list li::before {
  content: '›';
  position: absolute;
  left: 0;
  color: var(--accent);
}

/* Team cards */
.card--team {
  text-align: center;
}

.card__avatar {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: var(--gradient);
  color: #fff;
  font-weight: 700;
  font-size: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto var(--space-sm);
  letter-spacing: 0.05em;
}

.card__name {
  font-size: 1.125rem;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 0.25rem;
}

.card__role {
  font-size: 0.8125rem;
  font-weight: 500;
  color: var(--accent);
  margin-bottom: var(--space-sm);
}

.card__bio {
  font-size: 0.9375rem;
  color: var(--text-muted);
  line-height: 1.7;
}
```

- [ ] **Step 2: Verify Services and Team sections in browser**

Expect: two-column grid of cards for Services (gear icon, list items with › prefix) and Team (gradient avatar with initials, name, role, bio). Cards have subtle hover border highlight. On mobile, cards stack to single column.

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add service and team card styles"
```

---

## Task 7: Contact form and footer styles

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Append form, contact-info, and footer styles to `styles.css`**

```css
/* =============================================
   CONTACT FORM
   ============================================= */
.form {
  background-color: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: var(--space-lg);
  margin-top: var(--space-lg);
  margin-bottom: var(--space-md);
}

.form__honeypot {
  display: none;
}

.form__row {
  display: flex;
  flex-direction: column;
  gap: 0.375rem;
  margin-bottom: var(--space-sm);
}

.form__label {
  font-size: 0.8125rem;
  font-weight: 500;
  color: var(--text-muted);
}

.form__input {
  background-color: var(--bg);
  border: 1px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 0.625rem 0.875rem;
  color: var(--text);
  font-family: var(--font-sans);
  font-size: 0.9375rem;
  transition: border-color 0.2s;
  width: 100%;
}

.form__input:focus {
  outline: none;
  border-color: var(--accent);
}

.form__input::placeholder {
  color: var(--text-faint);
}

.form__input--textarea {
  resize: vertical;
  min-height: 120px;
}

/* =============================================
   CONTACT INFO (below form)
   ============================================= */
.contact-info {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-xs);
  flex-wrap: wrap;
}

.contact-info__item {
  font-size: 0.875rem;
  color: var(--text-faint);
}

a.contact-info__item:hover {
  color: var(--accent);
}

.contact-info__sep {
  color: var(--text-faint);
}

/* =============================================
   FOOTER
   ============================================= */
.footer {
  padding: var(--space-md);
  border-top: 1px solid var(--border);
  text-align: center;
}

.footer p {
  font-size: 0.8125rem;
  color: var(--text-faint);
}
```

- [ ] **Step 2: Verify Contact section and footer in browser**

Expect: Contact section with form card (dark background inputs, indigo focus ring), email and location below, and a minimal footer with border top.

- [ ] **Step 3: Commit**

```bash
git add styles.css
git commit -m "feat: add contact form and footer styles"
```

---

## Task 8: JavaScript — mobile nav toggle and year

**Files:**
- Create: `app.js`

- [ ] **Step 1: Create `app.js`**

```js
// Mobile nav toggle
const toggle = document.getElementById('navToggle');
const links  = document.getElementById('navLinks');

if (toggle && links) {
  toggle.addEventListener('click', () => {
    const open = links.classList.toggle('is-open');
    toggle.setAttribute('aria-expanded', open);
  });

  // Close nav when a link is clicked (smooth-scroll to section)
  links.querySelectorAll('a').forEach(link => {
    link.addEventListener('click', () => {
      links.classList.remove('is-open');
      toggle.setAttribute('aria-expanded', 'false');
    });
  });
}

// Footer year
const yearEl = document.getElementById('year');
if (yearEl) yearEl.textContent = new Date().getFullYear();
```

- [ ] **Step 2: Verify JS in browser**

On desktop: no visible change. On mobile width (< 640px): hamburger button toggles the nav links dropdown open/closed. Clicking a nav link closes the menu and scrolls to the section. Footer shows current year.

- [ ] **Step 3: Commit**

```bash
git add app.js
git commit -m "feat: add mobile nav toggle and footer year script"
```

---

## Task 9: Final visual QA and polish

**Files:**
- Modify: `styles.css` (append)

- [ ] **Step 1: Add scroll-activated nav shadow**

Append to `styles.css`:

```css
/* =============================================
   NAV SCROLL SHADOW (JS-driven class)
   ============================================= */
.nav.is-scrolled {
  box-shadow: 0 1px 20px rgba(0,0,0,0.4);
}
```

- [ ] **Step 2: Add scroll listener to `app.js`**

Append to `app.js`:

```js
// Nav shadow on scroll
const nav = document.getElementById('nav');
if (nav) {
  window.addEventListener('scroll', () => {
    nav.classList.toggle('is-scrolled', window.scrollY > 10);
  }, { passive: true });
}
```

- [ ] **Step 3: Visual QA checklist**

Open `index.html` in browser and verify each item:

- [ ] Nav is fixed, doesn't overlap hero content (scroll padding works)
- [ ] Hero headline renders with `clamp()` scaling at 320px, 768px, 1280px widths
- [ ] "Get in Touch" button scrolls smoothly to Contact section
- [ ] Services cards: 2-col on desktop, 1-col on mobile
- [ ] Team cards: 2-col on desktop, 1-col on mobile
- [ ] Contact form inputs are focusable, textarea is resizable
- [ ] Footer shows current year
- [ ] No horizontal scroll at any viewport width
- [ ] All text is readable (contrast > 4.5:1 — dark text on light bg and vice versa)

- [ ] **Step 4: Commit**

```bash
git add styles.css app.js
git commit -m "feat: add scroll shadow and complete visual QA"
```

---

## Task 10: Netlify deploy

**Files:**
- No code changes — deploy existing files

- [ ] **Step 1: Verify all 4 files exist**

```bash
ls -1 index.html styles.css app.js netlify.toml
```

Expected output:
```
app.js
index.html
netlify.toml
styles.css
```

- [ ] **Step 2: Push to GitHub (or drag-and-drop to Netlify)**

**Option A — GitHub-connected Netlify:**
```bash
git remote add origin https://github.com/<your-username>/betuel-web.git
git push -u origin main
```
Then in Netlify dashboard: New site → Import from Git → select repo. Build command: leave empty. Publish directory: `.`

**Option B — Netlify drag-and-drop:**
Go to app.netlify.com → drag the project folder onto the deploy zone.

- [ ] **Step 3: Configure custom domain in Netlify**

In Netlify: Site settings → Domain management → Add custom domain → `betuelsa.com`.
Follow the provided instructions to update GoDaddy DNS to point to Netlify's nameservers.

- [ ] **Step 4: Verify live site**

- Open https://betuelsa.com
- Verify all sections load
- Submit the contact form with a test message
- Check Netlify dashboard → Forms → contact → verify submission received
- Verify HTTPS is active (Let's Encrypt certificate auto-provisioned by Netlify)

---

## Self-Review

**Spec coverage:**
- ✅ Nav fixed, logo, 4 links, hamburger on mobile
- ✅ Hero: eyebrow, headline, subheadline, CTA, location
- ✅ About: company description, pills
- ✅ Services: two cards, DevOps + Leadership lists
- ✅ Team: Marcelo Aguero + Aurelia Giannattasio, avatars, bios
- ✅ Contact: Netlify Form with honeypot, email + location
- ✅ Footer with year
- ✅ Dark theme with indigo/violet palette
- ✅ Inter font via Google Fonts
- ✅ Responsive (mobile-first, 640px breakpoint)
- ✅ `netlify.toml` with security headers
- ✅ `betuelsa.com` deploy instructions

**Placeholders:** None found.

**Type consistency:** No shared types — pure HTML/CSS/JS. Class names used consistently across HTML and CSS (`.nav`, `.nav__inner`, `.nav__logo`, `.card`, `.card--team`, etc.).
