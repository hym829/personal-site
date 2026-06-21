# Personal Portfolio Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a cyberpunk-themed personal portfolio website with particle effects, neon glow, and smooth scroll animations.

**Architecture:** Pure static site — HTML/CSS/vanilla JS with CDN-loaded libraries. Single-page layout with 6 sections: nav, hero, about, projects, skills, contact. Deployed to GitHub Pages.

**Tech Stack:** HTML5, CSS3 (custom properties, flexbox/grid, animations), Vanilla JavaScript, Typed.js (typing effect), Particles.js (background particles), Font Awesome (icons), Google Fonts (Orbitron + Inter).

---

### Task 1: Project skeleton — index.html structure

**Files:**
- Create: `D:/workspace/projects/personal-site/index.html`

- [ ] **Step 1: Write the HTML skeleton with all 6 sections**

Create `index.html` with:
- `<head>` with meta tags, title, CSS links (Google Fonts: Orbitron + Inter, Font Awesome CDN), and `<link rel="stylesheet" href="css/style.css">`
- `<nav id="navbar">` with logo text "HYM" and links: Home, About, Projects, Skills, Contact
- `<section id="hero">` — full viewport height, contains `<h1>` with typing element `<span id="typed"></span>`, subtitle, scroll-down arrow
- `<section id="about">` — container with `<h2>About Me</h2>`, intro paragraph, social links
- `<section id="projects">` — container with `<h2>Projects</h2>`, `<div class="projects-grid">` with 4 project cards
- `<section id="skills">` — container with `<h2>Skills</h2>`, `<div class="skills-container">` with 4 skill categories
- `<section id="contact">` — container with `<h2>Contact</h2>`, email link, social icons
- `<footer>` with copyright text and back-to-top button
- Script tags at bottom: particles.js CDN, typed.js CDN, and `<script src="js/main.js"></script>`

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HYM | Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <nav id="navbar">
    <a href="#hero" class="logo">HYM</a>
    <ul class="nav-links">
      <li><a href="#hero">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="menu-toggle" aria-label="Toggle menu">
      <i class="fas fa-bars"></i>
    </button>
  </nav>

  <div id="particles-js"></div>

  <section id="hero">
    <div class="hero-content">
      <h1>Hello, I'm <span class="highlight">HYM</span></h1>
      <p><span id="typed"></span></p>
      <a href="#projects" class="cta-btn">View Projects</a>
    </div>
    <a href="#about" class="scroll-indicator">
      <i class="fas fa-chevron-down"></i>
    </a>
  </section>

  <section id="about">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      <div class="about-content">
        <p>Software developer passionate about building elegant solutions. Currently focused on full-stack development with Java and modern web technologies.</p>
        <div class="social-links">
          <a href="https://github.com/hym829" target="_blank"><i class="fab fa-github"></i></a>
          <a href="mailto:your-email@example.com"><i class="fas fa-envelope"></i></a>
        </div>
      </div>
    </div>
  </section>

  <section id="projects">
    <div class="container">
      <h2 class="section-title">Projects</h2>
      <div class="projects-grid">
        <div class="project-card">
          <div class="card-glow"></div>
          <h3>中学生体测管理系统</h3>
          <p>Spring Boot + MyBatis-Plus + 智谱AI. Full-stack student fitness test management system with AI-powered statistics and reporting.</p>
          <div class="tech-tags">
            <span>Spring Boot</span><span>MyBatis-Plus</span><span>JWT</span><span>EasyExcel</span>
          </div>
          <div class="project-links">
            <a href="https://github.com/hym829/demo" target="_blank"><i class="fab fa-github"></i> Code</a>
          </div>
        </div>
        <!-- Repeat 3 more project cards with different content -->
      </div>
    </div>
  </section>

  <section id="skills">
    <div class="container">
      <h2 class="section-title">Skills</h2>
      <div class="skills-container">
        <div class="skill-category">
          <h3><i class="fas fa-code"></i> Frontend</h3>
          <div class="skill-bar"><div class="skill-fill" data-level="80"></div><span>HTML/CSS/JS</span></div>
          <div class="skill-bar"><div class="skill-fill" data-level="60"></div><span>React</span></div>
        </div>
        <div class="skill-category">
          <h3><i class="fas fa-server"></i> Backend</h3>
          <div class="skill-bar"><div class="skill-fill" data-level="85"></div><span>Java / Spring Boot</span></div>
          <div class="skill-bar"><div class="skill-fill" data-level="70"></div><span>Python</span></div>
        </div>
        <div class="skill-category">
          <h3><i class="fas fa-database"></i> Database</h3>
          <div class="skill-bar"><div class="skill-fill" data-level="75"></div><span>MySQL</span></div>
          <div class="skill-bar"><div class="skill-fill" data-level="60"></div><span>Redis</span></div>
        </div>
        <div class="skill-category">
          <h3><i class="fas fa-tools"></i> Tools</h3>
          <div class="skill-bar"><div class="skill-fill" data-level="80"></div><span>Git</span></div>
          <div class="skill-bar"><div class="skill-fill" data-level="65"></div><span>Docker</span></div>
        </div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="container">
      <h2 class="section-title">Contact</h2>
      <p class="contact-text">Got a question or want to work together? Reach out!</p>
      <div class="contact-links">
        <a href="https://github.com/hym829" target="_blank"><i class="fab fa-github"></i> GitHub</a>
        <a href="mailto:your-email@example.com"><i class="fas fa-envelope"></i> Email</a>
      </div>
    </div>
  </section>

  <footer>
    <p>&copy; 2026 HYM. Built with code and caffeine.</p>
    <button id="back-to-top" aria-label="Back to top"><i class="fas fa-arrow-up"></i></button>
  </footer>

  <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
  <script src="js/main.js"></script>
