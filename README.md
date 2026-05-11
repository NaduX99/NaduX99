<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>NaduX99 — Profile</title>
<link href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600;700&family=SF+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  :root{
    --mac-bg:#1e1e1e;
    --mac-sidebar:#252525;
    --mac-titlebar:#2d2d2d;
    --mac-border:#3a3a3a;
    --mac-text:#e8e8e8;
    --mac-text-muted:#8a8a8e;
    --mac-text-dim:#5a5a5e;
    --mac-blue:#0a84ff;
    --mac-accent:#30d158;
    --mac-card:#2a2a2a;
    --mac-card-border:#383838;
    --mac-hover:#323232;
    --font-sf:"SF Pro Display",-apple-system,BlinkMacSystemFont,"Helvetica Neue",sans-serif;
    --font-mono:"SF Mono","Menlo","Monaco",monospace;
  }
  html,body{
    width:100%;min-height:100vh;
    background:radial-gradient(ellipse at 60% 0%,#1a2744 0%,#0d0d0d 55%);
    font-family:var(--font-sf);
    display:flex;align-items:center;justify-content:center;
    padding:32px 16px;
  }

  /* Desktop wallpaper dots */
  body::before{
    content:"";position:fixed;inset:0;
    background-image:radial-gradient(circle,rgba(255,255,255,0.04) 1px,transparent 1px);
    background-size:28px 28px;
    pointer-events:none;z-index:0;
  }

  .window{
    width:780px;max-width:100%;
    border-radius:14px;
    background:var(--mac-bg);
    border:1px solid rgba(255,255,255,0.1);
    box-shadow:
      0 40px 100px rgba(0,0,0,0.7),
      0 0 0 0.5px rgba(255,255,255,0.06);
    overflow:hidden;position:relative;z-index:1;
    animation:fadeUp 0.6s cubic-bezier(0.34,1.56,0.64,1) both;
  }
  @keyframes fadeUp{from{opacity:0;transform:translateY(32px) scale(0.97)}to{opacity:1;transform:none}}

  /* Title bar */
  .titlebar{
    height:44px;
    background:var(--mac-titlebar);
    border-bottom:1px solid var(--mac-border);
    display:flex;align-items:center;
    padding:0 16px;
    gap:8px;
    position:relative;
  }
  .traffic{display:flex;gap:8px;align-items:center}
  .dot{
    width:12px;height:12px;border-radius:50%;cursor:pointer;
    transition:filter 0.15s;
    display:flex;align-items:center;justify-content:center;
    font-size:8px;color:transparent;
  }
  .dot:hover{filter:brightness(1.2)}
  .dot.red{background:#ff5f57;border:1px solid rgba(0,0,0,0.2)}
  .dot.yellow{background:#febc2e;border:1px solid rgba(0,0,0,0.2)}
  .dot.green{background:#28c840;border:1px solid rgba(0,0,0,0.2)}
  .titlebar-center{
    position:absolute;left:50%;transform:translateX(-50%);
    font-size:13px;font-weight:500;color:var(--mac-text-muted);
    letter-spacing:-0.01em;
  }
  .titlebar-right{
    margin-left:auto;display:flex;gap:12px;align-items:center;
  }
  .titlebar-btn{
    background:rgba(255,255,255,0.07);
    border:1px solid rgba(255,255,255,0.1);
    border-radius:6px;padding:4px 10px;
    font-size:11px;color:var(--mac-text-muted);
    cursor:pointer;transition:background 0.15s;font-family:var(--font-sf);
  }
  .titlebar-btn:hover{background:rgba(255,255,255,0.12)}

  /* Layout */
  .layout{display:flex;min-height:520px}

  /* Sidebar */
  .sidebar{
    width:200px;flex-shrink:0;
    background:var(--mac-sidebar);
    border-right:1px solid var(--mac-border);
    padding:20px 12px;
    display:flex;flex-direction:column;gap:4px;
  }
  .sidebar-section{
    font-size:11px;font-weight:600;
    color:var(--mac-text-dim);
    letter-spacing:0.06em;text-transform:uppercase;
    padding:8px 8px 4px;margin-top:8px;
  }
  .sidebar-item{
    display:flex;align-items:center;gap:9px;
    padding:7px 10px;border-radius:7px;
    font-size:13px;color:var(--mac-text-muted);
    cursor:pointer;transition:all 0.15s;
    text-decoration:none;
  }
  .sidebar-item:hover{background:rgba(255,255,255,0.07);color:var(--mac-text)}
  .sidebar-item.active{background:rgba(10,132,255,0.2);color:var(--mac-blue)}
  .sidebar-icon{font-size:14px;width:16px;text-align:center}

  /* Main content */
  .main{flex:1;overflow-y:auto;padding:28px 28px 32px}

  /* Profile hero */
  .hero{
    display:flex;align-items:center;gap:20px;
    padding:20px;
    background:var(--mac-card);
    border:1px solid var(--mac-card-border);
    border-radius:13px;
    margin-bottom:20px;
    animation:fadeUp 0.6s 0.1s cubic-bezier(0.34,1.56,0.64,1) both;
  }
  .avatar{
    width:72px;height:72px;border-radius:50%;flex-shrink:0;
    overflow:hidden;
    border:2px solid rgba(255,255,255,0.12);
    background:linear-gradient(135deg,#1d3a6b,#2d6a4f);
    display:flex;align-items:center;justify-content:center;
    font-size:26px;font-weight:600;color:#fff;letter-spacing:-1px;
  }
  .avatar img{width:100%;height:100%;object-fit:cover}
  .hero-info{flex:1}
  .hero-name{
    font-size:20px;font-weight:600;color:var(--mac-text);
    letter-spacing:-0.03em;line-height:1.2;
    margin-bottom:3px;
  }
  .hero-handle{
    font-size:13px;color:var(--mac-blue);
    font-family:var(--font-mono);margin-bottom:6px;
  }
  .hero-bio{
    font-size:12.5px;color:var(--mac-text-muted);line-height:1.5;
  }
  .hero-tags{display:flex;gap:6px;flex-wrap:wrap;margin-top:10px}
  .tag{
    padding:3px 9px;border-radius:20px;
    font-size:11px;font-weight:500;
    background:rgba(48,209,88,0.12);
    color:#30d158;border:1px solid rgba(48,209,88,0.2);
  }
  .tag.blue{background:rgba(10,132,255,0.12);color:#0a84ff;border-color:rgba(10,132,255,0.2)}
  .tag.purple{background:rgba(191,90,242,0.12);color:#bf5af2;border-color:rgba(191,90,242,0.2)}
  .hero-right{display:flex;flex-direction:column;gap:8px;align-items:flex-end}
  .status-dot{
    width:8px;height:8px;border-radius:50%;
    background:#30d158;
    box-shadow:0 0 0 3px rgba(48,209,88,0.2);
    animation:pulse 2s infinite;
  }
  @keyframes pulse{0%,100%{box-shadow:0 0 0 3px rgba(48,209,88,0.2)}50%{box-shadow:0 0 0 6px rgba(48,209,88,0.08)}}

  /* Grid 2-col */
  .grid2{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:20px}

  /* Info card */
  .card{
    background:var(--mac-card);
    border:1px solid var(--mac-card-border);
    border-radius:12px;
    padding:16px 18px;
    animation:fadeUp 0.6s 0.2s cubic-bezier(0.34,1.56,0.64,1) both;
  }
  .card-header{
    display:flex;align-items:center;justify-content:space-between;
    margin-bottom:12px;
  }
  .card-title{
    font-size:12px;font-weight:600;
    color:var(--mac-text-dim);
    letter-spacing:0.05em;text-transform:uppercase;
  }
  .card-icon{font-size:15px;color:var(--mac-text-dim)}

  .info-row{
    display:flex;justify-content:space-between;align-items:center;
    padding:6px 0;
    border-bottom:1px solid rgba(255,255,255,0.04);
    font-size:12.5px;
  }
  .info-row:last-child{border-bottom:none}
  .info-label{color:var(--mac-text-muted)}
  .info-val{color:var(--mac-text);font-weight:500}
  .info-val.link{color:var(--mac-blue);text-decoration:none;font-family:var(--font-mono);font-size:11.5px}

  /* Stack */
  .stack-grid{
    display:flex;flex-wrap:wrap;gap:8px;padding-top:4px;
  }
  .stack-pill{
    display:flex;align-items:center;gap:6px;
    padding:5px 10px;border-radius:8px;
    font-size:12px;font-weight:500;
    background:rgba(255,255,255,0.05);
    border:1px solid rgba(255,255,255,0.08);
    color:var(--mac-text-muted);
    transition:all 0.15s;cursor:default;
  }
  .stack-pill:hover{background:rgba(255,255,255,0.1);color:var(--mac-text);border-color:rgba(255,255,255,0.15)}
  .pill-dot{width:7px;height:7px;border-radius:50%}

  /* Stats */
  .stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:20px}
  .stat-card{
    background:var(--mac-card);
    border:1px solid var(--mac-card-border);
    border-radius:11px;padding:14px 16px;text-align:center;
    animation:fadeUp 0.6s 0.3s cubic-bezier(0.34,1.56,0.64,1) both;
  }
  .stat-num{font-size:22px;font-weight:600;color:var(--mac-text);letter-spacing:-0.03em}
  .stat-label{font-size:11px;color:var(--mac-text-dim);margin-top:2px;text-transform:uppercase;letter-spacing:0.04em}

  /* Activity bar chart */
  .activity-row{
    display:flex;align-items:flex-end;gap:3px;height:52px;padding-top:4px;
  }
  .bar{
    flex:1;background:rgba(10,132,255,0.25);
    border-radius:3px 3px 0 0;
    transition:background 0.2s;cursor:pointer;
    min-height:4px;
  }
  .bar:hover{background:rgba(10,132,255,0.6)}
  .bar.high{background:rgba(10,132,255,0.5)}
  .bar.peak{background:var(--mac-blue)}

  /* Connect */
  .connect-row{display:flex;gap:10px;flex-wrap:wrap;margin-top:16px}
  .connect-btn{
    display:flex;align-items:center;gap:7px;
    padding:8px 14px;border-radius:9px;
    font-size:12.5px;font-weight:500;
    text-decoration:none;
    background:rgba(255,255,255,0.06);
    border:1px solid rgba(255,255,255,0.1);
    color:var(--mac-text-muted);
    transition:all 0.15s;
  }
  .connect-btn:hover{background:rgba(255,255,255,0.12);color:var(--mac-text);border-color:rgba(255,255,255,0.2)}
  .connect-btn svg{width:14px;height:14px;flex-shrink:0}

  /* Quote */
  .quote{
    font-size:13px;color:var(--mac-text-dim);
    font-style:italic;text-align:center;
    padding:14px;
    border-top:1px solid var(--mac-border);
    margin-top:8px;
    letter-spacing:0.01em;
  }

  /* Dock */
  .dock{
    position:fixed;bottom:20px;left:50%;transform:translateX(-50%);
    display:flex;gap:6px;align-items:flex-end;
    background:rgba(30,30,30,0.7);
    backdrop-filter:blur(20px);
    border:1px solid rgba(255,255,255,0.1);
    border-radius:18px;padding:8px 14px;
    z-index:100;
  }
  .dock-icon{
    width:44px;height:44px;border-radius:11px;
    display:flex;align-items:center;justify-content:center;
    font-size:22px;cursor:pointer;
    transition:transform 0.2s cubic-bezier(0.34,1.56,0.64,1);
    position:relative;
  }
  .dock-icon:hover{transform:scale(1.35) translateY(-6px)}
  .dock-icon:hover::after{
    content:attr(data-label);
    position:absolute;bottom:calc(100% + 8px);
    font-size:11px;white-space:nowrap;
    background:rgba(0,0,0,0.8);color:#fff;
    padding:3px 8px;border-radius:5px;
    pointer-events:none;
  }
  .dock-sep{
    width:1px;background:rgba(255,255,255,0.15);
    height:32px;align-self:center;margin:0 4px;
  }
  .dock-dot{
    width:4px;height:4px;border-radius:50%;
    background:rgba(255,255,255,0.4);
    position:absolute;bottom:-8px;left:50%;transform:translateX(-50%);
  }

  /* Scrollbar */
  .main::-webkit-scrollbar{width:6px}
  .main::-webkit-scrollbar-track{background:transparent}
  .main::-webkit-scrollbar-thumb{background:rgba(255,255,255,0.1);border-radius:3px}

  @media(max-width:600px){
    .layout{flex-direction:column}
    .sidebar{width:100%;flex-direction:row;flex-wrap:wrap;padding:10px 12px;border-right:none;border-bottom:1px solid var(--mac-border)}
    .sidebar-section{display:none}
    .grid2{grid-template-columns:1fr}
    .stats-row{grid-template-columns:repeat(3,1fr)}
    .dock{display:none}
    body{padding:12px 8px 60px}
  }
</style>
</head>
<body>

<!-- macOS Window -->
<div class="window">

  <!-- Title Bar -->
  <div class="titlebar">
    <div class="traffic">
      <div class="dot red" title="Close"></div>
      <div class="dot yellow" title="Minimize"></div>
      <div class="dot green" title="Fullscreen"></div>
    </div>
    <div class="titlebar-center">NaduX99 — Profile.app</div>
    <div class="titlebar-right">
      <a href="https://github.com/NaduX99" target="_blank" style="text-decoration:none">
        <div class="titlebar-btn">⭑ Follow</div>
      </a>
    </div>
  </div>

  <!-- Layout -->
  <div class="layout">

    <!-- Sidebar -->
    <div class="sidebar">
      <div class="sidebar-section">Navigation</div>
      <a class="sidebar-item active" href="#">
        <span class="sidebar-icon">⊙</span> Overview
      </a>
      <a class="sidebar-item" href="https://github.com/NaduX99?tab=repositories" target="_blank">
        <span class="sidebar-icon">⊞</span> Repos
      </a>
      <a class="sidebar-item" href="https://github.com/NaduX99?tab=projects" target="_blank">
        <span class="sidebar-icon">◧</span> Projects
      </a>
      <a class="sidebar-item" href="https://github.com/NaduX99?tab=stars" target="_blank">
        <span class="sidebar-icon">✦</span> Stars
      </a>
      <div class="sidebar-section">Connect</div>
      <a class="sidebar-item" href="https://www.linkedin.com/in/nadul-laknidu-53a244357" target="_blank">
        <span class="sidebar-icon">in</span> LinkedIn
      </a>
      <a class="sidebar-item" href="mailto:nadullaknidu7@gmail.com">
        <span class="sidebar-icon">✉</span> Email
      </a>
      <a class="sidebar-item" href="https://discord.gg/yourhandle" target="_blank">
        <span class="sidebar-icon">#</span> Discord
      </a>
    </div>

    <!-- Main -->
    <div class="main">

      <!-- Hero -->
      <div class="hero">
        <div class="avatar">
          <img src="https://github.com/NaduX99.png" alt="NaduX99" onerror="this.parentElement.innerHTML='NL'"/>
        </div>
        <div class="hero-info">
          <div class="hero-name">Nadul Laknidu</div>
          <div class="hero-handle">@NaduX99</div>
          <div class="hero-bio">Aspiring Software Engineer · AI Enthusiast · Web Developer<br/>Undergraduate SE Student · Sri Lanka 🇱🇰</div>
          <div class="hero-tags">
            <span class="tag">Open Source</span>
            <span class="tag blue">AI / ML</span>
            <span class="tag purple">Web Dev</span>
          </div>
        </div>
        <div class="hero-right">
          <div style="display:flex;align-items:center;gap:6px">
            <div class="status-dot"></div>
            <span style="font-size:11px;color:#30d158;font-weight:500">Available</span>
          </div>
          <a href="https://github.com/NaduX99" target="_blank" style="text-decoration:none">
            <div style="font-size:11px;color:var(--mac-text-dim);font-family:var(--font-mono);margin-top:4px">github.com/NaduX99</div>
          </a>
        </div>
      </div>

      <!-- Stats -->
      <div class="stats-row">
        <div class="stat-card">
          <div class="stat-num" id="repos">—</div>
          <div class="stat-label">Repositories</div>
        </div>
        <div class="stat-card">
          <div class="stat-num" id="followers">—</div>
          <div class="stat-label">Followers</div>
        </div>
        <div class="stat-card">
          <div class="stat-num" id="following">—</div>
          <div class="stat-label">Following</div>
        </div>
      </div>

      <!-- Two-col grid -->
      <div class="grid2">

        <!-- Info -->
        <div class="card">
          <div class="card-header">
            <div class="card-title">About</div>
            <span class="card-icon">ℹ</span>
          </div>
          <div class="info-row">
            <span class="info-label">Role</span>
            <span class="info-val">Undergrad SE Student</span>
          </div>
          <div class="info-row">
            <span class="info-label">Focus</span>
            <span class="info-val">AI · Web · Open Source</span>
          </div>
          <div class="info-row">
            <span class="info-label">Location</span>
            <span class="info-val">Sri Lanka 🇱🇰</span>
          </div>
          <div class="info-row">
            <span class="info-label">Pronouns</span>
            <span class="info-val">NaduX</span>
          </div>
          <div class="info-row">
            <span class="info-label">Email</span>
            <a class="info-val link" href="mailto:nadullaknidu7@gmail.com">nadullaknidu7@gmail.com</a>
          </div>
        </div>

        <!-- Activity -->
        <div class="card">
          <div class="card-header">
            <div class="card-title">Activity</div>
            <span class="card-icon" style="font-size:11px;color:var(--mac-text-dim)">Last 12 weeks</span>
          </div>
          <div class="activity-row" id="activityBars">
            <!-- Generated by JS -->
          </div>
          <div style="display:flex;justify-content:space-between;margin-top:6px">
            <span style="font-size:10px;color:var(--mac-text-dim)">12w ago</span>
            <span style="font-size:10px;color:var(--mac-text-dim)">Today</span>
          </div>
        </div>

      </div>

      <!-- Tech Stack -->
      <div class="card" style="margin-bottom:20px;animation-delay:0.35s">
        <div class="card-header">
          <div class="card-title">Tech Stack</div>
          <span class="card-icon">⌥</span>
        </div>
        <div class="stack-grid">
          <div class="stack-pill"><span class="pill-dot" style="background:#3776AB"></span>Python</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#F7DF1E"></span>JavaScript</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#61DAFB"></span>React</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#43853D"></span>Node.js</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#ED8B00"></span>Java</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#4EA94B"></span>MongoDB</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#E34F26"></span>HTML5</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#1572B6"></span>CSS3</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#F05032"></span>Git</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#FCC624"></span>Linux</div>
          <div class="stack-pill"><span class="pill-dot" style="background:#412991"></span>AI / ML</div>
        </div>
      </div>

      <!-- Connect -->
      <div class="card" style="animation-delay:0.4s">
        <div class="card-header">
          <div class="card-title">Connect</div>
          <span class="card-icon">⇢</span>
        </div>
        <div class="connect-row">
          <a class="connect-btn" href="https://github.com/NaduX99" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
            GitHub
          </a>
          <a class="connect-btn" href="https://www.linkedin.com/in/nadul-laknidu-53a244357" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
            LinkedIn
          </a>
          <a class="connect-btn" href="mailto:nadullaknidu7@gmail.com">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><polyline points="2,4 12,13 22,4"/></svg>
            Email
          </a>
          <a class="connect-btn" href="https://discord.gg/yourhandle" target="_blank">
            <svg viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057.1 18.077.11 18.09.124 18.1a19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03z"/></svg>
            Discord
          </a>
        </div>
      </div>

      <div class="quote">"Code when you're sad — it always helps."</div>

    </div>
  </div>
</div>

<!-- macOS Dock -->
<div class="dock">
  <a href="https://github.com/NaduX99" target="_blank" style="text-decoration:none">
    <div class="dock-icon" data-label="GitHub" style="background:linear-gradient(145deg,#24292e,#1a1f24)">
      <svg width="26" height="26" viewBox="0 0 24 24" fill="white"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
      <div class="dock-dot"></div>
    </div>
  </a>
  <a href="https://www.linkedin.com/in/nadul-laknidu-53a244357" target="_blank" style="text-decoration:none">
    <div class="dock-icon" data-label="LinkedIn" style="background:#0077b5">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="white"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
    </div>
  </a>
  <div class="dock-sep"></div>
  <a href="mailto:nadullaknidu7@gmail.com" style="text-decoration:none">
    <div class="dock-icon" data-label="Email" style="background:linear-gradient(145deg,#ea4335,#c31f0a)">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><polyline points="2,4 12,13 22,4"/></svg>
    </div>
  </a>
</div>

<script>
  // Generate fake-but-realistic activity bars
  const bars = document.getElementById('activityBars');
  const vals = [22,18,35,28,15,40,52,38,45,30,20,55];
  const max = Math.max(...vals);
  vals.forEach(v => {
    const pct = Math.round((v/max)*100);
    const cls = pct>80?'bar peak':pct>55?'bar high':'bar';
    bars.innerHTML += `<div class="${cls}" style="height:${pct}%" title="${v} contributions"></div>`;
  });

  // Fetch real GitHub stats
  fetch('https://api.github.com/users/NaduX99')
    .then(r=>r.json())
    .then(d=>{
      if(d.public_repos!=null) document.getElementById('repos').textContent=d.public_repos;
      if(d.followers!=null) document.getElementById('followers').textContent=d.followers;
      if(d.following!=null) document.getElementById('following').textContent=d.following;
    }).catch(()=>{
      document.getElementById('repos').textContent='—';
      document.getElementById('followers').textContent='—';
      document.getElementById('following').textContent='—';
    });

  // Traffic light hover effects
  document.querySelectorAll('.dot').forEach(d=>{
    d.addEventListener('mouseenter',()=>d.style.opacity='0.8');
    d.addEventListener('mouseleave',()=>d.style.opacity='1');
  });
</script>
</body>
</html>
