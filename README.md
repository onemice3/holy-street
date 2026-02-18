# holy-street
sitio web de ropa cristiana

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Gracia & Vestir — Ropa Cristiana</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --beige-light: #f5ede2;
      --beige-mid: #e8d5bc;
      --beige-dark: #d4b896;
      --cafe-light: #a67c52;
      --cafe-mid: #7a5330;
      --cafe-dark: #4e3219;
      --cream: #faf6f0;
      --gold: #c9a96e;
      --text-dark: #2e1f0f;
      --text-mid: #5a3d22;
      --text-soft: #8b6444;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--cream);
      color: var(--text-dark);
      font-family: 'Jost', sans-serif;
      font-weight: 300;
      overflow-x: hidden;
    }

    /* ─── GRAIN OVERLAY ─── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 1000;
      opacity: 0.5;
    }

    /* ─── NAV ─── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.4rem 3rem;
      background: rgba(250, 246, 240, 0.88);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--beige-mid);
    }

    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.5rem;
      font-weight: 300;
      letter-spacing: 0.08em;
      color: var(--cafe-dark);
    }
    .nav-logo span { color: var(--gold); font-style: italic; }

    .nav-links {
      display: flex;
      gap: 2.5rem;
      list-style: none;
    }
    .nav-links a {
      text-decoration: none;
      color: var(--text-mid);
      font-size: 0.8rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      transition: color 0.3s;
    }
    .nav-links a:hover { color: var(--cafe-mid); }

    .nav-actions {
      display: flex;
      gap: 1.2rem;
      align-items: center;
    }
    .nav-actions a {
      text-decoration: none;
      font-size: 0.78rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--text-mid);
      transition: color 0.3s;
    }
    .nav-actions .btn-cart {
      background: var(--cafe-mid);
      color: var(--beige-light);
      padding: 0.55rem 1.4rem;
      border-radius: 2px;
      letter-spacing: 0.1em;
      transition: background 0.3s;
    }
    .nav-actions .btn-cart:hover { background: var(--cafe-dark); }

    /* ─── HERO ─── */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 80px;
      overflow: hidden;
    }

    .hero-left {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 6rem 4rem 6rem 5rem;
      position: relative;
    }

    .hero-left::before {
      content: '✝';
      position: absolute;
      top: 10rem;
      left: 3rem;
      font-size: 6rem;
      color: var(--beige-mid);
      opacity: 0.6;
      font-family: serif;
    }

    .hero-tag {
      font-size: 0.72rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.5rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }
    .hero-tag::before {
      content: '';
      display: block;
      width: 2.5rem;
      height: 1px;
      background: var(--gold);
    }

    .hero-h1 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 5vw, 5.5rem);
      font-weight: 300;
      line-height: 1.08;
      color: var(--cafe-dark);
      margin-bottom: 1.8rem;
    }
    .hero-h1 em {
      font-style: italic;
      color: var(--cafe-light);
    }

    .hero-verse {
      font-size: 0.9rem;
      line-height: 1.9;
      color: var(--text-soft);
      max-width: 400px;
      margin-bottom: 3rem;
      border-left: 2px solid var(--beige-dark);
      padding-left: 1.2rem;
      font-style: italic;
    }

    .hero-btns {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .btn-primary {
      background: var(--cafe-mid);
      color: var(--beige-light);
      padding: 1rem 2.5rem;
      text-decoration: none;
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      border-radius: 2px;
      transition: background 0.3s, transform 0.2s;
      display: inline-block;
    }
    .btn-primary:hover { background: var(--cafe-dark); transform: translateY(-2px); }

    .btn-secondary {
      background: transparent;
      color: var(--cafe-mid);
      padding: 1rem 2rem;
      text-decoration: none;
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      border: 1px solid var(--beige-dark);
      border-radius: 2px;
      transition: border-color 0.3s, color 0.3s;
      display: inline-block;
    }
    .btn-secondary:hover { border-color: var(--cafe-light); color: var(--cafe-dark); }

    .hero-right {
      background: linear-gradient(145deg, var(--beige-mid) 0%, var(--beige-dark) 50%, var(--cafe-light) 100%);
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .hero-right::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at 30% 60%, rgba(255,255,255,0.15) 0%, transparent 60%);
    }

    .hero-mockup {
      position: relative;
      z-index: 2;
      text-align: center;
    }

    .hero-mockup .garment-icon {
      font-size: 10rem;
      line-height: 1;
      filter: drop-shadow(0 20px 40px rgba(78,50,25,0.3));
      animation: float 4s ease-in-out infinite;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-18px); }
    }

    .hero-badge {
      position: absolute;
      bottom: 3rem;
      right: 3rem;
      background: var(--cafe-dark);
      color: var(--beige-light);
      width: 100px;
      height: 100px;
      border-radius: 50%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-size: 0.62rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      text-align: center;
      line-height: 1.5;
      animation: rotate 12s linear infinite;
    }

    .hero-badge-inner {
      position: absolute;
      bottom: 3.8rem;
      right: 3.8rem;
      width: 84px;
      height: 84px;
      border-radius: 50%;
      border: 1px solid var(--gold);
      pointer-events: none;
    }

    /* ─── SECTION COMMON ─── */
    section { padding: 7rem 5rem; }

    .section-tag {
      font-size: 0.7rem;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1rem;
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 3.5vw, 3.5rem);
      font-weight: 300;
      color: var(--cafe-dark);
      line-height: 1.15;
    }
    .section-title em { font-style: italic; color: var(--cafe-light); }

    /* ─── VERSE BANNER ─── */
    .verse-banner {
      background: var(--cafe-dark);
      padding: 3.5rem 5rem;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    .verse-banner::before,
    .verse-banner::after {
      content: '✝';
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      font-size: 8rem;
      color: rgba(255,255,255,0.04);
      font-family: serif;
    }
    .verse-banner::before { left: 3rem; }
    .verse-banner::after { right: 3rem; }

    .verse-banner p {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.4rem, 2.5vw, 2.2rem);
      font-weight: 300;
      font-style: italic;
      color: var(--beige-light);
      letter-spacing: 0.03em;
      line-height: 1.6;
    }
    .verse-banner cite {
      display: block;
      margin-top: 0.8rem;
      font-size: 0.75rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold);
      font-style: normal;
    }

    /* ─── PRODUCTS ─── */
    .products-section { background: var(--beige-light); }

    .products-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      margin-bottom: 4rem;
    }

    .products-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 1.5rem;
    }

    .product-card {
      background: var(--cream);
      border-radius: 3px;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s;
    }
    .product-card:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 60px rgba(78,50,25,0.12);
    }
    .product-card:first-child {
      grid-column: span 2;
      grid-row: span 1;
    }

    .product-img {
      width: 100%;
      aspect-ratio: 3/4;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 5rem;
      position: relative;
      overflow: hidden;
    }
    .product-card:first-child .product-img { aspect-ratio: 16/9; font-size: 8rem; }

    .pi-1 { background: linear-gradient(135deg, var(--beige-mid), var(--cafe-light)); }
    .pi-2 { background: linear-gradient(135deg, var(--cafe-light), var(--cafe-mid)); }
    .pi-3 { background: linear-gradient(135deg, var(--beige-dark), var(--beige-mid)); }
    .pi-4 { background: linear-gradient(135deg, var(--cafe-mid), var(--cafe-dark)); }
    .pi-5 { background: linear-gradient(135deg, var(--beige-light), var(--gold)); }

    .product-badge-tag {
      position: absolute;
      top: 1rem;
      left: 1rem;
      background: var(--cafe-dark);
      color: var(--beige-light);
      font-size: 0.6rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 0.3rem 0.7rem;
      border-radius: 2px;
    }

    .product-info {
      padding: 1.2rem 1.4rem 1.5rem;
    }
    .product-info h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.15rem;
      font-weight: 400;
      color: var(--cafe-dark);
      margin-bottom: 0.3rem;
    }
    .product-info .verse-ref {
      font-size: 0.68rem;
      color: var(--text-soft);
      letter-spacing: 0.1em;
      margin-bottom: 0.8rem;
      font-style: italic;
    }
    .product-info .price-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .product-info .price {
      font-size: 1rem;
      color: var(--cafe-mid);
      font-weight: 500;
    }
    .product-info .add-btn {
      width: 32px;
      height: 32px;
      background: var(--cafe-mid);
      color: white;
      border: none;
      border-radius: 2px;
      cursor: pointer;
      font-size: 1.1rem;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background 0.2s;
    }
    .product-info .add-btn:hover { background: var(--cafe-dark); }

    /* ─── CATEGORIES ─── */
    .categories-section { background: var(--cream); }

    .categories-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
      margin-top: 3.5rem;
    }

    .cat-card {
      position: relative;
      height: 340px;
      border-radius: 3px;
      overflow: hidden;
      cursor: pointer;
      display: flex;
      align-items: flex-end;
      padding: 2rem;
    }
    .cat-card:first-child { height: 420px; }

    .cat-bg-1 { background: linear-gradient(160deg, var(--cafe-light) 0%, var(--cafe-dark) 100%); }
    .cat-bg-2 { background: linear-gradient(160deg, var(--beige-dark) 0%, var(--cafe-light) 100%); }
    .cat-bg-3 { background: linear-gradient(160deg, var(--gold) 0%, var(--cafe-mid) 100%); }

    .cat-card::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(20,8,0,0.6) 0%, transparent 60%);
    }

    .cat-icon {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -60%);
      font-size: 5rem;
      opacity: 0.25;
    }

    .cat-info { position: relative; z-index: 2; }
    .cat-info h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.8rem;
      font-weight: 300;
      color: var(--beige-light);
      margin-bottom: 0.3rem;
    }
    .cat-info p {
      font-size: 0.72rem;
      color: var(--beige-dark);
      letter-spacing: 0.1em;
    }

    /* ─── VALUES ─── */
    .values-section {
      background: var(--beige-mid);
      padding: 5rem;
    }

    .values-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 3rem;
      margin-top: 4rem;
    }

    .value-item { text-align: center; }
    .value-icon {
      font-size: 2.2rem;
      margin-bottom: 1.2rem;
      display: block;
    }
    .value-item h4 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.2rem;
      color: var(--cafe-dark);
      margin-bottom: 0.6rem;
    }
    .value-item p {
      font-size: 0.82rem;
      color: var(--text-soft);
      line-height: 1.8;
    }

    /* ─── NEWSLETTER ─── */
    .newsletter-section {
      background: linear-gradient(135deg, var(--cafe-dark) 0%, var(--cafe-mid) 100%);
      padding: 6rem 5rem;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    .newsletter-section::before {
      content: '✝';
      position: absolute;
      bottom: -2rem;
      right: 5rem;
      font-size: 18rem;
      color: rgba(255,255,255,0.04);
      font-family: serif;
      line-height: 1;
    }

    .newsletter-section .section-title { color: var(--beige-light); }
    .newsletter-section .section-title em { color: var(--gold); }
    .newsletter-section p {
      color: var(--beige-dark);
      margin: 1.2rem 0 2.5rem;
      font-size: 0.9rem;
    }

    .newsletter-form {
      display: flex;
      max-width: 480px;
      margin: 0 auto;
      gap: 0;
    }
    .newsletter-form input {
      flex: 1;
      padding: 1rem 1.5rem;
      border: none;
      background: rgba(255,255,255,0.1);
      backdrop-filter: blur(10px);
      color: var(--beige-light);
      font-family: 'Jost', sans-serif;
      font-size: 0.85rem;
      outline: none;
      border-radius: 2px 0 0 2px;
    }
    .newsletter-form input::placeholder { color: var(--beige-dark); }
    .newsletter-form button {
      background: var(--gold);
      color: var(--cafe-dark);
      border: none;
      padding: 1rem 2rem;
      font-family: 'Jost', sans-serif;
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      cursor: pointer;
      border-radius: 0 2px 2px 0;
      font-weight: 500;
      transition: background 0.3s;
    }
    .newsletter-form button:hover { background: var(--beige-light); }

    /* ─── FOOTER ─── */
    footer {
      background: var(--cafe-dark);
      color: var(--beige-mid);
      padding: 4rem 5rem 2rem;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 3rem;
      padding-bottom: 3rem;
      border-bottom: 1px solid rgba(255,255,255,0.1);
    }

    .footer-brand .logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem;
      color: var(--beige-light);
      margin-bottom: 1rem;
    }
    .footer-brand .logo span { color: var(--gold); font-style: italic; }
    .footer-brand p {
      font-size: 0.82rem;
      line-height: 1.8;
      color: var(--beige-dark);
      max-width: 240px;
    }

    .footer-col h5 {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.2rem;
    }
    .footer-col ul { list-style: none; }
    .footer-col ul li { margin-bottom: 0.6rem; }
    .footer-col ul li a {
      text-decoration: none;
      color: var(--beige-dark);
      font-size: 0.82rem;
      transition: color 0.2s;
    }
    .footer-col ul li a:hover { color: var(--beige-light); }

    .footer-bottom {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: 1.5rem;
      font-size: 0.72rem;
      color: var(--text-soft);
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .hero-left > * {
      animation: fadeUp 0.8s ease both;
    }
    .hero-left > *:nth-child(1) { animation-delay: 0.1s; }
    .hero-left > *:nth-child(2) { animation-delay: 0.25s; }
    .hero-left > *:nth-child(3) { animation-delay: 0.4s; }
    .hero-left > *:nth-child(4) { animation-delay: 0.55s; }
    .hero-left > *:nth-child(5) { animation-delay: 0.7s; }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 900px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      .hero { grid-template-columns: 1fr; }
      .hero-right { min-height: 300px; }
      section { padding: 5rem 2rem; }
      .products-grid { grid-template-columns: 1fr 1fr; }
      .product-card:first-child { grid-column: span 2; }
      .categories-grid { grid-template-columns: 1fr; }
      .values-grid { grid-template-columns: 1fr 1fr; }
      .footer-grid { grid-template-columns: 1fr 1fr; }
    }
  </style>
