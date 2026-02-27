<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aswin Krishna — an0n7os</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;700;800&family=IBM+Plex+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0c0c0e;
    --surface: #111114;
    --border: rgba(255,255,255,0.06);
    --border-hover: rgba(255,255,255,0.14);
    --text: #e8e8ec;
    --muted: #52525e;
    --accent: #c8f560;
    --accent-dim: rgba(200,245,96,0.08);
    --red: #ff4e6a;
    --blue: #5eb8ff;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;
    line-height: 1.7;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }

  .wrap {
    position: relative;
    z-index: 1;
    max-width: 780px;
    margin: 0 auto;
    padding: 60px 28px 80px;
  }

  /* HEADER */
  header {
    padding-bottom: 48px;
    border-bottom: 1px solid var(--border);
    animation: fadeUp 0.6s ease both;
  }

  .eyebrow {
    font-size: 10px;
    letter-spacing: 0.2em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .eyebrow::before {
    content: '';
    display: inline-block;
    width: 20px; height: 1px;
    background: var(--accent);
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 6vw, 3.6rem);
    font-weight: 800;
    letter-spacing: -0.02em;
    line-height: 1.05;
    color: #fff;
  }
  h1 .dim { color: var(--muted); font-weight: 400; }

  .tagline {
    margin-top: 18px;
    font-size: 12px;
    color: var(--muted);
    display: flex;
    flex-wrap: wrap;
    gap: 0 8px;
  }
  .tagline .sep { color: var(--border-hover); }
  .tagline .hi { color: var(--accent); }

  .pill-row {
    margin-top: 22px;
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }
  .pill {
    font-size: 10px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 4px 12px;
    border: 1px solid var(--border);
    color: var(--muted);
    border-radius: 2px;
    transition: all 0.2s;
    cursor: default;
  }
  .pill:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: var(--accent-dim);
  }

  /* SECTION */
  section {
    padding: 40px 0;
    border-bottom: 1px solid var(--border);
    animation: fadeUp 0.6s ease both;
  }
  section:nth-child(2) { animation-delay: 0.06s; }
  section:nth-child(3) { animation-delay: 0.12s; }
  section:nth-child(4) { animation-delay: 0.18s; }
  section:nth-child(5) { animation-delay: 0.22s; }
  section:nth-child(6) { animation-delay: 0.26s; }

  .sec-label {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .sec-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* TERMINAL */
  .terminal {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    overflow: hidden;
  }
  .term-bar {
    display: flex;
    align-items: center;
    gap: 6px;
    padding: 10px 16px;
    border-bottom: 1px solid var(--border);
    background: rgba(255,255,255,0.02);
  }
  .td { width: 9px; height: 9px; border-radius: 50%; }
  .td.r { background: #ff5f57; }
  .td.y { background: #febc2e; }
  .td.g { background: #28c840; }
  .term-title { font-size: 10px; color: var(--muted); margin-left: 8px; }
  .term-body { padding: 20px 22px; font-size: 12px; line-height: 2.1; }
  .t-p { color: var(--muted); }
  .t-k { color: var(--blue); }
  .t-s { color: var(--accent); }
  .t-c { color: #2a2a36; }
  .t-cur {
    display: inline-block; width: 7px; height: 13px;
    background: var(--accent); vertical-align: middle;
    margin-left: 3px; animation: blink 1.1s step-end infinite;
  }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* SKILLS */
  .skill-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }
  .sk {
    background: var(--bg);
    padding: 15px 14px;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: background 0.2s;
    cursor: default;
  }
  .sk:hover { background: var(--surface); }
  .sk:hover .sk-n { color: var(--accent); }
  .sk-i { font-size: 14px; flex-shrink: 0; }
  .sk-n { font-size: 11px; color: var(--muted); letter-spacing: 0.04em; transition: color 0.2s; }

  /* STATS */
  .stats-wrap {
    border: 1px solid var(--border);
    border-radius: 4px;
    overflow: hidden;
  }
  .stats-wrap img { width: 100%; display: block; }
  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: var(--border);
    border-top: 1px solid var(--border);
  }
  .stat-cell {
    background: var(--bg);
    padding: 18px 20px;
    transition: background 0.2s;
  }
  .stat-cell:hover { background: var(--surface); }
  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--accent);
    line-height: 1;
  }
  .stat-lbl { font-size: 10px; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; margin-top: 5px; }

  /* CERTS */
  .cert-row { display: flex; gap: 12px; flex-wrap: wrap; }
  .cert-box {
    border: 1px solid var(--border);
    padding: 14px 18px;
    border-radius: 4px;
    display: flex;
    align-items: center;
    gap: 12px;
    transition: border-color 0.2s;
  }
  .cert-box:hover { border-color: var(--accent); }
  .cert-box img { height: 42px; display: block; }
  .cert-n { font-size: 11px; color: var(--muted); }

  /* CONNECT */
  .conn-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(105px, 1fr));
    gap: 8px;
  }
  .conn-btn {
    border: 1px solid var(--border);
    padding: 14px 10px;
    text-align: center;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.2s;
    background: transparent;
    text-decoration: none;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 7px;
  }
  .conn-btn:hover {
    border-color: var(--border-hover);
    background: var(--surface);
    transform: translateY(-2px);
  }
  .conn-ic { font-size: 17px; }
  .conn-nm { font-size: 10px; color: var(--muted); letter-spacing: 0.08em; text-transform: uppercase; }

  /* SUGGESTIONS */
  .sugg-list { display: flex; flex-direction: column; }
  .sugg-row {
    display: grid;
    grid-template-columns: 28px 1fr auto;
    align-items: start;
    gap: 18px;
    padding: 18px 0;
    border-bottom: 1px solid var(--border);
    transition: all 0.15s;
  }
  .sugg-row:last-child { border-bottom: none; }
  .sugg-row:hover .sugg-t { color: var(--accent); }
  .sugg-i { font-size: 10px; color: var(--muted); padding-top: 2px; }
  .sugg-t { font-size: 12px; color: var(--text); margin-bottom: 4px; transition: color 0.2s; }
  .sugg-d { font-size: 11px; color: var(--muted); line-height: 1.7; }
  .tag {
    font-size: 9px; letter-spacing: 0.12em; text-transform: uppercase;
    padding: 3px 8px; border-radius: 2px; white-space: nowrap;
    align-self: start; margin-top: 2px;
  }
  .tag-must { background: rgba(255,78,106,0.1); color: var(--red); border: 1px solid rgba(255,78,106,0.2); }
  .tag-good { background: rgba(200,245,96,0.08); color: var(--accent); border: 1px solid rgba(200,245,96,0.15); }
  .tag-opt  { background: rgba(94,184,255,0.08); color: var(--blue); border: 1px solid rgba(94,184,255,0.15); }

  /* FOOTER */
  footer {
    padding-top: 36px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 10px;
    animation: fadeUp 0.6s ease 0.3s both;
  }
  .f-l { font-size: 11px; color: var(--muted); }
  .f-l span { color: var(--accent); }
  .f-r { font-size: 10px; color: #28282e; letter-spacing: 0.12em; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(14px); }
    to   { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>
<div class="wrap">

  <header>
    <div class="eyebrow">github profile readme</div>
    <h1>Aswin Krishna<br><span class="dim">@an0n7os</span></h1>
    <div class="tagline">
      <span class="hi">Ethical Hacker</span>
      <span class="sep">/</span>
      <span>Penetration Tester</span>
      <span class="sep">/</span>
      <span>Web Developer</span>
      <span class="sep">/</span>
      <span>CTF Player</span>
    </div>
    <div class="pill-row">
      <span class="pill">Security</span>
      <span class="pill">Bug Bounty</span>
      <span class="pill">OSINT</span>
      <span class="pill">Red Team</span>
      <span class="pill">India 🇮🇳</span>
    </div>
  </header>

  <section>
    <div class="sec-label">whoami</div>
    <div class="terminal">
      <div class="term-bar">
        <div class="td r"></div><div class="td y"></div><div class="td g"></div>
        <span class="term-title">aswin@kali — ~/profile</span>
      </div>
      <div class="term-body">
        <div><span class="t-p">$ </span>cat about.yaml</div>
        <br>
        <div><span class="t-k">name</span>:      <span class="t-s">Aswin Krishna</span></div>
        <div><span class="t-k">alias</span>:     an0n7os</div>
        <div><span class="t-k">location</span>: India 🇮🇳</div>
        <div><span class="t-k">os</span>:        Kali Linux · Debian · Parrot</div>
        <div><span class="t-k">tools</span>:     Burp Suite · Nmap · Metasploit · Wireshark</div>
        <div><span class="t-k">focus</span>:     <span class="t-s">["Web AppSec", "Pentesting", "CTF", "Dev"]</span></div>
        <div><span class="t-k">learning</span>: Red Teaming · Malware Analysis · Cloud Security</div>
        <div class="t-c"># "Think like an attacker. Defend like a guardian."</div>
        <br>
        <div><span class="t-p">$ </span><span class="t-cur"></span></div>
      </div>
    </div>
  </section>

  <section>
    <div class="sec-label">tech stack</div>
    <div class="skill-grid">
      <div class="sk"><span class="sk-i">🐧</span><span class="sk-n">Linux</span></div>
      <div class="sk"><span class="sk-i">🐍</span><span class="sk-n">Python</span></div>
      <div class="sk"><span class="sk-i">🟨</span><span class="sk-n">JavaScript</span></div>
      <div class="sk"><span class="sk-i">⚛️</span><span class="sk-n">React</span></div>
      <div class="sk"><span class="sk-i">🟩</span><span class="sk-n">Node.js</span></div>
      <div class="sk"><span class="sk-i">🐳</span><span class="sk-n">Docker</span></div>
      <div class="sk"><span class="sk-i">⚡</span><span class="sk-n">Express</span></div>
      <div class="sk"><span class="sk-i">🐙</span><span class="sk-n">GitHub</span></div>
      <div class="sk"><span class="sk-i">📦</span><span class="sk-n">npm</span></div>
      <div class="sk"><span class="sk-i">🔐</span><span class="sk-n">Burp Suite</span></div>
    </div>
  </section>

  <section>
    <div class="sec-label">github stats</div>
    <div class="stats-wrap">
      <img src="https://github-readme-stats.vercel.app/api?username=an0n7os&show_icons=true&hide_border=true&bg_color=0c0c0e&title_color=c8f560&icon_color=c8f560&text_color=e8e8ec" alt="GitHub Stats"/>
      <div class="stats-row">
        <div class="stat-cell">
          <div class="stat-num">🔥</div>
          <div class="stat-lbl">Current Streak</div>
        </div>
        <div class="stat-cell">
          <div class="stat-num">🏆</div>
          <div class="stat-lbl">CTF Wins</div>
        </div>
      </div>
    </div>
  </section>

  <section>
    <div class="sec-label">certifications</div>
    <div class="cert-row">
      <div class="cert-box">
        <img src="https://tryhackme-badges.s3.amazonaws.com/AswinkrishnaVB.png" alt="TryHackMe"/>
        <span class="cert-n">TryHackMe</span>
      </div>
      <div class="cert-box">
        <img src="https://api.accredible.com/v1/frontend/credential_website_embed_image/badge/78147650" alt="CWL"/>
        <span class="cert-n">CWL Badge</span>
      </div>
    </div>
  </section>

  <section>
    <div class="sec-label">connect</div>
    <div class="conn-grid">
      <a class="conn-btn"><span class="conn-ic">💬</span><span class="conn-nm">Discord</span></a>
      <a class="conn-btn"><span class="conn-ic">✈️</span><span class="conn-nm">Telegram</span></a>
      <a class="conn-btn"><span class="conn-ic">👽</span><span class="conn-nm">Reddit</span></a>
      <a class="conn-btn"><span class="conn-ic">📲</span><span class="conn-nm">WhatsApp</span></a>
      <a class="conn-btn"><span class="conn-ic">🎮</span><span class="conn-nm">Twitch</span></a>
      <a class="conn-btn"><span class="conn-ic">🌿</span><span class="conn-nm">Linktree</span></a>
      <a class="conn-btn"><span class="conn-ic">🎯</span><span class="conn-nm">TryHackMe</span></a>
    </div>
  </section>

  <section>
    <div class="sec-label">upgrade suggestions</div>
    <div class="sugg-list">
      <div class="sugg-row">
        <span class="sugg-i">01</span>
        <div>
          <div class="sugg-t">Snake Workflow Fix</div>
          <div class="sugg-d"><code>.github/workflows/snake.yml</code> file GitHub Actions-il add cheyyanam. Ithillenkil snake SVG generate aakilla.</div>
        </div>
        <span class="tag tag-must">Must</span>
      </div>
      <div class="sugg-row">
        <span class="sugg-i">02</span>
        <div>
          <div class="sugg-t">Real Social Links</div>
          <div class="sugg-d">Badge <code>(#)</code> placeholders — actual Discord, Telegram, WhatsApp links kondu replace cheyyanam.</div>
        </div>
        <span class="tag tag-must">Must</span>
      </div>
      <div class="sugg-row">
        <span class="sugg-i">03</span>
        <div>
          <div class="sugg-t">GitHub Trophy Widget</div>
          <div class="sugg-d"><code>github-profile-trophy</code> API — Stars, Commits, PRs visually show cheyyum. Professional look koottum.</div>
        </div>
        <span class="tag tag-good">Good</span>
      </div>
      <div class="sugg-row">
        <span class="sugg-i">04</span>
        <div>
          <div class="sugg-t">WakaTime Coding Stats</div>
          <div class="sugg-d">Daily coding time, language breakdown auto-update aakum. wakatime.com — free account create cheyyam.</div>
        </div>
        <span class="tag tag-good">Good</span>
      </div>
      <div class="sugg-row">
        <span class="sugg-i">05</span>
        <div>
          <div class="sugg-t">Hack The Box Badge</div>
          <div class="sugg-d">HTB profile undenkil dynamic badge add cheyyam. TryHackMe-nte koodeyirikumbol security credibility strong aakum.</div>
        </div>
        <span class="tag tag-opt">Optional</span>
      </div>
      <div class="sugg-row">
        <span class="sugg-i">06</span>
        <div>
          <div class="sugg-t">CTF WriteUps Auto-Fetch</div>
          <div class="sugg-d">Blog / writeups undenkil <code>blog-post-workflow</code> GitHub Action use cheythu latest posts auto-show cheyyam.</div>
        </div>
        <span class="tag tag-opt">Optional</span>
      </div>
    </div>
  </section>

  <footer>
    <div class="f-l"><span>an0n7os</span> · Aswin Krishna</div>
    <div class="f-r">THINK LIKE AN ATTACKER</div>
  </footer>

</div>
</body>
</html>
