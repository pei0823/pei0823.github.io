# pei0823.github.io
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Personal Website</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #667eea, #764ba2);
      color: #fff;
      line-height: 1.6;
    }

    header {
      height: 60vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 20px;
    }

    header h1 {
      font-size: 3rem;
      margin-bottom: 10px;
    }

    header p {
      font-size: 1.2rem;
      margin-bottom: 20px;
    }

    nav a {
      color: #fff;
      text-decoration: none;
      margin: 0 15px;
      font-weight: bold;
      transition: color 0.3s ease;
    }

    nav a:hover {
      color: #ffd369;
    }

    section {
      padding: 80px 20px;
      max-width: 1000px;
      margin: auto;
    }

    section h2 {
      text-align: center;
      font-size: 2rem;
      margin-bottom: 30px;
      color: #ffd369;
    }

    .about, .projects, .contact {
      background: rgba(0, 0, 0, 0.3);
      padding: 40px;
      border-radius: 15px;
      margin-bottom: 40px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
    }

    .project-card {
      background: rgba(255, 255, 255, 0.1);
      padding: 20px;
      border-radius: 12px;
      text-align: center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .project-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.5);
    }

    footer {
      text-align: center;
      padding: 20px;
      background: rgba(0, 0, 0, 0.5);
    }

    footer p {
      font-size: 0.9rem;
      color: #ccc;
    }
  </style>
</head>
<body>
  <header>
    <h1>Hi, I'm Pei-Sheng!</h1>
    <p>✨ Welcome to my personal website ✨</p>
    <nav>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <section id="about" class="about">
    <h2>About Me</h2>
    <p>Hello! I'm a student at Yuan Ze University, passionate about coding, design, and building meaningful projects. This website will showcase my learning journey and personal works.</p>
  </section>

  <section id="projects" class="projects">
    <h2>Projects</h2>
    <div class="projects-grid">
      <div class="project-card">
        <h3>Project 1</h3>
        <p>still working !!</p>
      </div>
      <div class="project-card">
        <h3>Project 2</h3>
        <p>still working !!</p>
      </div>
      <div class="project-card">
        <h3>Project 3</h3>
        <p>still working !!</p>
      </div>
    </div>
  </section>

  <section id="contact" class="contact">
    <h2>Contact</h2>
    <p>If you’d like to reach me, feel free to email me at <a href="mailto:easonlin0925250286@gmail.com" style="color:#ffd369;">my email(it's real!)</a>.</p>
  </section>

  <footer>
    <p>© 2025 [Pei-Sheng]. All Rights Reserved.</p>
  </footer>
</body>
</html>
