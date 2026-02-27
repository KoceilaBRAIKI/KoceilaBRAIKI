<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Koceila Braiki — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080810;
    --surface: #0f0f1a;
    --card: #13131f;
    --border: #1e1e30;
    --accent: #6366f1;
    --accent2: #a855f7;
    --text: #e2e8f0;
    --muted: #64748b;
    --light: #94a3b8;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    font-size: 14px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NOISE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 999;
    opacity: .5;
  }

  /* ── GLOW BG ── */
  .glow-orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(120px);
    pointer-events: none;
    z-index: 0;
  }
  .orb1 { width: 600px; height: 600px; background: rgba(99,102,241,.12); top: -200px; left: -200px; }
  .orb2 { width: 500px; height: 500px; background: rgba(168,85,247,.08); bottom: -100px; right: -100px; }

  /* ── LAYOUT ── */
  .container { max-width: 900px; margin: 0 auto; padding: 0 2rem; position: relative; z-index: 1; }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    padding: 1.2rem 2rem;
    display: flex; justify-content: space-between; align-items: center;
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
    background: rgba(8,8,16,.7);
  }
  .nav-logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1rem; color: var(--text); letter-spacing: -.01em; }
  .nav-links { display: flex; gap: 2rem; }
  .nav-links a { color: var(--muted); text-decoration: none; font-size: .8rem; letter-spacing: .05em; text-transform: uppercase; transition: color .2s; }
  .nav-links a:hover { color: var(--text); }
  .nav-badge {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    color: white; padding: .35rem .9rem; border-radius: 999px; font-size: .75rem;
    font-family: 'Syne', sans-serif; font-weight: 600; letter-spacing: .02em;
  }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center;
    padding: 8rem 0 4rem;
  }
  .hero-tag {
    display: inline-flex; align-items: center; gap: .5rem;
    color: var(--accent); font-size: .75rem; letter-spacing: .12em; text-transform: uppercase;
    margin-bottom: 1.5rem;
  }
  .hero-tag::before { content: ''; width: 24px; height: 1px; background: var(--accent); }
  h1 {
    font-family: 'Syne', sans-serif; font-weight: 800;
    font-size: clamp(3rem, 8vw, 6rem);
    line-height: 1.0; letter-spacing: -.04em;
    color: var(--text);
    margin-bottom: 1.5rem;
  }
  h1 span {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }
  .hero-desc {
    max-width: 520px; color: var(--light); font-size: .95rem; line-height: 1.8;
    margin-bottom: 2.5rem;
  }
  .hero-links { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn {
    display: inline-flex; align-items: center; gap: .5rem;
    padding: .75rem 1.5rem; border-radius: 8px; font-family: 'DM Mono', monospace;
    font-size: .8rem; text-decoration: none; transition: all .2s; cursor: pointer; border: none;
  }
  .btn-primary {
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    color: white;
  }
  .btn-primary:hover { opacity: .85; transform: translateY(-1px); }
  .btn-ghost {
    background: transparent; color: var(--light);
    border: 1px solid var(--border);
  }
  .btn-ghost:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-1px); }

  /* ── STATS ROW ── */
  .stats {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 1px; background: var(--border);
    border: 1px solid var(--border); border-radius: 12px;
    overflow: hidden; margin: 5rem 0;
  }
  .stat {
    background: var(--card); padding: 2rem;
    text-align: center;
  }
  .stat-num {
    font-family: 'Syne', sans-serif; font-weight: 800;
    font-size: 2.2rem; letter-spacing: -.03em;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  }
  .stat-label { color: var(--muted); font-size: .75rem; margin-top: .25rem; letter-spacing: .05em; text-transform: uppercase; }

  /* ── SECTIONS ── */
  section { padding: 5rem 0; }
  .section-tag {
    display: inline-flex; align-items: center; gap: .5rem;
    color: var(--accent); font-size: .72rem; letter-spacing: .12em; text-transform: uppercase;
    margin-bottom: 1rem;
  }
  .section-tag::before { content: ''; width: 18px; height: 1px; background: var(--accent); }
  h2 {
    font-family: 'Syne', sans-serif; font-weight: 800;
    font-size: clamp(1.8rem, 4vw, 2.5rem); letter-spacing: -.03em;
    margin-bottom: 3rem;
  }

  /* ── SKILLS ── */
  .skills-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.5rem; }
  .skill-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 12px; padding: 1.5rem;
    transition: border-color .2s, transform .2s;
  }
  .skill-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .skill-card-title {
    font-family: 'Syne', sans-serif; font-weight: 700;
    font-size: .9rem; margin-bottom: 1rem; color: var(--text);
    display: flex; align-items: center; gap: .6rem;
  }
  .tags { display: flex; flex-wrap: wrap; gap: .5rem; }
  .tag {
    padding: .3rem .75rem; border-radius: 6px; font-size: .72rem;
    background: rgba(99,102,241,.1); color: var(--accent);
    border: 1px solid rgba(99,102,241,.2); letter-spacing: .02em;
  }
  .tag.purple { background: rgba(168,85,247,.1); color: #c084fc; border-color: rgba(168,85,247,.2); }
  .tag.green { background: rgba(34,197,94,.08); color: #4ade80; border-color: rgba(34,197,94,.15); }
  .tag.orange { background: rgba(251,146,60,.08); color: #fb923c; border-color: rgba(251,146,60,.15); }
  .tag.blue { background: rgba(56,189,248,.08); color: #38bdf8; border-color: rgba(56,189,248,.15); }
  .tag.red { background: rgba(248,113,113,.08); color: #f87171; border-color: rgba(248,113,113,.15); }

  /* ── PROJECTS ── */
  .projects-list { display: flex; flex-direction: column; gap: 1.5rem; }
  .project-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 14px; padding: 1.75rem 2rem;
    display: grid; grid-template-columns: 1fr auto;
    gap: 1rem; align-items: start;
    transition: border-color .2s, transform .2s;
    text-decoration: none; color: inherit;
  }
  .project-card:hover { border-color: var(--accent); transform: translateY(-2px); }
  .project-header { display: flex; align-items: center; gap: .75rem; margin-bottom: .6rem; }
  .project-icon { font-size: 1.1rem; }
  .project-name {
    font-family: 'Syne', sans-serif; font-weight: 700;
    font-size: 1rem; color: var(--text);
  }
  .project-desc { color: var(--light); font-size: .82rem; line-height: 1.7; margin-bottom: 1rem; }
  .project-highlight {
    display: inline-block; font-size: .72rem;
    color: var(--accent); background: rgba(99,102,241,.08);
    border: 1px solid rgba(99,102,241,.15);
    padding: .25rem .65rem; border-radius: 6px; margin-bottom: 1rem;
  }
  .project-arrow {
    color: var(--muted); font-size: 1.2rem; align-self: center;
    transition: transform .2s, color .2s;
  }
  .project-card:hover .project-arrow { transform: translate(3px, -3px); color: var(--accent); }

  /* ── CONTACT ── */
  .contact-card {
    background: var(--card); border: 1px solid var(--border);
    border-radius: 16px; padding: 3rem;
    text-align: center;
  }
  .contact-card h3 {
    font-family: 'Syne', sans-serif; font-weight: 800;
    font-size: 1.8rem; letter-spacing: -.03em; margin-bottom: .75rem;
  }
  .contact-card p { color: var(--light); margin-bottom: 2rem; }
  .contact-links { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 0; text-align: center;
    color: var(--muted); font-size: .75rem;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
  .fade-up { animation: fadeUp .6s ease both; }
  .delay-1 { animation-delay: .1s; }
  .delay-2 { animation-delay: .2s; }
  .delay-3 { animation-delay: .3s; }
  .delay-4 { animation-delay: .4s; }

  @media (max-width: 640px) {
    .skills-grid { grid-template-columns: 1fr; }
    .stats { grid-template-columns: 1fr; }
    .project-card { grid-template-columns: 1fr; }
    .nav-links { display: none; }
  }
</style>
</head>
<body>

<div class="glow-orb orb1"></div>
<div class="glow-orb orb2"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">KB</div>
  <div class="nav-links">
    <a href="#competences">Compétences</a>
    <a href="#projets">Projets</a>
    <a href="#contact">Contact</a>
  </div>
  <div class="nav-badge">Alternance · Sept. 2026</div>
</nav>

<!-- HERO -->
<div class="container">
  <section class="hero">
    <div class="hero-tag fade-up">Étudiant L3 Informatique · IGM Gustave Eiffel</div>
    <h1 class="fade-up delay-1">Koceila<br/><span>Braiki</span></h1>
    <p class="hero-desc fade-up delay-2">
      Je construis des logiciels du bas niveau au web —
      compilateurs, codecs de compression, applications full-stack et jeux.
      Passionné par les fondamentaux et la qualité du code.
    </p>
    <div class="hero-links fade-up delay-3">
      <a href="mailto:braiki.koceila@outlook.fr" class="btn btn-primary">✉ Me contacter</a>
      <a href="https://www.linkedin.com/in/koceila-braiki" class="btn btn-ghost" target="_blank">LinkedIn</a>
      <a href="https://github.com/KoceilaBRAIKI" class="btn btn-ghost" target="_blank">GitHub</a>
    </div>
  </section>

  <!-- STATS -->
  <div class="stats fade-up">
    <div class="stat">
      <div class="stat-num">6</div>
      <div class="stat-label">Projets majeurs</div>
    </div>
    <div class="stat">
      <div class="stat-num">4</div>
      <div class="stat-label">Langages maîtrisés</div>
    </div>
    <div class="stat">
      <div class="stat-num">47%</div>
      <div class="stat-label">Gain compression CoDec</div>
    </div>
  </div>

  <!-- SKILLS -->
  <section id="competences">
    <div class="section-tag">Stack</div>
    <h2>Compétences</h2>
    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-card-title">💻 Langages</div>
        <div class="tags">
          <span class="tag">C</span>
          <span class="tag">Python</span>
          <span class="tag">Java</span>
          <span class="tag purple">Haskell</span>
          <span class="tag blue">SQL / PL-pgSQL</span>
          <span class="tag orange">NASM</span>
          <span class="tag green">LaTeX</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🔧 Compilation & Système</div>
        <div class="tags">
          <span class="tag">Flex</span>
          <span class="tag">Bison</span>
          <span class="tag orange">AST</span>
          <span class="tag orange">NASM</span>
          <span class="tag green">Linux / Unix</span>
          <span class="tag green">Makefile</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">🌐 Web & Base de données</div>
        <div class="tags">
          <span class="tag">Flask</span>
          <span class="tag red">Angular</span>
          <span class="tag purple">PHP</span>
          <span class="tag blue">PostgreSQL</span>
          <span class="tag blue">MySQL</span>
          <span class="tag">HTML / CSS</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-card-title">📐 Algorithmique & Réseaux</div>
        <div class="tags">
          <span class="tag purple">Graphes</span>
          <span class="tag purple">Huffman</span>
          <span class="tag green">TCP/IP</span>
          <span class="tag green">OSI</span>
          <span class="tag blue">Wireshark</span>
          <span class="tag">Git</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projets">
    <div class="section-tag">Réalisations</div>
    <h2>Projets</h2>
    <div class="projects-list">

      <a class="project-card" href="https://github.com/KoceilaBRAIKI/tpas-C-Flex-Bison-" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">⚙️</span>
            <span class="project-name">Compilateur TPC</span>
          </div>
          <div class="project-highlight">Grammaire stratifiée · 7 niveaux de non-terminaux</div>
          <p class="project-desc">Analyseur syntaxique complet pour un sous-ensemble du C. Construction d'un ASA, localisation précise des erreurs (ligne & colonne), zéro fuite mémoire.</p>
          <div class="tags">
            <span class="tag">C</span><span class="tag">Flex</span><span class="tag">Bison</span><span class="tag orange">AST</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/KoceilaBRAIKI/codec-dif" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">🗜️</span>
            <span class="project-name">CoDec DIF</span>
          </div>
          <div class="project-highlight">Compression lossless · 47% de gain · From scratch</div>
          <p class="project-desc">Codec de compression d'images en C. Format propriétaire .dif combinant codage différentiel et encodage entropique à préfixes variables sur 4 niveaux. Architecture libdif.so séparée.</p>
          <div class="tags">
            <span class="tag">C</span><span class="tag orange">BitStream</span><span class="tag green">Unix</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/KoceilaBRAIKI" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">🛒</span>
            <span class="project-name">TrouveCompo</span>
          </div>
          <div class="project-highlight">Architecture 3 tiers · Gestion multi-rôles</div>
          <p class="project-desc">Plateforme e-commerce de composants électroniques. Client, employé, gérant — chacun avec son espace. Recherche multicritères, stock et facturation.</p>
          <div class="tags">
            <span class="tag">Python</span><span class="tag">Flask</span><span class="tag blue">PostgreSQL</span><span class="tag">Jinja2</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/KoceilaBRAIKI/backpack-hero-java" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">🎒</span>
            <span class="project-name">BackpackHero</span>
          </div>
          <div class="project-highlight">Architecture MVC · Synergies spatiales · Java</div>
          <p class="project-desc">RPG tactique au tour par tour. Inventaire en grille avec formes non-rectangulaires (L, T, Z), rotation, synergies entre objets adjacents. 3 héros, 3 étages, progression XP.</p>
          <div class="tags">
            <span class="tag orange">Java</span><span class="tag">MVC</span><span class="tag">Zen 6.0</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/KoceilaBRAIKI/stellar-assault-Python-Pygame-" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">🚀</span>
            <span class="project-name">Stellar Assault</span>
          </div>
          <div class="project-highlight">100% procédural · 15 classes · FSM 3 états</div>
          <p class="project-desc">Space shooter 2D en Python, aucun asset externe. Système de particules, effets glow BLEND_ADD, screen-shake, 4 types d'ennemis avec boss, combo multiplicateur.</p>
          <div class="tags">
            <span class="tag">Python</span><span class="tag green">Pygame</span><span class="tag purple">POO</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

      <a class="project-card" href="https://github.com/KoceilaBRAIKI/darkest-dungeon-c" target="_blank">
        <div>
          <div class="project-header">
            <span class="project-icon">⚔️</span>
            <span class="project-name">Darkest Dungeon</span>
          </div>
          <div class="project-highlight">Listes chaînées · Queue FIFO · Sauvegarde fichier</div>
          <p class="project-desc">RPG tactique en C. Gestion mémoire manuelle, structures dynamiques, 4 classes de héros, système de stress, boutique, sauvegarde persistante complète.</p>
          <div class="tags">
            <span class="tag">C</span><span class="tag orange">Structures de données</span>
          </div>
        </div>
        <div class="project-arrow">↗</div>
      </a>

    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-card">
      <h3>Disponible pour une <span style="background:linear-gradient(135deg,#6366f1,#a855f7);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;">alternance</span></h3>
      <p>Septembre 2026 · Informatique · Paris et alentours</p>
      <div class="contact-links">
        <a href="mailto:braiki.koceila@outlook.fr" class="btn btn-primary">✉ braiki.koceila@outlook.fr</a>
        <a href="https://www.linkedin.com/in/koceila-braiki" class="btn btn-ghost" target="_blank">LinkedIn</a>
        <a href="https://github.com/KoceilaBRAIKI" class="btn btn-ghost" target="_blank">GitHub</a>
      </div>
    </div>
  </section>
</div>

<footer>
  <div class="container">
    Koceila Braiki · L3 Informatique · IGM Gustave Eiffel · 2025–2026
  </div>
</footer>

</body>
</html>