</body>
</html>
```

- [ ] **Step 2: Verify file created**

Check that `index.html` exists with proper structure.

---

### Task 2: CSS foundation — variables, reset, navbar

**Files:**
- Create: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write CSS custom properties, reset, and base styles**

Create `css/style.css` with:

```css
/* === Custom Properties === */
:root {
  --bg-primary: #0a0a0f;
  --bg-secondary: #0d1b2a;
  --bg-card: rgba(255, 255, 255, 0.05);
  --border-card: rgba(0, 212, 255, 0.15);
  --text-primary: #e0e0e0;
  --text-secondary: #a0a0b0;
  --text-highlight: #ffffff;
  --accent-cyan: #00d4ff;
  --accent-purple: #7b2ff7;
  --accent-pink: #ff006e;
  --glow-cyan: 0 0 15px rgba(0, 212, 255, 0.4);
  --glow-purple: 0 0 15px rgba(123, 47, 247, 0.4);
  --font-heading: 'Orbitron', sans-serif;
  --font-body: 'Inter', sans-serif;
  --transition-fast: 0.2s ease;
  --transition-med: 0.4s ease;
}

/* === Reset & Base === */
*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }
body {
  font-family: var(--font-body);
  background: var(--bg-primary);
  color: var(--text-primary);
  line-height: 1.6;
  overflow-x: hidden;
}
a { color: inherit; text-decoration: none; }
ul { list-style: none; }
img { max-width: 100%; display: block; }

/* === Scrollbar === */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: var(--bg-primary); }
::-webkit-scrollbar-thumb { background: var(--accent-cyan); border-radius: 3px; }

.container { max-width: 1100px; margin: 0 auto; padding: 0 24px; }
.section-title {
  font-family: var(--font-heading);
  font-size: 2rem;
  text-align: center;
  margin-bottom: 48px;
  color: var(--text-highlight);
  position: relative;
}
.section-title::after {
  content: '';
  display: block;
  width: 60px;
  height: 2px;
  background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
  margin: 12px auto 0;
}
```

- [ ] **Step 2: Write navbar styles**

Append to `css/style.css`:

```css
/* === Navbar === */
#navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 40px;
  transition: background var(--transition-fast), box-shadow var(--transition-fast);
  background: transparent;
}
#navbar.scrolled {
  background: rgba(10, 10, 15, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 20px rgba(0, 212, 255, 0.1);
}
.logo {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--accent-cyan);
  text-shadow: var(--glow-cyan);
  transition: text-shadow var(--transition-fast);
}
.logo:hover { text-shadow: 0 0 25px rgba(0, 212, 255, 0.7); }
.nav-links { display: flex; gap: 32px; }
.nav-links a {
  font-size: 0.95rem;
  color: var(--text-secondary);
  transition: color var(--transition-fast);
  position: relative;
}
.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -4px; left: 0;
  width: 0; height: 1px;
  background: var(--accent-cyan);
  transition: width var(--transition-fast);
}
.nav-links a:hover { color: var(--accent-cyan); }
.nav-links a:hover::after { width: 100%; }
.menu-toggle {
  display: none;
  background: none;
  border: none;
  color: var(--text-primary);
  font-size: 1.5rem;
  cursor: pointer;
}
```

- [ ] **Step 3: Verify CSS compiles without errors**

Check that `css/style.css` is valid CSS.

---

### Task 3: Hero section — particles, typing, glow

**Files:**
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write hero section CSS**

Append to `css/style.css`:

```css
/* === Particles Background === */
#particles-js {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

