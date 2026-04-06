[ABDE EL.html](https://github.com/user-attachments/files/26507756/ABDE.EL.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ABDELLAH EL BOUBKRI — Cloud & Infrastructure</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #f5f4f0;
      --surface: #eeecea;
      --border: #d8d5d0;
      --text: #1a1917;
      --muted: #7a7774;
      --accent: #2563eb;
      --accent-light: #eff4ff;
      --mono: 'DM Mono', monospace;
      --sans: 'Syne', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--sans);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.2rem 2.5rem;
      background: rgba(245, 244, 240, 0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }

    .nav-logo {
      font-family: var(--mono);
      font-size: 0.9rem;
      font-weight: 500;
      color: var(--text);
      letter-spacing: 0.05em;
    }

    .nav-logo span { color: var(--accent); }

    nav ul {
      list-style: none;
      display: flex; gap: 2rem;
    }

    nav ul a {
      font-family: var(--mono);
      font-size: 0.78rem;
      color: var(--muted);
      text-decoration: none;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    nav ul a:hover { color: var(--text); }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex; flex-direction: column; justify-content: center;
      padding: 8rem 2.5rem 4rem;
      max-width: 900px;
      margin: 0 auto;
    }

    .hero-tag {
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--accent);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.2s;
    }

    .hero h1 {
      font-size: clamp(3rem, 8vw, 6rem);
      font-weight: 800;
      line-height: 1.0;
      letter-spacing: -0.03em;
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.4s;
    }

    .hero h1 .highlight {
      color: var(--accent);
    }

    .hero-desc {
      font-family: var(--mono);
      font-size: 0.95rem;
      color: var(--muted);
      line-height: 1.8;
      max-width: 520px;
      margin-bottom: 2.5rem;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.6s;
    }

    .hero-actions {
      display: flex; gap: 1rem; flex-wrap: wrap;
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 0.8s;
    }

    .btn {
      font-family: var(--mono);
      font-size: 0.78rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 0.75rem 1.6rem;
      border-radius: 4px;
      text-decoration: none;
      transition: all 0.2s;
      cursor: pointer;
      border: none;
    }

    .btn-primary {
      background: var(--text);
      color: var(--bg);
    }

    .btn-primary:hover {
      background: var(--accent);
    }

    .btn-outline {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .btn-outline:hover {
      border-color: var(--text);
    }

    /* STATUS */
    .status-bar {
      display: flex; align-items: center; gap: 0.5rem;
      font-family: var(--mono);
      font-size: 0.75rem;
      color: var(--muted);
      margin-top: 3rem;
      padding-top: 2rem;
      border-top: 1px solid var(--border);
      opacity: 0;
      animation: fadeUp 0.6s ease forwards 1s;
    }

    .dot {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: #22c55e;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    /* SECTION */
    section {
      max-width: 900px;
      margin: 0 auto;
      padding: 5rem 2.5rem;
      border-top: 1px solid var(--border);
    }

    .section-label {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--accent);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 2.5rem;
    }

    /* SKILLS */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 8px;
      overflow: hidden;
    }

    .skill-card {
      background: var(--bg);
      padding: 1.8rem;
      transition: background 0.2s;
    }

    .skill-card:hover { background: var(--accent-light); }

    .skill-icon {
      font-size: 1.4rem;
      margin-bottom: 0.8rem;
    }

    .skill-card h3 {
      font-size: 0.95rem;
      font-weight: 700;
      margin-bottom: 0.4rem;
    }

    .skill-card p {
      font-family: var(--mono);
      font-size: 0.78rem;
      color: var(--muted);
      line-height: 1.6;
    }

    /* PROJECTS */
    .projects-list {
      display: flex; flex-direction: column; gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 8px;
      overflow: hidden;
    }

    .project-item {
      background: var(--bg);
      padding: 1.8rem 2rem;
      display: flex; align-items: center; justify-content: space-between;
      gap: 2rem;
      transition: background 0.2s;
      cursor: pointer;
    }

    .project-item:hover { background: var(--surface); }

    .project-info h3 {
      font-size: 1rem;
      font-weight: 700;
      margin-bottom: 0.3rem;
    }

    .project-info p {
      font-family: var(--mono);
      font-size: 0.78rem;
      color: var(--muted);
    }

    .project-tags {
      display: flex; gap: 0.5rem; flex-wrap: wrap;
      flex-shrink: 0;
    }

    .tag {
      font-family: var(--mono);
      font-size: 0.7rem;
      padding: 0.25rem 0.6rem;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 3px;
      color: var(--muted);
      white-space: nowrap;
    }

    /* ABOUT */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 8px;
      overflow: hidden;
    }

    .about-block {
      background: var(--bg);
      padding: 2rem;
    }

    .about-block h3 {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--accent);
      text-transform: uppercase;
      letter-spacing: 0.12em;
      margin-bottom: 0.8rem;
    }

    .about-block p {
      font-family: var(--mono);
      font-size: 0.82rem;
      color: var(--muted);
      line-height: 1.8;
    }

    /* CONTACT */
    .contact-row {
      display: flex; gap: 1rem; flex-wrap: wrap;
    }

    .contact-link {
      font-family: var(--mono);
      font-size: 0.8rem;
      color: var(--text);
      text-decoration: none;
      padding: 0.7rem 1.2rem;
      border: 1px solid var(--border);
      border-radius: 4px;
      display: flex; align-items: center; gap: 0.5rem;
      transition: all 0.2s;
    }

    .contact-link:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    /* FOOTER */
    footer {
      max-width: 900px;
      margin: 0 auto;
      padding: 2rem 2.5rem;
      border-top: 1px solid var(--border);
      display: flex; justify-content: space-between; align-items: center;
      flex-wrap: wrap; gap: 1rem;
    }

    footer p {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--muted);
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(16px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (max-width: 640px) {
      nav ul { display: none; }
      .about-grid { grid-template-columns: 1fr; }
      .project-item { flex-direction: column; align-items: flex-start; }
      footer { flex-direction: column; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo"><span>x</span>tra-crypto</div>
    <ul>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <p class="hero-tag">Cloud & Infrastructure </p>
    <h1>ABDELLAH <br/><span class="highlight">EL BOUBKRI</span></h1>
    <p class="hero-desc">
      Building scalable cloud infrastructure with Azure, Docker, and Kubernetes.<br/>
      Student @ OFPPT — Infrastructure Digitale · Cloud Computing.
    </p>
    <div class="hero-actions">
      <a href="#projects" class="btn btn-primary">View Projects</a>
      <a href="#contact" class="btn btn-outline">Get in Touch</a>
    </div>
    <div class="status-bar">
      <span class="dot"></span>
      Available for internship (PFE) · Morocco
    </div>
  </div>

  <!-- SKILLS -->
  <section id="skills">
    <p class="section-label reveal">// Skills</p>
    <div class="skills-grid reveal">
      <div class="skill-card">
        <div class="skill-icon">☁️</div>
        <h3>Microsoft Azure</h3>
        <p>VMs, VNet, NSG, App Service, Azure Functions, AKS, Key Vault, Sentinel</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🐳</div>
        <h3>Docker</h3>
        <p>Containerization, Docker Compose, ACR, ACI, multi-stage builds</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">⚙️</div>
        <h3>Kubernetes</h3>
        <p>Orchestration, Deployments, Services, AKS, scaling & monitoring</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🐧</div>
        <h3>Linux Administration</h3>
        <p>Ubuntu, bash scripting, networking, system management</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🌐</div>
        <h3>Networking</h3>
        <p>VLANs, routing, VPN, TCP/IP, subnetting, FLSM/VLSM</p>
      </div>
      <div class="skill-card">
        <div class="skill-icon">🏗️</div>
        <h3>Infrastructure as Code</h3>
        <p>Terraform on Azure, OpenStack via DevStack</p>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <p class="section-label reveal">// Projects</p>
    <div class="projects-list reveal">
      <div class="project-item">
        <div class="project-info">
          <h3>Azure Cloud Lab</h3>
          <p>VM setup, VPN Gateway Point-to-Site, Azure SQL, PHP App Service deployment</p>
        </div>
        <div class="project-tags">
          <span class="tag">Azure</span>
          <span class="tag">VPN</span>
          <span class="tag">SQL</span>
        </div>
      </div>
      <div class="project-item">
        <div class="project-info">
          <h3>Docker × Kubernetes Demo</h3>
          <p>Containerized app deployment with orchestration on AKS</p>
        </div>
        <div class="project-tags">
          <span class="tag">Docker</span>
          <span class="tag">K8s</span>
          <span class="tag">AKS</span>
        </div>
      </div>
      <div class="project-item">
        <div class="project-info">
          <h3>OpenStack Private Cloud</h3>
          <p>Private cloud setup using DevStack on Ubuntu for virtualization lab</p>
        </div>
        <div class="project-tags">
          <span class="tag">OpenStack</span>
          <span class="tag">DevStack</span>
          <span class="tag">Ubuntu</span>
        </div>
      </div>
      <div class="project-item">
        <div class="project-info">
          <h3>Network Design — Packet Tracer</h3>
          <p>Dual-LAN design with VLSM, static routing, VLANs configuration</p>
        </div>
        <div class="project-tags">
          <span class="tag">Networking</span>
          <span class="tag">VLSM</span>
          <span class="tag">Routing</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <p class="section-label reveal">// About</p>
    <div class="about-grid reveal">
      <div class="about-block">
        <h3>Background</h3>
        <p>Student at OFPPT in the Infrastructure Digitale program, specializing in Cloud Computing. Passionate about building reliable, scalable systems.</p>
      </div>
      <div class="about-block">
        <h3>Currently</h3>
        <p>Preparing for Azure certifications (AZ-900, AZ-104) and actively seeking PFE internship opportunities in cloud & infrastructure roles.</p>
      </div>
      <div class="about-block">
        <h3>Tools & Platforms</h3>
        <p>Azure Portal · Docker Desktop · VS Code · Terraform · Packet Tracer · DevStack · Ubuntu 24.04</p>
      </div>
      <div class="about-block">
        <h3>Languages</h3>
        <p>Arabic (Native) · French (Professional) · English (Technical) · Darija (Native)</p>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <p class="section-label reveal">// Contact</p>
    <div class="contact-row reveal">
      <a href="https://github.com/xtra-crypto" class="contact-link" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
        github.com/xtra-crypto
      </a>
      <a href="https://linkedin.com/in/xtra-crypto" class="contact-link" target="_blank">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a href="mailto:xtra.crypto@email.com" class="contact-link">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m22 7-10 7L2 7"/></svg>
        Email
      </a>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>© 2025   ABDELLAH EL BOUBKRI — Cloud & Infrastructure</p>
    <p>Built with HTML · Hosted on GitHub Pages</p>
  </footer>

  <script>
    // Scroll reveal
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => {
        if (e.isIntersecting) {
          e.target.classList.add('visible');
        }
      });
    }, { threshold: 0.1 });

    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));
  </script>
</body>
</html>
