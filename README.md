[gameweb.html](https://github.com/user-attachments/files/33446449/gameweb.html)


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#080b14">
<title>MUSA GAMES | 3D Gaming Hub</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

<style>
:root {
  --bg: #080b14;
  --panel: #101727;
  --text: #f4f7ff;
  --muted: #96a3bd;
  --blue: #4f8cff;
  --cyan: #00d9ff;
  --purple: #9b6cff;
  --green: #36e6ae;
  --border: rgba(255,255,255,.1);
}

* { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; }

body {
  background:
    radial-gradient(ellipse at 10% 0%, rgba(79,140,255,.13), transparent 36%),
    radial-gradient(ellipse at 95% 20%, rgba(155,108,255,.10), transparent 35%),
    var(--bg);
  color: var(--text);
  font-family: Inter, Arial, sans-serif;
  overflow-x: hidden;
}

a { color: inherit; text-decoration: none; }
button, input { font: inherit; }
button { cursor: pointer; }
.container { width: min(1180px, 92%); margin: auto; }

/* NAVIGATION */
.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  background: rgba(8,11,20,.86);
  border-bottom: 1px solid var(--border);
  backdrop-filter: blur(18px);
}

.nav-inner {
  min-height: 76px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
  font-weight: 900;
  letter-spacing: -.8px;
  font-size: 21px;
}

.logo-icon {
  width: 42px;
  height: 42px;
  border-radius: 13px;
  display: grid;
  place-items: center;
  background: linear-gradient(135deg, var(--blue), var(--purple));
  box-shadow: 0 0 25px rgba(79,140,255,.25);
}

.logo-text {
  background: linear-gradient(90deg, #fff, var(--cyan));
  color: transparent;
  background-clip: text;
}

.nav-links { display: flex; gap: 27px; align-items: center; }

.nav-links a {
  color: var(--muted);
  font-size: 13px;
  transition: color .25s;
}

.nav-links a:hover { color: var(--cyan); }

.nav-links .nav-cta {
  padding: 12px 17px;
  border-radius: 12px;
  background: linear-gradient(120deg, var(--blue), var(--purple));
  color: white;
  font-weight: 700;
}

/* HERO */
.hero {
  min-height: 550px;
  display: grid;
  grid-template-columns: 1.1fr .9fr;
  align-items: center;
  gap: 45px;
  padding: 75px 0;
  perspective: 1200px;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 9px;
  color: var(--cyan);
  background: rgba(0,217,255,.07);
  border: 1px solid rgba(0,217,255,.2);
  border-radius: 100px;
  padding: 10px 14px;
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 1.5px;
  margin-bottom: 23px;
}

.status-dot {
  width: 7px;
  height: 7px;
  background: var(--green);
  border-radius: 50%;
  box-shadow: 0 0 12px var(--green);
}

.hero h1 {
  font-size: clamp(42px, 6vw, 75px);
  line-height: 1.02;
  letter-spacing: -4px;
  font-weight: 900;
  margin-bottom: 24px;
}

.gradient-text {
  background: linear-gradient(100deg, var(--cyan), var(--blue), var(--purple));
  color: transparent;
  background-clip: text;
}

.hero p {
  max-width: 550px;
  color: var(--muted);
  line-height: 1.9;
  font-size: 15px;
}

.hero-actions { display: flex; gap: 13px; flex-wrap: wrap; margin-top: 30px; }

.btn {
  border: 1px solid var(--border);
  border-radius: 13px;
  padding: 15px 20px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  color: white;
  font-size: 13px;
  font-weight: 800;
  transition: transform .25s, box-shadow .25s;
}

.btn:hover { transform: translateY(-4px); }

.btn-primary {
  background: linear-gradient(120deg, var(--blue), var(--purple));
  border: none;
  box-shadow: 0 12px 35px rgba(79,140,255,.2);
}

.btn-secondary { background: rgba(255,255,255,.035); }

.hero-visual {
  position: relative;
  transform-style: preserve-3d;
  transition: transform .15s ease-out;
}

.hero-image {
  width: 100%;
  height: 380px;
  object-fit: cover;
  display: block;
  border-radius: 28px;
  border: 1px solid rgba(255,255,255,.18);
  box-shadow: 0 35px 90px rgba(0,0,0,.5);
}

.hero-visual::after {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: 28px;
  background: linear-gradient(180deg, transparent 40%, rgba(8,11,20,.8));
  pointer-events: none;
}

.floating-panel {
  position: absolute;
  z-index: 2;
  bottom: 22px;
  left: 22px;
  right: 22px;
  padding: 17px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  background: rgba(10,15,28,.8);
  backdrop-filter: blur(15px);
  border: 1px solid rgba(255,255,255,.15);
  border-radius: 17px;
  transform: translateZ(45px);
}

.floating-panel strong { display: block; font-size: 14px; margin-bottom: 5px; }
.floating-panel small { color: var(--muted); font-size: 11px; }
.floating-panel i { font-size: 22px; color: var(--cyan); }

/* GAME SECTION */
.section { padding: 45px 0 85px; }

.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: end;
  gap: 20px;
  margin-bottom: 28px;
}