/* === Hero Section === */
#hero {
  position: relative;
  z-index: 1;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 24px;
}
.hero-content { max-width: 700px; }
.hero-content h1 {
  font-family: var(--font-heading);
  font-size: clamp(1.8rem, 5vw, 3rem);
  margin-bottom: 16px;
  color: var(--text-highlight);
}
.highlight {
  color: var(--accent-cyan);
  text-shadow: var(--glow-cyan);
}
.hero-content p {
  font-size: clamp(1rem, 2.5vw, 1.3rem);
  color: var(--text-secondary);
  margin-bottom: 32px;
  min-height: 1.6em;
}
#typed-cursor { color: var(--accent-cyan); }
.cta-btn {
  display: inline-block;
  padding: 12px 36px;
  border: 1px solid var(--accent-cyan);
  border-radius: 4px;
  color: var(--accent-cyan);
  font-family: var(--font-heading);
  font-size: 0.9rem;
  letter-spacing: 1px;
  transition: all var(--transition-fast);
  text-shadow: var(--glow-cyan);
  box-shadow: var(--glow-cyan);
}
.cta-btn:hover {
  background: var(--accent-cyan);
  color: var(--bg-primary);
  box-shadow: 0 0 30px rgba(0, 212, 255, 0.6);
}
.scroll-indicator {
  position: absolute;
  bottom: 32px;
  left: 50%;
  transform: translateX(-50%);
  color: var(--text-secondary);
  font-size: 1.5rem;
  animation: bounce 2s infinite;
}
@keyframes bounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(10px); }
}
```

- [ ] **Step 2: Write particles.js config in main.js**

Append to `D:/workspace/projects/personal-site/js/main.js`:

```javascript
// Particles.js config
particlesJS('particles-js', {
  particles: {
    number: { value: 80, density: { enable: true, value_area: 800 } },
    color: { value: ['#00d4ff', '#7b2ff7', '#ff006e'] },
    shape: { type: 'circle' },
    opacity: { value: 0.3, random: true, anim: { enable: true, speed: 0.5, opacity_min: 0.1 } },
    size: { value: 2, random: true },
    line_linked: { enable: true, distance: 150, color: '#00d4ff', opacity: 0.15, width: 1 },
    move: { enable: true, speed: 1, direction: 'none', random: true, out_mode: 'out' }
  },
  interactivity: {
    detect_on: 'canvas',
    events: {
      onhover: { enable: true, mode: 'grab' },
      onclick: { enable: true, mode: 'push' },
      resize: true
    },
    modes: { grab: { distance: 140, line_linked: { opacity: 0.4 } }, push: { particles_nb: 3 } }
  },
  retina_detect: true
});
```

- [ ] **Step 3: Write Typed.js config in main.js**

Append to `D:/workspace/projects/personal-site/js/main.js`:

```javascript
// Typed.js config
new Typed('#typed', {
  strings: [
    'Software Developer.',
    'Full-Stack Builder.',
    'Java & Web Enthusiast.'
  ],
  typeSpeed: 50,
  backSpeed: 30,
  backDelay: 2000,
  loop: true
});
```

---

### Task 4: About section styles

**Files:**
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write about section CSS**

Append to `css/style.css`:

```css
/* === Sections Base === */
section {
  position: relative;
  z-index: 1;
  padding: 100px 0;
}

