---
layout: null
---
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Signal Security | Cyber Advisory & Risk Management</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;500;600&family=Barlow+Condensed:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --corn: #E3CC02;
    --maroon: #3B0A0F;
    --maroon-light: #5c1018;
    --maroon-dark: #220608;
    --off-white: #F0EBE0;
    --mid: #b0a98a;
    --font-display: 'Bebas Neue', sans-serif;
    --font-condensed: 'Barlow Condensed', sans-serif;
    --font-body: 'Barlow', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--maroon-dark);
    color: var(--off-white);
    font-family: var(--font-body);
    font-weight: 300;
    overflow-x: hidden;
  }

  /* ---- NOISE TEXTURE OVERLAY ---- */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.3;
  }

  /* ---- NAV ---- */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1.2rem 4rem;
    background: rgba(34, 6, 8, 0.85);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(227, 204, 2, 0.15);
  }

  .nav-logo {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    text-decoration: none;
  }

  .nav-logo-icon {
    width: 36px;
    height: 36px;
  }

  .nav-logo-text {
    font-family: var(--font-display);
    font-size: 1.6rem;
    letter-spacing: 0.1em;
    color: var(--corn);
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    list-style: none;
  }

  .nav-links a {
    text-decoration: none;
    color: var(--off-white);
    font-family: var(--font-condensed);
    font-size: 0.85rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-weight: 600;
    opacity: 0.7;
    transition: opacity 0.2s, color 0.2s;
  }

  .nav-links a:hover { opacity: 1; color: var(--corn); }

  .nav-cta {
    background: var(--corn);
    color: var(--maroon-dark) !important;
    padding: 0.5rem 1.4rem;
    opacity: 1 !important;
    transition: background 0.2s !important;
  }

  .nav-cta:hover { background: #c9b400 !important; color: var(--maroon-dark) !important; }

  /* ---- HERO ---- */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 10rem 4rem 6rem 4rem;
    position: relative;
    z-index: 2;
  }

  .hero-tag {
    font-family: var(--font-condensed);
    font-size: 0.75rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--corn);
    font-weight: 600;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .hero-tag::before {
    content: '';
    display: block;
    width: 32px;
    height: 2px;
    background: var(--corn);
  }

  .hero h1 {
    font-family: var(--font-display);
    font-size: clamp(4rem, 7vw, 7rem);
    line-height: 0.92;
    letter-spacing: 0.03em;
    color: var(--off-white);
    margin-bottom: 2rem;
  }

  .hero h1 span { color: var(--corn); }

  .hero-sub {
    font-size: 1.05rem;
    line-height: 1.7;
    color: var(--mid);
    max-width: 480px;
    margin-bottom: 3rem;
    font-weight: 400;
  }

  .hero-actions {
    display: flex;
    gap: 1rem;
    align-items: center;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--corn);
    color: var(--maroon-dark);
    padding: 0.85rem 2.2rem;
    font-family: var(--font-condensed);
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    display: inline-block;
    transition: background 0.2s, transform 0.2s;
  }

  .btn-primary:hover { background: #c9b400; transform: translateY(-2px); }

  .btn-ghost {
    color: var(--off-white);
    padding: 0.85rem 2.2rem;
    font-family: var(--font-condensed);
    font-weight: 600;
    font-size: 0.9rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    text-decoration: none;
    border: 1px solid rgba(240, 235, 224, 0.25);
    transition: border-color 0.2s, color 0.2s;
  }

  .btn-ghost:hover { border-color: var(--corn); color: var(--corn); }

  .hero-right {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
  }

  /* Animated signal/grid graphic */
  .hero-graphic {
    position: absolute;
    inset: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .signal-rings {
    position: relative;
    width: 480px;
    height: 480px;
  }

  .ring {
    position: absolute;
    border-radius: 50%;
    border: 1px solid rgba(227, 204, 2, 0.15);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    animation: pulse-ring 3s ease-out infinite;
  }

  .ring:nth-child(1) { width: 120px; height: 120px; animation-delay: 0s; border-color: rgba(227,204,2,0.5); }
  .ring:nth-child(2) { width: 220px; height: 220px; animation-delay: 0.4s; }
  .ring:nth-child(3) { width: 320px; height: 320px; animation-delay: 0.8s; }
  .ring:nth-child(4) { width: 420px; height: 420px; animation-delay: 1.2s; }
  .ring:nth-child(5) { width: 520px; height: 520px; animation-delay: 1.6s; }

  @keyframes pulse-ring {
    0% { opacity: 0; transform: translate(-50%, -50%) scale(0.9); }
    30% { opacity: 1; }
    100% { opacity: 0; transform: translate(-50%, -50%) scale(1.05); }
  }

  .center-lock {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 80px; height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
  }

  /* Grid lines fading into hero right */
  .hero-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(227,204,2,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(227,204,2,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    mask-image: radial-gradient(ellipse at center, black 20%, transparent 80%);
  }

  .hero-gradient {
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, var(--maroon-dark) 0%, var(--maroon) 60%, var(--maroon-dark) 100%);
  }

  /* ---- TICKER ---- */
  .ticker {
    background: var(--corn);
    padding: 0.6rem 0;
    overflow: hidden;
    white-space: nowrap;
  }

  .ticker-inner {
    display: inline-flex;
    gap: 4rem;
    animation: ticker 25s linear infinite;
  }

  .ticker-item {
    font-family: var(--font-condensed);
    font-weight: 700;
    font-size: 0.78rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--maroon-dark);
  }

  .ticker-dot {
    display: inline-block;
    width: 4px; height: 4px;
    background: var(--maroon);
    border-radius: 50%;
    vertical-align: middle;
    margin: 0 1rem;
  }

  @keyframes ticker { from { transform: translateX(0); } to { transform: translateX(-50%); } }

  /* ---- STATS ---- */
  .stats {
    padding: 5rem 4rem;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: rgba(227,204,2,0.1);
    border-top: 1px solid rgba(227,204,2,0.1);
    border-bottom: 1px solid rgba(227,204,2,0.1);
  }

  .stat {
    background: var(--maroon-dark);
    padding: 3rem 2.5rem;
    position: relative;
  }

  .stat::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 3px; height: 100%;
    background: var(--corn);
    opacity: 0;
    transition: opacity 0.3s;
  }

  .stat:hover::before { opacity: 1; }

  .stat-number {
    font-family: var(--font-display);
    font-size: 4rem;
    color: var(--corn);
    line-height: 1;
    margin-bottom: 0.5rem;
  }

  .stat-label {
    font-family: var(--font-condensed);
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--mid);
    font-weight: 600;
  }

  /* ---- SECTION COMMON ---- */
  section { padding: 7rem 4rem; }

  .section-tag {
    font-family: var(--font-condensed);
    font-size: 0.72rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--corn);
    font-weight: 600;
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: var(--font-display);
    font-size: clamp(2.5rem, 4vw, 4rem);
    line-height: 1;
    letter-spacing: 0.03em;
    margin-bottom: 1.5rem;
  }

  .section-body {
    font-size: 1rem;
    line-height: 1.8;
    color: var(--mid);
    max-width: 580px;
  }

  /* ---- SERVICES ---- */
  #services {
    background: var(--maroon-dark);
  }

  .services-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    margin-bottom: 4rem;
    gap: 2rem;
    flex-wrap: wrap;
  }

  .services-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1px;
    background: rgba(227,204,2,0.08);
  }

  .service-card {
    background: var(--maroon-dark);
    padding: 3rem 2.5rem;
    position: relative;
    overflow: hidden;
    transition: background 0.3s;
  }

  .service-card:hover { background: var(--maroon); }

  .service-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--corn);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }

  .service-card:hover::after { transform: scaleX(1); }

  .service-number {
    font-family: var(--font-display);
    font-size: 5rem;
    color: rgba(227,204,2,0.1);
    line-height: 1;
    margin-bottom: 1.5rem;
    transition: color 0.3s;
  }

  .service-card:hover .service-number { color: rgba(227,204,2,0.2); }

  .service-icon {
    width: 40px;
    height: 40px;
    margin-bottom: 1.5rem;
    color: var(--corn);
  }

  .service-title {
    font-family: var(--font-condensed);
    font-size: 1.3rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-bottom: 1rem;
    color: var(--off-white);
  }

  .service-desc {
    font-size: 0.9rem;
    line-height: 1.75;
    color: var(--mid);
  }

  /* ---- ABOUT ---- */
  #about {
    background: var(--maroon);
    position: relative;
    overflow: hidden;
  }

  #about::before {
    content: '';
    position: absolute;
    top: -100px; right: -100px;
    width: 500px; height: 500px;
    background: radial-gradient(circle, rgba(227,204,2,0.06) 0%, transparent 70%);
    pointer-events: none;
  }

  .about-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }

  .about-left {}

  .about-right {}

  .military-badge {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    background: rgba(227,204,2,0.08);
    border: 1px solid rgba(227,204,2,0.2);
    padding: 0.6rem 1.2rem;
    margin-bottom: 2rem;
  }

  .military-badge span {
    font-family: var(--font-condensed);
    font-size: 0.75rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--corn);
    font-weight: 600;
  }

  .founders {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    margin-top: 3rem;
  }

  .founder-card {
    display: flex;
    align-items: flex-start;
    gap: 1.2rem;
    padding: 1.5rem;
    border: 1px solid rgba(227,204,2,0.1);
    background: rgba(34,6,8,0.4);
    transition: border-color 0.3s;
  }

  .founder-card:hover { border-color: rgba(227,204,2,0.3); }

  .founder-avatar {
    width: 52px;
    height: 52px;
    background: var(--corn);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-display);
    font-size: 1.3rem;
    color: var(--maroon-dark);
    flex-shrink: 0;
  }

  .founder-info {}

  .founder-name {
    font-family: var(--font-condensed);
    font-weight: 700;
    font-size: 1.05rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--off-white);
    margin-bottom: 0.2rem;
  }

  .founder-role {
    font-size: 0.82rem;
    color: var(--corn);
    font-family: var(--font-condensed);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }

  .founder-bio {
    font-size: 0.88rem;
    line-height: 1.6;
    color: var(--mid);
  }

  .divider-line {
    width: 60px;
    height: 2px;
    background: var(--corn);
    margin: 2rem 0;
  }

  /* ---- PROCESS ---- */
  #process {
    background: var(--maroon-dark);
  }

  .process-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    margin-top: 4rem;
    position: relative;
  }

  .process-steps::before {
    content: '';
    position: absolute;
    top: 2.5rem;
    left: 10%;
    right: 10%;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--corn), transparent);
    opacity: 0.3;
  }

  .step {
    padding: 2rem;
    text-align: center;
    position: relative;
  }

  .step-num {
    width: 50px;
    height: 50px;
    background: var(--maroon);
    border: 2px solid var(--corn);
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--font-display);
    font-size: 1.4rem;
    color: var(--corn);
    margin: 0 auto 1.5rem;
    position: relative;
    z-index: 2;
  }

  .step-title {
    font-family: var(--font-condensed);
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--off-white);
    margin-bottom: 0.75rem;
  }

  .step-desc {
    font-size: 0.87rem;
    line-height: 1.7;
    color: var(--mid);
  }

  /* ---- CONTACT ---- */
  #contact {
    background: var(--maroon);
    position: relative;
    overflow: hidden;
  }

  .contact-inner {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: start;
  }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 1.2rem;
  }

  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }

  .form-group {
    display: flex;
    flex-direction: column;
    gap: 0.4rem;
  }

  label {
    font-family: var(--font-condensed);
    font-size: 0.72rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--corn);
    font-weight: 600;
  }

  input, textarea, select {
    background: rgba(34,6,8,0.6);
    border: 1px solid rgba(227,204,2,0.15);
    color: var(--off-white);
    padding: 0.85rem 1rem;
    font-family: var(--font-body);
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.2s;
    width: 100%;
  }

  input:focus, textarea:focus, select:focus {
    border-color: var(--corn);
  }

  textarea { resize: vertical; min-height: 120px; }

  select option { background: var(--maroon-dark); }

  .contact-info { padding-top: 0.5rem; }

  .contact-items { display: flex; flex-direction: column; gap: 1.5rem; margin-top: 2.5rem; }

  .contact-item {
    display: flex;
    align-items: flex-start;
    gap: 1rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid rgba(227,204,2,0.08);
  }

  .contact-item-icon {
    width: 40px;
    height: 40px;
    background: rgba(227,204,2,0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
    color: var(--corn);
  }

  .contact-item-label {
    font-family: var(--font-condensed);
    font-size: 0.7rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--corn);
    margin-bottom: 0.2rem;
  }

  .contact-item-value {
    font-size: 0.95rem;
    color: var(--off-white);
  }

  /* ---- FOOTER ---- */
  footer {
    background: var(--maroon-dark);
    padding: 3rem 4rem;
    border-top: 1px solid rgba(227,204,2,0.1);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1.5rem;
  }

  .footer-logo {
    font-family: var(--font-display);
    font-size: 1.4rem;
    letter-spacing: 0.1em;
    color: var(--corn);
  }

  .footer-copy {
    font-size: 0.8rem;
    color: var(--mid);
    font-family: var(--font-condensed);
    letter-spacing: 0.1em;
  }

  .footer-links {
    display: flex;
    gap: 2rem;
    list-style: none;
  }

  .footer-links a {
    text-decoration: none;
    color: var(--mid);
    font-family: var(--font-condensed);
    font-size: 0.8rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .footer-links a:hover { color: var(--corn); }

  /* ---- ANIMATIONS ---- */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-left > * {
    animation: fadeUp 0.8s ease forwards;
    opacity: 0;
  }

  .hero-tag { animation-delay: 0.1s; }
  .hero h1 { animation-delay: 0.25s; }
  .hero-sub { animation-delay: 0.4s; }
  .hero-actions { animation-delay: 0.55s; }

  /* ---- RESPONSIVE ---- */
  @media (max-width: 1024px) {
    nav { padding: 1rem 2rem; }
    .nav-links { gap: 1.5rem; }
    section { padding: 5rem 2rem; }
    .hero { grid-template-columns: 1fr; }
    .hero-right { display: none; }
    .hero-left { padding: 9rem 2rem 4rem; }
    .stats { grid-template-columns: repeat(2, 1fr); padding: 3rem 2rem; }
    .services-grid { grid-template-columns: 1fr; }
    .about-inner { grid-template-columns: 1fr; gap: 3rem; }
    .process-steps { grid-template-columns: repeat(2, 1fr); }
    .contact-inner { grid-template-columns: 1fr; gap: 3rem; }
    footer { padding: 2rem; }
    .form-row { grid-template-columns: 1fr; }
  }

  @media (max-width: 600px) {
    .nav-links { display: none; }
    .stats { grid-template-columns: 1fr; }
    .process-steps { grid-template-columns: 1fr; }
    .process-steps::before { display: none; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <svg class="nav-logo-icon" viewBox="0 0 36 36" fill="none">
      <circle cx="18" cy="18" r="17" stroke="#E3CC02" stroke-width="1.5"/>
      <circle cx="18" cy="18" r="11" stroke="#E3CC02" stroke-width="1" opacity="0.5"/>
      <circle cx="18" cy="18" r="5" stroke="#E3CC02" stroke-width="1" opacity="0.3"/>
      <circle cx="18" cy="18" r="2" fill="#E3CC02"/>
    </svg>
    <span class="nav-logo-text">Signal Security</span>
  </a>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#process">Process</a></li>
    <li><a href="#contact" class="nav-cta">Get in Touch</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-tag">Cyber Security Advisory &amp; Risk Management</div>
    <h1>Secure Your<br><span>Signal.</span><br>Defend Your<br>Mission.</h1>
    <p class="hero-sub">Signal Security brings military-grade discipline and deep technical expertise to corporate cyber risk. We protect what matters most: your data, your infrastructure, and your reputation.</p>
    <div class="hero-actions">
      <a href="#contact" class="btn-primary">Request a Consultation</a>
      <a href="#services" class="btn-ghost">Our Services</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-gradient"></div>
    <div class="hero-grid"></div>
    <div class="hero-graphic">
      <div class="signal-rings">
        <div class="ring"></div>
        <div class="ring"></div>
        <div class="ring"></div>
        <div class="ring"></div>
        <div class="ring"></div>
        <div class="center-lock">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none">
            <rect x="14" y="26" width="32" height="22" rx="2" stroke="#E3CC02" stroke-width="2"/>
            <path d="M20 26V20a10 10 0 0 1 20 0v6" stroke="#E3CC02" stroke-width="2"/>
            <circle cx="30" cy="37" r="3" fill="#E3CC02"/>
            <line x1="30" y1="40" x2="30" y2="44" stroke="#E3CC02" stroke-width="2"/>
          </svg>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span class="ticker-item">Risk Assessment</span><span class="ticker-dot"></span>
    <span class="ticker-item">Incident Response</span><span class="ticker-dot"></span>
    <span class="ticker-item">Compliance Advisory</span><span class="ticker-dot"></span>
    <span class="ticker-item">Penetration Testing</span><span class="ticker-dot"></span>
    <span class="ticker-item">Security Architecture</span><span class="ticker-dot"></span>
    <span class="ticker-item">NIST &amp; CMMC Frameworks</span><span class="ticker-dot"></span>
    <span class="ticker-item">Threat Intelligence</span><span class="ticker-dot"></span>
    <span class="ticker-item">Zero Trust Strategy</span><span class="ticker-dot"></span>
    <!-- duplicate for seamless loop -->
    <span class="ticker-item">Risk Assessment</span><span class="ticker-dot"></span>
    <span class="ticker-item">Incident Response</span><span class="ticker-dot"></span>
    <span class="ticker-item">Compliance Advisory</span><span class="ticker-dot"></span>
    <span class="ticker-item">Penetration Testing</span><span class="ticker-dot"></span>
    <span class="ticker-item">Security Architecture</span><span class="ticker-dot"></span>
    <span class="ticker-item">NIST &amp; CMMC Frameworks</span><span class="ticker-dot"></span>
    <span class="ticker-item">Threat Intelligence</span><span class="ticker-dot"></span>
    <span class="ticker-item">Zero Trust Strategy</span><span class="ticker-dot"></span>
  </div>
</div>

<!-- STATS -->
<div class="stats">
  <div class="stat">
    <div class="stat-number">30+</div>
    <div class="stat-label">Years Combined Experience</div>
  </div>
  <div class="stat">
    <div class="stat-number">US</div>
    <div class="stat-label">Army Veteran Founded</div>
  </div>
  <div class="stat">
    <div class="stat-number">100%</div>
    <div class="stat-label">Client Confidentiality</div>
  </div>
  <div class="stat">
    <div class="stat-number">S6</div>
    <div class="stat-label">90th Division Trained</div>
  </div>
</div>

<!-- SERVICES -->
<section id="services">
  <div class="services-header">
    <div>
      <div class="section-tag">What We Do</div>
      <h2 class="section-title">Core Services</h2>
    </div>
    <p class="section-body" style="margin:0;">Every engagement is tailored to your threat environment. We don't deliver reports that collect dust. We deliver actionable strategies grounded in real-world military and enterprise experience.</p>
  </div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-number">01</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <circle cx="20" cy="20" r="16"/>
        <path d="M20 4v4M20 32v4M4 20h4M32 20h4"/>
        <circle cx="20" cy="20" r="6"/>
        <circle cx="20" cy="20" r="2" fill="currentColor"/>
      </svg>
      <div class="service-title">Cyber Risk Assessment</div>
      <p class="service-desc">Comprehensive evaluation of your organization's security posture. We identify vulnerabilities across your infrastructure, processes, and personnel before adversaries do, and prioritize remediation by business impact.</p>
    </div>
    <div class="service-card">
      <div class="service-number">02</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <rect x="6" y="10" width="28" height="20" rx="2"/>
        <path d="M14 10V8a6 6 0 0 1 12 0v2"/>
        <circle cx="20" cy="21" r="3"/>
        <line x1="20" y1="24" x2="20" y2="27"/>
      </svg>
      <div class="service-title">Security Advisory</div>
      <p class="service-desc">Strategic guidance for executives and boards on building a resilient security culture. We translate complex threat landscapes into clear business decisions and long-term security roadmaps.</p>
    </div>
    <div class="service-card">
      <div class="service-number">03</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M20 6L6 14v10c0 8 14 12 14 12s14-4 14-12V14L20 6z"/>
        <polyline points="14,20 18,24 26,16"/>
      </svg>
      <div class="service-title">Compliance &amp; Frameworks</div>
      <p class="service-desc">NIST CSF, CMMC, SOC 2, ISO 27001, HIPAA. We guide you through complex regulatory requirements and build programs that satisfy auditors while actually improving your security outcomes.</p>
    </div>
    <div class="service-card">
      <div class="service-number">04</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <polyline points="6,30 14,18 20,24 26,14 34,10"/>
        <circle cx="34" cy="10" r="3" fill="currentColor"/>
        <line x1="6" y1="6" x2="6" y2="34"/>
        <line x1="6" y1="34" x2="34" y2="34"/>
      </svg>
      <div class="service-title">Incident Response Planning</div>
      <p class="service-desc">Build playbooks and response capabilities before a crisis hits. We develop tested incident response plans, conduct tabletop exercises, and ensure your team knows exactly what to do when seconds matter.</p>
    </div>
    <div class="service-card">
      <div class="service-number">05</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <rect x="8" y="8" width="10" height="10" rx="1"/>
        <rect x="22" y="8" width="10" height="10" rx="1"/>
        <rect x="8" y="22" width="10" height="10" rx="1"/>
        <rect x="22" y="22" width="10" height="10" rx="1"/>
        <line x1="18" y1="13" x2="22" y2="13"/>
        <line x1="18" y1="27" x2="22" y2="27"/>
        <line x1="13" y1="18" x2="13" y2="22"/>
        <line x1="27" y1="18" x2="27" y2="22"/>
      </svg>
      <div class="service-title">Security Architecture Review</div>
      <p class="service-desc">We evaluate your existing network architecture, cloud environments, and access controls against zero-trust principles, identifying gaps and recommending improvements that scale with your organization.</p>
    </div>
    <div class="service-card">
      <div class="service-number">06</div>
      <svg class="service-icon" viewBox="0 0 40 40" fill="none" stroke="currentColor" stroke-width="1.5">
        <circle cx="20" cy="14" r="5"/>
        <path d="M10 34c0-5.5 4.5-10 10-10s10 4.5 10 10"/>
        <line x1="28" y1="8" x2="34" y2="8"/>
        <line x1="28" y1="12" x2="34" y2="12"/>
        <line x1="28" y1="16" x2="34" y2="16"/>
      </svg>
      <div class="service-title">Security Awareness Training</div>
      <p class="service-desc">People remain the largest attack surface. We design and deliver tailored training programs that transform your workforce from a liability into a first line of defense through practical, scenario-based learning.</p>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-inner">
    <div class="about-left">
      <div class="section-tag">Who We Are</div>
      <h2 class="section-title">Operators Who<br>Understand Risk</h2>
      <div class="divider-line"></div>
      <p class="section-body">Signal Security was built on the principle that the best cyber defenders think like attackers and plan like soldiers. Founded by two veterans of the U.S. Army Reserve's 90th Division S6 shop, we bring a mission-first mindset to every client engagement.</p>
      <br>
      <p class="section-body">Where others deliver frameworks, we deliver outcomes. Our backgrounds in military communications and information operations give us a unique perspective on threat modeling and operational resilience that purely academic or commercial consultants simply cannot match.</p>
    </div>
    <div class="about-right">
      <div class="military-badge">
        <svg width="18" height="18" viewBox="0 0 18 18" fill="none">
          <polygon points="9,2 11,7 17,7 12,11 14,16 9,12 4,16 6,11 1,7 7,7" stroke="#E3CC02" stroke-width="1.2" fill="none"/>
        </svg>
        <span>U.S. Army Reserve Veteran-Founded Company</span>
      </div>
      <p style="font-size:0.95rem; line-height:1.8; color:var(--mid); margin-bottom:0.5rem;">90th Infantry Division &bull; S6 Communications &amp; Information Systems</p>
      <div class="founders">
        <div class="founder-card">
          <div class="founder-avatar">MS</div>
          <div class="founder-info">
            <div class="founder-name">Co-Founder</div>
            <div class="founder-role">Managing Partner &amp; Principal Advisor</div>
            <p class="founder-bio">U.S. Army Reserve veteran with S6 signals and communications experience. Brings a decade of enterprise security consulting to every client engagement, with deep expertise in risk governance and CMMC compliance.</p>
          </div>
        </div>
        <div class="founder-card">
          <div class="founder-avatar">M</div>
          <div class="founder-info">
            <div class="founder-name">Matt &mdash; Co-Founder</div>
            <div class="founder-role">Technical Director &amp; Lead Assessor</div>
            <p class="founder-bio">Fellow 90th Division S6 veteran and technical lead. Specializes in security architecture, penetration testing, and building incident response capabilities for small-to-midsize organizations across regulated industries.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROCESS -->
<section id="process">
  <div style="text-align:center; max-width:600px; margin:0 auto 1rem;">
    <div class="section-tag">How We Work</div>
    <h2 class="section-title">Our Process</h2>
    <p class="section-body" style="margin:0 auto;">Clear, disciplined, and repeatable. Every engagement follows a battle-tested approach refined over years of military and commercial practice.</p>
  </div>
  <div class="process-steps">
    <div class="step">
      <div class="step-num">01</div>
      <div class="step-title">Discovery</div>
      <p class="step-desc">We conduct deep discovery sessions to understand your business, risk tolerance, regulatory environment, and existing security posture without judgment.</p>
    </div>
    <div class="step">
      <div class="step-num">02</div>
      <div class="step-title">Assessment</div>
      <p class="step-desc">Technical and process-level evaluation of your environment. We identify gaps, prioritize threats by likelihood and business impact, and document findings clearly.</p>
    </div>
    <div class="step">
      <div class="step-num">03</div>
      <div class="step-title">Strategy</div>
      <p class="step-desc">We deliver a prioritized, actionable roadmap tailored to your budget and resources. No generic playbooks. No copy-paste recommendations.</p>
    </div>
    <div class="step">
      <div class="step-num">04</div>
      <div class="step-title">Execute &amp; Support</div>
      <p class="step-desc">We stand alongside you during implementation, validate controls, and remain available as your trusted security partner long after the engagement closes.</p>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-inner">
    <div class="contact-info">
      <div class="section-tag">Work With Us</div>
      <h2 class="section-title">Ready to<br>Strengthen<br>Your Defenses?</h2>
      <div class="divider-line"></div>
      <p class="section-body">Whether you're building a security program from the ground up or hardening an existing one, Signal Security is ready to help. Reach out and we'll respond within one business day.</p>
      <div class="contact-items">
        <div class="contact-item">
          <div class="contact-item-icon">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5">
              <path d="M4 4h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2z"/>
              <polyline points="2,6 10,12 18,6"/>
            </svg>
          </div>
          <div>
            <div class="contact-item-label">Email</div>
            <div class="contact-item-value">info@signalsecurity.com</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5">
              <path d="M15.05 5A5 5 0 0 1 19 8.95M15.05 1A9 9 0 0 1 19 12.95"/>
              <path d="M2 1l2.5 2.5-1.5 4 5 5 4-1.5L14.5 13 12 15c-3.3 0-7-2.7-9-5C1 8 1.7 4.3 2 2z"/>
            </svg>
          </div>
          <div>
            <div class="contact-item-label">Phone</div>
            <div class="contact-item-value">(555) 000-0000</div>
          </div>
        </div>
        <div class="contact-item" style="border:none;">
          <div class="contact-item-icon">
            <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5">
              <circle cx="10" cy="8" r="4"/>
              <path d="M3.5 18a7 7 0 0 1 13 0"/>
            </svg>
          </div>
          <div>
            <div class="contact-item-label">Location</div>
            <div class="contact-item-value">Serving clients nationwide</div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <form class="contact-form" onsubmit="return false;">
        <div class="form-row">
          <div class="form-group">
            <label for="fname">First Name</label>
            <input type="text" id="fname" placeholder="John">
          </div>
          <div class="form-group">
            <label for="lname">Last Name</label>
            <input type="text" id="lname" placeholder="Smith">
          </div>
        </div>
        <div class="form-group">
          <label for="email">Email Address</label>
          <input type="email" id="email" placeholder="john@company.com">
        </div>
        <div class="form-group">
          <label for="company">Company</label>
          <input type="text" id="company" placeholder="Acme Corp">
        </div>
        <div class="form-group">
          <label for="service">Service of Interest</label>
          <select id="service">
            <option value="">Select a service...</option>
            <option>Cyber Risk Assessment</option>
            <option>Security Advisory</option>
            <option>Compliance &amp; Frameworks</option>
            <option>Incident Response Planning</option>
            <option>Security Architecture Review</option>
            <option>Security Awareness Training</option>
            <option>General Inquiry</option>
          </select>
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" placeholder="Tell us about your security challenges..."></textarea>
        </div>
        <button type="submit" class="btn-primary" style="align-self:flex-start; border:none; cursor:pointer; font-size:0.9rem;">Send Message</button>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">Signal Security</div>
  <p class="footer-copy">&copy; 2025 Signal Security LLC. All rights reserved.</p>
  <ul class="footer-links">
    <li><a href="#">Privacy Policy</a></li>
    <li><a href="#">Terms</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</footer>

</body>
</html>