.section-heading h2 {
  font-size: clamp(27px, 4vw, 39px);
  letter-spacing: -1.5px;
  margin-bottom: 9px;
}

.section-heading p { color: var(--muted); font-size: 13px; line-height: 1.7; }

.game-count {
  color: var(--cyan);
  border: 1px solid rgba(0,217,255,.2);
  background: rgba(0,217,255,.06);
  border-radius: 10px;
  padding: 10px 13px;
  white-space: nowrap;
  font-size: 12px;
}

.toolbar { display: flex; gap: 13px; flex-wrap: wrap; margin-bottom: 27px; }

.search-box {
  flex: 1;
  min-width: 230px;
  display: flex;
  align-items: center;
  gap: 12px;
  background: rgba(255,255,255,.035);
  border: 1px solid var(--border);
  border-radius: 13px;
  padding: 0 15px;
}

.search-box i { color: var(--muted); }

.search-box input {
  width: 100%;
  height: 49px;
  color: white;
  outline: none;
  border: none;
  background: transparent;
  font-size: 13px;
}

.search-box input::placeholder { color: #78849d; }

.filters { display: flex; flex-wrap: wrap; gap: 8px; }

.filter-btn {
  border: 1px solid var(--border);
  background: rgba(255,255,255,.035);
  color: var(--muted);
  border-radius: 11px;
  padding: 0 15px;
  min-height: 49px;
  font-size: 12px;
  font-weight: 700;
  transition: .25s;
}

.filter-btn:hover, .filter-btn.active {
  color: white;
  border-color: rgba(0,217,255,.4);
  background: rgba(0,217,255,.1);
}

/* GAME CARDS */
.games-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0,1fr));
  gap: 23px;
  perspective: 1200px;
}

.game-card {
  min-width: 0;
  position: relative;
  overflow: hidden;
  border: 1px solid var(--border);
  border-radius: 21px;
  background: linear-gradient(155deg, #141d30, #0d1220 80%);
  transform-style: preserve-3d;
  transition: transform .15s ease-out, border-color .3s, box-shadow .3s, opacity .6s;
  opacity: 0;
  transform: translateY(25px);
}

.game-card.visible { opacity: 1; transform: translateY(0); }
.game-card:hover { border-color: rgba(0,217,255,.45); box-shadow: 0 22px 55px rgba(0,0,0,.3); }
.game-card[hidden] { display: none !important; }

.game-image-wrap {
  position: relative;
  height: 210px;
  overflow: hidden;
  background: #151d2d;
  transform: translateZ(15px);
}

.game-image {
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform .65s cubic-bezier(.2,.7,.2,1);
}

.game-card:hover .game-image { transform: scale(1.08); }

.image-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, transparent 35%, rgba(7,10,19,.88));
}

.game-tag {
  position: absolute;
  top: 13px;
  left: 13px;
  background: rgba(8,11,20,.83);
  border: 1px solid rgba(255,255,255,.15);
  padding: 7px 10px;
  border-radius: 8px;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: .5px;
  backdrop-filter: blur(10px);
}

.game-number {
  position: absolute;
  bottom: 13px;
  right: 15px;
  color: rgba(255,255,255,.65);
  font-size: 11px;
  font-weight: 700;
}

.game-info { padding: 21px; transform: translateZ(25px); }
.game-info h3 { font-size: 19px; letter-spacing: -.5px; margin-bottom: 10px; }

.game-info p {
  min-height: 43px;
  color: var(--muted);
  font-size: 12px;
  line-height: 1.8;
}

.game-meta { display: flex; flex-wrap: wrap; gap: 8px; margin: 16px 0 19px; }

