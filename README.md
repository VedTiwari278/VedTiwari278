<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Ved Tiwari | MERN Stack Developer Portfolio</title>
    <!-- Google Fonts & Font Awesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #0a0c10 0%, #0f1219 100%);
            font-family: 'Inter', sans-serif;
            color: #eef4ff;
            padding: 2rem 1.5rem;
            line-height: 1.5;
        }

        /* custom container with glassmorphism touches */
        .profile-container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(18, 22, 32, 0.55);
            backdrop-filter: blur(2px);
            border-radius: 3rem;
            box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.6), inset 0 1px 0 rgba(255,255,255,0.05);
            overflow: hidden;
            border: 1px solid rgba(0, 255, 255, 0.15);
            transition: all 0.2s ease;
        }

        /* mern accent: cyan + neon green touches */
        .mern-glow {
            text-shadow: 0 0 5px #00ffff80, 0 0 2px #00ffe0;
        }

        /* sections */
        .section-card {
            background: rgba(12, 16, 24, 0.65);
            border-radius: 2rem;
            margin: 1.8rem 2rem;
            padding: 1.8rem 2rem;
            backdrop-filter: blur(4px);
            border: 1px solid rgba(0, 255, 255, 0.2);
            transition: transform 0.2s, border-color 0.2s;
        }

        .section-card:hover {
            border-color: #00ffff66;
            box-shadow: 0 8px 20px -8px rgba(0, 255, 255, 0.2);
        }

        /* headings */
        h1, h2, h3 {
            font-weight: 700;
            letter-spacing: -0.02em;
        }

        h2 {
            font-size: 1.9rem;
            margin-bottom: 1.2rem;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            background: linear-gradient(135deg, #b3f0ff, #2dd4bf);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            border-left: 4px solid #0ff;
            padding-left: 1rem;
        }

        h2 i {
            background: none;
            color: #2dd4bf;
            font-size: 1.8rem;
        }

        /* tech badges */
        .tech-badge {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: #0e1622;
            padding: 0.6rem 1.2rem;
            border-radius: 40px;
            font-weight: 500;
            font-size: 0.9rem;
            backdrop-filter: blur(2px);
            border: 1px solid #2a3950;
            transition: all 0.2s;
            color: #ccf4ff;
        }

        .tech-badge i, .tech-badge svg {
            font-size: 1.2rem;
        }

        .tech-badge:hover {
            border-color: #0ff;
            transform: translateY(-2px);
            background: #0a101e;
            color: white;
        }

        .badge-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 1rem;
        }

        /* mern highlight row */
        .mern-stack-showcase {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            margin: 1.5rem 0 0.8rem;
        }

        .mern-icon {
            background: #0e1624;
            border-radius: 60px;
            padding: 0.7rem 1.6rem;
            font-weight: 700;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 12px;
            border-bottom: 2px solid #0ff;
            box-shadow: 0 6px 14px rgba(0,0,0,0.3);
        }

        /* stats row */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
            margin-top: 1rem;
        }

        .stat-card {
            flex: 1;
            min-width: 240px;
            background: #0b0f1a;
            border-radius: 1.5rem;
            padding: 1.2rem;
            text-align: center;
            border: 1px solid #2a3348;
            transition: all 0.2s;
        }

        .stat-card img {
            max-width: 100%;
            border-radius: 12px;
        }

        /* connect buttons */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin-top: 1rem;
        }

        .social-btn {
            background: rgba(0, 255, 255, 0.08);
            padding: 0.7rem 1.4rem;
            border-radius: 60px;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-weight: 600;
            transition: 0.2s;
            color: #d6f0ff;
            text-decoration: none;
            border: 1px solid #2e3b4e;
            backdrop-filter: blur(4px);
        }

        .social-btn i {
            font-size: 1.3rem;
        }

        .social-btn:hover {
            background: #0ff22a20;
            border-color: #0ff;
            color: white;
            transform: scale(1.02);
        }

        /* projects preview */
        .project-preview {
            background: linear-gradient(120deg, #0c1120, #0a0f1c);
            border-radius: 1.4rem;
            padding: 1rem 1.6rem;
            margin: 1rem 0;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            border-left: 5px solid #2dd4bf;
        }

        .project-preview span {
            font-weight: 600;
            font-size: 1.1rem;
        }

        .repo-link {
            color: #7ae9ff;
            text-decoration: none;
            font-weight: 500;
            transition: 0.2s;
        }

        .repo-link:hover {
            color: white;
            text-shadow: 0 0 3px cyan;
        }

        hr {
            border-color: #1f2a3e;
            margin: 1rem 0;
        }

        footer {
            text-align: center;
            padding: 1.5rem;
            font-size: 0.85rem;
            border-top: 1px solid rgba(0,255,255,0.2);
            margin-top: 1rem;
        }

        @media (max-width: 700px) {
            .section-card {
                margin: 1rem;
                padding: 1.2rem;
            }
            .mern-icon {
                font-size: 1rem;
                padding: 0.4rem 1rem;
            }
            h2 {
                font-size: 1.5rem;
            }
        }

        .typing-cursor {
            display: inline-block;
            width: 3px;
            background: cyan;
            animation: blink 1s infinite;
            margin-left: 5px;
        }

        @keyframes blink {
            0%,100%{ opacity:1; } 50%{ opacity:0; }
        }
    </style>
</head>
<body>
<div class="profile-container">
    <!-- Hero section with typed effect (static but beautiful mern fullstack vibe) -->
    <div style="padding: 2rem 2rem 1rem 2rem; text-align: center;">
        <div style="font-family: 'JetBrains Mono', monospace; font-size: 1.1rem; letter-spacing: 1px; color: #4ef3ff;"> 
            <i class="fas fa-code"></i> MERN ecosystem · Full Stack Alchemist
        </div>
        <div style="font-size: 3.2rem; font-weight: 800; margin: 0.5rem 0 0.2rem; background: linear-gradient(135deg, #FFFFFF, #7af0ff, #2dd4bf); background-clip: text; -webkit-background-clip: text; color: transparent;">
            Ved Tiwari
        </div>
        <div style="font-size: 1.1rem; color: #b2d9ff;">
            <i class="fas fa-globe"></i> building the web, one component at a time
        </div>
        <div style="margin-top: 1rem;">
            <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=500&size=20&duration=3500&pause=800&color=00F7FF&center=true&vCenter=true&width=500&lines=MERN+Stack+Architect;React+%2B+Node.js+Enthusiast;MongoDB+%7C+Express+Mastery;Creating+scalable+web+apps" alt="Typing SVG" style="max-width:100%; height:auto;" />
        </div>
    </div>

    <!-- MERN Stack Highlight -->
    <div class="section-card" style="text-align: center;">
        <h2 style="border-left-color: #2dd4bf; justify-content: center; display: flex;"><i class="fab fa-react"></i> MERN · Full Stack Arsenal</h2>
        <div class="mern-stack-showcase">
            <div class="mern-icon"><i class="fas fa-database"></i> MongoDB</div>
            <div class="mern-icon"><i class="fab fa-node-js"></i> Express.js</div>
            <div class="mern-icon"><i class="fab fa-react"></i> React.js</div>
            <div class="mern-icon"><i class="fab fa-node"></i> Node.js</div>
        </div>
        <div class="badge-grid" style="justify-content: center;">
            <span class="tech-badge"><i class="fas fa-server"></i> RESTful APIs</span>
            <span class="tech-badge"><i class="fas fa-cloud-upload-alt"></i> JWT Auth</span>
            <span class="tech-badge"><i class="fas fa-chart-line"></i> Redux Toolkit</span>
            <span class="tech-badge"><i class="fas fa-box"></i> Mongoose ODM</span>
            <span class="tech-badge"><i class="fab fa-graphql"></i> GraphQL basics</span>
        </div>
        <p style="margin-top: 1.5rem; font-size: 0.95rem; opacity: 0.8;">⚡ Crafting high-performance full-stack applications with MERN, modern UI libraries, and cloud deployment. Passionate about clean architecture & real-time experiences.</p>
    </div>

    <!-- About me + Connect (modern) -->
    <div class="section-card">
        <h2><i class="fas fa-user-astronaut"></i> About Me</h2>
        <div style="display: flex; flex-wrap: wrap; gap: 2rem; align-items: center;">
            <div style="flex:2; min-width: 200px;">
                <p style="font-size: 1.05rem; margin-bottom: 1rem;">🔭 <strong>Computer Science Engineer</strong> who breathes MERN — from crafting elegant React dashboards to robust Node.js backends. I love solving real-world problems through code that scales.</p>
                <p>💼 <strong>What drives me:</strong> building impactful full-stack solutions, mastering microservices, and contributing to open-source MERN libraries.</p>
                <p>🎯 Currently diving deep into <strong>Next.js + TypeScript</strong> & WebSockets for real-time collaboration tools.</p>
                <div style="margin-top: 1.2rem;">
                    <span class="tech-badge"><i class="fas fa-coffee"></i> Code -> Coffee -> Deploy</span>
                    <span class="tech-badge"><i class="fas fa-rocket"></i> Startup Mindset</span>
                </div>
            </div>
            <div style="flex:1; text-align: center;">
                <i class="fas fa-laptop-code" style="font-size: 4rem; color: #2dd4bf; opacity: 0.8;"></i>
                <div style="margin-top: 0.8rem;"><i class="fas fa-map-marker-alt"></i> India · Remote Ready</div>
            </div>
        </div>
    </div>

    <!-- Tech Stack - Emphasis on MERN + full dev tools -->
    <div class="section-card">
        <h2><i class="fas fa-cogs"></i> MERN & Core Tech Stack</h2>
        <div class="badge-grid">
            <span class="tech-badge"><i class="fab fa-js"></i> JavaScript (ES6+)</span>
            <span class="tech-badge"><i class="fab fa-react"></i> React Hooks / Context</span>
            <span class="tech-badge"><i class="fab fa-vuejs"></i> Vue.js (basic)</span>
            <span class="tech-badge"><i class="fab fa-node"></i> Node.js / Express</span>
            <span class="tech-badge"><i class="fas fa-leaf"></i> MongoDB Atlas</span>
            <span class="tech-badge"><i class="fas fa-database"></i> PostgreSQL / MySQL</span>
            <span class="tech-badge"><i class="fab fa-docker"></i> Docker / Container</span>
            <span class="tech-badge"><i class="fab fa-git-alt"></i> Git & GitHub Actions</span>
            <span class="tech-badge"><i class="fab fa-aws"></i> AWS EC2 / S3</span>
            <span class="tech-badge"><i class="fas fa-fire"></i> Firebase / Auth</span>
            <span class="tech-badge"><i class="fas fa-tachometer-alt"></i> Vite / Webpack</span>
        </div>
        <div style="margin-top: 1rem;">
            <span class="tech-badge"><i class="fas fa-palette"></i> Tailwind CSS / Styled Components</span>
            <span class="tech-badge"><i class="fas fa-code-branch"></i> Agile / Scrum</span>
        </div>
    </div>

    <!-- GitHub Stats / Streak (using real GitHub readme stats & top langs)  -->
    <div class="section-card">
        <h2><i class="fab fa-github"></i> GitHub Pulse</h2>
        <div class="stats-row">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=VedTiwari278&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0a0f1a&title_color=5effe6&icon_color=2dd4bf&text_color=cbd5ff" alt="GitHub Stats" loading="lazy"/>
            </div>
            <div class="stat-card">
                <img src="https://nirzak-streak-stats.vercel.app/?user=VedTiwari278&theme=tokyonight&hide_border=true&background=0a0f1a&stroke=2dd4bf&ring=2dd4bf&fire=00ffff&currStreakNum=ffffff" alt="GitHub Streak" loading="lazy"/>
            </div>
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=VedTiwari278&layout=compact&theme=tokyonight&hide_border=true&bg_color=0a0f1a&title_color=5effe6&text_color=a5c0ff" alt="Top Languages" loading="lazy"/>
            </div>
        </div>
        <div style="text-align: center; margin-top: 1rem;">
            <span class="tech-badge"><i class="fas fa-chart-simple"></i> 20+ MERN projects crafted</span>
            <span class="tech-badge"><i class="fas fa-users"></i> Open source contributions</span>
        </div>
    </div>

    <!-- Featured MERN PROJECTS section (showcase stories) -->
    <div class="section-card">
        <h2><i class="fas fa-star"></i> Flagship MERN Projects ✨</h2>
        <div class="project-preview">
            <span><i class="fab fa-react" style="color:#61dafb"></i> <strong>TaskFlow Hub</strong> — Full-stack task manager with real-time sync, JWT, drag-n-drop</span>
            <a href="#" class="repo-link" style="pointer-events: none; opacity:0.7;">→ Live Demo (soon)</a>
        </div>
        <div class="project-preview">
            <span><i class="fas fa-store"></i> <strong>ShopEase Commerce</strong> — MERN e‑commerce with admin panel, payment gateway, & cart</span>
            <a href="#" class="repo-link" style="pointer-events: none;">🔗 repository preview</a>
        </div>
        <div class="project-preview">
            <span><i class="fas fa-chalkboard-user"></i> <strong>DevCollab Hub</strong> — community platform for developers, built with MongoDB, Express, React, Node</span>
            <a href="#" class="repo-link" style="pointer-events: none;">🚧 WIP</a>
        </div>
        <div style="margin-top: 1rem; font-size: 0.9rem; text-align: right;">
            <i class="fas fa-github"></i> Check all repos → <a href="https://github.com/VedTiwari278?tab=repositories" style="color:#0ff; text-decoration: none;">github.com/VedTiwari278</a>
        </div>
    </div>

    <!-- Connect Section : Socials & lets build together -->
    <div class="section-card">
        <h2><i class="fas fa-share-alt"></i> Connect & Collaborate</h2>
        <div class="social-links">
            <a href="https://linkedin.com/in/vedtiwari278" target="_blank" class="social-btn"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            <a href="https://twitter.com/vedtiwari278" target="_blank" class="social-btn"><i class="fab fa-twitter"></i> Twitter</a>
            <a href="https://instagram.com/vedprakash_431" target="_blank" class="social-btn"><i class="fab fa-instagram"></i> Instagram</a>
            <a href="mailto:vedtiwari278@gmail.com" class="social-btn"><i class="fas fa-envelope"></i> Gmail</a>
            <a href="https://github.com/VedTiwari278" target="_blank" class="social-btn"><i class="fab fa-github"></i> GitHub</a>
        </div>
        <hr>
        <div style="text-align: center;">
            <i class="fas fa-hand-peace"></i> Looking for MERN collaborations? Let’s create the next big thing!<br/>
            <span style="font-size: 0.8rem;">💬 open to freelance, hackathons, and full-stack opportunities.</span>
        </div>
    </div>

    <!-- Fun facts & achievements -->
    <div class="section-card">
        <h2><i class="fas fa-trophy"></i> Achievements & Highlights</h2>
        <div class="badge-grid">
            <span class="tech-badge"><i class="fas fa-award"></i> MERN Stack Certified</span>
            <span class="tech-badge"><i class="fas fa-code-branch"></i> 200+ PR reviews</span>
            <span class="tech-badge"><i class="fas fa-brain"></i> Problem Solver (LeetCode 150+)</span>
            <span class="tech-badge"><i class="fas fa-server"></i> Deployed 8+ full-stack apps</span>
        </div>
        <div style="margin-top: 1.2rem; background: linear-gradient(95deg,#0f1420, #04080f); padding: 1rem; border-radius: 1.5rem; text-align: center;">
            <i class="fas fa-quote-left" style="color:#2dd4bf; margin-right: 8px;"></i> "Turning complex requirements into fluid, scalable MERN experiences — code that tells a story."
        </div>
    </div>

    <!-- visitors counter and footer -->
    <div style="text-align: center; padding: 0.5rem 0 2rem 0;">
        <img src="https://komarev.com/ghpvc/?username=VedTiwari278&label=Profile+Views&color=0e75b6&style=flat-square&abbreviated=true" alt="Profile Views" style="border-radius: 20px;" />
    </div>

    <footer>
        <i class="fas fa-heart" style="color:#ff5e7e;"></i> Made with MERN mindset — Ved Tiwari • Full Stack Artisan <br/>
        ⭐ If you resonate with the stack, star my repos & let’s build something legendary.
    </footer>
</div>
</body>
</html>
