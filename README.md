<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pei-Sheng's Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=Fira+Code:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-color: #0b131a;
            --accent-color: #00eaee;
            --glass-bg: rgba(11, 19, 26, 0.7);
            --glass-border: rgba(0, 234, 238, 0.2);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', system-ui, sans-serif; }
        html { scroll-behavior: smooth; }
        
        body {
            background-color: var(--bg-color);
            /* 科技感網格背景 */
            background-image: 
                linear-gradient(rgba(0, 234, 238, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(0, 234, 238, 0.03) 1px, transparent 1px);
            background-size: 40px 40px;
            color: #eaeaea;
            line-height: 1.7;
            overflow-x: hidden;
            position: relative;
        }

        /* 背景發光暈染 */
        body::before {
            content: ""; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 10%, rgba(0, 234, 238, 0.1), transparent 60%);
            z-index: -2;
        }

        header {
            min-height: 100vh; display: flex; flex-direction: column;
            justify-content: center; align-items: center; text-align: center; 
            padding: 20px; position: relative; overflow: hidden;
        }

        /* --- 動態漂浮程式碼特效 --- */
        .code-container {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            z-index: -1; overflow: hidden; pointer-events: none;
        }
        .floating-code {
            position: absolute; font-family: 'Fira Code', monospace; color: rgba(0, 234, 238, 0.15);
            font-size: 1.2rem; white-space: nowrap; user-select: none;
            animation: drift linear infinite; bottom: -10%;
        }
        @keyframes drift {
            0% { transform: translateY(0) rotate(0deg); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-110vh) rotate(10deg); opacity: 0; }
        }
        /* 設定不同程式碼的位置與飄浮速度 */
        .c1 { left: 10%; animation-duration: 18s; animation-delay: 0s; }
        .c2 { left: 30%; animation-duration: 22s; animation-delay: -5s; font-size: 1.8rem; }
        .c3 { left: 60%; animation-duration: 15s; animation-delay: -10s; }
        .c4 { left: 80%; animation-duration: 25s; animation-delay: -2s; font-size: 1.5rem; }
        .c5 { left: 20%; animation-duration: 20s; animation-delay: -12s; }

        /* --- 終端機動態頭像框 --- */
        .profile-wrapper {
            width: 150px; height: 150px; border-radius: 20px; /* 改成方形圓角更有科技感 */
            padding: 3px; background: linear-gradient(135deg, var(--accent-color), transparent);
            margin-bottom: 25px; box-shadow: 0 0 20px rgba(0, 234, 238, 0.3);
            animation: float 4s ease-in-out infinite; transform-origin: center;
        }
        .profile-img {
            width: 100%; height: 100%; border-radius: 18px; background: #0b131a;
            display: flex; justify-content: center; align-items: center;
            border: 2px solid #1a2f3a;
        }
        /* 終端機符號設計 */
        .terminal-icon { font-family: 'Fira Code', monospace; font-size: 2.5rem; font-weight: 700; color: #fff; }
        .terminal-icon span.arrow { color: var(--accent-color); }
        .terminal-icon span.cursor { 
            display: inline-block; width: 18px; height: 5px; background: var(--accent-color);
            animation: blink 1s step-end infinite; margin-left: 5px; vertical-align: middle;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) scale(1); }
            50% { transform: translateY(-10px) scale(1.02); }
        }
        @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }

        /* 名字大幅放大 */
        header h1 {
            font-size: clamp(3rem, 10vw, 5.5rem); font-weight: 800;
            margin-bottom: 10px; letter-spacing: -2px; 
            text-shadow: 0 0 20px rgba(0,234,238,0.4); color: #fff; line-height: 1.1;
        }

        /* 打字機效果 */
        .typewriter {
            font-family: 'Fira Code', monospace; color: var(--accent-color);
            font-size: clamp(1rem, 4vw, 1.2rem); margin-bottom: 30px;
            overflow: hidden; white-space: nowrap; border-right: .15em solid var(--accent-color);
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
            max-width: fit-content; margin: 0 auto 30px;
        }

        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--accent-color); } }

        /* 頂部行動按鈕 */
        .header-actions { display: flex; gap: 15px; margin-bottom: 30px; flex-wrap: wrap; justify-content: center; position: relative; z-index: 10; }
        .btn {
            padding: 12px 25px; border-radius: 8px; text-decoration: none; font-family: 'Fira Code', monospace;
            font-weight: 600; font-size: 0.9rem; transition: 0.3s; display: inline-flex; align-items: center; gap: 8px;
        }
        .btn-primary { background: var(--accent-color); color: #000; box-shadow: 0 0 15px rgba(0,234,238,0.2); }
        .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 5px 25px rgba(0,234,238,0.5); }
        .btn-outline { border: 1px solid var(--accent-color); color: var(--accent-color); background: rgba(0,234,238,0.05); }
        .btn-outline:hover { background: rgba(0,234,238,0.15); transform: translateY(-3px); }

        nav {
            backdrop-filter: blur(12px); background: rgba(11, 19, 26, 0.8);
            padding: 15px 30px; border-radius: 12px; border: 1px solid var(--glass-border);
            position: sticky; top: 20px; z-index: 100; margin: -50px auto 40px; width: fit-content;
        }
        nav a {
            color: #fff; text-decoration: none; margin: 0 15px;
            font-weight: 600; font-size: 0.9rem; text-transform: uppercase; transition: 0.3s;
        }
        nav a:hover { color: var(--accent-color); text-shadow: 0 0 8px var(--accent-color); }

        section { padding: 80px 20px; max-width: 900px; margin: auto; position: relative; z-index: 10; }
        .card {
            background: var(--glass-bg); backdrop-filter: blur(15px);
            padding: 40px; border-radius: 16px; border: 1px solid var(--glass-border);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); margin-bottom: 40px;
        }
        h2 { font-size: 2rem; margin-bottom: 25px; color: var(--accent-color); border-bottom: 1px dashed var(--glass-border); padding-bottom: 10px; font-family: 'Fira Code', monospace;}
        
        .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 20px; }
        .tag-container { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 15px; }
        .tag {
            background: rgba(0, 234, 238, 0.05); border: 1px solid rgba(0, 234, 238, 0.3);
            color: var(--accent-color); padding: 5px 15px; border-radius: 8px; font-size: 0.85rem; font-family: 'Fira Code', monospace;
        }
        .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
        .project-card {
            background: rgba(255, 255, 255, 0.02); padding: 25px; border-radius: 12px;
            border: 1px solid var(--glass-border); transition: all 0.3s ease;
            border-left: 3px solid transparent;
        }
        .project-card:hover { 
            transform: translateX(5px); border-left: 3px solid var(--accent-color); 
            background: rgba(0, 234, 238, 0.05); border-color: var(--accent-color);
        }
        .contact-link {
            display: inline-block; margin-top: 15px; color: var(--accent-color);
            text-decoration: none; font-weight: 600; transition: 0.3s; font-size: 1.1rem; font-family: 'Fira Code', monospace;
        }
        .contact-link:hover { text-shadow: 0 0 15px var(--accent-color); }
        footer { text-align: center; padding: 40px 20px; opacity: 0.5; font-size: 0.8rem; font-family: 'Fira Code', monospace; }
        @media (max-width: 600px) { .grid-2 { grid-template-columns: 1fr; } .typewriter { font-size: 0.9rem; } }
    </style>