.game-meta span {
  border: 1px solid rgba(255,255,255,.08);
  background: rgba(255,255,255,.035);
  color: #b9c4d8;
  border-radius: 7px;
  padding: 7px 9px;
  font-size: 10px;
}

.play-btn {
  width: 100%;
  min-height: 47px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  color: white;
  border-radius: 11px;
  background: linear-gradient(110deg, #337dff, #7958ff);
  font-size: 12px;
  font-weight: 800;
  transition: .25s;
}

.play-btn:hover {
  filter: brightness(1.15);
  box-shadow: 0 8px 25px rgba(79,140,255,.23);
}

/* WASM PANEL */
.wasm-panel {
  margin: 0 0 75px;
  padding: 35px;
  border: 1px solid rgba(0,217,255,.18);
  border-radius: 23px;
  background:
    radial-gradient(circle at 100% 0%, rgba(0,217,255,.1), transparent 38%),
    linear-gradient(140deg, #111a2a, #0c1120);
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 25px;
}

.wasm-panel h2 { font-size: 25px; margin-bottom: 12px; }
.wasm-panel p { color: var(--muted); font-size: 13px; line-height: 1.9; max-width: 650px; }
.wasm-panel .btn { margin-top: 18px; }

.wasm-icon {
  flex-shrink: 0;
  width: 70px;
  height: 70px;
  display: grid;
  place-items: center;
  border: 1px solid rgba(0,217,255,.2);
  border-radius: 20px;
  background: rgba(0,217,255,.08);
  color: var(--cyan);
  font-size: 28px;
}

/* NOTICE */
.notice {
  display: flex;
  gap: 15px;
  padding: 20px;
  border: 1px solid rgba(255,190,80,.19);
  border-radius: 15px;
  background: rgba(255,190,80,.045);
  margin-top: 28px;
}

.notice > i { color: #ffc45e; font-size: 19px; margin-top: 2px; }
.notice h4 { font-size: 13px; margin-bottom: 7px; }
.notice p { color: var(--muted); font-size: 12px; line-height: 1.9; }

/* FOOTER */
footer {
  border-top: 1px solid var(--border);
  padding: 30px 0;
  background: rgba(0,0,0,.12);
}

.footer-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 15px;
  flex-wrap: wrap;
}

.footer-inner p { color: var(--muted); font-size: 12px; }
.footer-inner strong { color: var(--cyan); }
.footer-links { display: flex; gap: 18px; }
.footer-links a { color: var(--muted); font-size: 12px; }
.footer-links a:hover { color: var(--cyan); }

/* AUTHOR CREDIT AT THE END */
.author-credit {
  border-top: 1px solid rgba(255,255,255,.07);
  margin-top: 24px;
  padding-top: 23px;
  text-align: center;
  color: #8795b0;
  font-size: 12px;
  letter-spacing: 3px;
  font-weight: 800;
}

.author-credit span {
  background: linear-gradient(90deg, var(--cyan), var(--blue), var(--purple));
  color: transparent;
  background-clip: text;
}

.reveal {
  opacity: 0;
  transform: translateY(25px);
  transition: opacity .7s ease, transform .7s ease;
}

.reveal.visible { opacity: 1; transform: translateY(0); }

/* RESPONSIVE */
@media (max-width: 900px) {
  .hero { grid-template-columns: 1fr; padding: 60px 0; gap: 35px; }
  .hero-visual { max-width: 650px; }
  .games-grid { grid-template-columns: repeat(2, minmax(0,1fr)); }
  .nav-links { gap: 15px; }
}

@media (max-width: 600px) {
  .nav-inner { min-height: 67px; }
  .logo { font-size: 17px; }
  .logo-icon { width: 37px; height: 37px; }
  .nav-links a:not(.nav-cta) { display: none; }
  .nav-links .nav-cta { padding: 10px 12px; font-size: 11px; }
  .hero { padding: 48px 0; min-height: auto; }
  .hero h1 { font-size: clamp(39px, 12vw, 58px); letter-spacing: -2.5px; }
  .hero p { font-size: 13px; }
  .hero-image { height: 280px; border-radius: 20px; }
  .floating-panel { left: 12px; right: 12px; bottom: 12px; padding: 13px; }
  .section { padding: 30px 0 55px; }
  .section-heading { align-items: start; }
  .section-heading h2 { font-size: 29px; }
  .game-count { font-size: 10px; padding: 8px; }
  .games-grid { grid-template-columns: 1fr; gap: 17px; }
  .game-image-wrap { height: 220px; }
  .game-info { padding: 18px; }
  .game-info p { min-height: 0; }
  .filter-btn { min-height: 42px; padding: 0 12px; }
  .wasm-panel { padding: 23px; flex-direction: column; align-items: flex-start; }
  .wasm-panel h2 { font-size: 22px; }
  .wasm-icon { width: 55px; height: 55px; font-size: 22px; }
  .notice { padding: 15px; }
  .footer-inner { justify-content: center; text-align: center; }
  .footer-links { justify-content: center; flex-wrap: wrap; }
  .author-credit { line-height: 1.8; }
}

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    animation-duration: .01ms !important;
    transition-duration: .01ms !important;
  }
}
</style>
</head>