</head>
<body>

<!-- ─── NAV ─── -->
<nav>
  <div class="nav-logo">Gracia <span>&</span> Vestir</div>
  <ul class="nav-links">
    <li><a href="#">Colección</a></li>
    <li><a href="#">Categorías</a></li>
    <li><a href="#">Versículos</a></li>
    <li><a href="#">Nuestra Historia</a></li>
  </ul>
  <div class="nav-actions">
    <a href="#">Mi Cuenta</a>
    <a href="#" class="btn-cart">🛒 Carrito</a>
  </div>
</nav>

<!-- ─── HERO ─── -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-tag">Colección Primavera 2026</div>
    <h1 class="hero-h1">Viste tu<br/>fe con <em>gracia</em><br/>y propósito</h1>
    <p class="hero-verse">
      "Revestíos del Señor Jesucristo"<br/>— Romanos 13:14
    </p>
    <div class="hero-btns">
      <a href="#" class="btn-primary">Explorar Colección</a>
      <a href="#" class="btn-secondary">Nuestra Historia</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-mockup">
      <div class="garment-icon">👘</div>
    </div>
    <div class="hero-badge">NUEVA<br/>COLEC<br/>CIÓN</div>
    <div class="hero-badge-inner"></div>
  </div>
</section>

<!-- ─── VERSE BANNER ─── -->
<div class="verse-banner">
  <p>"Vestíos, pues, como escogidos de Dios, santos y amados, de entrañable misericordia, de benignidad, de humildad, de mansedumbre, de paciencia."</p>
  <cite>— Colosenses 3:12</cite>