</head>
<body>

    <header>
        <div class="code-container">
            <div class="floating-code c1">std::cout &lt;&lt; "Hello World";</div>
            <div class="floating-code c2">git push -u origin main</div>
            <div class="floating-code c3">vector&lt;int&gt; dp(n, 0);</div>
            <div class="floating-code c4">while(true) { debug(); }</div>
            <div class="floating-code c5">Matrix A = Matrix::Identity(3, 3);</div>
        </div>

        <div class="profile-wrapper">
            <div class="profile-img">
                <div class="terminal-icon"><span class="arrow">></span>_<span class="cursor"></span></div>
            </div>
        </div>

        <h1>林沛陞 <br><span style="color: var(--accent-color); font-size: 0.8em;">PEI-SHENG</span></h1>
        
        <div class="typewriter">
            > const string role = "CS Student @ YZU";
        </div>

        <div class="header-actions">
            <a href="#projects" class="btn btn-primary">cd ./projects</a>
            <a href="https://github.com/你的GitHub帳號" target="_blank" class="btn btn-outline">git clone GitHub</a>
        </div>

    </header>

    <nav>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
    </nav>

    <section id="about">
        <div class="card">
            <h2>> whoami</h2>
            <p>嗨，我是林沛陞！目前就讀於元智大學資工系。平常的日常不是在寫 Code 的路上，就是在跟 C++ 還有線性代數奮戰的深淵裡。</p>
            <p style="margin-top: 10px;">寫程式的標配是 Spotify 放滿歌單，偶爾還會出沒在各大地標打 Pokémon Go 的團體戰。二月才剛去釜山充完電回來，現在心還有一半在放假，但作業還是得交，所以這個網站就這樣誕生了！</p>
            
            <div class="grid-2">
                <div style="background: rgba(0,0,0,0.3); padding: 15px; border-radius: 8px; border-left: 2px solid var(--accent-color);">🎓 <strong>Student ID：</strong> s1133341</div>
                <div style="background: rgba(0,0,0,0.3); padding: 15px; border-radius: 8px; border-left: 2px solid var(--accent-color);">📚 <strong>Major：</strong> Computer Science</div>
            </div>
        </div>
    </section>

    <section id="skills" style="padding-top: 20px;">
        <div class="card">
            <h2>> ls ./skills</h2>
            <p>目前點亮的技能樹跟日常狀態：</p>
            <div class="tag-container">
                <span class="tag">C++ Programming</span>
                <span class="tag">Linear Algebra</span>
                <span class="tag">HTML / CSS (現學現賣)</span>
                <span class="tag">GitHub Pages</span>
                <span class="tag">Google 通靈術</span>
                <span class="tag">Spotify 重度成癮</span>
                <span class="tag">Pokémon Go 訓練家</span>
            </div>
        </div>
    </section>

    <section id="projects" style="padding-top: 20px;">
        <div class="card" style="background: transparent; border: none; box-shadow: none; padding: 0;">
            <h2 style="border: none;">> cat ./projects.log</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3 style="font-family: 'Fira Code', monospace; color: var(--accent-color);">[1] C++ 實驗課紀錄</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">這學期 11402_CI002 課程的心血結晶。期末能不能過就看這個 Repo 了，充滿了各種語法測試跟作業解答。</p>
                </div>
                <div class="project-card">
                    <h3 style="font-family: 'Fira Code', monospace; color: var(--accent-color);">[2] 線性代數復健區</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">矩陣、行列式跟向量的痛苦筆記區，為了不被當掉而努力整理的學習軌跡。</p>
                </div>
                <div class="project-card">
                    <h3 style="font-family: 'Fira Code', monospace; color: var(--accent-color);">[3] 個人耍廢指南</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">籌備中... 可能會放一些去釜山玩的照片，或是今天抓到什麼異色寶可夢的廢文。</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" style="padding-top: 20px;">
        <div class="card" style="text-align: center;">
            <h2>> ping -c 4 contact</h2>
            <p>如果有程式問題想討論，或是剛好缺人打團戰，歡迎寄信給我！</p>
            <a href="mailto:easonlin0925250286@gmail.com" class="contact-link">easonlin0925250286@gmail.com</a>
        </div>
    </section>

    <footer>
        <p>System Exit(0). &copy; 2026 Pei-Sheng Lin. Built with 肝指數 & 滿滿的 Bug.</p>
    </footer>

</body>
</html>