<body>

<header class="navbar">
  <div class="container nav-inner">
    <a class="logo" href="#home">
      <span class="logo-icon"><i class="fa-solid fa-gamepad"></i></span>
      <span class="logo-text">MUSA GAMES</span>
    </a>

    <nav class="nav-links">
      <a href="#home">Home</a>
      <a href="#games">Games</a>
      <a href="#wasm">WASM Arcade</a>
      <a class="nav-cta" href="#games">Explore Games <i class="fa-solid fa-arrow-right"></i></a>
    </nav>
  </div>
</header>

<main>
  <section class="container hero" id="home">
    <div class="hero-copy">
      <div class="eyebrow"><span class="status-dot"></span> YOUR GAMING DESTINATION</div>
      <h1>ENTER THE<br><span class="gradient-text">GAME WORLD.</span></h1>
      <p>
        Discover browser-playable games from one modern gaming hub.
        Select a game to open its online gaming page. This website is a
        directory and does not host the games itself.
      </p>
      <div class="hero-actions">
        <a class="btn btn-primary" href="#games"><i class="fa-solid fa-play"></i> Explore Games</a>
        <a class="btn btn-secondary" href="https://wasmarcade.com/pc-games" target="_blank" rel="noopener noreferrer">
          <i class="fa-solid fa-globe"></i> WASM Arcade
        </a>
      </div>
    </div>

    <div class="hero-visual" id="heroVisual">
      <img
        class="hero-image"
        src="https://images.unsplash.com/photo-1542751371-adc38448a05e?auto=format&fit=crop&w=1200&q=85"
        alt="Gaming setup"
        fetchpriority="high">
      <div class="floating-panel">
        <div>
          <strong>YOUR NEXT ADVENTURE</strong>
          <small>Choose a game and start playing</small>
        </div>
        <i class="fa-solid fa-rocket"></i>
      </div>
    </div>
  </section>

  <section class="container section" id="games">
    <div class="section-heading reveal">
      <div>
        <h2>Explore <span class="gradient-text">Games</span></h2>
        <p>Select a game to open its corresponding online page.</p>
      </div>
      <span class="game-count"><i class="fa-solid fa-gamepad"></i> 05 GAMES</span>
    </div>

    <div class="toolbar reveal">
      <label class="search-box">
        <i class="fa-solid fa-magnifying-glass"></i>
        <input id="gameSearch" type="search" placeholder="SEARCH GAMES..." aria-label="Search games">
      </label>
      <div class="filters" aria-label="Filter games">
        <button class="filter-btn active" data-filter="all" type="button">All Games</button>
        <button class="filter-btn" data-filter="gta" type="button">GTA Series</button>
        <button class="filter-btn" data-filter="adventure" type="button">Adventure</button>
        <button class="filter-btn" data-filter="sandbox" type="button">Sandbox</button>
      </div>
    </div>

    <div class="games-grid" id="gamesGrid">

      <article class="game-card" data-category="gta adventure" data-name="gta v grand theft auto five">
        <div class="game-image-wrap">
          <img class="game-image"
               src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/271590/header.jpg"
               alt="Grand Theft Auto V artwork"
               loading="lazy"
               onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1000&q=80';">
          <div class="image-overlay"></div>
          <span class="game-tag">OPEN WORLD</span>
          <span class="game-number">GAME 01</span>
        </div>
        <div class="game-info">
          <h3>Grand Theft Auto V</h3>
          <p>Explore Los Santos through the external browser gaming page.</p>
          <div class="game-meta">
            <span><i class="fa-solid fa-earth-americas"></i> Open World</span>
            <span><i class="fa-solid fa-desktop"></i> PC</span>
          </div>
          <a class="play-btn" href="https://gta.deloskiyt.pl/" target="_blank" rel="noopener noreferrer">
            PLAY GTA V <i class="fa-solid fa-arrow-up-right-from-square"></i>
          </a>
        </div>
      </article>

      <article class="game-card" data-category="gta adventure" data-name="gta vice city">
        <div class="game-image-wrap">
          <img class="game-image"
               src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/12110/header.jpg"
               alt="Grand Theft Auto Vice City artwork"
               loading="lazy"
               onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1000&q=80';">
          <div class="image-overlay"></div>
          <span class="game-tag">ACTION</span>
          <span class="game-number">GAME 02</span>
        </div>
        <div class="game-info">
          <h3>GTA: Vice City</h3>
          <p>Visit Vice City and experience its classic open-world setting.</p>
          <div class="game-meta">
            <span><i class="fa-solid fa-city"></i> Open World</span>
            <span><i class="fa-solid fa-desktop"></i> PC</span>
          </div>
          <a class="play-btn" href="https://quenq.com/apps/vice-city/" target="_blank" rel="noopener noreferrer">
            PLAY VICE CITY <i class="fa-solid fa-arrow-up-right-from-square"></i>
          </a>
        </div>
      </article>

      <article class="game-card" data-category="gta adventure" data-name="gta iii gta 3 grand theft auto three">
        <div class="game-image-wrap">
          <img class="game-image"
               src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/12100/header.jpg"
               alt="Grand Theft Auto III artwork"
               loading="lazy"
               onerror="this.onerror=null;this.src='https://images.unsplash.com/photo-1511512578047-dfb367046420?auto=format&fit=crop&w=1000&q=80';">
          <div class="image-overlay"></div>
          <span class="game-tag">CLASSIC</span>
          <span class="game-number">GAME 03</span>
        </div>
        <div class="game-info">
          <h3>GTA III</h3>
          <p>Discover the classic city-based Grand Theft Auto experience.</p>
          <div class="game-meta">
            <span><i class="fa-solid fa-road"></i> Driving</span>
            <span><i class="fa-solid fa-desktop"></i> PC</span>
          </div>
          <a class="play-btn" href="https://wasmarcade.com/gta3" target="_blank" rel="noopener noreferrer">
            PLAY GTA III <i class="fa-solid fa-arrow-up-right-from-square"></i>
          </a>
        </div>
      </article>

      <article class="game-card" data-category="adventure" data-name="the simpsons hit and run">
        <div class="game-image-wrap">
          <img class="game-image"
               src="https://images.unsplash.com/photo-1535223289827-42f1e9919769?auto=format&fit=crop&w=1000&q=80"
               alt="Colorful gaming artwork"
               loading="lazy">
          <div class="image-overlay"></div>
          <span class="game-tag">ADVENTURE</span>
          <span class="game-number">GAME 04</span>
        </div>
        <div class="game-info">
          <h3>The Simpsons: Hit &amp; Run</h3>
          <p>A cartoon-inspired driving adventure listed on the game portal.</p>
          <div class="game-meta">
            <span><i class="fa-solid fa-car"></i> Driving</span>
            <span><i class="fa-solid fa-gamepad"></i> Adventure</span>
          </div>
          <a class="play-btn" href="https://wasmarcade.com/simpsons" target="_blank" rel="noopener noreferrer">
            PLAY GAME <i class="fa-solid fa-arrow-up-right-from-square"></i>
          </a>
        </div>
      </article>

      <article class="game-card" data-category="sandbox adventure" data-name="minecraft">
        <div class="game-image-wrap">
          <img class="game-image"
               src="https://images.unsplash.com/photo-1607513746994-51f730a44832?auto=format&fit=crop&w=1000&q=85"
               alt="Block-building game landscape"
               loading="lazy">
          <div class="image-overlay"></div>
          <span class="game-tag">SANDBOX</span>
          <span class="game-number">GAME 05</span>
        </div>
        <div class="game-info">
          <h3>Minecraft</h3>
          <p>Build, explore and create in a block-based browser game.</p>
          <div class="game-meta">
            <span><i class="fa-solid fa-cubes"></i> Sandbox</span>
            <span><i class="fa-solid fa-earth-americas"></i> Browser</span>
          </div>
          <a class="play-btn" href="https://wasmarcade.com/minecraft" target="_blank" rel="noopener noreferrer">
            PLAY MINECRAFT <i class="fa-solid fa-arrow-up-right-from-square"></i>
          </a>
        </div>
      </article>

    </div>

    <div class="notice reveal">
      <i class="fa-solid fa-triangle-exclamation"></i>
      <div>
        <h4>Before you play</h4>
        <p>
          This website is a directory, not a game emulator. Play buttons open
          third-party websites, and their availability and hardware requirements
          can vary. Be careful with unexpected downloads, browser permissions,
          and requests for personal information.
        </p>
      </div>
    </div>
  </section>

  <section class="container" id="wasm">
    <div class="wasm-panel reveal">
      <div>
        <h2>More games on <span class="gradient-text">WASM Arcade</span></h2>
        <p>
          Explore the external gaming portal for more browser game pages.
          Games may have different requirements and may not work on every device.
        </p>
        <a class="btn btn-primary" href="https://wasmarcade.com/pc-games" target="_blank" rel="noopener noreferrer">
          <i class="fa-solid fa-gamepad"></i> Browse PC Games
          <i class="fa-solid fa-arrow-up-right-from-square"></i>
        </a>
      </div>
      <div class="wasm-icon"><i class="fa-solid fa-cubes"></i></div>
    </div>
  </section>