</div>

<!-- ─── PRODUCTS ─── -->
<section class="products-section">
  <div class="products-header">
    <div>
      <p class="section-tag">Más Populares</p>
      <h2 class="section-title">Prendas que <em>proclaman</em></h2>
    </div>
    <a href="#" class="btn-secondary">Ver Todo</a>
  </div>
  <div class="products-grid">
    <div class="product-card">
      <div class="product-img pi-1">
        <span class="product-badge-tag">Destacado</span>
        👗
      </div>
      <div class="product-info">
        <h3>Vestido "Luz del Mundo"</h3>
        <p class="verse-ref">Mateo 5:14</p>
        <div class="price-row">
          <span class="price">$189.000</span>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
    <div class="product-card">
      <div class="product-img pi-2">👕</div>
      <div class="product-info">
        <h3>Blusa "Renovada"</h3>
        <p class="verse-ref">Romanos 12:2</p>
        <div class="price-row">
          <span class="price">$89.000</span>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
    <div class="product-card">
      <div class="product-img pi-3">🧥</div>
      <div class="product-info">
        <h3>Abrigo "Refugio"</h3>
        <p class="verse-ref">Salmos 91:4</p>
        <div class="price-row">
          <span class="price">$245.000</span>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
    <div class="product-card">
      <div class="product-img pi-4">👖</div>
      <div class="product-info">
        <h3>Pantalón "Firmeza"</h3>
        <p class="verse-ref">Efesios 6:14</p>
        <div class="price-row">
          <span class="price">$129.000</span>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
    <div class="product-card">
      <div class="product-img pi-5">🧣</div>
      <div class="product-info">
        <h3>Bufanda "Paz"</h3>
        <p class="verse-ref">Filipenses 4:7</p>
        <div class="price-row">
          <span class="price">$65.000</span>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ─── CATEGORIES ─── -->
