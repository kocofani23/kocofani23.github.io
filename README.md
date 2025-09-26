<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Koço Fani | Software Developer</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #2563eb;
      --primary-dark: #1d4ed8;
      --secondary: #7c3aed;
      --accent: #06b6d4;
      --text: #1e293b;
      --text-light: #64748b;
      --bg: #ffffff;
      --bg-alt: #f8fafc;
      --card-bg: #ffffff;
      --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
      --radius: 12px;
      --transition: all 0.3s ease;
    }
    .dark-mode {
      --primary: #3b82f6;
      --primary-dark: #2563eb;
      --secondary: #a855f7;
      --accent: #06b6d4;
      --text: #f1f5f9;
      --text-light: #cbd5e1;
      --bg: #0f172a;
      --bg-alt: #1e293b;
      --card-bg: #1e293b;
      --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.3), 0 2px 4px -1px rgba(0, 0, 0, 0.2);
      --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.3), 0 4px 6px -2px rgba(0, 0, 0, 0.2);
    }
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    html {
      scroll-behavior: smooth;
    }
    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg);
      color: var(--text);
      line-height: 1.6;
      transition: var(--transition);
      overflow-x: hidden;
    }
    /* Header & Navigation */
    header {
      position: fixed;
      top: 0;
      width: 100%;
      background-color: rgba(255, 255, 255, 0.9);
      backdrop-filter: blur(10px);
      z-index: 1000;
      transition: var(--transition);
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
    }
    .dark-mode header {
      background-color: rgba(15, 23, 42, 0.9);
    }
    .nav-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 70px;
    }
    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--primary);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    .logo span {
      color: var(--text);
    }
    .dark-mode .logo span {
      color: var(--text);
    }
    .nav-links {
      display: flex;
      gap: 2rem;
    }
    .nav-links a {
      color: var(--text);
      text-decoration: none;
      font-weight: 500;
      position: relative;
      transition: var(--transition);
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -5px;
      left: 0;
      width: 0;
      height: 2px;
      background-color: var(--primary);
      transition: var(--transition);
    }
    .nav-links a:hover::after {
      width: 100%;
    }
    .nav-links a:hover {
      color: var(--primary);
    }
    .nav-controls {
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .theme-toggle {
      background: none;
      border: none;
      color: var(--text);
      cursor: pointer;
      font-size: 1.2rem;
      transition: var(--transition);
    }
    .theme-toggle:hover {
      color: var(--primary);
    }
    .mobile-menu-btn {
      display: none;
      background: none;
      border: none;
      color: var(--text);
      font-size: 1.5rem;
      cursor: pointer;
    }
    /* Hero Section */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 0 2rem;
      background: linear-gradient(135deg, var(--bg) 0%, var(--bg-alt) 100%);
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      top: -50%;
      right: -20%;
      width: 500px;
      height: 500px;
      border-radius: 50%;
      background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
      opacity: 0.1;
      z-index: 0;
    }
    .hero-content {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
      position: relative;
      z-index: 1;
    }
    .hero-text h1 {
      font-size: 3.5rem;
      font-weight: 700;
      line-height: 1.2;
      margin-bottom: 1.5rem;
    }
    .hero-text h1 span {
      color: var(--primary);
    }
    .hero-text p {
      font-size: 1.2rem;
      color: var(--text-light);
      margin-bottom: 2rem;
      max-width: 500px;
    }
    .cta-buttons {
      display: flex;
      gap: 1rem;
    }
    .btn {
      padding: 0.8rem 1.5rem;
      border-radius: var(--radius);
      font-weight: 600;
      text-decoration: none;
      transition: var(--transition);
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
    }
    .btn-primary {
      background-color: var(--primary);
      color: white;
    }
    .btn-primary:hover {
      background-color: var(--primary-dark);
      transform: translateY(-2px);
      box-shadow: var(--shadow-lg);
    }
    .btn-secondary {
      background-color: transparent;
      color: var(--text);
      border: 1px solid var(--text-light);
    }
    .btn-secondary:hover {
      border-color: var(--primary);
      color: var(--primary);
      transform: translateY(-2px);
    }
    .hero-image {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .profile-container {
      width: 350px;
      height: 350px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      animation: float 6s ease-in-out infinite;
    }
    .profile-image {
  width: 330px;
  height: 330px;
  border-radius: 50%;
  overflow: hidden; /* Ensure image is clipped in circle */
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--bg-alt);
}
.profile-image img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Makes image cover the circle without distortion */
  display: block;
}
    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-20px); }
      100% { transform: translateY(0px); }
    }
    /* Sections */
    section {
      padding: 6rem 2rem;
    }
    .section-title {
      text-align: center;
      font-size: 2.5rem;
      font-weight: 700;
      margin-bottom: 3rem;
      position: relative;
    }
    .section-title::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 4px;
      background: linear-gradient(to right, var(--primary), var(--secondary));
      border-radius: 2px;
    }
    /* About Section */
    .about {
      background-color: var(--bg-alt);
    }
    .about-content {
      max-width: 1000px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
    }
    .about-text p {
      margin-bottom: 1.5rem;
      color: var(--text-light);
    }
    .quote-box {
      background-color: var(--card-bg);
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      border-left: 4px solid var(--primary);
      margin-top: 2rem;
    }
    .quote-box p {
      font-style: italic;
      color: var(--text);
      margin-bottom: 1rem;
    }
    .quote-author {
      text-align: right;
      font-weight: 600;
      color: var(--primary);
    }
    .skills-highlights {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
    }
    .skill-item {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      margin-bottom: 1rem;
    }
    .skill-icon {
      width: 40px;
      height: 40px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
    }
    /* Projects Section */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
      gap: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    .project-card {
      background-color: var(--card-bg);
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow);
      transition: var(--transition);
    }
    .project-card:hover {
      transform: translateY(-10px);
      box-shadow: var(--shadow-lg);
    }
    .project-image {
      height: 200px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 3rem;
    }
    .project-content {
      padding: 1.5rem;
    }
    .project-content h3 {
      font-size: 1.3rem;
      margin-bottom: 0.5rem;
    }
    .project-content p {
      color: var(--text-light);
      margin-bottom: 1.5rem;
    }
    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 1.5rem;
    }
    .tag {
      background-color: var(--bg-alt);
      color: var(--text);
      padding: 0.3rem 0.8rem;
      border-radius: 20px;
      font-size: 0.8rem;
      font-weight: 500;
    }
    .project-links {
      display: flex;
      gap: 1rem;
    }
    .project-link {
      color: var(--primary);
      text-decoration: none;
      font-weight: 500;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      transition: var(--transition);
    }
    .project-link:hover {
      color: var(--secondary);
    }
    /* Skills Section */
    .skills {
      background-color: var(--bg-alt);
    }
    .skills-container {
      max-width: 1000px;
      margin: 0 auto;
    }
    .skills-categories {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
    }
    .skill-category {
      background-color: var(--card-bg);
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }
    .skill-category h3 {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      margin-bottom: 1.5rem;
      font-size: 1.2rem;
    }
    .skill-category h3 i {
      color: var(--primary);
    }
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
    }
    .skill {
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }
    .skill-icon-small {
      width: 30px;
      height: 30px;
      background-color: var(--bg-alt);
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--primary);
    }
    /* Fun Section */
    .hobbies-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 2rem;
      max-width: 1000px;
      margin: 0 auto;
    }
    .hobby-card {
      background-color: var(--card-bg);
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      text-align: center;
      transition: var(--transition);
    }
    .hobby-card:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow-lg);
    }
    .hobby-icon {
      width: 70px;
      height: 70px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1.5rem;
      color: white;
      font-size: 1.8rem;
    }
    .hobby-card h3 {
      margin-bottom: 1rem;
    }
    .hobby-card p {
      color: var(--text-light);
    }
    /* Contact Section */
    .contact {
      background-color: var(--bg-alt);
    }
    .contact-container {
      max-width: 1000px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
    }
    .contact-info h3 {
      margin-bottom: 1.5rem;
      font-size: 1.5rem;
    }
    .contact-details {
      display: flex;
      flex-direction: column;
      gap: 1.5rem;
    }
    .contact-item {
      display: flex;
      align-items: center;
      gap: 1rem;
    }
    .contact-icon {
      width: 50px;
      height: 50px;
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 1.2rem;
    }
    .contact-text h4 {
      margin-bottom: 0.3rem;
    }
    .contact-text p, .contact-text a {
      color: var(--text-light);
      text-decoration: none;
      transition: var(--transition);
    }
    .contact-text a:hover {
      color: var(--primary);
    }
    .social-links {
      display: flex;
      gap: 1rem;
      margin-top: 2rem;
    }
    .social-link {
      width: 40px;
      height: 40px;
      background-color: var(--card-bg);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text);
      transition: var(--transition);
    }
    .social-link:hover {
      background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
      color: white;
      transform: translateY(-3px);
    }
    .contact-form {
      background-color: var(--card-bg);
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }
    .form-group {
      margin-bottom: 1.5rem;
    }
    .form-group label {
      display: block;
      margin-bottom: 0.5rem;
      font-weight: 500;
    }
    .form-control {
      width: 100%;
      padding: 0.8rem 1rem;
      border: 1px solid var(--text-light);
      border-radius: var(--radius);
      background-color: var(--bg);
      color: var(--text);
      transition: var(--transition);
    }
    .form-control:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
    }
    textarea.form-control {
      min-height: 150px;
      resize: vertical;
    }
    /* Footer */
    footer {
      background-color: var(--card-bg);
      padding: 3rem 2rem;
      text-align: center;
    }
    .footer-content {
      max-width: 1200px;
      margin: 0 auto;
    }
    .footer-logo {
      font-size: 1.8rem;
      font-weight: 700;
      color: var(--primary);
      margin-bottom: 1rem;
      display: inline-block;
    }
    .footer-links {
      display: flex;
      justify-content: center;
      gap: 2rem;
      margin-bottom: 2rem;
    }
    .footer-links a {
      color: var(--text-light);
      text-decoration: none;
      transition: var(--transition);
    }
    .footer-links a:hover {
      color: var(--primary);
    }
    .copyright {
      color: var(--text-light);
      font-size: 0.9rem;
    }
    /* Responsive Design */
    @media (max-width: 992px) {
      .hero-content {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .hero-text p {
        margin: 0 auto 2rem;
      }
      .cta-buttons {
        justify-content: center;
      }
      .about-content {
        grid-template-columns: 1fr;
      }
      .contact-container {
        grid-template-columns: 1fr;
      }
    }
    @media (max-width: 768px) {
      .nav-links {
        display: none;
      }
      .mobile-menu-btn {
        display: block;
      }
      .hero-text h1 {
        font-size: 2.5rem;
      }
      .profile-container {
        width: 280px;
        height: 280px;
      }
      .profile-image {
        width: 260px;
        height: 260px;
        font-size: 6rem;
      }
      .section-title {
        font-size: 2rem;
      }
      .projects-grid {
        grid-template-columns: 1fr;
      }
      .skills-categories {
        grid-template-columns: 1fr;
      }
      .hobbies-grid {
        grid-template-columns: 1fr;
      }
      .footer-links {
        flex-direction: column;
        gap: 1rem;
      }
    }
    /* Mobile Menu */
    .mobile-menu {
      position: fixed;
      top: 70px;
      left: 0;
      width: 100%;
      height: calc(100vh - 70px);
      background-color: var(--bg);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      padding-top: 2rem;
      transform: translateX(-100%);
      transition: var(--transition);
      z-index: 999;
    }
    .mobile-menu.active {
      transform: translateX(0);
    }
    .mobile-menu a {
      color: var(--text);
      text-decoration: none;
      font-size: 1.2rem;
      margin: 1rem 0;
      padding: 0.5rem 1rem;
      transition: var(--transition);
    }
    .mobile-menu a:hover {
      color: var(--primary);
    }
  </style>
</head>
<body>
  <!-- Header & Navigation -->
  <header>
    <div class="nav-container">
      <a href="#" class="logo">
        <i class="fas fa-code"></i>
        <span>Koço Fani</span>
      </a>
      <nav class="nav-links">
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#skills">Skills</a>
        <a href="#fun">Hobbies</a>
        <a href="#contact">Contact</a>
      </nav>
      <div class="nav-controls">
        <button class="theme-toggle" id="themeToggle">
          <i class="fas fa-moon"></i>
        </button>
        <button class="mobile-menu-btn" id="mobileMenuBtn">
          <i class="fas fa-bars"></i>
        </button>
      </div>
    </div>
    <div class="mobile-menu" id="mobileMenu">
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#fun">Hobbies</a>
      <a href="#contact">Contact</a>
    </div>
  </header>
  <!-- Hero Section -->
<section class="hero">
  <div class="hero-content">
    <div class="hero-text">
      <h1>Hi, I'm <span>Koço Fani</span></h1>
      <p>A passionate Computer Engineering student specializing in software development, databases, and mobile applications. I love building efficient systems that solve real-world problems.</p>
      <div class="cta-buttons">
        <a href="#projects" class="btn btn-primary">
          <i class="fas fa-rocket"></i> View My Work
        </a>
        <a href="#contact" class="btn btn-secondary">
          <i class="fas fa-envelope"></i> Get In Touch
        </a>
      </div>
    </div>
    <div class="hero-image">
      <div class="profile-container">
        <div class="profile-image">
          <!-- Replace src with your profile picture URL -->
          <img src="profile.jpg" alt="Koço Fani" />
        </div>
      </div>
    </div>
  </div> <!-- .hero-content -->
</section> <!-- .hero -->

    </div>
  </section>

  
<!-- About Section -->
<section id="about" class="about">
  <h2 class="section-title">About Me</h2>
  <div class="about-content">
    <div class="about-text">
      <p>I'm a Computer Engineering student with a strong passion for software development, databases, and mobile applications. I enjoy solving real-world problems with code, building efficient systems, and learning new technologies.</p>
      <p>My journey in technology started with curiosity about how things work, which evolved into a passion for creating solutions that make a difference. I'm constantly exploring new frameworks and tools to expand my skill set.</p>
      <div class="quote-box" aria-live="polite">
        <p id="quote-text">Loading a quote...</p>
        <p class="quote-author" id="quote-author"></p>
      </div>
    </div>
    <aside class="skills-highlights" aria-label="Skills highlights">
      <div class="skill-item">
        <div class="skill-icon" aria-hidden="true">
          <i class="fas fa-mobile-alt"></i>
        </div>
        <div>
          <h3 style="margin:0">Mobile Development</h3>
          <p style="margin:.3rem 0 0 0; font-size:.95rem;">Creating responsive and user-friendly mobile applications</p>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-icon" aria-hidden="true">
          <i class="fas fa-database"></i>
        </div>
        <div>
          <h3 style="margin:0">Database Design</h3>
          <p style="margin:.3rem 0 0 0; font-size:.95rem;">Designing efficient and scalable database systems</p>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-icon" aria-hidden="true">
          <i class="fas fa-code"></i>
        </div>
        <div>
          <h3 style="margin:0">Software Engineering</h3>
          <p style="margin:.3rem 0 0 0; font-size:.95rem;">Building robust and maintainable software solutions</p>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-icon" aria-hidden="true">
          <i class="fas fa-brain"></i>
        </div>
        <div>
          <h3 style="margin:0">Problem Solving</h3>
          <p style="margin:.3rem 0 0 0; font-size:.95rem;">Analyzing complex problems and developing effective solutions</p>
        </div>
      </div>
    </aside>
  </div>
</section>

<!-- Projects Section -->
<section id="projects">
  <h2 class="section-title">My Projects</h2>
  <div class="projects-grid">
    <div class="project-card">
      <div class="project-image" aria-hidden="true">
        <i class="fas fa-clipboard-check"></i>
      </div>
      <div class="project-content">
        <h3>Attendance Management System</h3>
        <p>A comprehensive system built with Flutter, Firebase, and MSSQL for tracking and managing attendance with real-time updates and data visualization.</p>
        <div class="project-tags" aria-hidden="true">
          <span class="tag">Flutter</span>
          <span class="tag">Firebase</span>
          <span class="tag">MSSQL</span>
          <span class="tag">Mobile</span>
        </div>
      </div>
    </div>
    <!-- Example additional project (keeps layout consistent) -->
    <div class="project-card">
      <div class="project-image" aria-hidden="true">
        <i class="fas fa-code"></i>
      </div>
      <div class="project-content">
        <h3>Portfolio Website</h3>
        <p>Personal site built with HTML, CSS, and a little JavaScript — responsive and minimal. Deployed on GitHub Pages.</p>
        <div class="project-tags">
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">JavaScript</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Skills Section -->
<section id="skills" class="skills">
  <h2 class="section-title">My Skills</h2>
  <div class="skills-container">
    <div class="skills-categories">
      <div class="skill-category">
        <h3 style="margin:0"><i class="fas fa-code" aria-hidden="true"></i> Programming Languages</h3>
        <div class="skills-grid">
          <div class="skill"><div class="skill-icon-small"><i class="fab fa-python"></i></div><span>Python</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fab fa-java"></i></div><span>Java</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-terminal"></i></div><span>C / C++</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fab fa-microsoft"></i></div><span>C#</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-database"></i></div><span>SQL</span></div>
        </div>
      </div>
      <div class="skill-category">
        <h3 style="margin:0"><i class="fas fa-tools" aria-hidden="true"></i> Frameworks & Technologies</h3>
        <div class="skills-grid">
          <div class="skill"><div class="skill-icon-small"><i class="fab fa-flutter"></i></div><span>Flutter</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fab fa-git-alt"></i></div><span>Git</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-fire"></i></div><span>Firebase</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-brain"></i></div><span>TensorFlow</span></div>
        </div>
      </div>
      <div class="skill-category">
        <h3 style="margin:0"><i class="fas fa-database" aria-hidden="true"></i> Databases</h3>
        <div class="skills-grid">
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-database"></i></div><span>MySQL</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-database"></i></div><span>PostgreSQL</span></div>
          <div class="skill"><div class="skill-icon-small"><i class="fas fa-server"></i></div><span>MSSQL</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Fun Section -->
<section id="fun">
  <h2 class="section-title">Hobbies & Interests</h2>
  <div class="hobbies-grid">
    <div class="hobby-card">
      <div class="hobby-icon" aria-hidden="true"><i class="fas fa-gamepad"></i></div>
      <h3>Gaming</h3>
      <p>I like old-school games that remind me of childhood — the vibe is everything.</p>
    </div>
    <div class="hobby-card">
      <div class="hobby-icon" aria-hidden="true"><i class="fas fa-book"></i></div>
      <h3>Reading</h3>
      <p>Literature classics in general. If you have any suggestions do not hesitate, message me.</p>
    </div>
    <div class="hobby-card">
      <div class="hobby-icon" aria-hidden="true"><i class="fas fa-bicycle"></i></div>
      <h3>Cycling</h3>
      <p>Old school strikes again. I have an old road bike that I spend more time fixing than riding it...</p>
    </div>
  </div>
</section>

<!-- Contact Section -->
<section id="contact" class="contact">
  <h2 class="section-title">Get In Touch</h2>
  <div class="contact-container">
    <div class="contact-info">
      <h3 style="margin-top:0">Let's Connect</h3>
      <p>I'm always open to discussing new opportunities or interesting projects.</p>
      <div class="contact-details" style="margin-top:1rem;">
        <div class="contact-item" style="display:flex; gap:.8rem; align-items:center; margin-bottom:.8rem;">
          <div class="contact-icon" aria-hidden="true"><i class="fas fa-envelope"></i></div>
          <div class="contact-text">
            <h4 style="margin:.0">Email</h4>
            <a href="mailto:kocofanni@gmail.com">kocofanni@gmail.com</a>
          </div>
        </div>
        <div class="contact-item" style="display:flex; gap:.8rem; align-items:center; margin-bottom:.8rem;">
          <div class="contact-icon" aria-hidden="true"><i class="fab fa-linkedin"></i></div>
          <div class="contact-text">
            <h4 style="margin:.0">LinkedIn</h4>
            <a href="https://www.linkedin.com/in/ko%C3%A7o-fani-144597294/" target="_blank" rel="noopener">Connect with me</a>
          </div>
        </div>
        <div class="contact-item" style="display:flex; gap:.8rem; align-items:center;">
          <div class="contact-icon" aria-hidden="true"><i class="fab fa-github"></i></div>
          <div class="contact-text">
            <h4 style="margin:.0">GitHub</h4>
            <a href="https://github.com/kocofani23" target="_blank" rel="noopener">View my projects</a>
          </div>
        </div>
      </div>
      <div class="social-links" style="margin-top:1rem;">
        <a href="https://www.instagram.com/_kocofani_" class="social-link" style="margin-right:.5rem;"><i class="fab fa-instagram"></i></a>
        <a href="https://www.facebook.com/share/1JSZuCdiLm/?mibextid=wwXIfr" class="social-link"><i class="fab fa-facebook-f"></i></a>
      </div>
    </div>
    <div class="contact-form">
      <h3 style="margin-top:0">Send Me a Message</h3>
      <form id="contactForm" onsubmit="handleContact(event)">
        <div class="form-group">
          <label for="name">Your Name</label>
          <input type="text" id="name" class="form-control" required>
        </div>
        <div class="form-group">
          <label for="email">Your Email</label>
          <input type="email" id="email" class="form-control" required>
        </div>
        <div class="form-group">
          <label for="subject">Subject</label>
          <input type="text" id="subject" class="form-control" required>
        </div>
        <div class="form-group">
          <label for="message">Your Message</label>
          <textarea id="message" class="form-control" rows="5" required></textarea>
        </div>
        <button type="submit" class="btn-primary"><i class="fas fa-paper-plane"></i> Send Message</button>
        <div id="contact-status" aria-live="polite" style="margin-top:.8rem;"></div>
      </form>
    </div>
  </div>
</section>

<!-- Footer -->
<footer>
  <div class="footer-content">
    <a href="#" class="footer-logo" style="font-weight:700; color:inherit; text-decoration:none;">Koço Fani</a>
    <div class="footer-links" style="margin-top:.6rem; display:flex; gap:1rem; justify-content:center; flex-wrap:wrap;">
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#fun">Hobbies</a>
      <a href="#contact">Contact</a>
    </div>
    <p class="copyright" style="margin-top:.8rem;">© 2025 Koço Fani. All rights reserved.</p>
  </div>
</footer>

  <script>
    // Theme Toggle
    const themeToggle = document.getElementById('themeToggle');
    const themeIcon = themeToggle.querySelector('i');
    
    // Check for saved theme or prefered scheme
    const prefersDarkScheme = window.matchMedia('(prefers-color-scheme: dark)');
    const currentTheme = localStorage.getItem('theme');
    
    if (currentTheme === 'dark' || (!currentTheme && prefersDarkScheme.matches)) {
      document.body.classList.add('dark-mode');
      themeIcon.classList.remove('fa-moon');
      themeIcon.classList.add('fa-sun');
    }
    
    themeToggle.addEventListener('click', function() {
      document.body.classList.toggle('dark-mode');
      
      if (document.body.classList.contains('dark-mode')) {
        localStorage.setItem('theme', 'dark');
        themeIcon.classList.remove('fa-moon');
        themeIcon.classList.add('fa-sun');
      } else {
        localStorage.setItem('theme', 'light');
        themeIcon.classList.remove('fa-sun');
        themeIcon.classList.add('fa-moon');
      }
    });
    
    // Mobile Menu Toggle
    const mobileMenuBtn = document.getElementById('mobileMenuBtn');
    const mobileMenu = document.getElementById('mobileMenu');
    const mobileMenuIcon = mobileMenuBtn.querySelector('i');
    
    mobileMenuBtn.addEventListener('click', function() {
      mobileMenu.classList.toggle('active');
      
      if (mobileMenu.classList.contains('active')) {
        mobileMenuIcon.classList.remove('fa-bars');
        mobileMenuIcon.classList.add('fa-times');
      } else {
        mobileMenuIcon.classList.remove('fa-times');
        mobileMenuIcon.classList.add('fa-bars');
      }
    });
    
    // Close mobile menu when clicking on a link
    const mobileMenuLinks = mobileMenu.querySelectorAll('a');
    mobileMenuLinks.forEach(link => {
      link.addEventListener('click', function() {
        mobileMenu.classList.remove('active');
        mobileMenuIcon.classList.remove('fa-times');
        mobileMenuIcon.classList.add('fa-bars');
      });
    });
    
    // Header scroll effect
    window.addEventListener('scroll', function() {
      const header = document.querySelector('header');
      if (window.scrollY > 50) {
        header.style.boxShadow = '0 4px 6px -1px rgba(0, 0, 0, 0.1)';
      } else {
        header.style.boxShadow = '0 1px 3px rgba(0, 0, 0, 0.1)';
      }
    });
    
    // Random Quote Generator
    const quotes = [
      {
        text: "Code is like humor. When you have to explain it, it's bad.",
        author: "Cory House"
      },
      {
        text: "First, solve the problem. Then, write the code.",
        author: "John Johnson"
      },
      {
        text: "Programming isn't about what you know; it's about what you can figure out.",
        author: "Chris Pine"
      },
      {
        text: "The best way to get a project done faster is to start sooner.",
        author: "Jim Highsmith"
      },
      {
        text: "Experience is the name everyone gives to their mistakes.",
        author: "Oscar Wilde"
      },
      {
        text: "The only way to learn a new programming language is by writing programs in it.",
        author: "Dennis Ritchie"
      }
    ];
    
    const quoteText = document.getElementById('quote-text');
    const quoteAuthor = document.getElementById('quote-author');
    
    function displayRandomQuote() {
      const randomIndex = Math.floor(Math.random() * quotes.length);
      const randomQuote = quotes[randomIndex];
      
      quoteText.textContent = randomQuote.text;
      quoteAuthor.textContent = `— ${randomQuote.author}`;
    }
    
    // Display a random quote on page load
    displayRandomQuote();
    
    // Contact Form Submission
    const contactForm = document.getElementById('contactForm');
    
    contactForm.addEventListener('submit', function(e) {
      e.preventDefault();
      
      // Get form values
      const name = document.getElementById('name').value;
      const email = document.getElementById('email').value;
      const subject = document.getElementById('subject').value;
      const message = document.getElementById('message').value;
      
      // In a real application, you would send this data to a server
      // For this example, we'll just show an alert
      alert(`Thank you for your message, ${name}! I'll get back to you soon.`);
      
      // Reset the form
      contactForm.reset();
    });
    
    // Smooth scrolling for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        
        const targetId = this.getAttribute('href');
        if (targetId === '#') return;
        
        const targetElement = document.querySelector(targetId);
        if (targetElement) {
          window.scrollTo({
            top: targetElement.offsetTop - 70,
            behavior: 'smooth'
          });
        }
      });
    });
  </script>
</body>
</html>