</main>

<footer>
  <div class="container">
    <div class="footer-inner">
      <p>© <span id="year"></span> <strong>MUSA GAMES</strong></p>
      <div class="footer-links">
        <a href="#home">Home</a>
        <a href="#games">Games</a>
        <a href="https://wasmarcade.com/" target="_blank" rel="noopener noreferrer">WASM Arcade</a>
      </div>
    </div>

    <!-- Your requested name at the very end -->
    <div class="author-credit">
      CREATED WITH PASSION <span>BY MUSA SOHAIL</span>
    </div>
  </div>
</footer>

<script>
document.getElementById("year").textContent = new Date().getFullYear();

/* Search and category filters */
const searchInput = document.getElementById("gameSearch");
const filterButtons = document.querySelectorAll(".filter-btn");
const gameCards = document.querySelectorAll(".game-card");

let activeFilter = "all";

function filterGames() {
  const query = searchInput.value.trim().toLowerCase();

  gameCards.forEach(card => {
    const name = (card.dataset.name || "").toLowerCase();
    const categories = (card.dataset.category || "").toLowerCase().split(/\s+/);

    const matchesSearch = name.includes(query);
    const matchesCategory = activeFilter === "all" || categories.includes(activeFilter);

    card.hidden = !(matchesSearch && matchesCategory);
  });
}