<section class="categories-section">
  <p class="section-tag">Explorar</p>
  <h2 class="section-title">Categorías con <em>propósito</em></h2>
  <div class="categories-grid">
    <div class="cat-card cat-bg-1">
      <span class="cat-icon">✝️</span>
      <div class="cat-info">
        <h3>Adoración & Culto</h3>
        <p>Prendas para momentos sagrados</p>
      </div>
    </div>
    <div class="cat-card cat-bg-2">
      <span class="cat-icon">🌿</span>
      <div class="cat-info">
        <h3>Vida Cotidiana</h3>
        <p>Fe en cada paso del día</p>
      </div>
    </div>
    <div class="cat-card cat-bg-3">
      <span class="cat-icon">🕊️</span>
      <div class="cat-info">
        <h3>Misión & Servicio</h3>
        <p>Viste tu llamado</p>
      </div>
    </div>
  </div>
</section>

<!-- ─── VALUES ─── -->
<section class="values-section">
  <div style="text-align:center; margin-bottom: 2rem;">
    <p class="section-tag">Nuestra Promesa</p>
    <h2 class="section-title">Por qué elegir <em>Gracia & Vestir</em></h2>
  </div>
  <div class="values-grid">
    <div class="value-item">
      <span class="value-icon">🙏</span>
      <h4>Hecho con Oración</h4>
      <p>Cada prenda nace de un proceso de oración y reflexión bíblica.</p>
    </div>
    <div class="value-item">
      <span class="value-icon">♻️</span>
      <h4>Telas Éticas</h4>
      <p>Materiales naturales y sostenibles que honran la creación de Dios.</p>
    </div>
    <div class="value-item">
      <span class="value-icon">📖</span>
      <h4>Versículos Bordados</h4>
      <p>Cada diseño lleva un versículo seleccionado con amor y significado.</p>
    </div>
    <div class="value-item">
      <span class="value-icon">🤝</span>
      <h4>Comercio Justo</h4>
      <p>Apoyamos a familias artesanas que trabajan con dignidad y fe.</p>
    </div>
  </div>
