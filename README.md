<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bruna Oliveira - Joias e Semijoias</title>
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

    /* ─── SCROLLBAR ─── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: var(--black); }
    ::-webkit-scrollbar-thumb { background: var(--gold); border-radius: 3px; }

    /* ─── NAVBAR ─── */
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

    /* ─── HERO ─── */
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

    .hero-badge i { font-size: 10px; }

    .hero-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(52px, 8vw, 100px);
      font-weight: 300;
      line-height: 1.0;
      letter-spacing: -1px;
      color: var(--white);
      margin-bottom: 12px;
      animation: fadeInUp 1s ease 0.2s both;
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
      animation: fadeInUp 1s ease 0.4s both;
    }

    .hero-divider {
      width: 80px;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      margin: 0 auto 28px;
      animation: fadeIn 1s ease 0.6s both;
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
      animation: fadeInUp 1s ease 0.6s both;
    }

    .hero-btns {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeInUp 1s ease 0.8s both;
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
      animation: fadeIn 2s ease 1.5s both;
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

    /* ─── ROMANEL BANNER ─── */
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

    .romanel-ticker span::before {
      content: '✦';
      font-size: 10px;
    }

    @keyframes ticker {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    /* ─── SECTIONS COMMON ─── */
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

    /* ─── SOBRE / ABOUT ─── */
    .about {
      background: var(--black-soft);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }

    .about-image-wrap {
      position: relative;
    }

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

    .about-image-main::before {
      content: '';
      position: absolute;
      inset: 0;
      background: 
        radial-gradient(circle at 30% 30%, rgba(201,168,76,0.1) 0%, transparent 50%),
        radial-gradient(circle at 70% 70%, rgba(201,168,76,0.05) 0%, transparent 50%);
    }

    .about-image-decor {
      position: absolute;
      bottom: -20px;
      right: -20px;
      width: 120px; height: 120px;
      border: 1px solid var(--gold);
      border-radius: 4px;
      opacity: 0.3;
    }

    .about-image-decor2 {
      position: absolute;
      top: -20px;
      left: -20px;
      width: 80px; height: 80px;
      border: 1px solid var(--gold);
      border-radius: 4px;
      opacity: 0.2;
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
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }

    .about-badge strong {
      display: block;
      font-size: 28px;
      font-family: 'Cormorant Garamond', serif;
      font-weight: 700;
    }

    .about-badge span {
      font-size: 9px;
      letter-spacing: 2px;
      text-transform: uppercase;
      font-weight: 600;
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
      transition: border-color 0.3s;
    }

    .stat-card:hover { border-color: var(--gold); }

    .stat-number {
      font-family: 'Cormorant Garamond', serif;
      font-size: 36px;
      font-weight: 600;
      color: var(--gold-light);
    }

    .stat-label {
      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-top: 4px;
    }

    /* ─── CATEGORIAS ─── */
    .categorias {
      background: var(--black);
      text-align: center;
    }

    .categorias-header { margin-bottom: 60px; }
    .categorias-header .section-label { justify-content: center; }
    .categorias-header .section-label::before { display: none; }

    .cat-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .cat-card {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.15);
      border-radius: 4px;
      padding: 40px 20px;
      cursor: pointer;
      transition: all 0.4s;
      position: relative;
      overflow: hidden;
      text-decoration: none;
      color: inherit;
      display: block;
    }

    .cat-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(201,168,76,0.05), transparent);
      opacity: 0;
      transition: opacity 0.3s;
    }

    .cat-card:hover {
      border-color: var(--gold);
      transform: translateY(-6px);
      box-shadow: 0 20px 50px rgba(201,168,76,0.15);
    }

    .cat-card:hover::before { opacity: 1; }

    .cat-icon {
      font-size: 36px;
      margin-bottom: 16px;
      display: block;
    }

    .cat-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
      font-weight: 600;
      color: var(--white);
      margin-bottom: 8px;
    }

    .cat-desc {
      font-size: 11px;
      color: var(--text-muted);
      letter-spacing: 1px;
      line-height: 1.6;
    }

    .cat-tag {
      display: inline-block;
      margin-top: 16px;
      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--gold);
      border: 1px solid rgba(201,168,76,0.3);
      padding: 4px 12px;
      border-radius: 50px;
    }

    /* ─── ROMANEL SECTION ─── */
    .romanel {
      background: var(--black-soft);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: center;
    }

    .romanel-visual {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .romanel-logo-box {
      width: 280px; height: 280px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--black-mid), var(--black-light));
      border: 2px solid rgba(201,168,76,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      gap: 8px;
      box-shadow: 0 0 60px rgba(201,168,76,0.15), inset 0 0 60px rgba(201,168,76,0.05);
    }

    .romanel-logo-box .r-text {
      font-family: 'Cormorant Garamond', serif;
      font-size: 80px;
      font-weight: 700;
      color: var(--gold-light);
      line-height: 1;
    }

    .romanel-logo-box .r-sub {
      font-size: 9px;
      letter-spacing: 5px;
      color: var(--gold);
      text-transform: uppercase;
    }

    .romanel-ring {
      position: absolute;
      border-radius: 50%;
      border: 1px solid rgba(201,168,76,0.2);
      animation: rotate-ring 20s linear infinite;
    }

    .romanel-ring:nth-child(1) { width: 340px; height: 340px; animation-duration: 20s; }
    .romanel-ring:nth-child(2) { width: 400px; height: 400px; animation-duration: 30s; animation-direction: reverse; border-style: dashed; }

    @keyframes rotate-ring {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .romanel-features {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 16px;
      margin-top: 36px;
    }

    .romanel-feat {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      padding: 16px;
      background: rgba(201,168,76,0.05);
      border: 1px solid rgba(201,168,76,0.1);
      border-radius: 4px;
      transition: border-color 0.3s;
    }

    .romanel-feat:hover { border-color: rgba(201,168,76,0.4); }

    .romanel-feat i {
      color: var(--gold);
      font-size: 16px;
      margin-top: 2px;
    }

    .romanel-feat-text strong {
      display: block;
      font-size: 13px;
      color: var(--white);
      margin-bottom: 4px;
    }

    .romanel-feat-text span {
      font-size: 11px;
      color: var(--text-muted);
      line-height: 1.5;
    }

    /* ─── DESTAQUES / PRODUTOS ─── */
    .produtos {
      background: var(--black);
      text-align: center;
    }

    .produtos-header { margin-bottom: 60px; }
    .produtos-header .section-label { justify-content: center; }
    .produtos-header .section-label::before { display: none; }

    .prod-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
      max-width: 1100px;
      margin: 0 auto 50px;
    }

    .prod-card {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.12);
      border-radius: 4px;
      overflow: hidden;
      transition: all 0.4s;
      text-align: left;
      cursor: pointer;
    }

    .prod-card:hover {
      border-color: var(--gold);
      transform: translateY(-6px);
      box-shadow: 0 20px 50px rgba(201,168,76,0.12);
    }

    .prod-img {
      width: 100%;
      aspect-ratio: 1;
      background: linear-gradient(135deg, var(--black-light), var(--black-mid));
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 56px;
      position: relative;
      overflow: hidden;
    }

    .prod-img::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to bottom, transparent 60%, rgba(0,0,0,0.5));
    }

    .prod-badge-new {
      position: absolute;
      top: 12px; left: 12px;
      background: var(--gold);
      color: var(--black);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: 2px;
      padding: 4px 10px;
      border-radius: 2px;
      text-transform: uppercase;
      z-index: 2;
    }

    .prod-info {
      padding: 20px;
    }

    .prod-cat {
      font-size: 9px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 8px;
    }

    .prod-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
      color: var(--white);
      margin-bottom: 8px;
      font-weight: 500;
    }

    .prod-desc {
      font-size: 11px;
      color: var(--text-muted);
      line-height: 1.6;
      margin-bottom: 16px;
    }

    .prod-cta {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 600;
      transition: gap 0.3s;
    }

    .prod-card:hover .prod-cta { gap: 14px; }

    /* ─── DIFERENCIAIS ─── */
    .diferenciais {
      background: var(--black-soft);
      text-align: center;
    }

    .dif-header { margin-bottom: 60px; }
    .dif-header .section-label { justify-content: center; }
    .dif-header .section-label::before { display: none; }

    .dif-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 24px;
      max-width: 1100px;
      margin: 0 auto;
    }

    .dif-card {
      padding: 40px 20px;
      border: 1px solid rgba(201,168,76,0.1);
      border-radius: 4px;
      transition: all 0.4s;
      background: var(--black-mid);
      position: relative;
      overflow: hidden;
    }

    .dif-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      opacity: 0;
      transition: opacity 0.3s;
    }

    .dif-card:hover {
      border-color: rgba(201,168,76,0.3);
      transform: translateY(-4px);
    }

    .dif-card:hover::before { opacity: 1; }

    .dif-icon {
      width: 64px; height: 64px;
      border-radius: 50%;
      background: rgba(201,168,76,0.08);
      border: 1px solid rgba(201,168,76,0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 20px;
      font-size: 22px;
      color: var(--gold);
    }

    .dif-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 20px;
      color: var(--white);
      margin-bottom: 12px;
    }

    .dif-text {
      font-size: 12px;
      color: var(--text-muted);
      line-height: 1.7;
    }

    /* ─── DEPOIMENTOS ─── */
    .depoimentos {
      background: var(--black);
      text-align: center;
    }

    .dep-header { margin-bottom: 60px; }
    .dep-header .section-label { justify-content: center; }
    .dep-header .section-label::before { display: none; }

    .dep-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
      max-width: 1100px;
      margin: 0 auto;
    }

    .dep-card {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.12);
      border-radius: 4px;
      padding: 32px;
      text-align: left;
      position: relative;
      transition: border-color 0.3s;
    }

    .dep-card:hover { border-color: rgba(201,168,76,0.3); }

    .dep-quote {
      font-size: 48px;
      font-family: 'Cormorant Garamond', serif;
      color: var(--gold);
      opacity: 0.3;
      line-height: 0.8;
      margin-bottom: 16px;
    }

    .dep-text {
      font-size: 13px;
      color: var(--text-light);
      line-height: 1.8;
      font-style: italic;
      margin-bottom: 24px;
    }

    .dep-stars {
      color: var(--gold);
      font-size: 12px;
      margin-bottom: 16px;
      letter-spacing: 2px;
    }

    .dep-author {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .dep-avatar {
      width: 40px; height: 40px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 16px;
      color: var(--black);
      font-weight: 700;
      font-family: 'Cormorant Garamond', serif;
    }

    .dep-name {
      font-size: 13px;
      font-weight: 600;
      color: var(--white);
    }

    .dep-local {
      font-size: 10px;
      color: var(--text-muted);
      letter-spacing: 1px;
    }

    /* ─── CTA BAND ─── */
    .cta-band {
      background: linear-gradient(135deg, var(--gold-dark) 0%, var(--gold) 60%, var(--gold-light) 100%);
      padding: 80px 60px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .cta-band::before {
      content: '';
      position: absolute;
      inset: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' stroke='rgba(0,0,0,0.05)' stroke-width='1'%3E%3Cpath d='M30 5 L55 20 L55 40 L30 55 L5 40 L5 20Z'/%3E%3C/g%3E%3C/svg%3E") repeat;
    }

    .cta-band-content { position: relative; z-index: 1; }

    .cta-band h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(32px, 5vw, 52px);
      font-weight: 400;
      color: var(--black);
      margin-bottom: 16px;
    }

    .cta-band p {
      font-size: 14px;
      color: rgba(0,0,0,0.7);
      margin-bottom: 36px;
      max-width: 500px;
      margin-left: auto;
      margin-right: auto;
      line-height: 1.7;
    }

    .cta-band .btn-dark {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      background: var(--black);
      color: var(--gold);
      text-decoration: none;
      padding: 18px 40px;
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 3px;
      text-transform: uppercase;
      border-radius: 2px;
      transition: all 0.3s;
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    }

    .cta-band .btn-dark:hover {
      background: var(--black-soft);
      transform: translateY(-3px);
      box-shadow: 0 16px 40px rgba(0,0,0,0.4);
    }

    /* ─── CONTATO ─── */
    .contato {
      background: var(--black-soft);
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 80px;
      align-items: start;
    }

    .contato-info { padding-top: 8px; }

    .contato-item {
      display: flex;
      align-items: flex-start;
      gap: 20px;
      margin-bottom: 32px;
      padding-bottom: 32px;
      border-bottom: 1px solid rgba(201,168,76,0.1);
    }

    .contato-item:last-child { border-bottom: none; margin-bottom: 0; }

    .contato-icon {
      width: 48px; height: 48px;
      border-radius: 50%;
      background: rgba(201,168,76,0.08);
      border: 1px solid rgba(201,168,76,0.2);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      color: var(--gold);
      flex-shrink: 0;
    }

    .contato-label {
      font-size: 10px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 6px;
    }

    .contato-value {
      font-size: 15px;
      color: var(--white);
      font-weight: 400;
    }

    .contato-sub {
      font-size: 11px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    .contato-form {
      background: var(--black-mid);
      border: 1px solid rgba(201,168,76,0.15);
      border-radius: 4px;
      padding: 40px;
    }

    .form-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 26px;
      color: var(--white);
      margin-bottom: 6px;
    }

    .form-sub {
      font-size: 12px;
      color: var(--text-muted);
      margin-bottom: 28px;
    }

    .form-group { margin-bottom: 20px; }

    .form-group label {
      display: block;
      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--text-muted);
      margin-bottom: 8px;
    }

    .form-group input,
    .form-group textarea,
    .form-group select {
      width: 100%;
      background: rgba(255,255,255,0.04);
      border: 1px solid rgba(201,168,76,0.2);
      border-radius: 2px;
      padding: 14px 16px;
      font-size: 13px;
      color: var(--white);
      font-family: 'Montserrat', sans-serif;
      outline: none;
      transition: border-color 0.3s;
    }

    .form-group input:focus,
    .form-group textarea:focus,
    .form-group select:focus {
      border-color: var(--gold);
    }

    .form-group textarea { height: 100px; resize: none; }

    .form-group select option { background: var(--black-mid); }

    .form-submit {
      width: 100%;
      background: linear-gradient(135deg, var(--gold-dark), var(--gold));
      color: var(--black);
      border: none;
      padding: 16px;
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 3px;
      text-transform: uppercase;
      border-radius: 2px;
      cursor: pointer;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
    }

    .form-submit:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 25px rgba(201,168,76,0.4);
    }

    /* ─── FOOTER ─── */
    footer {
      background: var(--black);
      border-top: 1px solid rgba(201,168,76,0.15);
      padding: 60px 60px 30px;
    }

    .footer-top {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 40px;
      padding-bottom: 50px;
      border-bottom: 1px solid rgba(201,168,76,0.1);
      margin-bottom: 30px;
    }

    .footer-brand .nav-logo { margin-bottom: 16px; }

    .footer-brand p {
      font-size: 12px;
      color: var(--text-muted);
      line-height: 1.8;
      max-width: 280px;
      margin-bottom: 24px;
    }

    .social-links {
      display: flex;
      gap: 12px;
    }

    .social-btn {
      width: 38px; height: 38px;
      border-radius: 50%;
      border: 1px solid rgba(201,168,76,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-muted);
      text-decoration: none;
      font-size: 14px;
      transition: all 0.3s;
    }

    .social-btn:hover {
      border-color: var(--gold);
      color: var(--gold);
      background: rgba(201,168,76,0.08);
    }

    .footer-col h4 {
      font-size: 11px;
      letter-spacing: 3px;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 20px;
    }

    .footer-col ul {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .footer-col ul a {
      font-size: 12px;
      color: var(--text-muted);
      text-decoration: none;
      transition: color 0.3s;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .footer-col ul a:hover { color: var(--gold); }
    .footer-col ul a::before { content: '→'; font-size: 10px; color: var(--gold); opacity: 0.5; }

    .footer-bottom {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
    }

    .footer-bottom p {
      font-size: 11px;
      color: var(--text-muted);
      letter-spacing: 1px;
    }

    .footer-bottom span { color: var(--gold); }

    /* ─── WHATSAPP FLOAT ─── */
    .whatsapp-float {
      position: fixed;
      bottom: 28px;
      right: 28px;
      z-index: 999;
      width: 56px; height: 56px;
      border-radius: 50%;
      background: #25D366;
      display: flex;
      align-items: center;
      justify-content: center;
      color: white;
      font-size: 26px;
      text-decoration: none;
      box-shadow: 0 6px 25px rgba(37,211,102,0.4);
      transition: all 0.3s;
      animation: pulse-wa 3s ease infinite;
    }

    .whatsapp-float:hover {
      transform: scale(1.1);
      box-shadow: 0 10px 35px rgba(37,211,102,0.6);
    }

    @keyframes pulse-wa {
      0%, 100% { box-shadow: 0 6px 25px rgba(37,211,102,0.4); }
      50% { box-shadow: 0 6px 40px rgba(37,211,102,0.7), 0 0 0 8px rgba(37,211,102,0.1); }
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .reveal {
      opacity: 0;
      transform: translateY(40px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* ─── MOBILE ─── */
    @media (max-width: 900px) {
      nav { padding: 16px 24px; }
      .nav-links { display: none; }
      .hamburger { display: flex; }

      section { padding: 70px 24px; }

      .about, .romanel, .contato { grid-template-columns: 1fr; gap: 40px; }
      .about-image-wrap { display: none; }
      .cat-grid { grid-template-columns: repeat(2, 1fr); }
      .prod-grid { grid-template-columns: 1fr; }
      .dif-grid { grid-template-columns: repeat(2, 1fr); }
      .dep-grid { grid-template-columns: 1fr; }
      .footer-top { grid-template-columns: 1fr 1fr; }
      .about-stats { grid-template-columns: repeat(3, 1fr); }
      .romanel-features { grid-template-columns: 1fr; }
      .cta-band { padding: 60px 24px; }
    }

    @media (max-width: 600px) {
      .cat-grid { grid-template-columns: 1fr 1fr; }
      .dif-grid { grid-template-columns: 1fr; }
      .footer-top { grid-template-columns: 1fr; }
      .about-stats { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>

<!-- WHATSAPP FLOAT -->
<a href="https://wa.me/5538992117178" target="_blank" class="whatsapp-float" title="Fale conosco no WhatsApp">
  <i class="fab fa-whatsapp"></i>
</a>

<!-- NAVBAR -->
<nav id="navbar">
  <a href="#" class="nav-logo">
    <div class="nav-logo-icon">B</div>
    <div class="nav-logo-text">
      <span class="nav-logo-name">Bruna Oliveira</span>
      <span class="nav-logo-sub">Joias & Semijoias</span>
    </div>
  </a>
  <ul class="nav-links">
    <li><a href="#sobre">Sobre</a></li>
    <li><a href="#categorias">Coleções</a></li>
    <li><a href="#romanel">Romanel</a></li>
    <li><a href="#diferenciais">Diferenciais</a></li>
    <li><a href="#contato" class="nav-cta">Contato</a></li>
  </ul>
  <div class="hamburger" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-bg"></div>
  <div class="hero-particles" id="particles"></div>
  <div class="hero-content">
    <div class="hero-badge">
      <i class="fas fa-gem"></i>
      Revendedora Oficial Romanel
      <i class="fas fa-gem"></i>
    </div>
    <h1 class="hero-title">
      Bruna<br><span>Oliveira</span>
    </h1>
    <p class="hero-subtitle">Joias e Semijoias · Acessórios</p>
    <div class="hero-divider"></div>
    <p class="hero-desc">
      Elegância e sofisticação em cada peça. Descubra nossa coleção exclusiva de joias e semijoias Romanel, com qualidade garantida e designs para todos os momentos.
    </p>
    <div class="hero-btns">
      <a href="https://wa.me/5538992117178" target="_blank" class="btn-primary">
        <i class="fab fa-whatsapp"></i> Ver Coleção
      </a>
      <a href="#categorias" class="btn-secondary">
        <i class="fas fa-gem"></i> Nossas Peças
      </a>
    </div>
  </div>
  <div class="hero-scroll">
    <div class="scroll-line"></div>
    <span>Scroll</span>
  </div>
</section>

<!-- ROMANEL TICKER -->
<div class="romanel-banner">
  <div class="romanel-ticker" id="ticker">
    <span>Revendedora Oficial Romanel</span>
    <span>Joias Banhadas em Ouro</span>
    <span>Semijoias de Alta Qualidade</span>
    <span>Entrega em Coração de Jesus e Região</span>
    <span>Garantia de Qualidade</span>
    <span>Atendimento Personalizado</span>
    <span>Revendedora Oficial Romanel</span>
    <span>Joias Banhadas em Ouro</span>
    <span>Semijoias de Alta Qualidade</span>
    <span>Entrega em Coração de Jesus e Região</span>
    <span>Garantia de Qualidade</span>
    <span>Atendimento Personalizado</span>
  </div>
</div>

<!-- SOBRE -->
<section class="about" id="sobre">
  <div class="about-image-wrap reveal">
    <div class="about-image-main">
      <div class="about-image-decor2"></div>
      <span>💎</span>
      <div class="about-image-decor"></div>
    </div>
    <div class="about-badge">
      <strong>100%</strong>
      <span>Romanel</span>
    </div>
  </div>
  <div class="reveal">
    <div class="section-label">Nossa História</div>
    <h2 class="section-title">Paixão por <span>Elegância</span></h2>
    <p class="section-desc">
      A Bruna Oliveira Joias e Semijoias nasceu do amor por acessórios que transformam e realçam a beleza de cada mulher. Como revendedora oficial Romanel, oferecemos peças de alta qualidade, com design sofisticado e acabamento impecável.
    </p>
    <p class="section-desc" style="margin-top: 16px;">
      Localizada em Coração de Jesus – MG, atendemos com carinho e atenção personalizada, ajudando cada cliente a encontrar a peça perfeita para cada ocasião especial.
    </p>
    <div class="about-stats">
      <div class="stat-card">
        <div class="stat-number">💛</div>
        <div class="stat-label">Qualidade</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">✦</div>
        <div class="stat-label">Romanel</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">🏅</div>
        <div class="stat-label">Garantia</div>
      </div>
    </div>
  </div>
</section>

<!-- CATEGORIAS -->
<section class="categorias" id="categorias">
  <div class="categorias-header reveal">
    <div class="section-label">Nossas Coleções</div>
    <h2 class="section-title">Encontre Sua <span>Peça Perfeita</span></h2>
    <p class="section-desc" style="margin: 0 auto;">Explore nossas categorias e descubra joias e semijoias para todos os estilos e momentos.</p>
  </div>
  <div class="cat-grid">
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20colares%20disponíveis." target="_blank" class="cat-card reveal">
      <span class="cat-icon">📿</span>
      <div class="cat-name">Colares</div>
      <div class="cat-desc">Designs delicados e sofisticados para compor qualquer look</div>
      <span class="cat-tag">Ver Peças</span>
    </a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20anéis%20disponíveis." target="_blank" class="cat-card reveal">
      <span class="cat-icon">💍</span>
      <div class="cat-name">Anéis</div>
      <div class="cat-desc">Aliançais, solitários e anéis em ouro e prata banhados</div>
      <span class="cat-tag">Ver Peças</span>
    </a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20as%20pulseiras%20disponíveis." target="_blank" class="cat-card reveal">
      <span class="cat-icon">✨</span>
      <div class="cat-name">Pulseiras</div>
      <div class="cat-desc">Pulseiras e braceletes elegantes para o dia a dia e festas</div>
      <span class="cat-tag">Ver Peças</span>
    </a>
    <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20os%20brincos%20disponíveis." target="_blank" class="cat-card reveal">
      <span class="cat-icon">🌟</span>
      <div class="cat-name">Brincos</div>
      <div class="cat-desc">Argolas, pérolas, cravejados e muito mais para todos os gostos</div>
      <span class="cat-tag">Ver Peças</span>
    </a>
  </div>
</section>

<!-- ROMANEL -->
<section class="romanel" id="romanel">
  <div class="reveal">
    <div class="section-label">Parceria Exclusiva</div>
    <h2 class="section-title">Somos <span>Romanel</span></h2>
    <p class="section-desc">
      A Romanel é reconhecida como a maior marca de joias e semijoias do Brasil, com mais de 30 anos de história, produção 100% nacional e compromisso com qualidade e inovação.
    </p>
    <div class="romanel-features">
      <div class="romanel-feat">
        <i class="fas fa-award"></i>
        <div class="romanel-feat-text">
          <strong>Maior do Brasil</strong>
          <span>Líder no mercado de joias e semijoias nacionais</span>
        </div>
      </div>
      <div class="romanel-feat">
        <i class="fas fa-shield-alt"></i>
        <div class="romanel-feat-text">
          <strong>Garantia Vitalícia</strong>
          <span>Peças com garantia na qualidade do banho</span>
        </div>
      </div>
      <div class="romanel-feat">
        <i class="fas fa-industry"></i>
        <div class="romanel-feat-text">
          <strong>100% Nacional</strong>
          <span>Produção brasileira com altíssima qualidade</span>
        </div>
      </div>
      <div class="romanel-feat">
        <i class="fas fa-gem"></i>
        <div class="romanel-feat-text">
          <strong>Design Exclusivo</strong>
          <span>Coleções modernas e sofisticadas sempre renovadas</span>
        </div>
      </div>
    </div>
  </div>
  <div class="romanel-visual reveal">
    <div class="romanel-ring"></div>
    <div class="romanel-ring"></div>
    <div class="romanel-logo-box">
      <div class="r-text">R</div>
      <div class="r-sub">Romanel</div>
    </div>
  </div>
</section>

<!-- DESTAQUES -->
<section class="produtos" id="produtos">
  <div class="produtos-header reveal">
    <div class="section-label">Mais Vendidos</div>
    <h2 class="section-title">Peças em <span>Destaque</span></h2>
    <p class="section-desc" style="margin: 0 auto;">Conheça algumas das nossas peças favoritas — elegância para cada momento da sua vida.</p>
  </div>
  <div class="prod-grid">
    <div class="prod-card reveal">
      <div class="prod-img">
        <span class="prod-badge-new">Novo</span>
        💎
      </div>
      <div class="prod-info">
        <div class="prod-cat">Colares · Romanel</div>
        <div class="prod-name">Colar Veneziana Ouro</div>
        <div class="prod-desc">Colar banhado em ouro 18k com elos venezianos, delicado e sofisticado para o uso diário.</div>
        <a href="https://wa.me/5538992117178?text=Olá!%20Tenho%20interesse%20no%20Colar%20Veneziana%20Ouro." target="_blank" class="prod-cta">
          Tenho Interesse <i class="fas fa-arrow-right"></i>
        </a>
      </div>
    </div>
    <div class="prod-card reveal">
      <div class="prod-img">
        <span class="prod-badge-new">Top</span>
        💍
      </div>
      <div class="prod-info">
        <div class="prod-cat">Anéis · Romanel</div>
        <div class="prod-name">Anel Solitário Cristal</div>
        <div class="prod-desc">Anel solitário com pedra de cristal cravejada, acabamento premium e banho de ouro 18k.</div>
        <a href="https://wa.me/5538992117178?text=Olá!%20Tenho%20interesse%20no%20Anel%20Solitário%20Cristal." target="_blank" class="prod-cta">
          Tenho Interesse <i class="fas fa-arrow-right"></i>
        </a>
      </div>
    </div>
    <div class="prod-card reveal">
      <div class="prod-img">
        ✨
      </div>
      <div class="prod-info">
        <div class="prod-cat">Brincos · Romanel</div>
        <div class="prod-name">Brinco Argola Premium</div>
        <div class="prod-desc">Argolas elegantes em banho de ouro, versáteis para combinar com looks casuais e sociais.</div>
        <a href="https://wa.me/5538992117178?text=Olá!%20Tenho%20interesse%20nos%20Brincos%20Argola%20Premium." target="_blank" class="prod-cta">
          Tenho Interesse <i class="fas fa-arrow-right"></i>
        </a>
      </div>
    </div>
  </div>
  <a href="https://wa.me/5538992117178?text=Olá!%20Quero%20ver%20todo%20o%20catálogo%20de%20joias." target="_blank" class="btn-primary reveal" style="display:inline-flex;">
    <i class="fab fa-whatsapp"></i> Ver Catálogo Completo
  </a>
</section>

<!-- DIFERENCIAIS -->
<section class="diferenciais" id="diferenciais">
  <div class="dif-header reveal">
    <div class="section-label">Por Que Escolher</div>
    <h2 class="section-title">Nossos <span>Diferenciais</span></h2>
  </div>
  <div class="dif-grid">
    <div class="dif-card reveal">
      <div class="dif-icon"><i class="fas fa-certificate"></i></div>
      <div class="dif-title">Produto Original</div>
      <div class="dif-text">Todas as peças são originais Romanel, com certificado de autenticidade e garantia da marca.</div>
    </div>
    <div class="dif-card reveal">
      <div class="dif-icon"><i class="fas fa-headset"></i></div>
      <div class="dif-title">Atendimento VIP</div>
      <div class="dif-text">Atendimento personalizado e consultivo para ajudá-la a encontrar a peça ideal para cada momento.</div>
    </div>
    <div class="dif-card reveal">
      <div class="dif-icon"><i class="fas fa-map-marker-alt"></i></div>
      <div class="dif-title">Atende Sua Região</div>
      <div class="dif-text">Localizada em Coração de Jesus, com atendimento presencial e entregas para a região.</div>
    </div>
    <div class="dif-card reveal">
      <div class="dif-icon"><i class="fas fa-heart"></i></div>
      <div class="dif-title">Feito com Amor</div>
      <div class="dif-text">Cada venda é única. Cuidamos de você com atenção e carinho do início ao fim.</div>
    </div>
  </div>
</section>

<!-- DEPOIMENTOS -->
<section class="depoimentos" id="depoimentos">
  <div class="dep-header reveal">
    <div class="section-label">Clientes Satisfeitas</div>
    <h2 class="section-title">O Que Dizem <span>Sobre Nós</span></h2>
  </div>
  <div class="dep-grid">
    <div class="dep-card reveal">
      <div class="dep-quote">"</div>
      <div class="dep-stars">★★★★★</div>
      <div class="dep-text">Comprei um colar da Romanel e simplesmente me apaixonei! A qualidade é incrível e o atendimento da Bruna é maravilhoso. Super indico!</div>
      <div class="dep-author">
        <div class="dep-avatar">A</div>
        <div>
          <div class="dep-name">Ana Paula</div>
          <div class="dep-local">Coração de Jesus, MG</div>
        </div>
      </div>
    </div>
    <div class="dep-card reveal">
      <div class="dep-quote">"</div>
      <div class="dep-stars">★★★★★</div>
      <div class="dep-text">As peças são lindas demais! Comprei um anel para minha filha e ela adorou. Produto original Romanel com um preço justo. Voltarei a comprar!</div>
      <div class="dep-author">
        <div class="dep-avatar">M</div>
        <div>
          <div class="dep-name">Márcia Silva</div>
          <div class="dep-local">Região</div>
        </div>
      </div>
    </div>
    <div class="dep-card reveal">
      <div class="dep-quote">"</div>
      <div class="dep-stars">★★★★★</div>
      <div class="dep-text">Atendimento impecável! A Bruna me ajudou a escolher o presente perfeito para minha mãe. Joias lindíssimas e entrega rápida. Muito obrigada!</div>
      <div class="dep-author">
        <div class="dep-avatar">J</div>
        <div>
          <div class="dep-name">Juliana Costa</div>
          <div class="dep-local">Coração de Jesus, MG</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA BAND -->
<div class="cta-band">
  <div class="cta-band-content">
    <h2>Encontre a Joia dos Seus Sonhos ✨</h2>
    <p>Entre em contato agora pelo WhatsApp e veja nossa coleção completa de joias e semijoias Romanel. Atendimento personalizado para você!</p>
    <a href="https://wa.me/5538992117178?text=Olá%20Bruna!%20Quero%20conhecer%20a%20coleção%20de%20joias%20e%20semijoias." target="_blank" class="btn-dark">
      <i class="fab fa-whatsapp"></i> Falar com a Bruna Agora
    </a>
  </div>
</div>

<!-- CONTATO -->
<section class="contato" id="contato">
  <div class="contato-info reveal">
    <div class="section-label">Fale Conosco</div>
    <h2 class="section-title">Entre em <span>Contato</span></h2>
    <p class="section-desc" style="margin-bottom: 40px;">Estamos aqui para te ajudar a encontrar a peça perfeita. Fale conosco!</p>

    <div class="contato-item">
      <div class="contato-icon"><i class="fab fa-whatsapp"></i></div>
      <div>
        <div class="contato-label">WhatsApp</div>
        <div class="contato-value">(38) 9.9211-7178</div>
        <div class="contato-sub">Atendimento rápido via mensagem</div>
      </div>
    </div>

    <div class="contato-item">
      <div class="contato-icon"><i class="fab fa-instagram"></i></div>
      <div>
        <div class="contato-label">Instagram</div>
        <div class="contato-value">@bruna_oliveira_acessorios</div>
        <div class="contato-sub">Veja novidades e lançamentos</div>
      </div>
    </div>

    <div class="contato-item">
      <div class="contato-icon"><i class="fas fa-map-marker-alt"></i></div>
      <div>
        <div class="contato-label">Localização</div>
        <div class="contato-value">Coração de Jesus, MG</div>
        <div class="contato-sub">Atendimento presencial com hora marcada</div>
      </div>
    </div>
  </div>

  <div class="contato-form reveal">
    <div class="form-title">Envie uma Mensagem</div>
    <div class="form-sub">Preencha o formulário e entraremos em contato via WhatsApp</div>

    <div class="form-group">
      <label>Seu Nome</label>
      <input type="text" placeholder="Como podemos chamar você?">
    </div>
    <div class="form-group">
      <label>Telefone / WhatsApp</label>
      <input type="tel" placeholder="(00) 0.0000-0000">
    </div>
    <div class="form-group">
      <label>Interesse</label>
      <select>
        <option value="">Selecione uma categoria...</option>
        <option>Colares</option>
        <option>Anéis</option>
        <option>Pulseiras</option>
        <option>Brincos</option>
        <option>Conjunto Completo</option>
        <option>Presente Especial</option>
        <option>Outro</option>
      </select>
    </div>
    <div class="form-group">
      <label>Mensagem</label>
      <textarea placeholder="Conta mais sobre o que você procura..."></textarea>
    </div>
    <button class="form-submit" onclick="enviarWhatsApp()">
      <i class="fab fa-whatsapp"></i> Enviar pelo WhatsApp
    </button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <a href="#" class="nav-logo" style="text-decoration:none;">
        <div class="nav-logo-icon">B</div>
        <div class="nav-logo-text">
          <span class="nav-logo-name">Bruna Oliveira</span>
          <span class="nav-logo-sub">Joias & Semijoias</span>
        </div>
      </a>
      <p>Revendedora oficial Romanel em Coração de Jesus – MG. Elegância, qualidade e atendimento personalizado em cada peça.</p>
      <div class="social-links">
        <a href="https://www.instagram.com/bruna_oliveira_acessorios" target="_blank" class="social-btn">
          <i class="fab fa-instagram"></i>
        </a>
        <a href="https://wa.me/5538992117178" target="_blank" class="social-btn">
          <i class="fab fa-whatsapp"></i>
        </a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Navegação</h4>
      <ul>
        <li><a href="#sobre">Sobre Nós</a></li>
        <li><a href="#categorias">Coleções</a></li>
        <li><a href="#romanel">Romanel</a></li>
        <li><a href="#diferenciais">Diferenciais</a></li>
        <li><a href="#contato">Contato</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Categorias</h4>
      <ul>
        <li><a href="#">Colares</a></li>
        <li><a href="#">Anéis</a></li>
        <li><a href="#">Pulseiras</a></li>
        <li><a href="#">Brincos</a></li>
        <li><a href="#">Conjuntos</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contato</h4>
      <ul>
        <li><a href="https://wa.me/5538992117178" target="_blank">(38) 9.9211-7178</a></li>
        <li><a href="https://www.instagram.com/bruna_oliveira_acessorios" target="_blank">@bruna_oliveira_acessorios</a></li>
        <li><a href="#">Coração de Jesus, MG</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2024 <span>Bruna Oliveira Joias & Semijoias</span> — Todos os direitos reservados.</p>
    <p>Revendedora Oficial <span>Romanel</span> ✦ Coração de Jesus, MG</p>
  </div>
</footer>

<script>
  // Particles
  const container = document.getElementById('particles');
  for (let i = 0; i < 30; i++) {
    const p = document.createElement('div');
    p.className = 'particle';
    p.style.cssText = `
      left: ${Math.random() * 100}%;
      width: ${Math.random() * 3 + 1}px;
      height: ${Math.random() * 3 + 1}px;
      animation-duration: ${Math.random() * 10 + 8}s;
      animation-delay: ${Math.random() * 10}s;
    `;
    container.appendChild(p);
  }

  // Reveal on scroll
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  reveals.forEach(el => observer.observe(el));

  // Navbar scroll
  window.addEventListener('scroll', () => {
    const nav = document.getElementById('navbar');
    if (window.scrollY > 60) {
      nav.style.padding = '12px 60px';
      nav.style.boxShadow = '0 4px 30px rgba(0,0,0,0.5)';
    } else {
      nav.style.padding = '18px 60px';
      nav.style.boxShadow = 'none';
    }
  });

  // Mobile menu
  function toggleMenu() {
    const links = document.querySelector('.nav-links');
    links.style.display = links.style.display === 'flex' ? 'none' : 'flex';
    links.style.flexDirection = 'column';
    links.style.position = 'absolute';
    links.style.top = '70px';
    links.style.left = '0';
    links.style.right = '0';
    links.style.background = 'rgba(10,10,10,0.98)';
    links.style.padding = '24px';
    links.style.gap = '20px';
    links.style.borderBottom = '1px solid rgba(201,168,76,0.2)';
  }

  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });

  // Form to WhatsApp
  function enviarWhatsApp() {
    const nome = document.querySelector('input[placeholder*="chamar"]').value;
    const tel = document.querySelector('input[type="tel"]').value;
    const interesse = document.querySelector('select').value;
    const msg = document.querySelector('textarea').value;

    if (!nome) { alert('Por favor, informe seu nome.'); return; }

    const texto = `Olá Bruna! Me chamo *${nome}*.\n📱 Telefone: ${tel || 'Não informado'}\n💎 Interesse: ${interesse || 'Não especificado'}\n💬 Mensagem: ${msg || 'Gostaria de mais informações sobre joias e semijoias.'}`;
    window.open(`https://wa.me/5538992117178?text=${encodeURIComponent(texto)}`, '_blank');
  }
</script>
</body>
</html>