searchInput.addEventListener("input", filterGames);

filterButtons.forEach(button => {
  button.addEventListener("click", () => {
    filterButtons.forEach(item => item.classList.remove("active"));
    button.classList.add("active");
    activeFilter = button.dataset.filter;
    filterGames();
  });
});

/* Scroll reveal */
const revealObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add("visible");
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.12 });

document.querySelectorAll(".reveal, .game-card").forEach(element => {
  revealObserver.observe(element);
});

/* Mouse-connected 3D hero */
const heroVisual = document.getElementById("heroVisual");
const reduceMotion = window.matchMedia("(prefers-reduced-motion: reduce)").matches;

if (heroVisual && !reduceMotion) {
  heroVisual.addEventListener("mousemove", event => {
    const rect = heroVisual.getBoundingClientRect();
    const x = (event.clientX - rect.left) / rect.width;
    const y = (event.clientY - rect.top) / rect.height;

    const rotateY = (x - 0.5) * 12;
    const rotateX = (0.5 - y) * 10;

    heroVisual.style.transform =
      `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
  });

  heroVisual.addEventListener("mouseleave", () => {
    heroVisual.style.transform =
      "perspective(1000px) rotateX(0deg) rotateY(0deg)";
  });
}

/* Mouse-connected 3D game cards */
if (!reduceMotion) {
  gameCards.forEach(card => {
    card.addEventListener("mousemove", event => {
      if (card.hidden) return;

      const rect = card.getBoundingClientRect();
      const x = (event.clientX - rect.left) / rect.width;
      const y = (event.clientY - rect.top) / rect.height;

      const rotateY = (x - 0.5) * 9;
      const rotateX = (0.5 - y) * 8;

      card.style.transform =
        `translateY(-3px) perspective(900px) rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
    });

    card.addEventListener("mouseleave", () => {
      card.style.transform = "";
    });
  });
}
</script>

</body>
</html>