/* === About === */
#about { background: linear-gradient(180deg, transparent, rgba(13, 27, 42, 0.5), transparent); }
.about-content {
  max-width: 700px;
  margin: 0 auto;
  text-align: center;
}
.about-content p {
  font-size: 1.1rem;
  color: var(--text-secondary);
  line-height: 1.8;
  margin-bottom: 24px;
}
.social-links {
  display: flex;
  justify-content: center;
  gap: 20px;
}
.social-links a {
  font-size: 1.5rem;
  color: var(--text-secondary);
  transition: all var(--transition-fast);
}
.social-links a:hover {
  color: var(--accent-cyan);
  text-shadow: var(--glow-cyan);
  transform: translateY(-2px);
}
```

- [ ] **Step 2: Write scroll reveal animation CSS**

Append to `css/style.css`:

```css
/* === Scroll Reveal === */
.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.8s ease, transform 0.8s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
```

Then update all section containers and content divs to have class `reveal` — this is handled in Task 7 with JS.

---

### Task 5: Projects section — glass cards with glow

**Files:**
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write projects grid and card CSS**

Append to `css/style.css`:

```css
/* === Projects === */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 24px;
}
.project-card {
  position: relative;
  background: var(--bg-card);
  border: 1px solid var(--border-card);
  border-radius: 8px;
  padding: 28px;
  transition: all var(--transition-med);
  overflow: hidden;
}
.card-glow {
  position: absolute;
  inset: -1px;
  border-radius: 8px;
  opacity: 0;
  transition: opacity var(--transition-med);
  background: radial-gradient(600px circle at var(--mouse-x, 50%) var(--mouse-y, 50%), rgba(0, 212, 255, 0.15), transparent 40%);
  z-index: 0;
}
.project-card:hover .card-glow { opacity: 1; }
.project-card:hover {
  border-color: rgba(0, 212, 255, 0.4);
  transform: translateY(-4px);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
}
.project-card h3 {
  font-family: var(--font-heading);
  font-size: 1.1rem;
  color: var(--text-highlight);
  margin-bottom: 12px;
  position: relative;
  z-index: 1;
}
.project-card p {
  font-size: 0.9rem;
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 16px;
  position: relative;
  z-index: 1;
}
.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 16px;
  position: relative;
  z-index: 1;
}
.tech-tags span {
  font-size: 0.75rem;
  padding: 4px 10px;
  border: 1px solid rgba(123, 47, 247, 0.4);
  border-radius: 20px;
  color: var(--accent-purple);
  background: rgba(123, 47, 247, 0.08);
}
.project-links {
  display: flex;
  gap: 16px;
  position: relative;
  z-index: 1;
}
.project-links a {
  font-size: 0.85rem;
  color: var(--text-secondary);
  transition: color var(--transition-fast);
}
.project-links a:hover { color: var(--accent-cyan); }
```

- [ ] **Step 2: Update index.html project cards**

In `index.html`, duplicate the project card 3 more times with different content (placeholder project names/descriptions that can be updated later). Add `class="reveal"` to each `.project-card` and to the `.projects-grid`.

---

### Task 6: Skills section — animated bars

**Files:**
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write skills CSS**

Append to `css/style.css`:

```css
/* === Skills === */
.skills-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 32px;
  max-width: 900px;
  margin: 0 auto;
}
.skill-category {
  background: var(--bg-card);
  border: 1px solid var(--border-card);
  border-radius: 8px;
  padding: 24px;
  transition: border-color var(--transition-fast);
}
.skill-category:hover { border-color: rgba(0, 212, 255, 0.3); }
.skill-category h3 {
  font-family: var(--font-heading);
  font-size: 0.95rem;
  color: var(--accent-cyan);
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.skill-bar {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 14px;
  font-size: 0.85rem;
  color: var(--text-secondary);
}
.skill-bar span { flex-shrink: 0; min-width: 110px; }
.skill-fill {
  flex-grow: 1;
  height: 4px;
  background: rgba(255, 255, 255, 0.08);
  border-radius: 2px;
  overflow: hidden;
  position: relative;
}
.skill-fill::after {
  content: '';
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 0;
  background: linear-gradient(90deg, var(--accent-cyan), var(--accent-purple));
  transition: width 1.2s ease;
}
.skill-fill.animated::after {
  width: var(--level);
}
```

- [ ] **Step 2: Add skill bar fill levels**

In `index.html`, add `style="--level: 80%"` (etc.) to each `.skill-fill` element matching the `data-level` attribute.

---

### Task 7: Contact section + footer + back-to-top

**Files:**
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Write contact and footer CSS**

Append to `css/style.css`:

```css
/* === Contact === */
#contact { background: linear-gradient(180deg, transparent, rgba(13, 27, 42, 0.3), transparent); }
.contact-text {
  text-align: center;
  font-size: 1.05rem;
  color: var(--text-secondary);
  margin-bottom: 32px;
}
.contact-links {
  display: flex;
  justify-content: center;
  gap: 32px;
  flex-wrap: wrap;
}
.contact-links a {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 28px;
  border: 1px solid var(--border-card);
  border-radius: 4px;
  color: var(--text-secondary);
  transition: all var(--transition-fast);
}
.contact-links a:hover {
  border-color: var(--accent-cyan);
  color: var(--accent-cyan);
  box-shadow: var(--glow-cyan);
}

/* === Footer === */
footer {
  position: relative;
  z-index: 1;
  text-align: center;
  padding: 40px 24px;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  color: var(--text-secondary);
  font-size: 0.85rem;
}
#back-to-top {
  position: fixed;
  bottom: 32px;
  right: 32px;
  z-index: 999;
  width: 44px;
  height: 44px;
  border: 1px solid var(--border-card);
  border-radius: 50%;
  background: rgba(10, 10, 15, 0.9);
  color: var(--accent-cyan);
  font-size: 1.1rem;
  cursor: pointer;
  opacity: 0;
  visibility: hidden;
  transition: all var(--transition-fast);
  backdrop-filter: blur(6px);
}
#back-to-top.show { opacity: 1; visibility: visible; }
#back-to-top:hover {
  border-color: var(--accent-cyan);
  box-shadow: var(--glow-cyan);
}
```

---

### Task 8: JavaScript — scroll effects, reveal, mobile menu

**Files:**
- Create: `D:/workspace/projects/personal-site/js/main.js`

- [ ] **Step 1: Write main.js with all interactive behavior**

Create `js/main.js`:

```javascript
// Navbar scroll effect
const navbar = document.getElementById('navbar');
window.addEventListener('scroll', () => {
  navbar.classList.toggle('scrolled', window.scrollY > 50);
});

