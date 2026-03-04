
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pei-Sheng's Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-gradient: linear-gradient(135deg, #0f2027 0%, #203a43 50%, #2c5364 100%);
            --accent-color: #00eaee;
            --glass-bg: rgba(255, 255, 255, 0.05);
            --glass-border: rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Inter', system-ui, sans-serif; }
        html { scroll-behavior: smooth; }
        
        body {
            background: var(--primary-gradient);
            background-attachment: fixed;
            color: #eaeaea;
            line-height: 1.7;
            overflow-x: hidden;
        }

        /* 網底的科技感發光 */
        body::before {
            content: ""; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 10%, rgba(0, 234, 238, 0.15), transparent 50%);
            z-index: -1;
        }

        header {
            min-height: 100vh; display: flex; flex-direction: column;
            justify-content: center; align-items: center; text-align: center; 
            padding: 20px; position: relative; overflow: hidden;
        }

        /* 背景浮動程式碼裝飾 */
        .floating-code {
            position: absolute; font-family: 'Fira Code', monospace; color: rgba(255,255,255,0.05);
            font-size: 1.5rem; z-index: -1; white-space: nowrap; user-select: none;
        }
        .code-1 { top: 20%; left: 10%; transform: rotate(-15deg); }
        .code-2 { top: 60%; right: 5%; transform: rotate(10deg); font-size: 2rem; }
        .code-3 { bottom: 20%; left: 15%; transform: rotate(-5deg); }

        /* 頭像框設計 */
        .profile-wrapper {
            width: 160px; height: 160px; border-radius: 50%;
            padding: 5px; background: linear-gradient(45deg, var(--accent-color), #b06ab3);
            margin-bottom: 25px; box-shadow: 0 0 30px rgba(0, 234, 238, 0.4);
            animation: float 4s ease-in-out infinite;
        }
        .profile-img {
            width: 100%; height: 100%; border-radius: 50%; background: #203a43;
            display: flex; justify-content: center; align-items: center;
            font-size: 3rem; overflow: hidden; border: 4px solid #0f2027;
        }
        .profile-img img { width: 100%; height: 100%; object-fit: cover; }

        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }

        /* 名字大幅放大 */
        header h1 {
            font-size: clamp(3.5rem, 10vw, 6rem); font-weight: 800;
            margin-bottom: 10px; letter-spacing: -2px; 
            text-shadow: 0 10px 30px rgba(0,0,0,0.5); color: #fff;
            line-height: 1.1;
        }

        /* 打字機效果 */
        .typewriter {
            font-family: 'Fira Code', monospace;
            color: var(--accent-color);
            font-size: clamp(1rem, 4vw, 1.5rem);
            margin-bottom: 30px;
            overflow: hidden; white-space: nowrap; border-right: .15em solid var(--accent-color);
            animation: typing 3.5s steps(40, end), blink-caret .75s step-end infinite;
            max-width: fit-content; margin-left: auto; margin-right: auto;
        }

        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink-caret { from, to { border-color: transparent } 50% { border-color: var(--accent-color); } }

        /* 頂部行動按鈕 */
        .header-actions { display: flex; gap: 15px; margin-bottom: 30px; flex-wrap: wrap; justify-content: center; }
        .btn {
            padding: 12px 25px; border-radius: 30px; text-decoration: none;
            font-weight: 600; font-size: 1rem; transition: 0.3s;
            display: inline-flex; align-items: center; gap: 8px;
        }
        .btn-primary { background: var(--accent-color); color: #000; box-shadow: 0 0 15px rgba(0,234,238,0.3); }
        .btn-primary:hover { transform: scale(1.05); box-shadow: 0 0 25px rgba(0,234,238,0.6); }
        .btn-outline { border: 1px solid var(--accent-color); color: var(--accent-color); }
        .btn-outline:hover { background: rgba(0,234,238,0.1); transform: scale(1.05); }

        nav {
            backdrop-filter: blur(12px); background: rgba(0, 0, 0, 0.4);
            padding: 15px 30px; border-radius: 50px; border: 1px solid var(--glass-border);
            position: sticky; top: 20px; z-index: 100; margin: -50px auto 40px; width: fit-content;
        }

        nav a {
            color: #fff; text-decoration: none; margin: 0 15px;
            font-weight: 600; font-size: 0.9rem; text-transform: uppercase; transition: 0.3s;
        }
        nav a:hover { color: var(--accent-color); }

        /* 其他區塊樣式保持不變 */
        section { padding: 80px 20px; max-width: 900px; margin: auto; }
        .card {
            background: var(--glass-bg); backdrop-filter: blur(15px);
            padding: 40px; border-radius: 20px; border: 1px solid var(--glass-border);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3); margin-bottom: 40px;
        }
        h2 { font-size: 2rem; margin-bottom: 25px; color: var(--accent-color); border-bottom: 1px solid var(--glass-border); padding-bottom: 10px;}
        .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 20px; }
        .tag-container { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 15px; }
        .tag {
            background: rgba(0, 234, 238, 0.1); border: 1px solid var(--accent-color);
            color: var(--accent-color); padding: 5px 15px; border-radius: 20px; font-size: 0.85rem;
        }
        .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
        .project-card {
            background: rgba(0, 0, 0, 0.3); padding: 25px; border-radius: 15px;
            border: 1px solid var(--glass-border); transition: all 0.3s ease;
        }
        .project-card:hover { transform: translateY(-8px); border-color: var(--accent-color); background: rgba(0, 0, 0, 0.5); }
        .contact-link {
            display: inline-block; margin-top: 15px; color: var(--accent-color);
            text-decoration: none; font-weight: 600; transition: 0.3s; font-size: 1.1rem;
        }
        .contact-link:hover { text-shadow: 0 0 10px var(--accent-color); }
        footer { text-align: center; padding: 40px 20px; opacity: 0.5; font-size: 0.8rem; }
        @media (max-width: 600px) { .grid-2 { grid-template-columns: 1fr; } .typewriter { font-size: 0.9rem; } }
    </style>
