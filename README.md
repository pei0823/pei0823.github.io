
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pei-Sheng's Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --accent-color: #ffd369;
            --glass-bg: rgba(255, 255, 255, 0.1);
            --glass-border: rgba(255, 255, 255, 0.2);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Inter', 'Segoe UI', system-ui, sans-serif;
        }

        html {
            scroll-behavior: smooth; /* 平滑滾動 */
        }

        body {
            background: var(--primary-gradient);
            background-attachment: fixed;
            color: #fff;
            line-height: 1.7;
            overflow-x: hidden;
        }

        /* 背景動態效果 */
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 50%, rgba(118, 75, 162, 0.5), transparent);
            z-index: -1;
        }

        header {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 20px;
        }

        header h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem); /* 自適應字體 */
            font-weight: 800;
            margin-bottom: 10px;
            letter-spacing: -1px;
            text-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        header p {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 30px;
            font-weight: 300;
        }

        nav {
            backdrop-filter: blur(10px);
            background: rgba(0, 0, 0, 0.2);
            padding: 15px 30px;
            border-radius: 50px;
            border: 1px solid var(--glass-border);
            position: sticky;
            top: 20px;
            z-index: 100;
            margin: -60px auto 40px;
            width: fit-content;
        }

        nav a {
            color: #fff;
            text-decoration: none;
            margin: 0 20px;
            font-weight: 600;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: 0.3s;
        }

        nav a:hover {
            color: var(--accent-color);
        }

        section {
            padding: 100px 20px;
            max-width: 900px;
            margin: auto;
        }

        .card {
            background: var(--glass-bg);
            backdrop-filter: blur(15px);
            padding: 50px;
            border-radius: 24px;
            border: 1px solid var(--glass-border);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            margin-bottom: 50px;
        }

        h2 {
            font-size: 2.2rem;
            margin-bottom: 30px;
            color: var(--accent-color);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .about-info {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            margin-top: 20px;
            font-size: 0.95rem;
        }

        .info-item {
            background: rgba(0,0,0,0.2);
            padding: 15px;
            border-radius: 12px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid var(--glass-border);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .project-card:hover {
            transform: translateY(-12px);
            background: rgba(255, 255, 255, 0.1);
            border-color: var(--accent-color);
        }

        .contact-link {
            display: inline-block;
            margin-top: 20px;
            color: var(--accent-color);
            text-decoration: none;
            font-weight: 600;
            border-bottom: 2px solid transparent;
            transition: 0.3s;
        }

        .contact-link:hover {
            border-bottom-color: var(--accent-color);
        }

        footer {
            text-align: center;
            padding: 60px 20px;
            opacity: 0.6;
            font-size: 0.8rem;
        }

        @media (max-width: 600px) {
            .about-info { grid-template-columns: 1fr; }
            nav a { margin: 0 10px; font-size: 0.8rem; }
        }
    </style>
</head>
<body>

    <header>
        <h1>林沛陞 <span style="color: var(--accent-color);">PEI-SHENG</span></h1>
        <p>Computer Science Student | Explorer | C++ Programmer</p>
        <a href="#about" style="color: white; text-decoration: none; font-size: 1.5rem;">↓</a>
    </header>

    <nav>
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
    </nav>

    <section id="about">
        <div class="card">
            <h2>👤 About Me</h2>
            <p>你好！我是林沛陞。目前就讀於元智大學，主修電腦科學。我熱衷於學習程式設計與邏輯建構。這是我在 GitHub Pages 上的第一個個人網站，紀錄我的學習歷程與專案實作。</p>
            
            <div class="about-info">
                <div class="info-item"><strong>University:</strong> Yuan Ze University</div>
                <div class="info-item"><strong>Student ID:</strong> s1133341</div>
                <div class="info-item"><strong>Major:</strong> Computer Science</div>
                <div class="info-item"><strong>Course:</strong> C++ Programming Lab</div>
            </div>
        </div>
    </section>

    <section id="projects">
        <h2 style="justify-content: center;">💻 My Projects</h2>
        <div class="projects-grid">
            <div class="project-card">
                <h3>C++ Lab Works</h3>
                <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">整理本學期 C++ 程式實作課的所有練習與作業。</p>
            </div>
            <div class="project-card">
                <h3>Personal Blog</h3>
                <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">正在規劃中的技術筆記，用來記錄學習心得。</p>
            </div>
            <div class="project-card">
                <h3>Future Works</h3>
                <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">Loading... 更多精彩專案開發中！</p>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="card" style="text-align: center;">
            <h2>✉️ Let's Connect</h2>
            <p>如果你對我的專案有興趣，或者想交流程式心得，歡迎隨時聯繫我！</p>
            <a href="mailto:easonlin0925250286@gmail.com" class="contact-link">easonlin0925250286@gmail.com</a>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Pei-Sheng Lin. Built with Passion & HTML/CSS.</p>
    </footer>

</body>
</html>
  <footer>
    <p>© 2025 [Pei-Sheng]. All Rights Reserved.</p>
  </footer>
</body>
</html>