// Back to top button
const backToTop = document.getElementById('back-to-top');
window.addEventListener('scroll', () => {
  backToTop.classList.toggle('show', window.scrollY > 400);
});
backToTop.addEventListener('click', () => {
  window.scrollTo({ top: 0, behavior: 'smooth' });
});

// Scroll reveal
const reveals = document.querySelectorAll('.reveal');
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });
reveals.forEach(el => revealObserver.observe(el));

// Skill bars animation
const skillFills = document.querySelectorAll('.skill-fill');
const skillObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      const level = entry.target.getAttribute('data-level');
      entry.target.style.setProperty('--level', level + '%');
      entry.target.classList.add('animated');
      skillObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.5 });
skillFills.forEach(el => skillObserver.observe(el));

// Card mouse glow tracking
document.querySelectorAll('.project-card').forEach(card => {
  card.addEventListener('mousemove', (e) => {
    const rect = card.getBoundingClientRect();
    const x = ((e.clientX - rect.left) / rect.width) * 100;
    const y = ((e.clientY - rect.top) / rect.height) * 100;
    card.querySelector('.card-glow').style.setProperty('--mouse-x', x + '%');
    card.querySelector('.card-glow').style.setProperty('--mouse-y', y + '%');
  });
});

// Mobile menu toggle
const menuToggle = document.querySelector('.menu-toggle');
const navLinks = document.querySelector('.nav-links');
menuToggle.addEventListener('click', () => {
  navLinks.classList.toggle('mobile-open');
});
// Close menu on link click
navLinks.querySelectorAll('a').forEach(link => {
  link.addEventListener('click', () => navLinks.classList.remove('mobile-open'));
});

