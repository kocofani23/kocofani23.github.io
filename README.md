<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Koço Fani | Portfolio</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background: #FAF9F6;
      color: #ED2100;
      scroll-behavior: smooth;
    }

    header {
      position: sticky;
      top: 0;
      background: #161b22;
      padding: 1rem;
      display: flex;
      justify-content: center;
      gap: 2rem;
      z-index: 1000;
    }
    header a {
      color: #e6edf3;
      text-decoration: none;
      font-weight: bold;
    }
    header a:hover {
      color: #58a6ff;
    }

    section {
      padding: 3rem 2rem;
      max-width: 1000px;
      margin: auto;
    }

    h2 {
      text-align: center;
      margin-bottom: 2rem;
      color: #58a6ff;
    }

    /* Cards */
    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
    }
    .card {
      background: #161b22;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.3);
      transition: transform 0.2s;
    }
    .card:hover {
      transform: translateY(-5px);
    }
    .card h3 {
      margin-top: 0;
      color: #58a6ff;
    }

    /* Badge Grid */
    .badge-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
      gap: 1rem;
      text-align: center;
    }
    .badge-grid img {
      width: 60px;
      height: 60px;
    }

    /* Quote */
    #quote-box {
      text-align: center;
      font-style: italic;
      font-size: 1.2rem;
      padding: 1rem;
      background: #161b22;
      border-radius: 8px;
      margin-top: 1rem;
    }
  </style>
</head>
<body>

  <!-- Navigation -->
  <header>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#skills">Skills</a>
    <a href="#fun">Fun</a>
    <a href="#contact">Contact</a>
  </header>

  <!-- About -->
  <section id="about">
    <h2>👨‍💻 About Me</h2>
    <p>
      Hi! I'm <b>Koço Fani</b>, a Computer Engineering student passionate about software development, databases, 
      and mobile applications. I enjoy solving real-world problems with code, building efficient systems, 
      and learning new technologies.
    </p>
    <div id="quote-box">Loading a quote...</div>
  </section>

  <!-- Projects -->
  <section id="projects">
    <h2>📌 Featured Projects</h2>
    <div class="cards">
      <div class="card">
        <h3>Attendance Management System</h3>
        <p>Built with Flutter, Firebase, MSSQL. Includes authentication, real-time database sync, and data visualization.</p>
      </div>
      <div class="card">
        <h3>Another Project</h3>
        <p>Short description of another cool project you want to showcase.</p>
      </div>
      <div class="card">
        <h3>Open Source Contribution</h3>
        <p>Describe your contribution to open-source software here.</p>
      </div>
    </div>
  </section>

  <!-- Skills -->
  <section id="skills">
    <h2>🛠️ Tech Stack</h2>
    <div class="badge-grid">
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C"><p>C</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg" alt="C#"><p>C#</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python"><p>Python</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" alt="Java"><p>Java</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/flutter/flutter-original.svg" alt="Flutter"><p>Flutter</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MSSQL"><p>MSSQL</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="PostgreSQL"><p>PostgreSQL</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" alt="Firebase"><p>Firebase</p></div>
      <div><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" alt="TensorFlow"><p>TensorFlow</p></div>
    </div>
  </section>

  <!-- Fun -->
  <section id="fun">
    <h2>🎉 Fun & Hobbies</h2>
    <div class="cards">
      <div class="card">
        <h3>🎮 Gaming</h3>
        <p>I enjoy strategy games and co-op adventures.</p>
      </div>
      <div class="card">
        <h3>📚 Reading</h3>
        <p>Mostly tech books and sci-fi novels.</p>
      </div>
      <div class="card">
        <h3>🚴 Cycling</h3>
        <p>Great way to relax and explore nature.</p>
      </div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact">
    <h2>📬 Contact Me</h2>
    <p>Email: <a href="mailto:kocofanni@gmail.com">kocofanni@gmail.com</a></p>
    <p>LinkedIn: <a href="https://www.linkedin.com/in/ko%C3%A7o-fani-144597294/" target="_blank">My LinkedIn</a></p>
    <p>GitHub: <a href="https://github.com/kocofani23" target="_blank">My GitHub</a></p>
  </section>

  <script>
    // Random Quote of the Day
    const quotes = [
      "Code is like humor. When you have to explain it, it’s bad.",
      "First, solve the problem. Then, write the code.",
      "Programming isn’t about what you know; it’s about what you can figure out.",
      "The best way to get a project done faster is to start sooner.",
      "Experience is the name everyone gives to their mistakes."
    ];
    document.getElementById("quote-box").innerText =
      quotes[Math.floor(Math.random() * quotes.length)];
  </script>
</body>
</html>
