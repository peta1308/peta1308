<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Emanuel · peta1308</title>
<link href="https://fonts.googleapis.com/css2?family=Geist+Mono:wght@300;400;500;600&family=Geist:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:       #ffffff;
    --surface:  #f6f8fa;
    --border:   #d0d7de;
    --border2:  #eaeef2;
    --text:     #1f2328;
    --muted:    #636c76;
    --dim:      #afb8c1;
    --accent:   #0969da;
    --green:    #1a7f37;
    --purple:   #8250df;
    --mono:     'Geist Mono', monospace;
    --sans:     'Geist', sans-serif;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--mono);
    min-height: 100vh;
    padding: 3rem 2rem;
    line-height: 1;
  }

  .page { max-width: 680px; margin: 0 auto; }

  /* ── Top bar ── */
  .topbar {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-bottom: 3rem;
    font-size: 0.65rem;
    color: var(--dim);
    letter-spacing: 1.5px;
    text-transform: uppercase;
  }
  .topbar-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--green); }

  /* ── Hero ── */
  .hero { margin-bottom: 3rem; }

  .hero-pre {
    font-size: 0.68rem;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0.6rem;
  }

  .hero-name {
    font-family: var(--sans);
    font-size: clamp(2rem, 6vw, 3rem);
    font-weight: 300;
    color: var(--text);
    letter-spacing: -2px;
    line-height: 1;
    margin-bottom: 0.5rem;
  }
  .hero-name strong {
    font-weight: 500;
  }

  .hero-handle {
    font-size: 0.72rem;
    color: var(--dim);
    letter-spacing: 1px;
    margin-bottom: 1.5rem;
  }
  .hero-handle a {
    color: var(--accent);
    text-decoration: none;
  }

  .hero-bio {
    font-family: var(--sans);
    font-size: 0.9rem;
    font-weight: 300;
    color: var(--muted);
    line-height: 1.7;
    max-width: 440px;
    border-left: 2px solid var(--border2);
    padding-left: 1rem;
  }

  /* ── Divider ── */
  .divider {
    height: 1px;
    background: var(--border2);
    margin: 2.5rem 0;
  }

  /* ── Section label ── */
  .label {
    font-size: 0.6rem;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--dim);
    margin-bottom: 1.25rem;
  }

  /* ── Stack ── */
  .stack {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 2.5rem;
  }
  .chip {
    font-size: 0.68rem;
    font-family: var(--mono);
    padding: 5px 12px;
    border-radius: 3px;
    border: 1px solid var(--border);
    color: var(--muted);
    background: var(--surface);
    transition: border-color 0.15s, color 0.15s;
    cursor: default;
  }
  .chip:hover { border-color: var(--accent); color: var(--accent); }
  .chip.hi { border-color: var(--border); color: var(--text); font-weight: 500; }

  /* ── Projects ── */
  .projects {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1px;
    background: var(--border2);
    border: 1px solid var(--border2);
    border-radius: 6px;
    overflow: hidden;
    margin-bottom: 2.5rem;
  }
  .proj {
    background: var(--bg);
    padding: 1.25rem;
    transition: background 0.15s;
    text-decoration: none;
    color: inherit;
    display: block;
  }
  .proj:hover { background: var(--surface); }

  .proj-top {
    display: flex;
    align-items: center;
    gap: 6px;
    margin-bottom: 0.5rem;
  }
  .proj-icon {
    width: 14px; height: 14px; opacity: 0.35;
    flex-shrink: 0;
  }
  .proj-name {
    font-size: 0.78rem;
    font-weight: 500;
    color: var(--accent);
  }
  .proj-desc {
    font-family: var(--sans);
    font-size: 0.75rem;
    font-weight: 300;
    color: var(--muted);
    line-height: 1.55;
    margin-bottom: 1rem;
  }
  .proj-meta {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .lang {
    display: flex;
    align-items: center;
    gap: 5px;
    font-size: 0.65rem;
    color: var(--muted);
  }
  .lang-dot {
    width: 8px; height: 8px; border-radius: 50%;
    flex-shrink: 0;
  }
  .proj-badge {
    font-size: 0.6rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--green);
    border: 1px solid #d4edda;
    background: #f0fff4;
    padding: 2px 7px;
    border-radius: 2px;
    margin-left: auto;
  }

  /* ── Activity grid ── */
  .grid-wrap { margin-bottom: 2.5rem; }
  .contrib-grid {
    display: grid;
    grid-template-columns: repeat(24, 1fr);
    grid-template-rows: repeat(7, 1fr);
    gap: 2px;
  }
  .cell {
    aspect-ratio: 1;
    border-radius: 2px;
    background: var(--border2);
  }
  .c1 { background: #9be9a8; }
  .c2 { background: #40c463; }
  .c3 { background: #30a14e; }
  .c4 { background: #216e39; }

  /* ── Footer ── */
  .footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 1rem;
  }
  .footer-links {
    display: flex;
    gap: 1.5rem;
  }
  .footer-link {
    font-size: 0.65rem;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--dim);
    text-decoration: none;
    transition: color 0.15s;
  }
  .footer-link:hover { color: var(--accent); }

  .footer-loc {
    font-size: 0.65rem;
    color: var(--dim);
    letter-spacing: 1px;
  }

  /* ── Animations ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(10px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .page > * {
    animation: fadeUp 0.5s ease both;
  }
  .topbar   { animation-delay: 0.0s; }
  .hero     { animation-delay: 0.08s; }
  .divider  { animation-delay: 0.14s; }
  .label    { animation-delay: 0.18s; }
  .stack    { animation-delay: 0.22s; }
  .projects { animation-delay: 0.30s; }
  .grid-wrap{ animation-delay: 0.38s; }
  .footer   { animation-delay: 0.44s; }
</style>
</head>
<body>
<div class="page">

  <!-- Top bar -->
  <div class="topbar">
    <span class="topbar-dot"></span>
    disponible para colaborar
  </div>

  <!-- Hero -->
  <div class="hero">
    <div class="hero-pre">Software Developer</div>
    <h1 class="hero-name"><strong>Emanuel</strong> Peta</h1>
    <div class="hero-handle">
      <a href="https://github.com/peta1308" target="_blank">github.com/peta1308</a>
      &nbsp;·&nbsp; Colombia
    </div>
    <p class="hero-bio">
      Estudiante de Desarrollo de Software. Construyo interfaces, aprendo backend
      y disfruto colaborar en proyectos con impacto real.
    </p>
  </div>

  <div class="divider"></div>

  <!-- Stack -->
  <div class="label">Stack</div>
  <div class="stack">
    <span class="chip hi">Java</span>
    <span class="chip hi">Spring Boot</span>
    <span class="chip hi">JavaScript</span>
    <span class="chip hi">HTML</span>
    <span class="chip hi">CSS</span>
    <span class="chip">Git</span>
    <span class="chip">REST APIs</span>
    <span class="chip">SQL</span>
  </div>

  <!-- Projects -->
  <div class="label">Proyectos</div>
  <div class="projects">

    <a class="proj" href="https://github.com/peta1308/Game-oleadas" target="_blank">
      <div class="proj-top">
        <svg class="proj-icon" viewBox="0 0 16 16" fill="currentColor">
          <path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 010-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9z"/>
        </svg>
        <span class="proj-name">Game-oleadas</span>
      </div>
      <p class="proj-desc">Videojuego de oleadas desarrollado en Java. Lógica de juego, manejo de eventos y ciclos de dificultad progresiva.</p>
      <div class="proj-meta">
        <span class="lang">
          <span class="lang-dot" style="background:#b07219"></span>
          Java
        </span>
        <span class="proj-badge">Personal</span>
      </div>
    </a>

    <a class="proj" href="https://github.com/Libardo07/reportes-urbanos" target="_blank">
      <div class="proj-top">
        <svg class="proj-icon" viewBox="0 0 16 16" fill="currentColor">
          <path d="M2 2.5A2.5 2.5 0 014.5 0h8.75a.75.75 0 01.75.75v12.5a.75.75 0 01-.75.75h-2.5a.75.75 0 010-1.5h1.75v-2h-8a1 1 0 00-.714 1.7.75.75 0 01-1.072 1.05A2.495 2.495 0 012 11.5v-9z"/>
        </svg>
        <span class="proj-name">reportes-urbanos</span>
      </div>
      <p class="proj-desc">App colaborativa para reportar incidencias urbanas. Proyecto universitario en equipo con Spring Boot y JavaScript.</p>
      <div class="proj-meta">
        <span class="lang">
          <span class="lang-dot" style="background:#f1e05a"></span>
          JavaScript
        </span>
        <span class="proj-badge">Equipo</span>
      </div>
    </a>

  </div>

  <!-- Activity -->
  <div class="grid-wrap">
    <div class="label">Actividad</div>
    <div class="contrib-grid" id="cgrid"></div>
  </div>

  <!-- Footer -->
  <div class="footer">
    <div class="footer-links">
      <a class="footer-link" href="https://github.com/peta1308" target="_blank">GitHub</a>
      <a class="footer-link" href="#">LinkedIn</a>
    </div>
    <div class="footer-loc">Colombia · en formación</div>
  </div>

</div>

<script>
// Contribution grid — pseudo-random but plausible pattern
const seed = [0,0,1,0,2,1,0,0,1,2,0,1,3,2,1,0,0,1,2,1,0,2,3,2,1,1,0,0,1,0,0,1,2,3,1,0,0,1,2,0,0,1,0,2,4,3,2,1,0,1,2,3,1,0,0,0,1,1,2,0,0,1,2,1,0,1,3,2,0,0,1,2,1,0,0,1,2,0,1,2,3,1,0,0,1,2,1,0,0,1,2,3,2,1,0,1,3,2,1,0,0,1,2,0,1,3,2,1,0,0,1,2,1,0,1,3,4,2,1,0,0,1,2,0,0,1,2,1,0,1,2,3,2,1,0,1,4,3,2,1,0,0,1,2,1,0,0,0,1,2,0,0,1,2,1,0,0,1,2,1,0,1,2,3,2,1,0,0];
const cls = ['','c1','c2','c3','c4'];
const grid = document.getElementById('cgrid');
const total = 24 * 7;
for (let i = 0; i < total; i++) {
  const cell = document.createElement('div');
  const v = seed[i % seed.length];
  cell.className = 'cell ' + (cls[v] || '');
  grid.appendChild(cell);
}
</script>
</body>
</html>