</section>

<!-- ─── NEWSLETTER ─── -->
<section class="newsletter-section">
  <p class="section-tag">Comunidad</p>
  <h2 class="section-title">Únete a nuestra <em>familia</em></h2>
  <p>Recibe inspiración bíblica, nuevas colecciones y descuentos especiales.</p>
  <form class="newsletter-form" onsubmit="return false;">
    <input type="email" placeholder="Tu correo electrónico..." />
    <button type="submit">Suscribirse</button>
  </form>
</section>

<!-- ─── FOOTER ─── -->
<footer>
  <div class="footer-grid">
    <div class="footer-brand">
      <div class="logo">Gracia <span>&</span> Vestir</div>
      <p>Ropa cristiana diseñada para proclamar la fe con elegancia, propósito y amor a Dios en cada prenda.</p>
    </div>
    <div class="footer-col">
      <h5>Tienda</h5>
      <ul>
        <li><a href="#">Nueva Colección</a></li>
        <li><a href="#">Vestidos</a></li>
        <li><a href="#">Blusas</a></li>
        <li><a href="#">Accesorios</a></li>
        <li><a href="#">Ofertas</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Nosotros</h5>
      <ul>
        <li><a href="#">Nuestra Historia</a></li>
        <li><a href="#">Nuestra Fe</a></li>
        <li><a href="#">Artesanos</a></li>
        <li><a href="#">Blog</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h5>Ayuda</h5>
      <ul>
        <li><a href="#">Guía de Tallas</a></li>
        <li><a href="#">Envíos</a></li>
        <li><a href="#">Devoluciones</a></li>
        <li><a href="#">Contacto</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Gracia & Vestir. Todos los derechos reservados.</span>
    <span>"Todo lo que hagáis, hacedlo de corazón." — Col. 3:23</span>
  </div>
</footer>

</body>
</html>
