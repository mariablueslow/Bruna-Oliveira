   <!DOCTYPE html>
<html lang="pt-BR">
<head><base href="https://d16ilfvy4mv02r.cloudfront.net/workspaces/h9RH8zkvRUU3Txnng4IYoaMFvRWVvSoc/6ec1e875-24fe-4b5d-bc6a-87423f5cf98f/files/">
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bruna Oliveira - Joias e Semijoias | Galeria com Imagens Reais</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
  <style>
    :root {
      --gold: #C9A84C;
      --gold-light: #E8C97A;
      --gold-dark: #A07830;
      --black: #0A0A0A;
      --black-soft: #111111;
      --black-mid: #1A1A1A;
      --black-light: #222222;
      --white: #FFFFFF;
      --white-soft: #F9F5EE;
      --text-light: #CCCCCC;
      --text-muted: #888888;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Montserrat', sans-serif;
      background-color: var(--black);
      color: var(--white);
      overflow-x: hidden;
    }

    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--black); }
    ::-webkit-scrollbar-thumb { background: var(--gold); border-radius: 3px; }

    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 1000;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 18px 60px;
      background: rgba(10,10,10,0.95);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(201,168,76,0.2);
      transition: all 0.3s ease;
    }

    .nav-logo {
      display: flex;
      align-items: center;
      gap: 14px;
      text-decoration: none;
    }

    .nav-logo-icon {
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold-light));
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      color: var(--black);
      font-weight: 700;
      font-family: 'Cormorant Garamond', serif;
      box-shadow: 0 0 20px rgba(201,168,76,0.3);
    }

    .nav-logo-text {
      display: flex;
      flex-direction: column;
    }

    .nav-logo-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
      font-weight: 600;
      color: var(--gold-light);
      letter-spacing: 1px;
      line-height: 1.1;
    }

    .nav-logo-sub {
      font-size: 9px;
      font-weight: 400;
      color: var(--text-muted);
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .nav-links {
      display: flex;
      gap: 36px;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      color: var(--text-light);
      font-size: 12px;
      font-weight: 500;
      letter-spacing: 2px;
      text-transform: uppercase;
      transition: color 0.3s;
      position: relative;
      padding-bottom: 4px;
    }

    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: 0; left: 0;
      width: 0; height: 1px;
      background: var(--gold);
      transition: width 0.3s;
    }

    .nav-links a:hover { color: var(--gold); }
    .nav-links a:hover::after { width: 100%; }

    .nav-cta {
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      color: var(--black) !important;
      padding: 10px 22px !important;
      border-radius: 2px;
      font-weight: 600 !important;
      letter-spacing: 2px;
    }
    .nav-cta::after { display: none !important; }
    .nav-cta:hover { opacity: 0.9; transform: translateY(-1px); }

    .hamburger {
      display: none;
      flex-direction: column;
      gap: 5px;
      cursor: pointer;
      padding: 4px;
    }

    .hamburger span {
      display: block;
      width: 25px; height: 2px;
      background: var(--gold);
      transition: all 0.3s;
    }

    /* HERO */
    .hero {
      min-height: 100vh;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      background: var(--black);
    }

    .hero-bg {
      position: absolute;
      inset: 0;
      background: 
        radial-gradient(ellipse 80% 60% at 50% 0%, rgba(201,168,76,0.12) 0%, transparent 60%),
        radial-gradient(ellipse 50% 50% at 80% 80%, rgba(201,168,76,0.06) 0%, transparent 50%),
        linear-gradient(180deg, #0A0A0A 0%, #111111 50%, #0A0A0A 100%);
    }

    .hero-particles {
      position: absolute;
      inset: 0;
      overflow: hidden;
    }

    .particle {
      position: absolute;
      width: 2px; height: 2px;
      border-radius: 50%;
      background: var(--gold);
      opacity: 0;
      animation: float-particle linear infinite;
    }

    @keyframes float-particle {
      0% { transform: translateY(100vh) scale(0); opacity: 0; }
      10% { opacity: 0.6; }
      90% { opacity: 0.3; }
      100% { transform: translateY(-100px) scale(1.5); opacity: 0; }
    }

    .hero-content {
      position: relative;
      z-index: 2;
      text-align: center;
      padding: 0 20px;
      max-width: 900px;
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      border: 1px solid rgba(201,168,76,0.4);
      padding: 8px 20px;
      border-radius: 50px;
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 32px;
      animation: fadeInDown 1s ease forwards;
    }

    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(52px, 8vw, 100px);
      font-weight: 300;
      line-height: 1.0;
      letter-spacing: -1px;
      color: var(--white);
      margin-bottom: 12px;
    }

    .hero-title span {
      color: var(--gold-light);
      font-style: italic;
    }

    .hero-subtitle {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(18px, 3vw, 28px);
      font-weight: 300;
      color: var(--text-muted);
      letter-spacing: 6px;
      text-transform: uppercase;
      margin-bottom: 28px;
    }

    .hero-divider {
      width: 80px;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      margin: 0 auto 28px;
    }

    .hero-desc {
      font-size: 14px;
      font-weight: 300;
      color: var(--text-light);
      letter-spacing: 1px;
      line-height: 1.8;
      margin-bottom: 48px;
      max-width: 520px;
      margin-left: auto;
      margin-right: auto;
    }

    .hero-btns {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold-light));
      color: var(--black);
      text-decoration: none;
      padding: 16px 36px;
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 3px;
      text-transform: uppercase;
      border-radius: 2px;
      transition: all 0.3s;
      box-shadow: 0 8px 30px rgba(201,168,76,0.3);
    }

    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 14px 40px rgba(201,168,76,0.5);
    }

    .btn-secondary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      border: 1px solid rgba(201,168,76,0.5);
      color: var(--gold);
      text-decoration: none;
      padding: 16px 36px;
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 3px;
      text-transform: uppercase;
      border-radius: 2px;
      transition: all 0.3s;
    }

    .btn-secondary:hover {
      background: rgba(201,168,76,0.1);
      border-color: var(--gold);
      transform: translateY(-3px);
    }

    .hero-scroll {
      position: absolute;
      bottom: 32px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      color: var(--text-muted);
      font-size: 10px;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .scroll-line {
      width: 1px;
      height: 40px;
      background: linear-gradient(to bottom, var(--gold), transparent);
      animation: scroll-down 2s ease infinite;
    }

    @keyframes scroll-down {
      0% { transform: scaleY(0); transform-origin: top; }
      50% { transform: scaleY(1); transform-origin: top; }
      51% { transform: scaleY(1); transform-origin: bottom; }
      100% { transform: scaleY(0); transform-origin: bottom; }
    }

    /* ROMANEL BANNER */
    .romanel-banner {
      background: linear-gradient(135deg, var(--gold-dark) 0%, var(--gold) 50%, var(--gold-light) 100%);
      padding: 20px 0;
      overflow: hidden;
    }

    .romanel-ticker {
      display: flex;
      gap: 60px;
      animation: ticker 20s linear infinite;
      white-space: nowrap;
    }

    .romanel-ticker span {
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 4px;
      text-transform: uppercase;
      color: var(--black);
      display: flex;
      align-items: center;
      gap: 20px;
    }

    .romanel-ticker span::before { content: '✦'; font-size: 10px; }

    @keyframes ticker {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    section { padding: 100px 60px; }

    .section-label {
      font-size: 10px;
      letter-spacing: 5px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .section-label::before {
      content: '';
      width: 30px; height: 1px;
      background: var(--gold);
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(36px, 5vw, 60px);
      font-weight: 400;
      line-height: 1.1;
      color: var(--white);
      margin-bottom: 20px;
    }

    .section-title span { color: var(--gold-light); font-style: italic; }

    .section-desc {
      font-size: 14px;
      font-weight: 300;
      color: var(--text-muted);
      line-height: 1.8;
      max-width: 550px;
    }

    /* SOBRE (mantido) */
    .about {
      background: var(--black-soft);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }

    .about-image-wrap { position: relative; }
    .about-image-main {
      width: 100%;
      aspect-ratio: 4/5;
      background: linear-gradient(135deg, var(--black-mid), var(--black-light));
      border-radius: 4px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(201,168,76,0.15);
    }
    .about-badge {
      position: absolute;
      bottom: 30px;
      right: -20px;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      color: var(--black);
      padding: 16px 20px;
      border-radius: 4px;
      text-align: center;
    }
    .about-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      margin-top: 40px;
    }
    .stat-card {
      background: var(--black-light);
      border: 1px solid rgba(201,168,76,0.15);
      padding: 24px 16px;
      border-radius: 4px;
      text-align: center;
    }
    .stat-number { font-family: 'Cormorant Garamond', serif; font-size: 36px; font-weight: 600; color: var(--gold-light); }
    .stat-label { font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--text-muted); }

    /* CATEGORIAS COM IMAGENS REAIS */
    .categorias { background: var(--black); text-align: center; }
    .categorias-header { margin-bottom: 60px; }
    .categorias-header .section-label { justify-content: center; }
    .categorias-header .section-label::before { display: none; }

    .cat-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 28px;
      max-width: 1300px;
      margin: 0 auto;
    }

    .cat-card {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.15);
      border-radius: 8px;
      overflow: hidden;
      transition: all 0.4s;
      text-decoration: none;
      color: inherit;
      display: block;
    }

    .cat-card:hover {
      border-color: var(--gold);
      transform: translateY(-6px);
      box-shadow: 0 20px 50px rgba(201,168,76,0.15);
    }

    .cat-img {
      width: 100%;
      aspect-ratio: 1 / 1;
      object-fit: cover;
      display: block;
      transition: transform 0.4s;
    }
    .cat-card:hover .cat-img { transform: scale(1.02); }

    .cat-info { padding: 20px 16px 24px; text-align: center; }
    .cat-name { font-family: 'Cormorant Garamond', serif; font-size: 22px; font-weight: 600; color: var(--white); margin-bottom: 6px; }
    .cat-desc { font-size: 12px; color: var(--text-muted); line-height: 1.5; margin-bottom: 12px; }
    .cat-tag { display: inline-block; font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--gold); border: 1px solid rgba(201,168,76,0.3); padding: 4px 12px; border-radius: 50px; }

    /* GALERIA COM IMAGENS REAIS */
    .galeria { background: var(--black-soft); text-align: center; }
    .galeria-header { margin-bottom: 60px; }
    .galeria-header .section-label { justify-content: center; }
    .galeria-header .section-label::before { display: none; }

    .galeria-filtros {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      margin-bottom: 50px;
    }
    .filtro-btn {
      background: transparent;
      border: 1px solid rgba(201,168,76,0.3);
      padding: 8px 18px;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--text-muted);
      cursor: pointer;
      transition: all 0.3s;
      border-radius: 30px;
      font-weight: 500;
    }
    .filtro-btn:hover, .filtro-btn.active {
      background: var(--gold);
      color: var(--black);
      border-color: var(--gold);
    }

    .galeria-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 24px;
      max-width: 1300px;
      margin: 0 auto 50px;
    }
    .galeria-item {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.12);
      border-radius: 8px;
      overflow: hidden;
      transition: all 0.4s;
    }
    .galeria-item:hover {
      border-color: var(--gold);
      transform: translateY(-5px);
    }
    .galeria-img {
      width: 100%;
      aspect-ratio: 1 / 1;
      object-fit: cover;
      display: block;
    }
    .galeria-info { padding: 18px; text-align: left; }
    .galeria-cat { font-size: 9px; letter-spacing: 2px; text-transform: uppercase; color: var(--gold); margin-bottom: 6px; }
    .galeria-titulo { font-family: 'Cormorant Garamond', serif; font-size: 18px; color: var(--white); margin-bottom: 4px; }
    .galeria-preco { font-size: 11px; color: var(--text-muted); margin-bottom: 12px; }
    .galeria-link { display: inline-flex; align-items: center; gap: 6px; font-size: 11px; letter-spacing: 1.5px; color: var(--gold); text-decoration: none; font-weight: 600; }

    /* ROMANEL, DIFERENCIAIS, DEPOIMENTOS, CONTATO (manter estilos) */
    .romanel, .contato { background: var(--black-soft); display: grid; grid-template-columns: 1fr 1fr; gap: 80px; align-items: center; }
    .romanel-visual { position: relative; display: flex; justify-content: center; }
    .romanel-logo-box { width: 280px; height: 280px; border-radius: 50%; background: linear-gradient(135deg, var(--black-mid), var(--black-light)); border: 2px solid rgba(201,168,76,0.3); display: flex; align-items: center; justify-content: center; flex-direction: column; }
    .romanel-logo-box .r-text { font-family: 'Cormorant Garamond', serif; font-size: 80px; font-weight: 700; color: var(--gold-light); }
    .romanel-ring { position: absolute; border-radius: 50%; border: 1px solid rgba(201,168,76,0.2); animation: rotate-ring 20s linear infinite; }
    .romanel-ring:nth-child(1) { width: 340px; height: 340px; }
    .romanel-ring:nth-child(2) { width: 400px; height: 400px; animation-duration: 30s; animation-direction: reverse; border-style: dashed; }
    @keyframes rotate-ring { from { transform: rotate(0deg); } to { transform: rotate(360deg); } }
    .romanel-features { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 36px; }
    .romanel-feat { display: flex; gap: 12px; padding: 16px; background: rgba(201,168,76,0.05); border: 1px solid rgba(201,168,76,0.1); border-radius: 4px; }
    .dif-grid, .dep-grid, .prod-grid { display: grid; gap: 24px; max-width: 1100px; margin: 0 auto; }
    .dif-grid { grid-template-columns: repeat(4, 1fr); }
    .dep-grid { grid-template-columns: repeat(3, 1fr); }
    .prod-grid { grid-template-columns: repeat(3, 1fr); margin-bottom: 50px; }
    .dif-card, .dep-card, .prod-card { background: var(--black-mid); border: 1px solid rgba(201,168,76,0.12); border-radius: 4px; padding: 32px 20px; transition: all 0.3s; }
    .contato-form { background: var(--black-mid); border: 1px solid rgba(201,168,76,0.15); padding: 40px; border-radius: 4px; }
    .form-group input, .form-group textarea, .form-group select { width: 100%; background: rgba(255,255,255,0.04); border: 1px solid rgba(201,168,76,0.2); padding: 14px; color: white; }
    .form-submit { background: linear-gradient(135deg, var(--gold-dark), var(--gold)); color: black; width: 100%; padding: 16px; font-weight: 700; border: none; cursor: pointer; }
    .whatsapp-float { position: fixed; bottom: 28px; right: 28px; z-index: 999; width: 56px; height: 56px; border-radius: 50%; background: #25D366; display: flex; align-items: center; justify-content: center; color: white; font-size: 26px; text-decoration: none; box-shadow: 0 6px 25px rgba(37,211,102,0.4); transition: all 0.3s; animation: pulse-wa 3s ease infinite; }
    @keyframes pulse-wa { 0%, 100% { box-shadow: 0 6px 25px rgba(37,211,102,0.4); } 50% { box-shadow: 0 6px 40px rgba(37,211,102,0.7), 0 0 0 8px rgba(37,211,102,0.1); } }
    .reveal { opacity: 0; transform: translateY(40px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    @media (max-width: 900px) {
      nav { padding: 16px 24px; }
      .nav-links { display: none; }
      .hamburger { display: flex; }
      section { padding: 70px 24px; }
      .about, .romanel, .contato { grid-template-columns: 1fr; }
      .cat-grid, .galeria-grid, .dif-grid { grid-template-columns: repeat(2, 1fr); }
      .prod-grid, .dep-grid { grid-template-columns: 1fr; }
      .about-image-wrap { display: none; }
    }
    @media (max-width: 600px) {
      .cat-grid, .galeria-grid, .dif-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<a href="https://wa.me/5538992117178" target="_blank" class="whatsapp-float"><i class="fab fa-whatsapp"></i></a>

<nav id="navbar">
  <a href="#" class="nav-logo">
    <div class="nav-logo-icon">B</div>
    <div class="nav-logo-text"><span class="nav-logo-name">Bruna Oliveira</span><span class="nav-logo-sub">Joias & Semijoias</span></div>
  </a>
  <ul class="nav-links">
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#categorias">Coleções</a></li>
    <li><a href="#galeria">Galeria</a></li>
    <li><a href="#romanel">Romanel</a></li>
    <li><a href="#diferenciais">Diferenciais</a></li>
    <li><a href="#contato" class="nav-cta">Contato</a></li>
  </ul>
  <div class="hamburger" onclick="toggleMenu()"><span></span><span></span><span></span></div>
</nav>

<section class="hero" id="inicio">
  <div class="hero-bg"></div>
  <div class="hero-particles" id="particles"></div>
  <div class="hero-content">
    <div class="hero-badge"><i class="fas fa-gem"></i> Revendedora Oficial Romanel <i class="fas fa-gem"></i></div>
    <h1 class="hero-title">Bruna<br><span>Oliveira</span></h1>
    <p class="hero-subtitle">Joias e Semijoias · Acessórios</p>
    <div class="hero-divider"></div>
    <p class="hero-desc">Elegância e sofisticação em cada peça. Descubra nossa coleção exclusiva com imagens reais dos produtos.</p>
    <div class="hero-btns">
      <a href="https://wa.me/5538992117178" target="_blank" class="btn-primary"><i class="fab fa-whatsapp"></i> Ver Coleção</a>
      <a href="#galeria" class="btn-secondary"><i class="fas fa-images"></i> Galeria Premium</a>
    </div>
  </div>
  <div class="hero-scroll"><div class="scroll-line"></div><span>Scroll</span></div>
</section>

<div class="romanel-banner"><div class="romanel-ticker" id="ticker"><span>Revendedora Oficial Romanel</span><span>Joias Banhadas em Ouro</span><span>Semijoias de Alta Qualidade</span><span>Entrega em Coração de Jesus e Região</span><span>Garantia de Qualidade</span><span>Atendimento Personalizado</span><span>Revendedora Oficial Romanel</span></div></div>

<section class="about" id="sobre">
  <div class="about-image-wrap reveal"><div class="about-image-main"><span>💎</span></div><div class="about-badge"><strong>100%</strong><span>Romanel</span></div></div>
  <div class="reveal"><div class="section-label">Nossa História</div><h2 class="section-title">Paixão por <span>Elegância</span></h2><p class="section-desc">Bruna Oliveira Joias e Semijoias, revendedora oficial Romanel em Coração de Jesus – MG. Qualidade e atendimento personalizado.</p><div class="about-stats"><div class="stat-card"><div class="stat-number">💛</div><div class="stat-label">Qualidade</div></div><div class="stat-card"><div class="stat-number">✦</div><div class="stat-label">Romanel</div></div><div class="stat-card"><div class="stat-number">🏅</div><div class="stat-label">Garantia</div></div></div></div>
</section>

<!-- CATEGORIAS COM IMAGENS REAIS -->
<section class="categorias" id="categorias">
  <div class="categorias-header reveal"><div class="section-label">Nossas Coleções</div><h2 class="section-title">Imagens Reais das <span>Peças</span></h2><p class="section-desc" style="margin:0 auto">Clique e solicite via WhatsApp a joia que mais combina com você.</p></div>
  <div class="cat-grid">
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20colares%20disponíveis." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1599643477877-530eb83abc8e?w=400&h=400&fit=crop" alt="Colar Ouro"/><div class="cat-info"><div class="cat-name">Colares</div><div class="cat-desc">Peças delicadas e sofisticadas</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20anéis." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=400&h=400&fit=crop" alt="Anel Solitário"/><div class="cat-info"><div class="cat-name">Anéis</div><div class="cat-desc">Solitários, alianças e cravejados</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20as%20pulseiras." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1611652022419-a9419f74343d?w=400&h=400&fit=crop" alt="Pulseira Ouro"/><div class="cat-info"><div class="cat-name">Pulseiras</div><div class="cat-desc">Braceletes e elos modernos</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20brincos." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=400&h=400&fit=crop" alt="Brincos Argola"/><div class="cat-info"><div class="cat-name">Brincos</div><div class="cat-desc">Argolas, pérolas e maxi</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20tornozeleiras." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1509316975850-ff9c5e7f16a5?w=400&h=400&fit=crop" alt="Tornozeleira"/><div class="cat-info"><div class="cat-name">Tornozeleiras</div><div class="cat-desc">Delicadas e charmosas</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20cordões%20femininos." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?w=400&h=400&fit=crop" alt="Cordão Feminino"/><div class="cat-info"><div class="cat-name">Cordão Feminino</div><div class="cat-desc">Corrente e pingentes</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20cordões%20masculinos." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1611591437281-460bfbe1220a?w=400&h=400&fit=crop" alt="Cordão Masculino"/><div class="cat-info"><div class="cat-name">Cordão Masculino</div><div class="cat-desc">Estilo robusto e elegante</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20relógios." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1524592094714-0f0654e20314?w=400&h=400&fit=crop" alt="Relógio Premium"/><div class="cat-info"><div class="cat-name">Relógios</div><div class="cat-desc">Elegância e precisão</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20pingentes." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1589674781759-21f379bbdcde?w=400&h=400&fit=crop" alt="Pingente"/><div class="cat-info"><div class="cat-name">Pingentes</div><div class="cat-desc">Estrelas, corações e mais</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20bolsas." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1584917865442-de89df76afd3?w=400&h=400&fit=crop" alt="Bolsa"/><div class="cat-info"><div class="cat-name">Bolsas</div><div class="cat-desc">Modelos exclusivos</div><span class="cat-tag">Ver Coleção</span></div></a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20carteiras." target="_blank" class="cat-card reveal"><img class="cat-img" src="https://images.unsplash.com/photo-1601924994987-69e26d50dc26?w=400&h=400&fit=crop" alt="Carteira"/><div class="cat-info"><div class="cat-name">Carteiras</div><div class="cat-desc">Finos acabamentos</div><span class="cat-tag">Ver Coleção</span></div></a>
  </div>
</section>

<!-- GALERIA PREMIUM COM IMAGENS REAIS -->
<section class="galeria" id="galeria">
  <div class="galeria-header reveal"><div class="section-label">Galeria Premium</div><h2 class="section-title">Produtos em <span>Imagens Reais</span></h2><p class="section-desc" style="margin:0 auto">Filtre por categoria e veja as joias disponíveis.</p></div>
  <div class="galeria-filtros" id="filtrosGaleria">
    <button class="filtro-btn active" data-filter="todos">Todos</button>
    <button class="filtro-btn" data-filter="aneis">Anéis</button>
    <button class="filtro-btn" data-filter="colares">Colares</button>
    <button class="filtro-btn" data-filter="pulseiras">Pulseiras</button>
    <button class="filtro-btn" data-filter="brincos">Brincos</button>
    <button class="filtro-btn" data-filter="cordao">Cordões</button>
    <button class="filtro-btn" data-filter="relogios">Relógios</button>
  </div>
  <div class="galeria-grid" id="galeriaGrid"></div>
  <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20o%20catálogo%20completo." class="btn-primary reveal" style="display:inline-flex;"><i class="fab fa-whatsapp"></i> Catálogo Completo</a>
</section>

<section class="romanel" id="romanel">
  <div class="reveal"><div class="section-label">Parceria Exclusiva</div><h2 class="section-title">Somos <span>Romanel</span></h2><p class="section-desc">Maior marca do Brasil, produção 100% nacional e garantia vitalícia.</p><div class="romanel-features"><div class="romanel-feat"><i class="fas fa-award"></i><div><strong>Maior do Brasil</strong><br><span>Líder em joias</span></div></div><div class="romanel-feat"><i class="fas fa-shield-alt"></i><div><strong>Garantia Vitalícia</strong><br><span>Banho de qualidade</span></div></div><div class="romanel-feat"><i class="fas fa-industry"></i><div><strong>100% Nacional</strong><br><span>Produção brasileira</span></div></div><div class="romanel-feat"><i class="fas fa-gem"></i><div><strong>Design Exclusivo</strong><br><span>Coleções renovadas</span></div></div></div></div>
  <div class="romanel-visual reveal"><div class="romanel-ring"></div><div class="romanel-ring"></div><div class="romanel-logo-box"><div class="r-text">R</div><div class="r-sub">Romanel</div></div></div>
</section>

<section class="diferenciais" id="diferenciais"><div class="dif-header reveal"><div class="section-label">Por Que Escolher</div><h2 class="section-title">Nossos <span>Diferenciais</span></h2></div><div class="dif-grid"><div class="dif-card reveal"><div class="dif-icon"><i class="fas fa-certificate"></i></div><div class="dif-title">Produto Original</div><div class="dif-text">Romanel com certificado</div></div><div class="dif-card reveal"><div class="dif-icon"><i class="fas fa-headset"></i></div><div class="dif-title">Atendimento VIP</div><div class="dif-text">Consultoria personalizada</div></div><div class="dif-card reveal"><div class="dif-icon"><i class="fas fa-map-marker-alt"></i></div><div class="dif-title">Atende Sua Região</div><div class="dif-text">Coração de Jesus e entorno</div></div><div class="dif-card reveal"><div class="dif-icon"><i class="fas fa-heart"></i></div><div class="dif-title">Feito com Amor</div><div class="dif-text">Cuidado em cada detalhe</div></div></div></section>

<section class="contato" id="contato"><div class="contato-info reveal"><div class="section-label">Fale Conosco</div><h2 class="section-title">Entre em <span>Contato</span></h2><div class="contato-item"><div class="contato-icon"><i class="fab fa-whatsapp"></i></div><div><div class="contato-label">WhatsApp</div><div class="contato-value">(38) 9.9211-7178</div></div></div><div class="contato-item"><div class="contato-icon"><i class="fab fa-instagram"></i></div><div><div class="contato-label">Instagram</div><div class="contato-value">@bruna_oliveira_acessorios</div></div></div></div><div class="contato-form reveal"><div class="form-title">Envie uma Mensagem</div><div class="form-sub">Preencha e fale conosco via WhatsApp</div><div class="form-group"><label>Seu Nome</label><input type="text" id="formNome" placeholder="Seu nome"></div><div class="form-group"><label>Telefone</label><input type="tel" id="formTel" placeholder="(00) 0.0000-0000"></div><div class="form-group"><label>Interesse</label><select id="formInteresse"><option>Colares</option><option>Anéis</option><option>Pulseiras</option><option>Brincos</option><option>Tornozeleira</option><option>Cordão</option><option>Relógios</option><option>Bolsas/Carteiras</option></select></div><div class="form-group"><label>Mensagem</label><textarea id="formMsg" placeholder="Detalhe o que procura..."></textarea></div><button class="form-submit" onclick="enviarFormContato()"><i class="fab fa-whatsapp"></i> Enviar agora</button></div></section>

<footer><div class="footer-top"><div class="footer-brand"><a href="#" class="nav-logo"><div class="nav-logo-icon">B</div><div class="nav-logo-text"><span class="nav-logo-name">Bruna Oliveira</span><span class="nav-logo-sub">Joias & Semijoias</span></div></a><p>Revendedora oficial Romanel em Coração de Jesus – MG.</p><div class="social-links"><a href="#" class="social-btn"><i class="fab fa-instagram"></i></a><a href="#" class="social-btn"><i class="fab fa-whatsapp"></i></a></div></div><div class="footer-col"><h4>Navegação</h4><ul><li><a href="#sobre">Sobre</a></li><li><a href="#categorias">Coleções</a></li><li><a href="#galeria">Galeria</a></li><li><a href="#contato">Contato</a></li></ul></div><div class="footer-col"><h4>Categorias</h4><ul><li><a href="#">Colares</a></li><li><a href="#">Anéis</a></li><li><a href="#">Tornozeleiras</a></li><li><a href="#">Relógios</a></li></ul></div><div class="footer-col"><h4>Contato</h4><ul><li><a href="https://wa.me/5538992117178">(38) 9.9211-7178</a></li><li><a href="#">Coração de Jesus, MG</a></li></ul></div></div><div class="footer-bottom"><p>© 2024 <span>Bruna Oliveira Joias & Semijoias</span> — Todos os direitos reservados.</p><p>Revendedora Oficial <span>Romanel</span> ✦ MG</p></div></footer>

<script>
  // Array de produtos da galeria com imagens reais
  const produtosGaleria = [
    { nome: "Anel Solitário Ouro", categoria: "aneis", img: "https://images.unsplash.com/photo-1605100804763-247f67b3557e?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Colar Corrente Feminina", categoria: "colares", img: "https://images.unsplash.com/photo-1599643477877-530eb83abc8e?w=400&h=400&fit=crop", preco: "Consulte" },
    { nome: "Pulseira Elos Dourados", categoria: "pulseiras", img: "https://images.unsplash.com/photo-1611652022419-a9419f74343d?w=400&h=400&fit=crop", preco: "Promoção" },
    { nome: "Brinco Argolas Maxi", categoria: "brincos", img: "https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Cordão Masculino Aço", categoria: "cordao", img: "https://images.unsplash.com/photo-1611591437281-460bfbe1220a?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Relógio Premium Dourado", categoria: "relogios", img: "https://images.unsplash.com/photo-1524592094714-0f0654e20314?w=400&h=400&fit=crop", preco: "Lançamento" },
    { nome: "Tornozeleira Pérolas", categoria: "pulseiras", img: "https://images.unsplash.com/photo-1509316975850-ff9c5e7f16a5?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Anel Duas Cores", categoria: "aneis", img: "https://images.unsplash.com/photo-1603561591411-07134e71a2a9?w=400&h=400&fit=crop", preco: "Exclusivo" },
    { nome: "Cordão Feminino Coração", categoria: "cordao", img: "https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Brinco Pedra Lunar", categoria: "brincos", img: "https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=400&h=400&fit=crop", preco: "Super Oferta" },
    { nome: "Pulseira de Couro", categoria: "pulseiras", img: "https://images.unsplash.com/photo-1589674781759-21f379bbdcde?w=400&h=400&fit=crop", preco: "Sob Consulta" },
    { nome: "Colar Masculino Prata", categoria: "colares", img: "https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=400&h=400&fit=crop", preco: "Consulte" },
    { nome: "Relógio Pulseira Feminina", categoria: "relogios", img: "https://images.unsplash.com/photo-1522312346375-d1a52e2b99b3?w=400&h=400&fit=crop", preco: "Parcele já" },
    { nome: "Anel Cravejado Rubi", categoria: "aneis", img: "https://images.unsplash.com/photo-1583402217325-eeaa6a1a50e7?w=400&h=400&fit=crop", preco: "Sob Consulta" }
  ];

  function renderizarGaleria(filtro = "todos") {
    const grid = document.getElementById("galeriaGrid");
    if (!grid) return;
    const filtrados = filtro === "todos" ? produtosGaleria : produtosGaleria.filter(p => p.categoria === filtro);
    grid.innerHTML = filtrados.map(prod => `
      <div class="galeria-item reveal" data-categoria="${prod.categoria}">
        <img class="galeria-img" src="${prod.img}" alt="${prod.nome}">
        <div class="galeria-info">
          <div class="galeria-cat">${prod.categoria.toUpperCase()}</div>
          <div class="galeria-titulo">${prod.nome}</div>
          <div class="galeria-preco">${prod.preco}</div>
          <a href="https://wa.me/5538992117178?text=Olá!%20Tenho%20interesse%20na%20peça%20*${encodeURIComponent(prod.nome)}*" target="_blank" class="galeria-link">Solicitar <i class="fas fa-arrow-right"></i></a>
        </div>
      </div>
    `).join('');
    document.querySelectorAll('.galeria-item.reveal').forEach(el => observer.observe(el));
  }

  function initFiltros() {
    const botoes = document.querySelectorAll('.filtro-btn');
    botoes.forEach(btn => {
      btn.addEventListener('click', () => {
        botoes.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        renderizarGaleria(btn.getAttribute('data-filter'));
      });
    });
  }

  // Partículas, observer, menu etc
  const container = document.getElementById('particles');
  if(container){
    for (let i = 0; i < 30; i++) {
      const p = document.createElement('div');
      p.className = 'particle';
      p.style.cssText = `left: ${Math.random() * 100}%; width: ${Math.random() * 3 + 1}px; height: ${Math.random() * 3 + 1}px; animation-duration: ${Math.random() * 10 + 8}s; animation-delay: ${Math.random() * 10}s;`;
      container.appendChild(p);
    }
  }

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => { if (entry.isIntersecting) { entry.target.classList.add('visible'); observer.unobserve(entry.target); } });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  window.addEventListener('scroll', () => {
    const nav = document.getElementById('navbar');
    if (window.scrollY > 60) nav.style.padding = '12px 60px';
    else nav.style.padding = '18px 60px';
  });

  function toggleMenu() {
    const links = document.querySelector('.nav-links');
    links.style.display = links.style.display === 'flex' ? 'none' : 'flex';
    links.style.flexDirection = 'column';
    links.style.position = 'absolute';
    links.style.top = '70px'; links.style.left = '0'; links.style.right = '0';
    links.style.background = 'rgba(10,10,10,0.98)'; links.style.padding = '24px';
  }

  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });

  function enviarFormContato() {
    const nome = document.getElementById('formNome')?.value || '';
    const tel = document.getElementById('formTel')?.value || '';
    const interesse = document.getElementById('formInteresse')?.value || '';
    const msg = document.getElementById('formMsg')?.value || '';
    if (!nome) { alert('Por favor, informe seu nome.'); return; }
    const texto = `Olá Bruna! Me chamo *${nome}*.%0A📱 Telefone: ${tel}%0A💎 Interesse: ${interesse}%0A💬 Mensagem: ${msg || 'Gostaria de mais informações.'}`;
    window.open(`https://wa.me/5538992117178?text=${texto}`, '_blank');
  }

  window.enviarFormContato = enviarFormContato;
  window.toggleMenu = toggleMenu;
  renderizarGaleria('todos');
  initFiltros();
</script>
</body>
</html>

     
