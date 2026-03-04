<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pei-Sheng's Portfolio</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-gradient: linear-gradient(135deg, #4b6cb7 0%, #182848 100%);
            --accent-color: #00d2ff;
            --glass-bg: rgba(255, 255, 255, 0.08);
            --glass-border: rgba(255, 255, 255, 0.15);
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

        body::before {
            content: ""; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 80% 20%, rgba(0, 210, 255, 0.15), transparent);
            z-index: -1;
        }

        header {
            min-height: 85vh; display: flex; flex-direction: column;
            justify-content: center; align-items: center; text-align: center; padding: 20px;
        }

        header h1 {
            font-size: clamp(2.5rem, 8vw, 4.5rem); font-weight: 800;
            margin-bottom: 15px; letter-spacing: -1px; text-shadow: 0 10px 30px rgba(0,0,0,0.3);
            color: #fff;
        }

        header p { font-size: 1.2rem; opacity: 0.9; margin-bottom: 30px; font-weight: 300; }

        nav {
            backdrop-filter: blur(12px); background: rgba(0, 0, 0, 0.3);
            padding: 15px 30px; border-radius: 50px; border: 1px solid var(--glass-border);
            position: sticky; top: 20px; z-index: 100; margin: -40px auto 40px; width: fit-content;
        }

        nav a {
            color: #fff; text-decoration: none; margin: 0 15px;
            font-weight: 600; font-size: 0.9rem; text-transform: uppercase; transition: 0.3s;
        }
        nav a:hover { color: var(--accent-color); }

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
            background: rgba(0, 210, 255, 0.1); border: 1px solid var(--accent-color);
            color: var(--accent-color); padding: 5px 15px; border-radius: 20px; font-size: 0.85rem;
        }

        .projects-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 20px; }
        .project-card {
            background: rgba(0, 0, 0, 0.2); padding: 25px; border-radius: 15px;
            border: 1px solid var(--glass-border); transition: all 0.3s ease;
        }
        .project-card:hover { transform: translateY(-8px); border-color: var(--accent-color); background: rgba(0, 0, 0, 0.4); }

        .contact-link {
            display: inline-block; margin-top: 15px; color: var(--accent-color);
            text-decoration: none; font-weight: 600; transition: 0.3s; font-size: 1.1rem;
        }
        .contact-link:hover { text-shadow: 0 0 10px var(--accent-color); }

        footer { text-align: center; padding: 40px 20px; opacity: 0.5; font-size: 0.8rem; }

        @media (max-width: 600px) { .grid-2 { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

    <header>
        <h1>林沛陞 <span style="color: var(--accent-color);">PEI-SHENG</span></h1>
        <p>資工系求生中 💻 | C++ 新手村玩家 | Debug 到天亮</p>
        <a href="#about" style="color: rgba(255,255,255,0.5); text-decoration: none; font-size: 2rem; margin-top: 20px; animation: bounce 2s infinite;">↓</a>
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
                <div style="background: rgba(0,0,0,0.2); padding: 15px; border-radius: 10px;">🎓 <strong>學號：</strong> s1133341</div>
                <div style="background: rgba(0,0,0,0.2); padding: 15px; border-radius: 10px;">📚 <strong>主修：</strong> Computer Science</div>
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