</head>
<body>

    <header>
        <div class="floating-code code-1">std::cout &lt;&lt; "Hello World";</div>
        <div class="floating-code code-2">git push -f origin main</div>
        <div class="floating-code code-3">while(true) { debug(); }</div>

        <div class="profile-wrapper">
            <div class="profile-img">
                👨‍💻
            </div>
        </div>

        <h1>林沛陞 <br><span style="color: var(--accent-color); font-size: 0.8em;">PEI-SHENG</span></h1>
        
        <div class="typewriter">
            > Computer Science Student @ YZU _
        </div>

        <div class="header-actions">
            <a href="#projects" class="btn btn-primary">⬇️ 看我的專案</a>
            <a href="https://github.com/你的GitHub帳號" target="_blank" class="btn btn-outline">🐙 GitHub</a>
        </div>

    </header>

    <nav>
        <a href="#about">關於我</a>
        <a href="#skills">生存技能</a>
        <a href="#projects">專案紀錄</a>
        <a href="#contact">聯絡方式</a>
    </nav>

    <section id="about">
        <div class="card">
            <h2>👤 About Me</h2>
            <p>嗨，我是林沛陞！目前就讀於元智大學資工系。平常的日常不是在寫 Code 的路上，就是在跟 C++ 還有線性代數奮戰的深淵裡。</p>
            <p style="margin-top: 10px;">寫程式的標配是 Spotify 放滿歌單，偶爾還會出沒在各大地標打 Pokémon Go 的團體戰。二月才剛去釜山充完電回來，現在心還有一半在放假，但作業還是得交，所以這個網站就這樣誕生了！</p>
            
            <div class="grid-2">
                <div style="background: rgba(0,0,0,0.3); padding: 15px; border-radius: 10px;">🎓 <strong>學號：</strong> s1133341</div>
                <div style="background: rgba(0,0,0,0.3); padding: 15px; border-radius: 10px;">📚 <strong>主修：</strong> Computer Science</div>
            </div>
        </div>
    </section>

    <section id="skills" style="padding-top: 20px;">
        <div class="card">
            <h2>🛠️ Tech & Vibe</h2>
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
            <h2 style="border: none;">💻 專案與作業 (Projects)</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>C++ 實驗課紀錄</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">這學期 11402_CI002 課程的心血結晶。期末能不能過就看這個 Repo 了，充滿了各種語法測試跟作業解答。</p>
                </div>
                <div class="project-card">
                    <h3>線性代數復健區</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">矩陣、行列式跟向量的痛苦筆記區，為了不被當掉而努力整理的學習軌跡。</p>
                </div>
                <div class="project-card">
                    <h3>個人耍廢指南</h3>
                    <p style="font-size: 0.9rem; opacity: 0.8; margin-top: 10px;">籌備中... 可能會放一些去釜山玩的照片，或是今天抓到什麼異色寶可夢的廢文。</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" style="padding-top: 20px;">
        <div class="card" style="text-align: center;">
            <h2>✉️ 聯絡我 (找我求救或傳教皆可)</h2>
            <p>如果有程式問題想討論，或是剛好缺人打團戰，歡迎寄信給我！</p>
            <a href="mailto:easonlin0925250286@gmail.com" class="contact-link">easonlin0925250286@gmail.com</a>
        </div>
    </section>

    <footer>
        <p>&copy; 2026 Pei-Sheng Lin. Built with 肝指數 & 滿滿的 Bug.</p>
    </footer>

</body>
</html>