// Active nav link highlight on scroll
const sections = document.querySelectorAll('section[id]');
window.addEventListener('scroll', () => {
  const scrollY = window.scrollY + 100;
  sections.forEach(section => {
    const top = section.offsetTop;
    const height = section.offsetHeight;
    const id = section.getAttribute('id');
    const link = document.querySelector(`.nav-links a[href="#${id}"]`);
    if (link) {
      link.classList.toggle('active', scrollY >= top && scrollY < top + height);
    }
  });
});
```

- [ ] **Step 2: Add mobile menu CSS to style.css**

Append to `css/style.css`:

```css
/* === Mobile Responsive === */
@media (max-width: 768px) {
  #navbar { padding: 14px 20px; }
  .menu-toggle { display: block; }
  .nav-links {
    position: fixed;
    top: 56px; right: -100%;
    width: 200px;
    height: calc(100vh - 56px);
    background: rgba(10, 10, 15, 0.98);
    backdrop-filter: blur(10px);
    flex-direction: column;
    padding: 24px;
    gap: 20px;
    transition: right var(--transition-fast);
    border-left: 1px solid var(--border-card);
  }
  .nav-links.mobile-open { right: 0; }
  .projects-grid { grid-template-columns: 1fr; }
  .skills-container { grid-template-columns: 1fr 1fr; }
  .contact-links { flex-direction: column; align-items: center; }
  section { padding: 60px 0; }
}
@media (max-width: 480px) {
  .skills-container { grid-template-columns: 1fr; }
}
```

- [ ] **Step 3: Add reveal class to HTML sections**

In `index.html`, add `class="reveal"` to:
- `.about-content`
- `.projects-grid`
- `.skill-category` (each of the 4)
- `.contact-text` and `.contact-links`

---

### Task 9: GitHub Pages deployment

**Files:**
- New: `D:/workspace/projects/personal-site/CNAME` (optional, if custom domain)
- New: `D:/workspace/projects/personal-site/.github/workflows/deploy.yml`

- [ ] **Step 1: Create GitHub Actions workflow for GitHub Pages**

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: pages
  cancel-in-progress: false

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/upload-pages-artifact@v3
        with:
          path: .
      - id: deployment
        uses: actions/deploy-pages@v4
```

- [ ] **Step 2: Push to GitHub and enable Pages**

Commands to run:
```bash
cd D:/workspace/projects/personal-site
git add -A
git commit -m "feat: personal portfolio site - cyberpunk themed"
git branch -M main
git remote add origin https://github.com/hym829/personal-site.git
git push -u origin main
```

Then in GitHub repo settings: Settings > Pages > Source: Deploy from a branch > main / root.

---

### Task 10: Final review and polish

**Files:**
- Modify: `D:/workspace/projects/personal-site/index.html`
- Modify: `D:/workspace/projects/personal-site/css/style.css`

- [ ] **Step 1: Verify all sections present and styled**

Checklist:
- [ ] Navbar fixed, scrolls to compact state, mobile hamburger works
- [ ] Hero: particles background rendering, typed.js cycling, CTA button hover glow
- [ ] About: text centered, social icons glow on hover
- [ ] Projects: 4 cards in responsive grid, hover glow follows mouse
- [ ] Skills: 4 categories, bars animate on scroll into view
- [ ] Contact: links styled, footer visible
- [ ] Back-to-top button appears after scrolling

- [ ] **Step 2: Local test — open in browser**

Open `index.html` in browser (use file:// or a local server). Verify:
- All CDN resources load correctly
- Particles render
- Typed.js cycles through strings
- Scroll animations fire
- Mobile responsive at 768px breakpoint
- No console errors

- [ ] **Step 3: Commit and push**

```bash
git add -A
git commit -m "chore: final polish and local testing fixes"
git push
```

---

## File Summary

| File | Purpose |
|------|---------|
| `index.html` | Single-page HTML with 6 sections |
| `css/style.css` | All styles: custom properties, layout, animations, responsive |
| `js/main.js` | Particles config, Typed.js, scroll effects, mobile menu |
| `.github/workflows/deploy.yml` | GitHub Pages CI/CD |

## Key Dependencies (CDN)
- Particles.js 2.0.0
- Typed.js 2.0.12
- Font Awesome 6.5.0
- Google Fonts: Orbitron, Inter

## Design Tokens
- Background: `#0a0a0f` → `#0d1b2a` gradient
- Accent cyan: `#00d4ff`, purple: `#7b2ff7`, pink: `#ff006e`
- Glass cards: `rgba(255,255,255,0.05)` with `backdrop-filter: blur`
- Glow: `0 0 15px rgba(0,212,255,0.4)`
- Fonts: Orbitron (headings), Inter (body)
