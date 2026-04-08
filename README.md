<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GitHub Profile README — Noa Danon</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Fira+Code:wght@400;500&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: #010409;
      color: #e6edf3;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Helvetica, Arial, sans-serif;
      font-size: 16px;
      line-height: 1.5;
    }

    /* ── GitHub chrome simulation ── */
    .gh-topbar {
      height: 62px;
      background: #161b22;
      border-bottom: 1px solid #21262d;
      display: flex;
      align-items: center;
      padding: 0 32px;
      gap: 16px;
    }
    .gh-logo { fill: #e6edf3; }
    .gh-topbar-pill {
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 5px 12px;
      font-size: 14px;
      color: #8b949e;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-topbar-pill span { color: #58a6ff; }

    /* ── Profile sidebar + main layout ── */
    .gh-layout {
      max-width: 1280px;
      margin: 32px auto;
      padding: 0 32px;
      display: grid;
      grid-template-columns: 296px 1fr;
      gap: 32px;
      align-items: start;
    }

    /* ── Sidebar ── */
    .gh-sidebar {}
    .gh-avatar {
      width: 296px;
      height: 296px;
      border-radius: 50%;
      background: linear-gradient(135deg, #1a0533, #0d0221);
      border: 1px solid #30363d;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      margin-bottom: 16px;
      overflow: hidden;
    }
    .gh-sidebar h1 {
      font-size: 26px;
      font-weight: 600;
      color: #e6edf3;
      line-height: 1.25;
    }
    .gh-sidebar .gh-username {
      font-size: 20px;
      font-weight: 300;
      color: #8b949e;
      margin: 4px 0 16px;
    }
    .gh-sidebar .gh-bio {
      font-size: 15px;
      color: #8b949e;
      margin-bottom: 16px;
      line-height: 1.5;
    }
    .gh-follow-btn {
      display: block;
      width: 100%;
      background: #21262d;
      border: 1px solid #363b42;
      color: #e6edf3;
      border-radius: 6px;
      padding: 5px 16px;
      font-size: 14px;
      font-weight: 600;
      text-align: center;
      cursor: pointer;
      margin-bottom: 16px;
      transition: background 0.15s, border-color 0.15s;
    }
    .gh-follow-btn:hover { background: #30363d; border-color: #484f58; }
    .gh-meta { display: flex; flex-direction: column; gap: 8px; margin-top: 16px; }
    .gh-meta-item {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      color: #8b949e;
    }
    .gh-meta-item svg { flex-shrink: 0; }
    .gh-meta-item a { color: #58a6ff; text-decoration: none; }
    .gh-meta-item a:hover { text-decoration: underline; }
    .gh-followers {
      display: flex;
      gap: 16px;
      font-size: 14px;
      color: #e6edf3;
      margin-top: 16px;
    }
    .gh-followers span { color: #8b949e; }

    /* ── Main content ── */
    .gh-main {}

    /* ── Tab bar ── */
    .gh-tabs {
      display: flex;
      gap: 0;
      border-bottom: 1px solid #21262d;
      margin-bottom: 24px;
    }
    .gh-tab {
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #8b949e;
      cursor: pointer;
      border-bottom: 2px solid transparent;
      margin-bottom: -1px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-tab.active { color: #e6edf3; border-bottom-color: #f78166; }
    .gh-tab-count {
      background: #21262d;
      border-radius: 20px;
      padding: 1px 7px;
      font-size: 12px;
      font-weight: 500;
    }

    /* ── README box ── */
    .gh-readme-box {
      background: #0d1117;
      border: 1px solid #21262d;
      border-radius: 6px;
      overflow: hidden;
    }
    .gh-readme-header {
      background: #161b22;
      border-bottom: 1px solid #21262d;
      padding: 10px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      font-weight: 600;
      color: #e6edf3;
    }
    .gh-readme-header svg { color: #8b949e; }
    .gh-readme-body {
      padding: 32px 40px;
    }

    /* ─────────────────────────────────────────
       MARKDOWN CONTENT STYLES
    ───────────────────────────────────────── */
    .md { color: #e6edf3; }
    .md-center { text-align: center; }

    /* SVG header */
    .md-header-svg {
      display: flex;
      justify-content: center;
      margin-bottom: 4px;
    }
    .md-header-svg svg { max-width: 100%; border-radius: 15px; }

    /* Typing line */
    .md-typing {
      text-align: center;
      font-family: 'Fira Code', monospace;
      font-size: 17px;
      color: #bc13fe;
      margin: 10px 0 28px;
      min-height: 28px;
    }
    .md-cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: #bc13fe;
      vertical-align: text-bottom;
      animation: blink 0.8s step-end infinite;
      margin-left: 2px;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* HR */
    .md hr { border: none; border-top: 1px solid #21262d; margin: 24px 0; }

    /* Headings */
    .md h2 {
      font-size: 22px;
      font-weight: 600;
      color: #e6edf3;
      border-bottom: 1px solid #21262d;
      padding-bottom: 8px;
      margin: 32px 0 16px;
    }
    .md h3 {
      font-size: 18px;
      font-weight: 600;
      color: #e6edf3;
      margin: 20px 0 12px;
    }

    /* Code block */
    .md pre {
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 16px;
      overflow-x: auto;
      font-family: 'Fira Code', monospace;
      font-size: 13px;
      line-height: 1.7;
      color: #c9d1d9;
      margin: 16px 0;
    }
    .md pre .kw  { color: #ff7b72; }
    .md pre .ty  { color: #ffa657; }
    .md pre .str { color: #a5d6ff; }
    .md pre .cm  { color: #8b949e; }
    .md pre .key { color: #79c0ff; }
    .md pre .arr { color: #bc13fe; }

    /* Badges row */
    .md-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin: 8px 0 16px;
    }
    .md-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 5px 12px;
      font-size: 13px;
      font-weight: 600;
      font-family: 'Inter', sans-serif;
      color: #fff;
      cursor: default;
      transition: transform 0.15s, opacity 0.15s;
    }
    .md-badge:hover { transform: translateY(-1px); opacity: 0.9; }

    /* Table */
    .md-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
      margin: 16px 0;
    }
    .md-table th {
      background: #161b22;
      color: #8b949e;
      font-weight: 600;
      text-align: left;
      padding: 8px 16px;
      border-bottom: 1px solid #21262d;
    }
    .md-table td {
      padding: 10px 16px;
      border-bottom: 1px solid #21262d;
      color: #c9d1d9;
      font-size: 14px;
      vertical-align: top;
    }
    .md-table tr:hover td { background: #161b22; }
    .md-table td a { color: #58a6ff; text-decoration: none; font-weight: 600; }
    .md-table td a:hover { text-decoration: underline; }
    .code-tag {
      font-family: 'Fira Code', monospace;
      font-size: 12px;
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 4px;
      padding: 1px 6px;
      color: #bc13fe;
      margin: 0 2px;
      white-space: nowrap;
    }

    /* Stats images */
    .md-stats {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .md-stats img {
      border-radius: 8px;
      height: 155px;
      max-width: 100%;
    }

    /* Connect badges */
    .md-connect {
      display: flex;
      gap: 8px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .connect-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #fff;
      text-decoration: none;
      transition: transform 0.15s, opacity 0.15s;
    }
    .connect-badge:hover { transform: translateY(-2px); opacity: 0.9; }

    /* Footer */
    .md-footer {
      text-align: center;
      margin-top: 8px;
      font-size: 13px;
      color: #8b949e;
    }
    .md-footer .views-badge {
      display: inline-block;
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 20px;
      padding: 3px 12px;
      font-size: 12px;
      color: #bc13fe;
      font-family: 'Fira Code', monospace;
    }
  </style>
</head>
<body>

  <!-- GitHub top bar -->
  <div class="gh-topbar">
    <svg class="gh-logo" height="32" viewBox="0 0 16 16" width="32">
      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
    </svg>
    <div class="gh-topbar-pill">
      <span>noadanon220</span> / <span>noadanon220</span>
    </div>
  </div>

  <!-- Layout -->
  <div class="gh-layout">

    <!-- Sidebar -->
    <aside class="gh-sidebar">
      <div class="gh-avatar">🐾</div>
      <h1>Noa Danon</h1>
      <div class="gh-username">noadanon220</div>
      <div class="gh-bio">CS Student @ Afeka · Android &amp; Full-Stack Developer · Design background 🎨→💻</div>
      <button class="gh-follow-btn">Follow</button>
      <div class="gh-followers">
        <div><strong>–</strong> <span>followers</span></div>
        <div><strong>–</strong> <span>following</span></div>
      </div>
      <div class="gh-meta">
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM6.379 5.227A4.5 4.5 0 0110.5 8a4.5 4.5 0 01-4.121 4.492c-.353-.169-.654-.437-.854-.775a3 3 0 11-.01-5.442c.195-.333.493-.598.864-.048z"/></svg>
          Afeka College of Engineering
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"/></svg>
          <a href="#">noadanon220.github.io/noa-danon-portfolio</a>
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 4.75C0 3.784.784 3 1.75 3h12.5c.966 0 1.75.784 1.75 1.75v7.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-7.5zM1.75 4.5a.25.25 0 00-.25.25v.463l6.5 3.25 6.5-3.25V4.75a.25.25 0 00-.25-.25H1.75zM14 6.917l-5.834 2.917a1.25 1.25 0 01-1.332 0L1 6.917V12.25c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25V6.917z"/></svg>
          <a href="#">noadanon220@gmail.com</a>
        </div>
      </div>
    </aside>

    <!-- Main -->
    <main class="gh-main">
      <div class="gh-tabs">
        <div class="gh-tab active">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"/></svg>
          Overview
        </div>
        <div class="gh-tab">Repositories <span class="gh-tab-count">4</span></div>
        <div class="gh-tab">Projects</div>
        <div class="gh-tab">Stars</div>
      </div>

      <!-- README box -->
      <div class="gh-readme-box">
        <div class="gh-readme-header">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 2.75C0 1.784.784 1 1.75 1h12.5c.966 0 1.75.784 1.75 1.75v9.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-9.5zm1.75-.25a.25.25 0 00-.25.25v9.5c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25v-9.5a.25.25 0 00-.25-.25H1.75z"/><path d="M8 4a.75.75 0 01.75.75v3.5h1.5a.75.75 0 010 1.5h-4.5a.75.75 0 010-1.5h1.5v-3.5A.75.75 0 018 4z"/></svg>
          noadanon220 / README.md
        </div>
        <div class="gh-readme-body md">

          <!-- ══ SVG HEADER ══ -->
          <div class="md-header-svg">
            <svg width="860" height="280" viewBox="0 0 900 300" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <style>
                  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&display=swap');
                  .bg-rect2 { fill: #0d0221; }
                  .main-title2 {
                    font-family: 'Orbitron', sans-serif;
                    font-size: 80px;
                    fill: #bc13fe;
                    filter: drop-shadow(0 0 10px #bc13fe);
                    text-transform: uppercase;
                    animation: glitch2 3s infinite;
                  }
                  @keyframes glitch2 {
                    0%,6%,100% { transform: translate(0); }
                    2%         { transform: translate(-2px, 2px); }
                    4%         { transform: translate(2px, -2px); }
                  }
                  .floating-cat2 {
                    fill: none; stroke: #bc13fe; stroke-width: 1.5; opacity: 0.4;
                    filter: drop-shadow(0 0 5px #bc13fe);
                    animation: float2 6s infinite ease-in-out;
                  }
                  @keyframes float2 {
                    0%,100% { transform: translateY(0) rotate(0deg); }
                    50%      { transform: translateY(-20px) rotate(10deg); }
                  }
                  .scanner2 {
                    stroke: #bc13fe; stroke-width: 2;
                    filter: drop-shadow(0 0 15px #bc13fe);
                    animation: scan2 4s infinite linear;
                  }
                  @keyframes scan2 {
                    0%   { y1: 50;  y2: 50;  opacity: 0; }
                    50%  { opacity: 1; }
                    100% { y1: 250; y2: 250; opacity: 0; }
                  }
                </style>
              </defs>
              <rect width="900" height="300" class="bg-rect2" rx="15" />
              <g class="floating-cat2" style="animation-delay: 0s;">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <g class="floating-cat2" style="animation-delay: 2s; transform: translate(650px, 150px) scale(0.8);">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <text x="50%" y="150" dominant-baseline="middle" text-anchor="middle" class="main-title2">NOA DANON</text>
              <text x="50%" y="210" dominant-baseline="middle" text-anchor="middle" fill="#d896ff" font-family="monospace" font-size="18">&gt; INITIALIZING_CREATIVE_SYSTEM... [DONE]</text>
              <line x1="100" y1="50" x2="800" y2="50" class="scanner2" />
            </svg>
          </div>

          <!-- Typing line -->
          <div class="md-typing" id="typing-line"></div>

          <hr/>

          <!-- About -->
          <h2>👾 About Me</h2>
          <pre><span class="kw">const</span> <span class="key">noa</span>: <span class="ty">Developer</span> = {
  <span class="key">education</span>:  <span class="str">"B.Sc. Computer Science — Afeka College of Engineering (2022–2025)"</span>,
  <span class="key">background</span>: <span class="arr">[</span><span class="str">"Diploma in Animation &amp; Design"</span>, <span class="str">"Freelance Graphic Designer (2019–2022)"</span><span class="arr">]</span>,
  <span class="key">focus</span>:      <span class="arr">[</span><span class="str">"Android Dev"</span>, <span class="str">"Full-Stack"</span>, <span class="str">"AI &amp; Algorithms"</span><span class="arr">]</span>,
  <span class="key">languages</span>:  <span class="arr">[</span><span class="str">"Java"</span>, <span class="str">"Kotlin"</span>, <span class="str">"C++"</span>, <span class="str">"Python"</span>, <span class="str">"TypeScript"</span>, <span class="str">"JavaScript"</span><span class="arr">]</span>,
  <span class="key">design</span>:     <span class="arr">[</span><span class="str">"Figma"</span>, <span class="str">"Illustrator"</span>, <span class="str">"Photoshop"</span>, <span class="str">"After Effects"</span><span class="arr">]</span>,
  <span class="key">funFact</span>:    <span class="str">"Graphic designer turned engineer 🎨→💻"</span>,
};</pre>

          <hr/>

          <!-- Tech Stack -->
          <h2>🛠️ Tech Stack</h2>

          <h3>Languages</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#ED8B00;">☕ Java</span>
            <span class="md-badge" style="background:#A97142;">🤖 Kotlin</span>
            <span class="md-badge" style="background:#3670A0;">🐍 Python</span>
            <span class="md-badge" style="background:#007ACC;">🔷 TypeScript</span>
            <span class="md-badge" style="background:#F0DB4F;color:#323330;">📜 JavaScript</span>
            <span class="md-badge" style="background:#00599C;">⚙️ C++</span>
            <span class="md-badge" style="background:#555;">© C</span>
          </div>

          <h3>Mobile &amp; Frontend</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#3DDC84;color:#111;">🤖 Android SDK</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">🧩 Jetpack Compose</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">⚛️ React</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">📱 React Native</span>
            <span class="md-badge" style="background:#E34F26;">🌐 HTML</span>
            <span class="md-badge" style="background:#1572B6;">🎨 CSS</span>
          </div>

          <h3>Backend &amp; Tools</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#039BE5;">🔥 Firebase</span>
            <span class="md-badge" style="background:#4285F4;">🗺️ Google Maps API</span>
            <span class="md-badge" style="background:#F05033;">🔀 Git</span>
            <span class="md-badge" style="background:#2496ED;">🐳 Docker</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">📱 Android Studio</span>
          </div>

          <h3>Design</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#F24E1E;">🎨 Figma</span>
            <span class="md-badge" style="background:#FF9A00;">🖌️ Illustrator</span>
            <span class="md-badge" style="background:#31A8FF;">🖼️ Photoshop</span>
            <span class="md-badge" style="background:#9999FF;">✨ After Effects</span>
            <span class="md-badge" style="background:#FF0000;">📖 InDesign</span>
          </div>

          <hr/>

          <!-- Projects -->
          <h2>🚀 Featured Projects</h2>
          <table class="md-table">
            <thead>
              <tr>
                <th>Project</th>
                <th>Description</th>
                <th>Stack</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>🐾 <a href="#">Paws</a></td>
                <td>Android pet-care app — manage walks, vet visits &amp; feeding times, built from scratch</td>
                <td><span class="code-tag">Kotlin</span> <span class="code-tag">Firebase</span> <span class="code-tag">Jetpack</span></td>
              </tr>
              <tr>
                <td>🤖 <a href="#">AI Tactical Combat Sim</a></td>
                <td>2D strategic AI game with autonomous units using A*, BFS &amp; FSM algorithms</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">OpenGL</span></td>
              </tr>
              <tr>
                <td>🏦 <a href="#">Bank System</a></td>
                <td>Console banking app simulating multi-account management &amp; client operations</td>
                <td><span class="code-tag">Java</span> <span class="code-tag">OOP</span></td>
              </tr>
              <tr>
                <td>🧩 <a href="#">Rubik's Cube Solver</a></td>
                <td>Interactive cube simulation with real-time 3D rendering &amp; solving logic</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">SFML</span></td>
              </tr>
              <tr>
                <td>✨ <a href="#">Gemini Clone</a></td>
                <td>Fully functional AI chat interface — responsive UI &amp; real-time history</td>
                <td><span class="code-tag">React</span> <span class="code-tag">Gen AI SDK</span></td>
              </tr>
            </tbody>
          </table>

          <hr/>

          <!-- GitHub Stats -->
          <h2>📊 GitHub Stats</h2>
          <div class="md-stats">

            <!-- Stats card -->
            <svg width="495" height="155" viewBox="0 0 495 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="495" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="20" y="30" fill="#bc13fe" font-family="monospace" font-size="14" font-weight="700">noadanon220's GitHub Stats</text>
              <line x1="20" y1="38" x2="475" y2="38" stroke="#21262d" stroke-width="1"/>
              <!-- icons + labels -->
              <text x="20" y="62" fill="#8b949e" font-family="monospace" font-size="12">⭐ Total Stars</text>
              <text x="370" y="62" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="85" fill="#8b949e" font-family="monospace" font-size="12">🔀 Total Commits</text>
              <text x="370" y="85" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="108" fill="#8b949e" font-family="monospace" font-size="12">🐛 Issues</text>
              <text x="370" y="108" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="131" fill="#8b949e" font-family="monospace" font-size="12">🔁 Pull Requests</text>
              <text x="370" y="131" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
            </svg>

            <!-- Top Languages card -->
            <svg width="330" height="155" viewBox="0 0 330 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="330" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="16" y="28" fill="#bc13fe" font-family="monospace" font-size="13" font-weight="700">Most Used Languages</text>
              <line x1="16" y1="36" x2="314" y2="36" stroke="#21262d" stroke-width="1"/>

              <!-- Java -->
              <rect x="16" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="48" width="72" height="7" rx="3" fill="#ED8B00"/>
              <text x="16" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">Java <tspan fill="#8b949e">34%</tspan></text>

              <!-- C++ -->
              <rect x="130" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="48" width="60" height="7" rx="3" fill="#00599C"/>
              <text x="130" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">C++ <tspan fill="#8b949e">28%</tspan></text>

              <!-- Kotlin -->
              <rect x="16" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="88" width="45" height="7" rx="3" fill="#A97142"/>
              <text x="16" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Kotlin <tspan fill="#8b949e">18%</tspan></text>

              <!-- Python -->
              <rect x="130" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="88" width="30" height="7" rx="3" fill="#3670A0"/>
              <text x="130" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Python <tspan fill="#8b949e">12%</tspan></text>

              <!-- JS / TS -->
              <rect x="16" y="126" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="126" width="20" height="7" rx="3" fill="#F0DB4F"/>
              <text x="16" y="148" fill="#c9d1d9" font-family="monospace" font-size="11">JS/TS <tspan fill="#8b949e">8%</tspan></text>
            </svg>

          </div>

          <hr/>

          <!-- Connect -->
          <h2>🌐 Connect</h2>
          <div class="md-connect">
            <a class="connect-badge" style="background:#0077B5;" href="https://www.linkedin.com/in/noadanon/" target="_blank">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              LinkedIn
            </a>
            <a class="connect-badge" style="background:#181717;border:1px solid #444;" href="https://github.com/noadanon220" target="_blank">
              <svg width="14" height="14" viewBox="0 0 16 16" fill="white"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
              GitHub
            </a>
            <a class="connect-badge" style="background:#bc13fe;" href="https://noadanon220.github.io/noa-danon-portfolio" target="_blank">
              🌐 Portfolio
            </a>
            <a class="connect-badge" style="background:#D14836;" href="mailto:noadanon220@gmail.com">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
              Email
            </a>
          </div>

          <hr/>

          <!-- Footer -->
          <div class="md-footer">
            <div class="views-badge">👁 profile views: noadanon220</div>
            <br/><br/>
            <span style="font-size:13px; color:#484f58;">built with ♥ — and my dog 🐾</span>
          </div>

        </div><!-- /readme-body -->
      </div><!-- /readme-box -->
    </main>
  </div>

  <script>
    // Typing animation
    const lines = [
      "CS Student @ Afeka College",
      "Android & Full-Stack Developer",
      "Design Background 🎨 → 💻",
      "AI & Algorithms Enthusiast 🤖",
      "Always building something new ✨",
    ];
    let lineIdx = 0, charIdx = 0, deleting = false;
    const el = document.getElementById('typing-line');

    function tick() {
      const line = lines[lineIdx];
      if (!deleting) {
        charIdx++;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === line.length) {
          deleting = true;
          setTimeout(tick, 2000);
          return;
        }
      } else {
        charIdx--;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === 0) {
          deleting = false;
          lineIdx = (lineIdx + 1) % lines.length;
        }
      }
      setTimeout(tick, deleting ? 40 : 70);
    }
    tick();
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GitHub Profile README — Noa Danon</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Fira+Code:wght@400;500&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: #010409;
      color: #e6edf3;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Helvetica, Arial, sans-serif;
      font-size: 16px;
      line-height: 1.5;
    }

    /* ── GitHub chrome simulation ── */
    .gh-topbar {
      height: 62px;
      background: #161b22;
      border-bottom: 1px solid #21262d;
      display: flex;
      align-items: center;
      padding: 0 32px;
      gap: 16px;
    }
    .gh-logo { fill: #e6edf3; }
    .gh-topbar-pill {
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 5px 12px;
      font-size: 14px;
      color: #8b949e;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-topbar-pill span { color: #58a6ff; }

    /* ── Profile sidebar + main layout ── */
    .gh-layout {
      max-width: 1280px;
      margin: 32px auto;
      padding: 0 32px;
      display: grid;
      grid-template-columns: 296px 1fr;
      gap: 32px;
      align-items: start;
    }

    /* ── Sidebar ── */
    .gh-sidebar {}
    .gh-avatar {
      width: 296px;
      height: 296px;
      border-radius: 50%;
      background: linear-gradient(135deg, #1a0533, #0d0221);
      border: 1px solid #30363d;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      margin-bottom: 16px;
      overflow: hidden;
    }
    .gh-sidebar h1 {
      font-size: 26px;
      font-weight: 600;
      color: #e6edf3;
      line-height: 1.25;
    }
    .gh-sidebar .gh-username {
      font-size: 20px;
      font-weight: 300;
      color: #8b949e;
      margin: 4px 0 16px;
    }
    .gh-sidebar .gh-bio {
      font-size: 15px;
      color: #8b949e;
      margin-bottom: 16px;
      line-height: 1.5;
    }
    .gh-follow-btn {
      display: block;
      width: 100%;
      background: #21262d;
      border: 1px solid #363b42;
      color: #e6edf3;
      border-radius: 6px;
      padding: 5px 16px;
      font-size: 14px;
      font-weight: 600;
      text-align: center;
      cursor: pointer;
      margin-bottom: 16px;
      transition: background 0.15s, border-color 0.15s;
    }
    .gh-follow-btn:hover { background: #30363d; border-color: #484f58; }
    .gh-meta { display: flex; flex-direction: column; gap: 8px; margin-top: 16px; }
    .gh-meta-item {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      color: #8b949e;
    }
    .gh-meta-item svg { flex-shrink: 0; }
    .gh-meta-item a { color: #58a6ff; text-decoration: none; }
    .gh-meta-item a:hover { text-decoration: underline; }
    .gh-followers {
      display: flex;
      gap: 16px;
      font-size: 14px;
      color: #e6edf3;
      margin-top: 16px;
    }
    .gh-followers span { color: #8b949e; }

    /* ── Main content ── */
    .gh-main {}

    /* ── Tab bar ── */
    .gh-tabs {
      display: flex;
      gap: 0;
      border-bottom: 1px solid #21262d;
      margin-bottom: 24px;
    }
    .gh-tab {
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #8b949e;
      cursor: pointer;
      border-bottom: 2px solid transparent;
      margin-bottom: -1px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-tab.active { color: #e6edf3; border-bottom-color: #f78166; }
    .gh-tab-count {
      background: #21262d;
      border-radius: 20px;
      padding: 1px 7px;
      font-size: 12px;
      font-weight: 500;
    }

    /* ── README box ── */
    .gh-readme-box {
      background: #0d1117;
      border: 1px solid #21262d;
      border-radius: 6px;
      overflow: hidden;
    }
    .gh-readme-header {
      background: #161b22;
      border-bottom: 1px solid #21262d;
      padding: 10px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      font-weight: 600;
      color: #e6edf3;
    }
    .gh-readme-header svg { color: #8b949e; }
    .gh-readme-body {
      padding: 32px 40px;
    }

    /* ─────────────────────────────────────────
       MARKDOWN CONTENT STYLES
    ───────────────────────────────────────── */
    .md { color: #e6edf3; }
    .md-center { text-align: center; }

    /* SVG header */
    .md-header-svg {
      display: flex;
      justify-content: center;
      margin-bottom: 4px;
    }
    .md-header-svg svg { max-width: 100%; border-radius: 15px; }

    /* Typing line */
    .md-typing {
      text-align: center;
      font-family: 'Fira Code', monospace;
      font-size: 17px;
      color: #bc13fe;
      margin: 10px 0 28px;
      min-height: 28px;
    }
    .md-cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: #bc13fe;
      vertical-align: text-bottom;
      animation: blink 0.8s step-end infinite;
      margin-left: 2px;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* HR */
    .md hr { border: none; border-top: 1px solid #21262d; margin: 24px 0; }

    /* Headings */
    .md h2 {
      font-size: 22px;
      font-weight: 600;
      color: #e6edf3;
      border-bottom: 1px solid #21262d;
      padding-bottom: 8px;
      margin: 32px 0 16px;
    }
    .md h3 {
      font-size: 18px;
      font-weight: 600;
      color: #e6edf3;
      margin: 20px 0 12px;
    }

    /* Code block */
    .md pre {
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 16px;
      overflow-x: auto;
      font-family: 'Fira Code', monospace;
      font-size: 13px;
      line-height: 1.7;
      color: #c9d1d9;
      margin: 16px 0;
    }
    .md pre .kw  { color: #ff7b72; }
    .md pre .ty  { color: #ffa657; }
    .md pre .str { color: #a5d6ff; }
    .md pre .cm  { color: #8b949e; }
    .md pre .key { color: #79c0ff; }
    .md pre .arr { color: #bc13fe; }

    /* Badges row */
    .md-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin: 8px 0 16px;
    }
    .md-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 5px 12px;
      font-size: 13px;
      font-weight: 600;
      font-family: 'Inter', sans-serif;
      color: #fff;
      cursor: default;
      transition: transform 0.15s, opacity 0.15s;
    }
    .md-badge:hover { transform: translateY(-1px); opacity: 0.9; }

    /* Table */
    .md-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
      margin: 16px 0;
    }
    .md-table th {
      background: #161b22;
      color: #8b949e;
      font-weight: 600;
      text-align: left;
      padding: 8px 16px;
      border-bottom: 1px solid #21262d;
    }
    .md-table td {
      padding: 10px 16px;
      border-bottom: 1px solid #21262d;
      color: #c9d1d9;
      font-size: 14px;
      vertical-align: top;
    }
    .md-table tr:hover td { background: #161b22; }
    .md-table td a { color: #58a6ff; text-decoration: none; font-weight: 600; }
    .md-table td a:hover { text-decoration: underline; }
    .code-tag {
      font-family: 'Fira Code', monospace;
      font-size: 12px;
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 4px;
      padding: 1px 6px;
      color: #bc13fe;
      margin: 0 2px;
      white-space: nowrap;
    }

    /* Stats images */
    .md-stats {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .md-stats img {
      border-radius: 8px;
      height: 155px;
      max-width: 100%;
    }

    /* Connect badges */
    .md-connect {
      display: flex;
      gap: 8px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .connect-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #fff;
      text-decoration: none;
      transition: transform 0.15s, opacity 0.15s;
    }
    .connect-badge:hover { transform: translateY(-2px); opacity: 0.9; }

    /* Footer */
    .md-footer {
      text-align: center;
      margin-top: 8px;
      font-size: 13px;
      color: #8b949e;
    }
    .md-footer .views-badge {
      display: inline-block;
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 20px;
      padding: 3px 12px;
      font-size: 12px;
      color: #bc13fe;
      font-family: 'Fira Code', monospace;
    }
  </style>
</head>
<body>

  <!-- GitHub top bar -->
  <div class="gh-topbar">
    <svg class="gh-logo" height="32" viewBox="0 0 16 16" width="32">
      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
    </svg>
    <div class="gh-topbar-pill">
      <span>noadanon220</span> / <span>noadanon220</span>
    </div>
  </div>

  <!-- Layout -->
  <div class="gh-layout">

    <!-- Sidebar -->
    <aside class="gh-sidebar">
      <div class="gh-avatar">🐾</div>
      <h1>Noa Danon</h1>
      <div class="gh-username">noadanon220</div>
      <div class="gh-bio">CS Student @ Afeka · Android &amp; Full-Stack Developer · Design background 🎨→💻</div>
      <button class="gh-follow-btn">Follow</button>
      <div class="gh-followers">
        <div><strong>–</strong> <span>followers</span></div>
        <div><strong>–</strong> <span>following</span></div>
      </div>
      <div class="gh-meta">
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM6.379 5.227A4.5 4.5 0 0110.5 8a4.5 4.5 0 01-4.121 4.492c-.353-.169-.654-.437-.854-.775a3 3 0 11-.01-5.442c.195-.333.493-.598.864-.048z"/></svg>
          Afeka College of Engineering
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"/></svg>
          <a href="#">noadanon220.github.io/noa-danon-portfolio</a>
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 4.75C0 3.784.784 3 1.75 3h12.5c.966 0 1.75.784 1.75 1.75v7.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-7.5zM1.75 4.5a.25.25 0 00-.25.25v.463l6.5 3.25 6.5-3.25V4.75a.25.25 0 00-.25-.25H1.75zM14 6.917l-5.834 2.917a1.25 1.25 0 01-1.332 0L1 6.917V12.25c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25V6.917z"/></svg>
          <a href="#">noadanon220@gmail.com</a>
        </div>
      </div>
    </aside>

    <!-- Main -->
    <main class="gh-main">
      <div class="gh-tabs">
        <div class="gh-tab active">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"/></svg>
          Overview
        </div>
        <div class="gh-tab">Repositories <span class="gh-tab-count">4</span></div>
        <div class="gh-tab">Projects</div>
        <div class="gh-tab">Stars</div>
      </div>

      <!-- README box -->
      <div class="gh-readme-box">
        <div class="gh-readme-header">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 2.75C0 1.784.784 1 1.75 1h12.5c.966 0 1.75.784 1.75 1.75v9.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-9.5zm1.75-.25a.25.25 0 00-.25.25v9.5c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25v-9.5a.25.25 0 00-.25-.25H1.75z"/><path d="M8 4a.75.75 0 01.75.75v3.5h1.5a.75.75 0 010 1.5h-4.5a.75.75 0 010-1.5h1.5v-3.5A.75.75 0 018 4z"/></svg>
          noadanon220 / README.md
        </div>
        <div class="gh-readme-body md">

          <!-- ══ SVG HEADER ══ -->
          <div class="md-header-svg">
            <svg width="860" height="280" viewBox="0 0 900 300" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <style>
                  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&display=swap');
                  .bg-rect2 { fill: #0d0221; }
                  .main-title2 {
                    font-family: 'Orbitron', sans-serif;
                    font-size: 80px;
                    fill: #bc13fe;
                    filter: drop-shadow(0 0 10px #bc13fe);
                    text-transform: uppercase;
                    animation: glitch2 3s infinite;
                  }
                  @keyframes glitch2 {
                    0%,6%,100% { transform: translate(0); }
                    2%         { transform: translate(-2px, 2px); }
                    4%         { transform: translate(2px, -2px); }
                  }
                  .floating-cat2 {
                    fill: none; stroke: #bc13fe; stroke-width: 1.5; opacity: 0.4;
                    filter: drop-shadow(0 0 5px #bc13fe);
                    animation: float2 6s infinite ease-in-out;
                  }
                  @keyframes float2 {
                    0%,100% { transform: translateY(0) rotate(0deg); }
                    50%      { transform: translateY(-20px) rotate(10deg); }
                  }
                  .scanner2 {
                    stroke: #bc13fe; stroke-width: 2;
                    filter: drop-shadow(0 0 15px #bc13fe);
                    animation: scan2 4s infinite linear;
                  }
                  @keyframes scan2 {
                    0%   { y1: 50;  y2: 50;  opacity: 0; }
                    50%  { opacity: 1; }
                    100% { y1: 250; y2: 250; opacity: 0; }
                  }
                </style>
              </defs>
              <rect width="900" height="300" class="bg-rect2" rx="15" />
              <g class="floating-cat2" style="animation-delay: 0s;">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <g class="floating-cat2" style="animation-delay: 2s; transform: translate(650px, 150px) scale(0.8);">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <text x="50%" y="150" dominant-baseline="middle" text-anchor="middle" class="main-title2">NOA DANON</text>
              <text x="50%" y="210" dominant-baseline="middle" text-anchor="middle" fill="#d896ff" font-family="monospace" font-size="18">&gt; INITIALIZING_CREATIVE_SYSTEM... [DONE]</text>
              <line x1="100" y1="50" x2="800" y2="50" class="scanner2" />
            </svg>
          </div>

          <!-- Typing line -->
          <div class="md-typing" id="typing-line"></div>

          <hr/>

          <!-- About -->
          <h2>👾 About Me</h2>
          <pre><span class="kw">const</span> <span class="key">noa</span>: <span class="ty">Developer</span> = {
  <span class="key">education</span>:  <span class="str">"B.Sc. Computer Science — Afeka College of Engineering (2022–2025)"</span>,
  <span class="key">background</span>: <span class="arr">[</span><span class="str">"Diploma in Animation &amp; Design"</span>, <span class="str">"Freelance Graphic Designer (2019–2022)"</span><span class="arr">]</span>,
  <span class="key">focus</span>:      <span class="arr">[</span><span class="str">"Android Dev"</span>, <span class="str">"Full-Stack"</span>, <span class="str">"AI &amp; Algorithms"</span><span class="arr">]</span>,
  <span class="key">languages</span>:  <span class="arr">[</span><span class="str">"Java"</span>, <span class="str">"Kotlin"</span>, <span class="str">"C++"</span>, <span class="str">"Python"</span>, <span class="str">"TypeScript"</span>, <span class="str">"JavaScript"</span><span class="arr">]</span>,
  <span class="key">design</span>:     <span class="arr">[</span><span class="str">"Figma"</span>, <span class="str">"Illustrator"</span>, <span class="str">"Photoshop"</span>, <span class="str">"After Effects"</span><span class="arr">]</span>,
  <span class="key">funFact</span>:    <span class="str">"Graphic designer turned engineer 🎨→💻"</span>,
};</pre>

          <hr/>

          <!-- Tech Stack -->
          <h2>🛠️ Tech Stack</h2>

          <h3>Languages</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#ED8B00;">☕ Java</span>
            <span class="md-badge" style="background:#A97142;">🤖 Kotlin</span>
            <span class="md-badge" style="background:#3670A0;">🐍 Python</span>
            <span class="md-badge" style="background:#007ACC;">🔷 TypeScript</span>
            <span class="md-badge" style="background:#F0DB4F;color:#323330;">📜 JavaScript</span>
            <span class="md-badge" style="background:#00599C;">⚙️ C++</span>
            <span class="md-badge" style="background:#555;">© C</span>
          </div>

          <h3>Mobile &amp; Frontend</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#3DDC84;color:#111;">🤖 Android SDK</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">🧩 Jetpack Compose</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">⚛️ React</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">📱 React Native</span>
            <span class="md-badge" style="background:#E34F26;">🌐 HTML</span>
            <span class="md-badge" style="background:#1572B6;">🎨 CSS</span>
          </div>

          <h3>Backend &amp; Tools</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#039BE5;">🔥 Firebase</span>
            <span class="md-badge" style="background:#4285F4;">🗺️ Google Maps API</span>
            <span class="md-badge" style="background:#F05033;">🔀 Git</span>
            <span class="md-badge" style="background:#2496ED;">🐳 Docker</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">📱 Android Studio</span>
          </div>

          <h3>Design</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#F24E1E;">🎨 Figma</span>
            <span class="md-badge" style="background:#FF9A00;">🖌️ Illustrator</span>
            <span class="md-badge" style="background:#31A8FF;">🖼️ Photoshop</span>
            <span class="md-badge" style="background:#9999FF;">✨ After Effects</span>
            <span class="md-badge" style="background:#FF0000;">📖 InDesign</span>
          </div>

          <hr/>

          <!-- Projects -->
          <h2>🚀 Featured Projects</h2>
          <table class="md-table">
            <thead>
              <tr>
                <th>Project</th>
                <th>Description</th>
                <th>Stack</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>🐾 <a href="#">Paws</a></td>
                <td>Android pet-care app — manage walks, vet visits &amp; feeding times, built from scratch</td>
                <td><span class="code-tag">Kotlin</span> <span class="code-tag">Firebase</span> <span class="code-tag">Jetpack</span></td>
              </tr>
              <tr>
                <td>🤖 <a href="#">AI Tactical Combat Sim</a></td>
                <td>2D strategic AI game with autonomous units using A*, BFS &amp; FSM algorithms</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">OpenGL</span></td>
              </tr>
              <tr>
                <td>🏦 <a href="#">Bank System</a></td>
                <td>Console banking app simulating multi-account management &amp; client operations</td>
                <td><span class="code-tag">Java</span> <span class="code-tag">OOP</span></td>
              </tr>
              <tr>
                <td>🧩 <a href="#">Rubik's Cube Solver</a></td>
                <td>Interactive cube simulation with real-time 3D rendering &amp; solving logic</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">SFML</span></td>
              </tr>
              <tr>
                <td>✨ <a href="#">Gemini Clone</a></td>
                <td>Fully functional AI chat interface — responsive UI &amp; real-time history</td>
                <td><span class="code-tag">React</span> <span class="code-tag">Gen AI SDK</span></td>
              </tr>
            </tbody>
          </table>

          <hr/>

          <!-- GitHub Stats -->
          <h2>📊 GitHub Stats</h2>
          <div class="md-stats">

            <!-- Stats card -->
            <svg width="495" height="155" viewBox="0 0 495 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="495" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="20" y="30" fill="#bc13fe" font-family="monospace" font-size="14" font-weight="700">noadanon220's GitHub Stats</text>
              <line x1="20" y1="38" x2="475" y2="38" stroke="#21262d" stroke-width="1"/>
              <!-- icons + labels -->
              <text x="20" y="62" fill="#8b949e" font-family="monospace" font-size="12">⭐ Total Stars</text>
              <text x="370" y="62" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="85" fill="#8b949e" font-family="monospace" font-size="12">🔀 Total Commits</text>
              <text x="370" y="85" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="108" fill="#8b949e" font-family="monospace" font-size="12">🐛 Issues</text>
              <text x="370" y="108" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="131" fill="#8b949e" font-family="monospace" font-size="12">🔁 Pull Requests</text>
              <text x="370" y="131" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
            </svg>

            <!-- Top Languages card -->
            <svg width="330" height="155" viewBox="0 0 330 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="330" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="16" y="28" fill="#bc13fe" font-family="monospace" font-size="13" font-weight="700">Most Used Languages</text>
              <line x1="16" y1="36" x2="314" y2="36" stroke="#21262d" stroke-width="1"/>

              <!-- Java -->
              <rect x="16" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="48" width="72" height="7" rx="3" fill="#ED8B00"/>
              <text x="16" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">Java <tspan fill="#8b949e">34%</tspan></text>

              <!-- C++ -->
              <rect x="130" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="48" width="60" height="7" rx="3" fill="#00599C"/>
              <text x="130" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">C++ <tspan fill="#8b949e">28%</tspan></text>

              <!-- Kotlin -->
              <rect x="16" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="88" width="45" height="7" rx="3" fill="#A97142"/>
              <text x="16" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Kotlin <tspan fill="#8b949e">18%</tspan></text>

              <!-- Python -->
              <rect x="130" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="88" width="30" height="7" rx="3" fill="#3670A0"/>
              <text x="130" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Python <tspan fill="#8b949e">12%</tspan></text>

              <!-- JS / TS -->
              <rect x="16" y="126" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="126" width="20" height="7" rx="3" fill="#F0DB4F"/>
              <text x="16" y="148" fill="#c9d1d9" font-family="monospace" font-size="11">JS/TS <tspan fill="#8b949e">8%</tspan></text>
            </svg>

          </div>

          <hr/>

          <!-- Connect -->
          <h2>🌐 Connect</h2>
          <div class="md-connect">
            <a class="connect-badge" style="background:#0077B5;" href="https://www.linkedin.com/in/noadanon/" target="_blank">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              LinkedIn
            </a>
            <a class="connect-badge" style="background:#181717;border:1px solid #444;" href="https://github.com/noadanon220" target="_blank">
              <svg width="14" height="14" viewBox="0 0 16 16" fill="white"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
              GitHub
            </a>
            <a class="connect-badge" style="background:#bc13fe;" href="https://noadanon220.github.io/noa-danon-portfolio" target="_blank">
              🌐 Portfolio
            </a>
            <a class="connect-badge" style="background:#D14836;" href="mailto:noadanon220@gmail.com">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
              Email
            </a>
          </div>

          <hr/>

          <!-- Footer -->
          <div class="md-footer">
            <div class="views-badge">👁 profile views: noadanon220</div>
            <br/><br/>
            <span style="font-size:13px; color:#484f58;">built with ♥ — and my dog 🐾</span>
          </div>

        </div><!-- /readme-body -->
      </div><!-- /readme-box -->
    </main>
  </div>

  <script>
    // Typing animation
    const lines = [
      "CS Student @ Afeka College",
      "Android & Full-Stack Developer",
      "Design Background 🎨 → 💻",
      "AI & Algorithms Enthusiast 🤖",
      "Always building something new ✨",
    ];
    let lineIdx = 0, charIdx = 0, deleting = false;
    const el = document.getElementById('typing-line');

    function tick() {
      const line = lines[lineIdx];
      if (!deleting) {
        charIdx++;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === line.length) {
          deleting = true;
          setTimeout(tick, 2000);
          return;
        }
      } else {
        charIdx--;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === 0) {
          deleting = false;
          lineIdx = (lineIdx + 1) % lines.length;
        }
      }
      setTimeout(tick, deleting ? 40 : 70);
    }
    tick();
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GitHub Profile README — Noa Danon</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Fira+Code:wght@400;500&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: #010409;
      color: #e6edf3;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Helvetica, Arial, sans-serif;
      font-size: 16px;
      line-height: 1.5;
    }

    /* ── GitHub chrome simulation ── */
    .gh-topbar {
      height: 62px;
      background: #161b22;
      border-bottom: 1px solid #21262d;
      display: flex;
      align-items: center;
      padding: 0 32px;
      gap: 16px;
    }
    .gh-logo { fill: #e6edf3; }
    .gh-topbar-pill {
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 5px 12px;
      font-size: 14px;
      color: #8b949e;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-topbar-pill span { color: #58a6ff; }

    /* ── Profile sidebar + main layout ── */
    .gh-layout {
      max-width: 1280px;
      margin: 32px auto;
      padding: 0 32px;
      display: grid;
      grid-template-columns: 296px 1fr;
      gap: 32px;
      align-items: start;
    }

    /* ── Sidebar ── */
    .gh-sidebar {}
    .gh-avatar {
      width: 296px;
      height: 296px;
      border-radius: 50%;
      background: linear-gradient(135deg, #1a0533, #0d0221);
      border: 1px solid #30363d;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      margin-bottom: 16px;
      overflow: hidden;
    }
    .gh-sidebar h1 {
      font-size: 26px;
      font-weight: 600;
      color: #e6edf3;
      line-height: 1.25;
    }
    .gh-sidebar .gh-username {
      font-size: 20px;
      font-weight: 300;
      color: #8b949e;
      margin: 4px 0 16px;
    }
    .gh-sidebar .gh-bio {
      font-size: 15px;
      color: #8b949e;
      margin-bottom: 16px;
      line-height: 1.5;
    }
    .gh-follow-btn {
      display: block;
      width: 100%;
      background: #21262d;
      border: 1px solid #363b42;
      color: #e6edf3;
      border-radius: 6px;
      padding: 5px 16px;
      font-size: 14px;
      font-weight: 600;
      text-align: center;
      cursor: pointer;
      margin-bottom: 16px;
      transition: background 0.15s, border-color 0.15s;
    }
    .gh-follow-btn:hover { background: #30363d; border-color: #484f58; }
    .gh-meta { display: flex; flex-direction: column; gap: 8px; margin-top: 16px; }
    .gh-meta-item {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      color: #8b949e;
    }
    .gh-meta-item svg { flex-shrink: 0; }
    .gh-meta-item a { color: #58a6ff; text-decoration: none; }
    .gh-meta-item a:hover { text-decoration: underline; }
    .gh-followers {
      display: flex;
      gap: 16px;
      font-size: 14px;
      color: #e6edf3;
      margin-top: 16px;
    }
    .gh-followers span { color: #8b949e; }

    /* ── Main content ── */
    .gh-main {}

    /* ── Tab bar ── */
    .gh-tabs {
      display: flex;
      gap: 0;
      border-bottom: 1px solid #21262d;
      margin-bottom: 24px;
    }
    .gh-tab {
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #8b949e;
      cursor: pointer;
      border-bottom: 2px solid transparent;
      margin-bottom: -1px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-tab.active { color: #e6edf3; border-bottom-color: #f78166; }
    .gh-tab-count {
      background: #21262d;
      border-radius: 20px;
      padding: 1px 7px;
      font-size: 12px;
      font-weight: 500;
    }

    /* ── README box ── */
    .gh-readme-box {
      background: #0d1117;
      border: 1px solid #21262d;
      border-radius: 6px;
      overflow: hidden;
    }
    .gh-readme-header {
      background: #161b22;
      border-bottom: 1px solid #21262d;
      padding: 10px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      font-weight: 600;
      color: #e6edf3;
    }
    .gh-readme-header svg { color: #8b949e; }
    .gh-readme-body {
      padding: 32px 40px;
    }

    /* ─────────────────────────────────────────
       MARKDOWN CONTENT STYLES
    ───────────────────────────────────────── */
    .md { color: #e6edf3; }
    .md-center { text-align: center; }

    /* SVG header */
    .md-header-svg {
      display: flex;
      justify-content: center;
      margin-bottom: 4px;
    }
    .md-header-svg svg { max-width: 100%; border-radius: 15px; }

    /* Typing line */
    .md-typing {
      text-align: center;
      font-family: 'Fira Code', monospace;
      font-size: 17px;
      color: #bc13fe;
      margin: 10px 0 28px;
      min-height: 28px;
    }
    .md-cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: #bc13fe;
      vertical-align: text-bottom;
      animation: blink 0.8s step-end infinite;
      margin-left: 2px;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* HR */
    .md hr { border: none; border-top: 1px solid #21262d; margin: 24px 0; }

    /* Headings */
    .md h2 {
      font-size: 22px;
      font-weight: 600;
      color: #e6edf3;
      border-bottom: 1px solid #21262d;
      padding-bottom: 8px;
      margin: 32px 0 16px;
    }
    .md h3 {
      font-size: 18px;
      font-weight: 600;
      color: #e6edf3;
      margin: 20px 0 12px;
    }

    /* Code block */
    .md pre {
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 16px;
      overflow-x: auto;
      font-family: 'Fira Code', monospace;
      font-size: 13px;
      line-height: 1.7;
      color: #c9d1d9;
      margin: 16px 0;
    }
    .md pre .kw  { color: #ff7b72; }
    .md pre .ty  { color: #ffa657; }
    .md pre .str { color: #a5d6ff; }
    .md pre .cm  { color: #8b949e; }
    .md pre .key { color: #79c0ff; }
    .md pre .arr { color: #bc13fe; }

    /* Badges row */
    .md-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin: 8px 0 16px;
    }
    .md-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 5px 12px;
      font-size: 13px;
      font-weight: 600;
      font-family: 'Inter', sans-serif;
      color: #fff;
      cursor: default;
      transition: transform 0.15s, opacity 0.15s;
    }
    .md-badge:hover { transform: translateY(-1px); opacity: 0.9; }

    /* Table */
    .md-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
      margin: 16px 0;
    }
    .md-table th {
      background: #161b22;
      color: #8b949e;
      font-weight: 600;
      text-align: left;
      padding: 8px 16px;
      border-bottom: 1px solid #21262d;
    }
    .md-table td {
      padding: 10px 16px;
      border-bottom: 1px solid #21262d;
      color: #c9d1d9;
      font-size: 14px;
      vertical-align: top;
    }
    .md-table tr:hover td { background: #161b22; }
    .md-table td a { color: #58a6ff; text-decoration: none; font-weight: 600; }
    .md-table td a:hover { text-decoration: underline; }
    .code-tag {
      font-family: 'Fira Code', monospace;
      font-size: 12px;
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 4px;
      padding: 1px 6px;
      color: #bc13fe;
      margin: 0 2px;
      white-space: nowrap;
    }

    /* Stats images */
    .md-stats {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .md-stats img {
      border-radius: 8px;
      height: 155px;
      max-width: 100%;
    }

    /* Connect badges */
    .md-connect {
      display: flex;
      gap: 8px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .connect-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #fff;
      text-decoration: none;
      transition: transform 0.15s, opacity 0.15s;
    }
    .connect-badge:hover { transform: translateY(-2px); opacity: 0.9; }

    /* Footer */
    .md-footer {
      text-align: center;
      margin-top: 8px;
      font-size: 13px;
      color: #8b949e;
    }
    .md-footer .views-badge {
      display: inline-block;
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 20px;
      padding: 3px 12px;
      font-size: 12px;
      color: #bc13fe;
      font-family: 'Fira Code', monospace;
    }
  </style>
</head>
<body>

  <!-- GitHub top bar -->
  <div class="gh-topbar">
    <svg class="gh-logo" height="32" viewBox="0 0 16 16" width="32">
      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
    </svg>
    <div class="gh-topbar-pill">
      <span>noadanon220</span> / <span>noadanon220</span>
    </div>
  </div>

  <!-- Layout -->
  <div class="gh-layout">

    <!-- Sidebar -->
    <aside class="gh-sidebar">
      <div class="gh-avatar">🐾</div>
      <h1>Noa Danon</h1>
      <div class="gh-username">noadanon220</div>
      <div class="gh-bio">CS Student @ Afeka · Android &amp; Full-Stack Developer · Design background 🎨→💻</div>
      <button class="gh-follow-btn">Follow</button>
      <div class="gh-followers">
        <div><strong>–</strong> <span>followers</span></div>
        <div><strong>–</strong> <span>following</span></div>
      </div>
      <div class="gh-meta">
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM6.379 5.227A4.5 4.5 0 0110.5 8a4.5 4.5 0 01-4.121 4.492c-.353-.169-.654-.437-.854-.775a3 3 0 11-.01-5.442c.195-.333.493-.598.864-.048z"/></svg>
          Afeka College of Engineering
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"/></svg>
          <a href="#">noadanon220.github.io/noa-danon-portfolio</a>
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 4.75C0 3.784.784 3 1.75 3h12.5c.966 0 1.75.784 1.75 1.75v7.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-7.5zM1.75 4.5a.25.25 0 00-.25.25v.463l6.5 3.25 6.5-3.25V4.75a.25.25 0 00-.25-.25H1.75zM14 6.917l-5.834 2.917a1.25 1.25 0 01-1.332 0L1 6.917V12.25c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25V6.917z"/></svg>
          <a href="#">noadanon220@gmail.com</a>
        </div>
      </div>
    </aside>

    <!-- Main -->
    <main class="gh-main">
      <div class="gh-tabs">
        <div class="gh-tab active">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"/></svg>
          Overview
        </div>
        <div class="gh-tab">Repositories <span class="gh-tab-count">4</span></div>
        <div class="gh-tab">Projects</div>
        <div class="gh-tab">Stars</div>
      </div>

      <!-- README box -->
      <div class="gh-readme-box">
        <div class="gh-readme-header">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 2.75C0 1.784.784 1 1.75 1h12.5c.966 0 1.75.784 1.75 1.75v9.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-9.5zm1.75-.25a.25.25 0 00-.25.25v9.5c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25v-9.5a.25.25 0 00-.25-.25H1.75z"/><path d="M8 4a.75.75 0 01.75.75v3.5h1.5a.75.75 0 010 1.5h-4.5a.75.75 0 010-1.5h1.5v-3.5A.75.75 0 018 4z"/></svg>
          noadanon220 / README.md
        </div>
        <div class="gh-readme-body md">

          <!-- ══ SVG HEADER ══ -->
          <div class="md-header-svg">
            <svg width="860" height="280" viewBox="0 0 900 300" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <style>
                  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&display=swap');
                  .bg-rect2 { fill: #0d0221; }
                  .main-title2 {
                    font-family: 'Orbitron', sans-serif;
                    font-size: 80px;
                    fill: #bc13fe;
                    filter: drop-shadow(0 0 10px #bc13fe);
                    text-transform: uppercase;
                    animation: glitch2 3s infinite;
                  }
                  @keyframes glitch2 {
                    0%,6%,100% { transform: translate(0); }
                    2%         { transform: translate(-2px, 2px); }
                    4%         { transform: translate(2px, -2px); }
                  }
                  .floating-cat2 {
                    fill: none; stroke: #bc13fe; stroke-width: 1.5; opacity: 0.4;
                    filter: drop-shadow(0 0 5px #bc13fe);
                    animation: float2 6s infinite ease-in-out;
                  }
                  @keyframes float2 {
                    0%,100% { transform: translateY(0) rotate(0deg); }
                    50%      { transform: translateY(-20px) rotate(10deg); }
                  }
                  .scanner2 {
                    stroke: #bc13fe; stroke-width: 2;
                    filter: drop-shadow(0 0 15px #bc13fe);
                    animation: scan2 4s infinite linear;
                  }
                  @keyframes scan2 {
                    0%   { y1: 50;  y2: 50;  opacity: 0; }
                    50%  { opacity: 1; }
                    100% { y1: 250; y2: 250; opacity: 0; }
                  }
                </style>
              </defs>
              <rect width="900" height="300" class="bg-rect2" rx="15" />
              <g class="floating-cat2" style="animation-delay: 0s;">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <g class="floating-cat2" style="animation-delay: 2s; transform: translate(650px, 150px) scale(0.8);">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <text x="50%" y="150" dominant-baseline="middle" text-anchor="middle" class="main-title2">NOA DANON</text>
              <text x="50%" y="210" dominant-baseline="middle" text-anchor="middle" fill="#d896ff" font-family="monospace" font-size="18">&gt; INITIALIZING_CREATIVE_SYSTEM... [DONE]</text>
              <line x1="100" y1="50" x2="800" y2="50" class="scanner2" />
            </svg>
          </div>

          <!-- Typing line -->
          <div class="md-typing" id="typing-line"></div>

          <hr/>

          <!-- About -->
          <h2>👾 About Me</h2>
          <pre><span class="kw">const</span> <span class="key">noa</span>: <span class="ty">Developer</span> = {
  <span class="key">education</span>:  <span class="str">"B.Sc. Computer Science — Afeka College of Engineering (2022–2025)"</span>,
  <span class="key">background</span>: <span class="arr">[</span><span class="str">"Diploma in Animation &amp; Design"</span>, <span class="str">"Freelance Graphic Designer (2019–2022)"</span><span class="arr">]</span>,
  <span class="key">focus</span>:      <span class="arr">[</span><span class="str">"Android Dev"</span>, <span class="str">"Full-Stack"</span>, <span class="str">"AI &amp; Algorithms"</span><span class="arr">]</span>,
  <span class="key">languages</span>:  <span class="arr">[</span><span class="str">"Java"</span>, <span class="str">"Kotlin"</span>, <span class="str">"C++"</span>, <span class="str">"Python"</span>, <span class="str">"TypeScript"</span>, <span class="str">"JavaScript"</span><span class="arr">]</span>,
  <span class="key">design</span>:     <span class="arr">[</span><span class="str">"Figma"</span>, <span class="str">"Illustrator"</span>, <span class="str">"Photoshop"</span>, <span class="str">"After Effects"</span><span class="arr">]</span>,
  <span class="key">funFact</span>:    <span class="str">"Graphic designer turned engineer 🎨→💻"</span>,
};</pre>

          <hr/>

          <!-- Tech Stack -->
          <h2>🛠️ Tech Stack</h2>

          <h3>Languages</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#ED8B00;">☕ Java</span>
            <span class="md-badge" style="background:#A97142;">🤖 Kotlin</span>
            <span class="md-badge" style="background:#3670A0;">🐍 Python</span>
            <span class="md-badge" style="background:#007ACC;">🔷 TypeScript</span>
            <span class="md-badge" style="background:#F0DB4F;color:#323330;">📜 JavaScript</span>
            <span class="md-badge" style="background:#00599C;">⚙️ C++</span>
            <span class="md-badge" style="background:#555;">© C</span>
          </div>

          <h3>Mobile &amp; Frontend</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#3DDC84;color:#111;">🤖 Android SDK</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">🧩 Jetpack Compose</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">⚛️ React</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">📱 React Native</span>
            <span class="md-badge" style="background:#E34F26;">🌐 HTML</span>
            <span class="md-badge" style="background:#1572B6;">🎨 CSS</span>
          </div>

          <h3>Backend &amp; Tools</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#039BE5;">🔥 Firebase</span>
            <span class="md-badge" style="background:#4285F4;">🗺️ Google Maps API</span>
            <span class="md-badge" style="background:#F05033;">🔀 Git</span>
            <span class="md-badge" style="background:#2496ED;">🐳 Docker</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">📱 Android Studio</span>
          </div>

          <h3>Design</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#F24E1E;">🎨 Figma</span>
            <span class="md-badge" style="background:#FF9A00;">🖌️ Illustrator</span>
            <span class="md-badge" style="background:#31A8FF;">🖼️ Photoshop</span>
            <span class="md-badge" style="background:#9999FF;">✨ After Effects</span>
            <span class="md-badge" style="background:#FF0000;">📖 InDesign</span>
          </div>

          <hr/>

          <!-- Projects -->
          <h2>🚀 Featured Projects</h2>
          <table class="md-table">
            <thead>
              <tr>
                <th>Project</th>
                <th>Description</th>
                <th>Stack</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>🐾 <a href="#">Paws</a></td>
                <td>Android pet-care app — manage walks, vet visits &amp; feeding times, built from scratch</td>
                <td><span class="code-tag">Kotlin</span> <span class="code-tag">Firebase</span> <span class="code-tag">Jetpack</span></td>
              </tr>
              <tr>
                <td>🤖 <a href="#">AI Tactical Combat Sim</a></td>
                <td>2D strategic AI game with autonomous units using A*, BFS &amp; FSM algorithms</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">OpenGL</span></td>
              </tr>
              <tr>
                <td>🏦 <a href="#">Bank System</a></td>
                <td>Console banking app simulating multi-account management &amp; client operations</td>
                <td><span class="code-tag">Java</span> <span class="code-tag">OOP</span></td>
              </tr>
              <tr>
                <td>🧩 <a href="#">Rubik's Cube Solver</a></td>
                <td>Interactive cube simulation with real-time 3D rendering &amp; solving logic</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">SFML</span></td>
              </tr>
              <tr>
                <td>✨ <a href="#">Gemini Clone</a></td>
                <td>Fully functional AI chat interface — responsive UI &amp; real-time history</td>
                <td><span class="code-tag">React</span> <span class="code-tag">Gen AI SDK</span></td>
              </tr>
            </tbody>
          </table>

          <hr/>

          <!-- GitHub Stats -->
          <h2>📊 GitHub Stats</h2>
          <div class="md-stats">

            <!-- Stats card -->
            <svg width="495" height="155" viewBox="0 0 495 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="495" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="20" y="30" fill="#bc13fe" font-family="monospace" font-size="14" font-weight="700">noadanon220's GitHub Stats</text>
              <line x1="20" y1="38" x2="475" y2="38" stroke="#21262d" stroke-width="1"/>
              <!-- icons + labels -->
              <text x="20" y="62" fill="#8b949e" font-family="monospace" font-size="12">⭐ Total Stars</text>
              <text x="370" y="62" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="85" fill="#8b949e" font-family="monospace" font-size="12">🔀 Total Commits</text>
              <text x="370" y="85" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="108" fill="#8b949e" font-family="monospace" font-size="12">🐛 Issues</text>
              <text x="370" y="108" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="131" fill="#8b949e" font-family="monospace" font-size="12">🔁 Pull Requests</text>
              <text x="370" y="131" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
            </svg>

            <!-- Top Languages card -->
            <svg width="330" height="155" viewBox="0 0 330 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="330" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="16" y="28" fill="#bc13fe" font-family="monospace" font-size="13" font-weight="700">Most Used Languages</text>
              <line x1="16" y1="36" x2="314" y2="36" stroke="#21262d" stroke-width="1"/>

              <!-- Java -->
              <rect x="16" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="48" width="72" height="7" rx="3" fill="#ED8B00"/>
              <text x="16" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">Java <tspan fill="#8b949e">34%</tspan></text>

              <!-- C++ -->
              <rect x="130" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="48" width="60" height="7" rx="3" fill="#00599C"/>
              <text x="130" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">C++ <tspan fill="#8b949e">28%</tspan></text>

              <!-- Kotlin -->
              <rect x="16" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="88" width="45" height="7" rx="3" fill="#A97142"/>
              <text x="16" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Kotlin <tspan fill="#8b949e">18%</tspan></text>

              <!-- Python -->
              <rect x="130" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="88" width="30" height="7" rx="3" fill="#3670A0"/>
              <text x="130" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Python <tspan fill="#8b949e">12%</tspan></text>

              <!-- JS / TS -->
              <rect x="16" y="126" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="126" width="20" height="7" rx="3" fill="#F0DB4F"/>
              <text x="16" y="148" fill="#c9d1d9" font-family="monospace" font-size="11">JS/TS <tspan fill="#8b949e">8%</tspan></text>
            </svg>

          </div>

          <hr/>

          <!-- Connect -->
          <h2>🌐 Connect</h2>
          <div class="md-connect">
            <a class="connect-badge" style="background:#0077B5;" href="https://www.linkedin.com/in/noadanon/" target="_blank">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              LinkedIn
            </a>
            <a class="connect-badge" style="background:#181717;border:1px solid #444;" href="https://github.com/noadanon220" target="_blank">
              <svg width="14" height="14" viewBox="0 0 16 16" fill="white"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
              GitHub
            </a>
            <a class="connect-badge" style="background:#bc13fe;" href="https://noadanon220.github.io/noa-danon-portfolio" target="_blank">
              🌐 Portfolio
            </a>
            <a class="connect-badge" style="background:#D14836;" href="mailto:noadanon220@gmail.com">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
              Email
            </a>
          </div>

          <hr/>

          <!-- Footer -->
          <div class="md-footer">
            <div class="views-badge">👁 profile views: noadanon220</div>
            <br/><br/>
            <span style="font-size:13px; color:#484f58;">built with ♥ — and my dog 🐾</span>
          </div>

        </div><!-- /readme-body -->
      </div><!-- /readme-box -->
    </main>
  </div>

  <script>
    // Typing animation
    const lines = [
      "CS Student @ Afeka College",
      "Android & Full-Stack Developer",
      "Design Background 🎨 → 💻",
      "AI & Algorithms Enthusiast 🤖",
      "Always building something new ✨",
    ];
    let lineIdx = 0, charIdx = 0, deleting = false;
    const el = document.getElementById('typing-line');

    function tick() {
      const line = lines[lineIdx];
      if (!deleting) {
        charIdx++;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === line.length) {
          deleting = true;
          setTimeout(tick, 2000);
          return;
        }
      } else {
        charIdx--;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === 0) {
          deleting = false;
          lineIdx = (lineIdx + 1) % lines.length;
        }
      }
      setTimeout(tick, deleting ? 40 : 70);
    }
    tick();
  </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GitHub Profile README — Noa Danon</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Fira+Code:wght@400;500&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: #010409;
      color: #e6edf3;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Inter', Helvetica, Arial, sans-serif;
      font-size: 16px;
      line-height: 1.5;
    }

    /* ── GitHub chrome simulation ── */
    .gh-topbar {
      height: 62px;
      background: #161b22;
      border-bottom: 1px solid #21262d;
      display: flex;
      align-items: center;
      padding: 0 32px;
      gap: 16px;
    }
    .gh-logo { fill: #e6edf3; }
    .gh-topbar-pill {
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 5px 12px;
      font-size: 14px;
      color: #8b949e;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-topbar-pill span { color: #58a6ff; }

    /* ── Profile sidebar + main layout ── */
    .gh-layout {
      max-width: 1280px;
      margin: 32px auto;
      padding: 0 32px;
      display: grid;
      grid-template-columns: 296px 1fr;
      gap: 32px;
      align-items: start;
    }

    /* ── Sidebar ── */
    .gh-sidebar {}
    .gh-avatar {
      width: 296px;
      height: 296px;
      border-radius: 50%;
      background: linear-gradient(135deg, #1a0533, #0d0221);
      border: 1px solid #30363d;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      margin-bottom: 16px;
      overflow: hidden;
    }
    .gh-sidebar h1 {
      font-size: 26px;
      font-weight: 600;
      color: #e6edf3;
      line-height: 1.25;
    }
    .gh-sidebar .gh-username {
      font-size: 20px;
      font-weight: 300;
      color: #8b949e;
      margin: 4px 0 16px;
    }
    .gh-sidebar .gh-bio {
      font-size: 15px;
      color: #8b949e;
      margin-bottom: 16px;
      line-height: 1.5;
    }
    .gh-follow-btn {
      display: block;
      width: 100%;
      background: #21262d;
      border: 1px solid #363b42;
      color: #e6edf3;
      border-radius: 6px;
      padding: 5px 16px;
      font-size: 14px;
      font-weight: 600;
      text-align: center;
      cursor: pointer;
      margin-bottom: 16px;
      transition: background 0.15s, border-color 0.15s;
    }
    .gh-follow-btn:hover { background: #30363d; border-color: #484f58; }
    .gh-meta { display: flex; flex-direction: column; gap: 8px; margin-top: 16px; }
    .gh-meta-item {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      color: #8b949e;
    }
    .gh-meta-item svg { flex-shrink: 0; }
    .gh-meta-item a { color: #58a6ff; text-decoration: none; }
    .gh-meta-item a:hover { text-decoration: underline; }
    .gh-followers {
      display: flex;
      gap: 16px;
      font-size: 14px;
      color: #e6edf3;
      margin-top: 16px;
    }
    .gh-followers span { color: #8b949e; }

    /* ── Main content ── */
    .gh-main {}

    /* ── Tab bar ── */
    .gh-tabs {
      display: flex;
      gap: 0;
      border-bottom: 1px solid #21262d;
      margin-bottom: 24px;
    }
    .gh-tab {
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #8b949e;
      cursor: pointer;
      border-bottom: 2px solid transparent;
      margin-bottom: -1px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .gh-tab.active { color: #e6edf3; border-bottom-color: #f78166; }
    .gh-tab-count {
      background: #21262d;
      border-radius: 20px;
      padding: 1px 7px;
      font-size: 12px;
      font-weight: 500;
    }

    /* ── README box ── */
    .gh-readme-box {
      background: #0d1117;
      border: 1px solid #21262d;
      border-radius: 6px;
      overflow: hidden;
    }
    .gh-readme-header {
      background: #161b22;
      border-bottom: 1px solid #21262d;
      padding: 10px 16px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 14px;
      font-weight: 600;
      color: #e6edf3;
    }
    .gh-readme-header svg { color: #8b949e; }
    .gh-readme-body {
      padding: 32px 40px;
    }

    /* ─────────────────────────────────────────
       MARKDOWN CONTENT STYLES
    ───────────────────────────────────────── */
    .md { color: #e6edf3; }
    .md-center { text-align: center; }

    /* SVG header */
    .md-header-svg {
      display: flex;
      justify-content: center;
      margin-bottom: 4px;
    }
    .md-header-svg svg { max-width: 100%; border-radius: 15px; }

    /* Typing line */
    .md-typing {
      text-align: center;
      font-family: 'Fira Code', monospace;
      font-size: 17px;
      color: #bc13fe;
      margin: 10px 0 28px;
      min-height: 28px;
    }
    .md-cursor {
      display: inline-block;
      width: 2px;
      height: 1.1em;
      background: #bc13fe;
      vertical-align: text-bottom;
      animation: blink 0.8s step-end infinite;
      margin-left: 2px;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* HR */
    .md hr { border: none; border-top: 1px solid #21262d; margin: 24px 0; }

    /* Headings */
    .md h2 {
      font-size: 22px;
      font-weight: 600;
      color: #e6edf3;
      border-bottom: 1px solid #21262d;
      padding-bottom: 8px;
      margin: 32px 0 16px;
    }
    .md h3 {
      font-size: 18px;
      font-weight: 600;
      color: #e6edf3;
      margin: 20px 0 12px;
    }

    /* Code block */
    .md pre {
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 6px;
      padding: 16px;
      overflow-x: auto;
      font-family: 'Fira Code', monospace;
      font-size: 13px;
      line-height: 1.7;
      color: #c9d1d9;
      margin: 16px 0;
    }
    .md pre .kw  { color: #ff7b72; }
    .md pre .ty  { color: #ffa657; }
    .md pre .str { color: #a5d6ff; }
    .md pre .cm  { color: #8b949e; }
    .md pre .key { color: #79c0ff; }
    .md pre .arr { color: #bc13fe; }

    /* Badges row */
    .md-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin: 8px 0 16px;
    }
    .md-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 5px 12px;
      font-size: 13px;
      font-weight: 600;
      font-family: 'Inter', sans-serif;
      color: #fff;
      cursor: default;
      transition: transform 0.15s, opacity 0.15s;
    }
    .md-badge:hover { transform: translateY(-1px); opacity: 0.9; }

    /* Table */
    .md-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 14px;
      margin: 16px 0;
    }
    .md-table th {
      background: #161b22;
      color: #8b949e;
      font-weight: 600;
      text-align: left;
      padding: 8px 16px;
      border-bottom: 1px solid #21262d;
    }
    .md-table td {
      padding: 10px 16px;
      border-bottom: 1px solid #21262d;
      color: #c9d1d9;
      font-size: 14px;
      vertical-align: top;
    }
    .md-table tr:hover td { background: #161b22; }
    .md-table td a { color: #58a6ff; text-decoration: none; font-weight: 600; }
    .md-table td a:hover { text-decoration: underline; }
    .code-tag {
      font-family: 'Fira Code', monospace;
      font-size: 12px;
      background: #161b22;
      border: 1px solid #30363d;
      border-radius: 4px;
      padding: 1px 6px;
      color: #bc13fe;
      margin: 0 2px;
      white-space: nowrap;
    }

    /* Stats images */
    .md-stats {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .md-stats img {
      border-radius: 8px;
      height: 155px;
      max-width: 100%;
    }

    /* Connect badges */
    .md-connect {
      display: flex;
      gap: 8px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 16px 0;
    }
    .connect-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      border-radius: 4px;
      padding: 8px 16px;
      font-size: 14px;
      font-weight: 600;
      color: #fff;
      text-decoration: none;
      transition: transform 0.15s, opacity 0.15s;
    }
    .connect-badge:hover { transform: translateY(-2px); opacity: 0.9; }

    /* Footer */
    .md-footer {
      text-align: center;
      margin-top: 8px;
      font-size: 13px;
      color: #8b949e;
    }
    .md-footer .views-badge {
      display: inline-block;
      background: #21262d;
      border: 1px solid #30363d;
      border-radius: 20px;
      padding: 3px 12px;
      font-size: 12px;
      color: #bc13fe;
      font-family: 'Fira Code', monospace;
    }
  </style>
</head>
<body>

  <!-- GitHub top bar -->
  <div class="gh-topbar">
    <svg class="gh-logo" height="32" viewBox="0 0 16 16" width="32">
      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/>
    </svg>
    <div class="gh-topbar-pill">
      <span>noadanon220</span> / <span>noadanon220</span>
    </div>
  </div>

  <!-- Layout -->
  <div class="gh-layout">

    <!-- Sidebar -->
    <aside class="gh-sidebar">
      <div class="gh-avatar">🐾</div>
      <h1>Noa Danon</h1>
      <div class="gh-username">noadanon220</div>
      <div class="gh-bio">CS Student @ Afeka · Android &amp; Full-Stack Developer · Design background 🎨→💻</div>
      <button class="gh-follow-btn">Follow</button>
      <div class="gh-followers">
        <div><strong>–</strong> <span>followers</span></div>
        <div><strong>–</strong> <span>following</span></div>
      </div>
      <div class="gh-meta">
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M1.5 8a6.5 6.5 0 1113 0 6.5 6.5 0 01-13 0zM8 0a8 8 0 100 16A8 8 0 008 0zM6.379 5.227A4.5 4.5 0 0110.5 8a4.5 4.5 0 01-4.121 4.492c-.353-.169-.654-.437-.854-.775a3 3 0 11-.01-5.442c.195-.333.493-.598.864-.048z"/></svg>
          Afeka College of Engineering
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"/></svg>
          <a href="#">noadanon220.github.io/noa-danon-portfolio</a>
        </div>
        <div class="gh-meta-item">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 4.75C0 3.784.784 3 1.75 3h12.5c.966 0 1.75.784 1.75 1.75v7.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-7.5zM1.75 4.5a.25.25 0 00-.25.25v.463l6.5 3.25 6.5-3.25V4.75a.25.25 0 00-.25-.25H1.75zM14 6.917l-5.834 2.917a1.25 1.25 0 01-1.332 0L1 6.917V12.25c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25V6.917z"/></svg>
          <a href="#">noadanon220@gmail.com</a>
        </div>
      </div>
    </aside>

    <!-- Main -->
    <main class="gh-main">
      <div class="gh-tabs">
        <div class="gh-tab active">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 110-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9zm10.5-1V9h-8c-.356 0-.694.074-1 .208V2.5a1 1 0 011-1h8zM5 12.25v3.25a.25.25 0 00.4.2l1.45-1.087a.25.25 0 01.3 0L8.6 15.7a.25.25 0 00.4-.2v-3.25a.25.25 0 00-.25-.25h-3.5a.25.25 0 00-.25.25z"/></svg>
          Overview
        </div>
        <div class="gh-tab">Repositories <span class="gh-tab-count">4</span></div>
        <div class="gh-tab">Projects</div>
        <div class="gh-tab">Stars</div>
      </div>

      <!-- README box -->
      <div class="gh-readme-box">
        <div class="gh-readme-header">
          <svg width="16" height="16" viewBox="0 0 16 16" fill="currentColor"><path d="M0 2.75C0 1.784.784 1 1.75 1h12.5c.966 0 1.75.784 1.75 1.75v9.5A1.75 1.75 0 0114.25 14H1.75A1.75 1.75 0 010 12.25v-9.5zm1.75-.25a.25.25 0 00-.25.25v9.5c0 .138.112.25.25.25h12.5a.25.25 0 00.25-.25v-9.5a.25.25 0 00-.25-.25H1.75z"/><path d="M8 4a.75.75 0 01.75.75v3.5h1.5a.75.75 0 010 1.5h-4.5a.75.75 0 010-1.5h1.5v-3.5A.75.75 0 018 4z"/></svg>
          noadanon220 / README.md
        </div>
        <div class="gh-readme-body md">

          <!-- ══ SVG HEADER ══ -->
          <div class="md-header-svg">
            <svg width="860" height="280" viewBox="0 0 900 300" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <style>
                  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&display=swap');
                  .bg-rect2 { fill: #0d0221; }
                  .main-title2 {
                    font-family: 'Orbitron', sans-serif;
                    font-size: 80px;
                    fill: #bc13fe;
                    filter: drop-shadow(0 0 10px #bc13fe);
                    text-transform: uppercase;
                    animation: glitch2 3s infinite;
                  }
                  @keyframes glitch2 {
                    0%,6%,100% { transform: translate(0); }
                    2%         { transform: translate(-2px, 2px); }
                    4%         { transform: translate(2px, -2px); }
                  }
                  .floating-cat2 {
                    fill: none; stroke: #bc13fe; stroke-width: 1.5; opacity: 0.4;
                    filter: drop-shadow(0 0 5px #bc13fe);
                    animation: float2 6s infinite ease-in-out;
                  }
                  @keyframes float2 {
                    0%,100% { transform: translateY(0) rotate(0deg); }
                    50%      { transform: translateY(-20px) rotate(10deg); }
                  }
                  .scanner2 {
                    stroke: #bc13fe; stroke-width: 2;
                    filter: drop-shadow(0 0 15px #bc13fe);
                    animation: scan2 4s infinite linear;
                  }
                  @keyframes scan2 {
                    0%   { y1: 50;  y2: 50;  opacity: 0; }
                    50%  { opacity: 1; }
                    100% { y1: 250; y2: 250; opacity: 0; }
                  }
                </style>
              </defs>
              <rect width="900" height="300" class="bg-rect2" rx="15" />
              <g class="floating-cat2" style="animation-delay: 0s;">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <g class="floating-cat2" style="animation-delay: 2s; transform: translate(650px, 150px) scale(0.8);">
                <path d="M100,80 Q110,60 130,70 T150,90 T130,120 T100,100 Z" />
              </g>
              <text x="50%" y="150" dominant-baseline="middle" text-anchor="middle" class="main-title2">NOA DANON</text>
              <text x="50%" y="210" dominant-baseline="middle" text-anchor="middle" fill="#d896ff" font-family="monospace" font-size="18">&gt; INITIALIZING_CREATIVE_SYSTEM... [DONE]</text>
              <line x1="100" y1="50" x2="800" y2="50" class="scanner2" />
            </svg>
          </div>

          <!-- Typing line -->
          <div class="md-typing" id="typing-line"></div>

          <hr/>

          <!-- About -->
          <h2>👾 About Me</h2>
          <pre><span class="kw">const</span> <span class="key">noa</span>: <span class="ty">Developer</span> = {
  <span class="key">education</span>:  <span class="str">"B.Sc. Computer Science — Afeka College of Engineering (2022–2025)"</span>,
  <span class="key">background</span>: <span class="arr">[</span><span class="str">"Diploma in Animation &amp; Design"</span>, <span class="str">"Freelance Graphic Designer (2019–2022)"</span><span class="arr">]</span>,
  <span class="key">focus</span>:      <span class="arr">[</span><span class="str">"Android Dev"</span>, <span class="str">"Full-Stack"</span>, <span class="str">"AI &amp; Algorithms"</span><span class="arr">]</span>,
  <span class="key">languages</span>:  <span class="arr">[</span><span class="str">"Java"</span>, <span class="str">"Kotlin"</span>, <span class="str">"C++"</span>, <span class="str">"Python"</span>, <span class="str">"TypeScript"</span>, <span class="str">"JavaScript"</span><span class="arr">]</span>,
  <span class="key">design</span>:     <span class="arr">[</span><span class="str">"Figma"</span>, <span class="str">"Illustrator"</span>, <span class="str">"Photoshop"</span>, <span class="str">"After Effects"</span><span class="arr">]</span>,
  <span class="key">funFact</span>:    <span class="str">"Graphic designer turned engineer 🎨→💻"</span>,
};</pre>

          <hr/>

          <!-- Tech Stack -->
          <h2>🛠️ Tech Stack</h2>

          <h3>Languages</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#ED8B00;">☕ Java</span>
            <span class="md-badge" style="background:#A97142;">🤖 Kotlin</span>
            <span class="md-badge" style="background:#3670A0;">🐍 Python</span>
            <span class="md-badge" style="background:#007ACC;">🔷 TypeScript</span>
            <span class="md-badge" style="background:#F0DB4F;color:#323330;">📜 JavaScript</span>
            <span class="md-badge" style="background:#00599C;">⚙️ C++</span>
            <span class="md-badge" style="background:#555;">© C</span>
          </div>

          <h3>Mobile &amp; Frontend</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#3DDC84;color:#111;">🤖 Android SDK</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">🧩 Jetpack Compose</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">⚛️ React</span>
            <span class="md-badge" style="background:#20232a;border:1px solid #61DAFB;color:#61DAFB;">📱 React Native</span>
            <span class="md-badge" style="background:#E34F26;">🌐 HTML</span>
            <span class="md-badge" style="background:#1572B6;">🎨 CSS</span>
          </div>

          <h3>Backend &amp; Tools</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#039BE5;">🔥 Firebase</span>
            <span class="md-badge" style="background:#4285F4;">🗺️ Google Maps API</span>
            <span class="md-badge" style="background:#F05033;">🔀 Git</span>
            <span class="md-badge" style="background:#2496ED;">🐳 Docker</span>
            <span class="md-badge" style="background:#3DDC84;color:#111;">📱 Android Studio</span>
          </div>

          <h3>Design</h3>
          <div class="md-badges">
            <span class="md-badge" style="background:#F24E1E;">🎨 Figma</span>
            <span class="md-badge" style="background:#FF9A00;">🖌️ Illustrator</span>
            <span class="md-badge" style="background:#31A8FF;">🖼️ Photoshop</span>
            <span class="md-badge" style="background:#9999FF;">✨ After Effects</span>
            <span class="md-badge" style="background:#FF0000;">📖 InDesign</span>
          </div>

          <hr/>

          <!-- Projects -->
          <h2>🚀 Featured Projects</h2>
          <table class="md-table">
            <thead>
              <tr>
                <th>Project</th>
                <th>Description</th>
                <th>Stack</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>🐾 <a href="#">Paws</a></td>
                <td>Android pet-care app — manage walks, vet visits &amp; feeding times, built from scratch</td>
                <td><span class="code-tag">Kotlin</span> <span class="code-tag">Firebase</span> <span class="code-tag">Jetpack</span></td>
              </tr>
              <tr>
                <td>🤖 <a href="#">AI Tactical Combat Sim</a></td>
                <td>2D strategic AI game with autonomous units using A*, BFS &amp; FSM algorithms</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">OpenGL</span></td>
              </tr>
              <tr>
                <td>🏦 <a href="#">Bank System</a></td>
                <td>Console banking app simulating multi-account management &amp; client operations</td>
                <td><span class="code-tag">Java</span> <span class="code-tag">OOP</span></td>
              </tr>
              <tr>
                <td>🧩 <a href="#">Rubik's Cube Solver</a></td>
                <td>Interactive cube simulation with real-time 3D rendering &amp; solving logic</td>
                <td><span class="code-tag">C++</span> <span class="code-tag">SFML</span></td>
              </tr>
              <tr>
                <td>✨ <a href="#">Gemini Clone</a></td>
                <td>Fully functional AI chat interface — responsive UI &amp; real-time history</td>
                <td><span class="code-tag">React</span> <span class="code-tag">Gen AI SDK</span></td>
              </tr>
            </tbody>
          </table>

          <hr/>

          <!-- GitHub Stats -->
          <h2>📊 GitHub Stats</h2>
          <div class="md-stats">

            <!-- Stats card -->
            <svg width="495" height="155" viewBox="0 0 495 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="495" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="20" y="30" fill="#bc13fe" font-family="monospace" font-size="14" font-weight="700">noadanon220's GitHub Stats</text>
              <line x1="20" y1="38" x2="475" y2="38" stroke="#21262d" stroke-width="1"/>
              <!-- icons + labels -->
              <text x="20" y="62" fill="#8b949e" font-family="monospace" font-size="12">⭐ Total Stars</text>
              <text x="370" y="62" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="85" fill="#8b949e" font-family="monospace" font-size="12">🔀 Total Commits</text>
              <text x="370" y="85" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="108" fill="#8b949e" font-family="monospace" font-size="12">🐛 Issues</text>
              <text x="370" y="108" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
              <text x="20" y="131" fill="#8b949e" font-family="monospace" font-size="12">🔁 Pull Requests</text>
              <text x="370" y="131" fill="#c9d1d9" font-family="monospace" font-size="12" font-weight="700">coming soon</text>
            </svg>

            <!-- Top Languages card -->
            <svg width="330" height="155" viewBox="0 0 330 155" xmlns="http://www.w3.org/2000/svg">
              <rect width="330" height="155" rx="8" fill="#0d1117" stroke="#21262d" stroke-width="1"/>
              <text x="16" y="28" fill="#bc13fe" font-family="monospace" font-size="13" font-weight="700">Most Used Languages</text>
              <line x1="16" y1="36" x2="314" y2="36" stroke="#21262d" stroke-width="1"/>

              <!-- Java -->
              <rect x="16" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="48" width="72" height="7" rx="3" fill="#ED8B00"/>
              <text x="16" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">Java <tspan fill="#8b949e">34%</tspan></text>

              <!-- C++ -->
              <rect x="130" y="48" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="48" width="60" height="7" rx="3" fill="#00599C"/>
              <text x="130" y="70" fill="#c9d1d9" font-family="monospace" font-size="11">C++ <tspan fill="#8b949e">28%</tspan></text>

              <!-- Kotlin -->
              <rect x="16" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="88" width="45" height="7" rx="3" fill="#A97142"/>
              <text x="16" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Kotlin <tspan fill="#8b949e">18%</tspan></text>

              <!-- Python -->
              <rect x="130" y="88" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="130" y="88" width="30" height="7" rx="3" fill="#3670A0"/>
              <text x="130" y="110" fill="#c9d1d9" font-family="monospace" font-size="11">Python <tspan fill="#8b949e">12%</tspan></text>

              <!-- JS / TS -->
              <rect x="16" y="126" width="100" height="7" rx="3" fill="#21262d"/>
              <rect x="16" y="126" width="20" height="7" rx="3" fill="#F0DB4F"/>
              <text x="16" y="148" fill="#c9d1d9" font-family="monospace" font-size="11">JS/TS <tspan fill="#8b949e">8%</tspan></text>
            </svg>

          </div>

          <hr/>

          <!-- Connect -->
          <h2>🌐 Connect</h2>
          <div class="md-connect">
            <a class="connect-badge" style="background:#0077B5;" href="https://www.linkedin.com/in/noadanon/" target="_blank">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              LinkedIn
            </a>
            <a class="connect-badge" style="background:#181717;border:1px solid #444;" href="https://github.com/noadanon220" target="_blank">
              <svg width="14" height="14" viewBox="0 0 16 16" fill="white"><path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"/></svg>
              GitHub
            </a>
            <a class="connect-badge" style="background:#bc13fe;" href="https://noadanon220.github.io/noa-danon-portfolio" target="_blank">
              🌐 Portfolio
            </a>
            <a class="connect-badge" style="background:#D14836;" href="mailto:noadanon220@gmail.com">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="white"><path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
              Email
            </a>
          </div>

          <hr/>

          <!-- Footer -->
          <div class="md-footer">
            <div class="views-badge">👁 profile views: noadanon220</div>
            <br/><br/>
            <span style="font-size:13px; color:#484f58;">built with ♥ — and my dog 🐾</span>
          </div>

        </div><!-- /readme-body -->
      </div><!-- /readme-box -->
    </main>
  </div>

  <script>
    // Typing animation
    const lines = [
      "CS Student @ Afeka College",
      "Android & Full-Stack Developer",
      "Design Background 🎨 → 💻",
      "AI & Algorithms Enthusiast 🤖",
      "Always building something new ✨",
    ];
    let lineIdx = 0, charIdx = 0, deleting = false;
    const el = document.getElementById('typing-line');

    function tick() {
      const line = lines[lineIdx];
      if (!deleting) {
        charIdx++;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === line.length) {
          deleting = true;
          setTimeout(tick, 2000);
          return;
        }
      } else {
        charIdx--;
        el.innerHTML = line.slice(0, charIdx) + '<span class="md-cursor"></span>';
        if (charIdx === 0) {
          deleting = false;
          lineIdx = (lineIdx + 1) % lines.length;
        }
      }
      setTimeout(tick, deleting ? 40 : 70);
    }
    tick();
  </script>
</body>
</html>
