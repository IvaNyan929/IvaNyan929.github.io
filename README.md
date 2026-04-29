<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dream Coffee | www.dreamcoffee.com.mx</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --crimson: #8B0000;
    --crimson-light: #B22222;
    --crimson-dark: #5C0000;
    --rose: #C41E3A;
    --blush: #E8B4B8;
    --cream: #FFF8F0;
    --ivory: #FAF0E6;
    --gold: #C9A84C;
    --gold-light: #E8CC7A;
    --charcoal: #1A0A0A;
    --dark: #0D0505;
    --muted: #6B3A3A;
    --text-light: #F5E6E8;
    --shadow: rgba(139,0,0,0.4);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Montserrat', sans-serif;
    background: var(--dark);
    color: var(--text-light);
    overflow-x: hidden;
  }

  /* ===== COOKIE BANNER ===== */
  #cookie-banner {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    background: rgba(13,5,5,0.97);
    border-top: 2px solid var(--gold);
    padding: 18px 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    z-index: 9999;
    gap: 20px;
    flex-wrap: wrap;
    backdrop-filter: blur(10px);
  }
  #cookie-banner p { font-size: 0.78rem; color: var(--blush); max-width: 700px; line-height: 1.5; }
  #cookie-banner p a { color: var(--gold); text-decoration: underline; cursor: pointer; }
  #cookie-banner .cookie-btns { display: flex; gap: 10px; flex-shrink: 0; }
  #cookie-banner button {
    padding: 8px 22px; border: none; border-radius: 2px; cursor: pointer;
    font-family: 'Montserrat', sans-serif; font-size: 0.75rem; font-weight: 600;
    text-transform: uppercase; letter-spacing: 1px; transition: all 0.3s;
  }
  .btn-accept { background: var(--gold); color: var(--dark); }
  .btn-accept:hover { background: var(--gold-light); }
  .btn-reject { background: transparent; color: var(--blush); border: 1px solid var(--muted) !important; }
  .btn-reject:hover { border-color: var(--blush) !important; }

  /* ===== HEADER ===== */
  header {
    position: sticky; top: 0; z-index: 1000;
    background: rgba(13,5,5,0.96);
    border-bottom: 1px solid rgba(201,168,76,0.3);
    backdrop-filter: blur(12px);
  }
  .header-top {
    display: flex; align-items: center; justify-content: space-between;
    padding: 10px 40px; gap: 20px;
  }
  .logo-area { display: flex; align-items: center; gap: 14px; }
  .logo-icon {
    width: 60px; height: 60px;
    background: radial-gradient(circle, var(--crimson-light), var(--crimson-dark));
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 28px;
    border: 2px solid var(--gold);
    box-shadow: 0 0 20px rgba(201,168,76,0.3);
    flex-shrink: 0;
  }
  .logo-text { line-height: 1; }
  .logo-text .brand { font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 900; color: var(--gold); letter-spacing: 2px; }
  .logo-text .tagline { font-size: 0.6rem; color: var(--blush); letter-spacing: 4px; text-transform: uppercase; }

  .header-info { text-align: center; font-size: 0.7rem; color: var(--blush); line-height: 1.6; }
  .header-info strong { color: var(--gold); font-size: 0.8rem; }

  .search-bar {
    flex: 1; max-width: 380px;
    display: flex; align-items: center;
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(201,168,76,0.3);
    border-radius: 2px; overflow: hidden;
  }
  .search-bar input {
    flex: 1; background: transparent; border: none; outline: none;
    padding: 9px 16px; color: var(--text-light); font-family: 'Montserrat', sans-serif;
    font-size: 0.8rem;
  }
  .search-bar input::placeholder { color: var(--muted); }
  .search-bar button {
    background: var(--gold); border: none; padding: 9px 14px; cursor: pointer; color: var(--dark); font-size: 1rem;
    transition: background 0.3s;
  }
  .search-bar button:hover { background: var(--gold-light); }

  .header-actions { display: flex; align-items: center; gap: 10px; }
  .btn-auth {
    padding: 7px 18px; border-radius: 2px; cursor: pointer; font-size: 0.75rem;
    font-family: 'Montserrat', sans-serif; font-weight: 600; text-transform: uppercase;
    letter-spacing: 1px; transition: all 0.3s; text-decoration: none; display: inline-block;
  }
  .btn-login { background: transparent; color: var(--gold); border: 1px solid var(--gold); }
  .btn-login:hover { background: var(--gold); color: var(--dark); }
  .btn-register { background: var(--crimson); color: var(--cream); border: 1px solid var(--crimson); }
  .btn-register:hover { background: var(--rose); }
  .cart-btn {
    background: rgba(201,168,76,0.1); border: 1px solid rgba(201,168,76,0.4);
    padding: 7px 14px; border-radius: 2px; cursor: pointer;
    color: var(--gold); font-size: 0.75rem; font-family: 'Montserrat', sans-serif;
    display: flex; align-items: center; gap: 6px; transition: all 0.3s;
  }
  .cart-btn:hover { background: rgba(201,168,76,0.2); }

  /* ===== NAV ===== */
  nav {
    background: var(--crimson-dark);
    padding: 0 40px;
    display: flex; align-items: center; gap: 0;
    border-bottom: 2px solid var(--gold);
    overflow-x: auto;
  }
  nav a {
    color: var(--text-light); text-decoration: none;
    padding: 12px 22px; font-size: 0.75rem; font-weight: 600;
    text-transform: uppercase; letter-spacing: 1.5px;
    transition: all 0.3s; white-space: nowrap; display: block;
    border-bottom: 3px solid transparent;
  }
  nav a:hover, nav a.active { color: var(--gold); border-bottom-color: var(--gold); background: rgba(201,168,76,0.08); }

  /* ===== HERO ===== */
  .hero {
    min-height: 85vh;
    background: linear-gradient(135deg, var(--dark) 0%, var(--crimson-dark) 50%, var(--dark) 100%);
    position: relative; overflow: hidden;
    display: flex; align-items: center; justify-content: center;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse at 30% 50%, rgba(139,0,0,0.6) 0%, transparent 60%),
                radial-gradient(ellipse at 70% 50%, rgba(92,0,0,0.4) 0%, transparent 60%);
  }
  .hero-roses {
    position: absolute; inset: 0; pointer-events: none;
    overflow: hidden;
  }
  .rose-deco {
    position: absolute; font-size: 3rem; opacity: 0.08;
    animation: floatRose 8s ease-in-out infinite;
  }
  .rose-deco:nth-child(1) { top: 10%; left: 5%; animation-delay: 0s; font-size: 2rem; }
  .rose-deco:nth-child(2) { top: 20%; right: 8%; animation-delay: 1.5s; font-size: 4rem; }
  .rose-deco:nth-child(3) { top: 60%; left: 3%; animation-delay: 3s; font-size: 2.5rem; }
  .rose-deco:nth-child(4) { bottom: 15%; right: 5%; animation-delay: 0.8s; font-size: 3.5rem; }
  .rose-deco:nth-child(5) { top: 40%; left: 15%; animation-delay: 2s; font-size: 1.5rem; opacity: 0.05; }
  .rose-deco:nth-child(6) { bottom: 30%; right: 15%; animation-delay: 4s; font-size: 2rem; opacity: 0.06; }
  @keyframes floatRose {
    0%, 100% { transform: translateY(0) rotate(0deg); }
    50% { transform: translateY(-20px) rotate(5deg); }
  }
  .hero-content { position: relative; z-index: 2; text-align: center; padding: 40px 20px; }
  .hero-eyebrow {
    font-size: 0.7rem; letter-spacing: 6px; text-transform: uppercase;
    color: var(--gold); margin-bottom: 20px;
    animation: fadeUp 0.8s ease both;
  }
  .hero-title {
    font-family: 'Playfair Display', serif; font-size: clamp(3.5rem, 8vw, 7rem);
    font-weight: 900; line-height: 0.9; color: var(--cream);
    animation: fadeUp 0.8s 0.2s ease both;
  }
  .hero-title .italic { font-style: italic; color: var(--gold); }
  .hero-subtitle {
    font-family: 'Cormorant Garamond', serif; font-size: 1.2rem; font-style: italic;
    color: var(--blush); margin: 24px 0 40px;
    animation: fadeUp 0.8s 0.4s ease both;
  }
  .hero-cta {
    display: flex; gap: 16px; justify-content: center; flex-wrap: wrap;
    animation: fadeUp 0.8s 0.6s ease both;
  }
  .btn-primary {
    background: var(--gold); color: var(--dark); padding: 14px 36px;
    border: none; border-radius: 1px; cursor: pointer; font-size: 0.8rem;
    font-family: 'Montserrat', sans-serif; font-weight: 700; text-transform: uppercase;
    letter-spacing: 2px; text-decoration: none; transition: all 0.3s;
    box-shadow: 0 4px 20px rgba(201,168,76,0.4);
  }
  .btn-primary:hover { background: var(--gold-light); transform: translateY(-2px); box-shadow: 0 8px 30px rgba(201,168,76,0.5); }
  .btn-secondary {
    background: transparent; color: var(--cream); padding: 14px 36px;
    border: 1px solid rgba(255,255,255,0.3); border-radius: 1px; cursor: pointer;
    font-size: 0.8rem; font-family: 'Montserrat', sans-serif; font-weight: 600;
    text-transform: uppercase; letter-spacing: 2px; text-decoration: none; transition: all 0.3s;
  }
  .btn-secondary:hover { border-color: var(--gold); color: var(--gold); }

  .hero-offer {
    position: absolute; right: 40px; top: 50%; transform: translateY(-50%);
    background: rgba(13,5,5,0.85);
    border: 2px solid var(--gold);
    padding: 24px 20px; text-align: center;
    border-radius: 2px; max-width: 180px;
    backdrop-filter: blur(8px);
    animation: pulse 3s ease-in-out infinite;
    z-index: 3;
  }
  @keyframes pulse { 0%,100%{box-shadow:0 0 20px rgba(201,168,76,0.3)} 50%{box-shadow:0 0 40px rgba(201,168,76,0.6)} }
  .hero-offer .offer-label { font-size: 0.6rem; letter-spacing: 3px; color: var(--gold); text-transform: uppercase; margin-bottom: 8px; }
  .hero-offer .offer-title { font-family: 'Playfair Display', serif; font-size: 1.1rem; color: var(--cream); font-weight: 700; margin-bottom: 4px; }
  .hero-offer .offer-desc { font-size: 0.7rem; color: var(--blush); line-height: 1.4; }
  .hero-offer .offer-emoji { font-size: 2.5rem; display: block; margin: 10px 0 6px; }

  @keyframes fadeUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }

  /* ===== SECTIONS ===== */
  .section { padding: 80px 40px; }
  .section-alt { background: rgba(255,255,255,0.02); }
  .section-title {
    font-family: 'Playfair Display', serif; font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 900; color: var(--cream); text-align: center;
    margin-bottom: 12px;
  }
  .section-title .accent { color: var(--gold); font-style: italic; }
  .section-subtitle { text-align: center; color: var(--blush); font-size: 0.85rem; margin-bottom: 60px; letter-spacing: 2px; text-transform: uppercase; }
  .gold-line { width: 80px; height: 2px; background: var(--gold); margin: 16px auto 48px; }

  /* ===== SERVICES OVERVIEW ===== */
  .services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 24px; max-width: 1200px; margin: 0 auto; }
  .service-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(201,168,76,0.2);
    border-radius: 2px; padding: 36px 28px;
    text-align: center; cursor: pointer;
    transition: all 0.4s; position: relative; overflow: hidden;
  }
  .service-card::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(139,0,0,0.1), transparent);
    opacity: 0; transition: opacity 0.4s;
  }
  .service-card:hover { border-color: var(--gold); transform: translateY(-6px); box-shadow: 0 20px 60px rgba(139,0,0,0.3); }
  .service-card:hover::before { opacity: 1; }
  .service-icon { font-size: 3rem; display: block; margin-bottom: 16px; }
  .service-card h3 { font-family: 'Playfair Display', serif; font-size: 1.4rem; color: var(--gold); margin-bottom: 12px; font-weight: 700; }
  .service-card p { font-size: 0.8rem; color: var(--blush); line-height: 1.7; margin-bottom: 20px; }
  .service-card ul { list-style: none; text-align: left; }
  .service-card ul li { font-size: 0.78rem; color: var(--text-light); padding: 4px 0; padding-left: 16px; position: relative; }
  .service-card ul li::before { content: '›'; position: absolute; left: 0; color: var(--gold); font-weight: 700; }

  /* ===== DEPARTMENTS ===== */
  .dept-nav { display: flex; justify-content: center; gap: 0; margin-bottom: 48px; flex-wrap: wrap; }
  .dept-btn {
    padding: 12px 28px; background: transparent; border: 1px solid rgba(201,168,76,0.3);
    color: var(--blush); cursor: pointer; font-family: 'Montserrat', sans-serif;
    font-size: 0.75rem; font-weight: 600; text-transform: uppercase; letter-spacing: 1.5px;
    transition: all 0.3s;
  }
  .dept-btn.active, .dept-btn:hover { background: var(--gold); color: var(--dark); border-color: var(--gold); }

  .dept-panel { display: none; }
  .dept-panel.active { display: block; }

  .dept-header { text-align: center; margin-bottom: 48px; }
  .dept-header h2 { font-family: 'Playfair Display', serif; font-size: 2.2rem; color: var(--gold); margin-bottom: 8px; }
  .dept-header p { color: var(--blush); font-size: 0.85rem; max-width: 600px; margin: 0 auto; line-height: 1.7; }

  .sections-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; max-width: 1200px; margin: 0 auto; }
  @media(max-width:900px){ .sections-grid { grid-template-columns: 1fr; } }

  .subsection { background: rgba(255,255,255,0.03); border: 1px solid rgba(201,168,76,0.15); border-radius: 2px; overflow: hidden; }
  .subsection-header {
    background: linear-gradient(135deg, var(--crimson-dark), var(--crimson));
    padding: 20px 28px; display: flex; align-items: center; gap: 12px;
    border-bottom: 2px solid var(--gold);
  }
  .subsection-header .sub-icon { font-size: 1.6rem; }
  .subsection-header h3 { font-family: 'Playfair Display', serif; font-size: 1.3rem; color: var(--cream); font-weight: 700; }

  .items-list { padding: 8px 0; }
  .item-row {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 28px; border-bottom: 1px solid rgba(255,255,255,0.05);
    transition: background 0.2s; cursor: pointer;
  }
  .item-row:last-child { border-bottom: none; }
  .item-row:hover { background: rgba(201,168,76,0.06); }
  .item-info { display: flex; align-items: center; gap: 12px; }
  .item-emoji { font-size: 1.6rem; }
  .item-name { font-size: 0.88rem; color: var(--text-light); font-weight: 500; }
  .item-desc { font-size: 0.72rem; color: var(--muted); margin-top: 2px; }
  .item-price { font-family: 'Playfair Display', serif; font-size: 1.05rem; color: var(--gold); font-weight: 700; white-space: nowrap; }

  /* ===== ENTERTAINMENT SPECIAL ===== */
  .gaming-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 20px; max-width: 1200px; margin: 0 auto 40px; }
  .game-card {
    background: rgba(255,255,255,0.04); border: 1px solid rgba(201,168,76,0.2);
    border-radius: 2px; padding: 24px 20px; text-align: center; transition: all 0.3s;
  }
  .game-card:hover { border-color: var(--gold); transform: translateY(-4px); }
  .game-card .game-icon { font-size: 2.5rem; display: block; margin-bottom: 12px; }
  .game-card h4 { font-family: 'Playfair Display', serif; font-size: 1rem; color: var(--gold); margin-bottom: 8px; }
  .game-card p { font-size: 0.75rem; color: var(--blush); line-height: 1.5; margin-bottom: 10px; }
  .game-card .price-badge {
    display: inline-block; background: var(--crimson-dark); border: 1px solid var(--gold);
    color: var(--gold); font-size: 0.75rem; font-weight: 700; padding: 4px 12px; border-radius: 1px;
  }

  /* ===== DELIVERY SECTION ===== */
  .delivery-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; max-width: 1000px; margin: 0 auto 40px; }
  @media(max-width:700px){ .delivery-grid { grid-template-columns: 1fr; } }
  .delivery-card {
    background: rgba(255,255,255,0.03); border: 1px solid rgba(201,168,76,0.2);
    border-radius: 2px; padding: 36px 28px; text-align: center;
  }
  .delivery-card .delivery-icon { font-size: 3.5rem; display: block; margin-bottom: 16px; }
  .delivery-card h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--gold); margin-bottom: 12px; }
  .delivery-card .price-tag { font-size: 1.8rem; font-weight: 700; color: var(--cream); margin-bottom: 8px; }
  .delivery-card .price-tag span { font-size: 0.8rem; color: var(--blush); font-weight: 400; }
  .delivery-card p { font-size: 0.8rem; color: var(--blush); line-height: 1.7; }

  .check-form { max-width: 500px; margin: 0 auto; text-align: center; }
  .check-form h3 { font-family: 'Playfair Display', serif; font-size: 1.3rem; color: var(--gold); margin-bottom: 20px; }
  .check-form .input-group { display: flex; gap: 0; }
  .check-form input {
    flex: 1; background: rgba(255,255,255,0.06); border: 1px solid rgba(201,168,76,0.3);
    border-right: none; padding: 12px 18px; color: var(--text-light);
    font-family: 'Montserrat', sans-serif; font-size: 0.85rem; outline: none; border-radius: 0;
  }
  .check-form input::placeholder { color: var(--muted); }
  .check-form button { background: var(--gold); color: var(--dark); border: none; padding: 12px 20px; cursor: pointer; font-weight: 700; font-size: 0.8rem; transition: background 0.3s; }
  .check-form button:hover { background: var(--gold-light); }

  /* ===== FAQ ===== */
  .faq-list { max-width: 800px; margin: 0 auto; }
  .faq-item {
    border-bottom: 1px solid rgba(201,168,76,0.15); overflow: hidden;
  }
  .faq-q {
    width: 100%; background: transparent; border: none; text-align: left;
    padding: 20px 0; color: var(--text-light); font-family: 'Montserrat', sans-serif;
    font-size: 0.9rem; font-weight: 600; cursor: pointer;
    display: flex; justify-content: space-between; align-items: center;
    transition: color 0.3s;
  }
  .faq-q:hover { color: var(--gold); }
  .faq-q .faq-icon { color: var(--gold); font-size: 1.2rem; transition: transform 0.3s; }
  .faq-q.open .faq-icon { transform: rotate(45deg); }
  .faq-a {
    display: none; padding: 0 0 20px; font-size: 0.82rem; color: var(--blush);
    line-height: 1.8;
  }
  .faq-a.open { display: block; }

  /* ===== ABOUT ===== */
  .about-content { max-width: 800px; margin: 0 auto; }
  .about-content p { color: var(--blush); font-size: 0.88rem; line-height: 1.9; margin-bottom: 16px; }

  /* ===== CONTACT ===== */
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; max-width: 1000px; margin: 0 auto; }
  @media(max-width:700px){ .contact-grid { grid-template-columns: 1fr; } }
  .contact-info h3 { font-family: 'Playfair Display', serif; font-size: 1.5rem; color: var(--gold); margin-bottom: 24px; }
  .contact-item { display: flex; align-items: center; gap: 12px; margin-bottom: 16px; }
  .contact-item .icon { font-size: 1.2rem; }
  .contact-item .text { font-size: 0.83rem; color: var(--blush); line-height: 1.5; }
  .contact-item .text strong { color: var(--text-light); display: block; }
  .social-links { display: flex; gap: 12px; margin-top: 28px; }
  .social-link {
    width: 44px; height: 44px; border-radius: 50%; display: flex; align-items: center; justify-content: center;
    text-decoration: none; font-size: 1.1rem; transition: all 0.3s;
    border: 1px solid rgba(201,168,76,0.3);
  }
  .social-link:hover { border-color: var(--gold); transform: translateY(-3px); background: rgba(201,168,76,0.1); }

  /* ===== FORM ===== */
  .form-group { margin-bottom: 20px; }
  .form-group label { display: block; font-size: 0.75rem; color: var(--blush); text-transform: uppercase; letter-spacing: 1px; margin-bottom: 8px; }
  .form-group input, .form-group textarea {
    width: 100%; background: rgba(255,255,255,0.05); border: 1px solid rgba(201,168,76,0.25);
    padding: 12px 16px; color: var(--text-light); font-family: 'Montserrat', sans-serif;
    font-size: 0.85rem; outline: none; border-radius: 0; transition: border-color 0.3s;
  }
  .form-group input:focus, .form-group textarea:focus { border-color: var(--gold); }
  .form-group textarea { min-height: 120px; resize: vertical; }
  .form-required { color: var(--crimson); }

  /* ===== SITEMAP ===== */
  .sitemap-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 32px; max-width: 900px; margin: 0 auto; }
  .sitemap-col h4 { font-family: 'Playfair Display', serif; font-size: 1rem; color: var(--gold); margin-bottom: 16px; padding-bottom: 8px; border-bottom: 1px solid rgba(201,168,76,0.3); }
  .sitemap-col ul { list-style: none; }
  .sitemap-col ul li { margin-bottom: 8px; }
  .sitemap-col ul li a { color: var(--blush); text-decoration: none; font-size: 0.8rem; transition: color 0.3s; display: flex; align-items: center; gap: 6px; }
  .sitemap-col ul li a::before { content: '›'; color: var(--gold); }
  .sitemap-col ul li a:hover { color: var(--gold); }

  /* ===== FOOTER ===== */
  footer {
    background: var(--charcoal);
    border-top: 2px solid var(--gold);
    padding: 60px 40px 30px;
  }
  .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 40px; margin-bottom: 40px; }
  .footer-col h4 { font-family: 'Playfair Display', serif; color: var(--gold); font-size: 1rem; margin-bottom: 18px; letter-spacing: 1px; }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 8px; }
  .footer-col ul li a { color: var(--muted); text-decoration: none; font-size: 0.78rem; transition: color 0.3s; }
  .footer-col ul li a:hover { color: var(--gold); }
  .footer-col p { color: var(--muted); font-size: 0.78rem; line-height: 1.7; }
  .footer-social { display: flex; gap: 10px; margin-top: 16px; }
  .footer-social a {
    width: 38px; height: 38px; border: 1px solid rgba(201,168,76,0.3); border-radius: 50%;
    display: flex; align-items: center; justify-content: center; font-size: 1rem;
    text-decoration: none; transition: all 0.3s;
  }
  .footer-social a:hover { border-color: var(--gold); background: rgba(201,168,76,0.1); }
  .footer-bottom {
    border-top: 1px solid rgba(201,168,76,0.15); padding-top: 24px;
    display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px;
  }
  .footer-bottom p { color: var(--muted); font-size: 0.72rem; }
  .footer-bottom .phone { color: var(--gold); font-weight: 600; }

  /* ===== TABS ===== */
  .page-section { display: none; }
  .page-section.active { display: block; }

  /* ===== POLICIES ===== */
  .policy-content { max-width: 800px; margin: 0 auto; }
  .policy-content h3 { font-family: 'Playfair Display', serif; color: var(--gold); font-size: 1.2rem; margin: 28px 0 12px; }
  .policy-content p { color: var(--blush); font-size: 0.83rem; line-height: 1.9; margin-bottom: 14px; }
  .policy-content ul { list-style: none; margin-bottom: 14px; padding-left: 16px; }
  .policy-content ul li { color: var(--blush); font-size: 0.83rem; line-height: 1.8; padding-left: 16px; position: relative; margin-bottom: 6px; }
  .policy-content ul li::before { content: '◆'; position: absolute; left: 0; color: var(--gold); font-size: 0.5rem; top: 6px; }

  /* Responsive */
  @media(max-width:768px){
    .header-top { flex-wrap: wrap; padding: 12px 20px; }
    .hero-offer { display: none; }
    .section { padding: 60px 20px; }
    nav { padding: 0 20px; }
    footer { padding: 40px 20px 20px; }
    .contact-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- COOKIE BANNER -->
<div id="cookie-banner">
  <p>🍪 Utilizamos cookies propias y de terceros para mejorar tu experiencia de navegación, análisis estadísticos y personalización de contenido. Al continuar navegando aceptas nuestra <a onclick="showPage('cookies')">Política de Cookies</a> y <a onclick="showPage('privacidad')">Política de Privacidad</a>. Puedes configurar tu navegador para rechazarlas.</p>
  <div class="cookie-btns">
    <button class="btn-reject" onclick="closeCookie()">Rechazar</button>
    <button class="btn-accept" onclick="closeCookie()">Aceptar Cookies</button>
  </div>
</div>

<!-- HEADER -->
<header>
  <div class="header-top">
    <div class="logo-area">
      <div class="logo-icon">☕</div>
      <div class="logo-text">
        <div class="brand">DREAM COFFEE</div>
        <div class="tagline">Café · Entretenimiento · Delivery</div>
      </div>
    </div>
    <div class="header-info">
      <strong>🕐 Lun – Sáb &nbsp;|&nbsp; 7:00 a.m. – 5:00 p.m.</strong><br>
      📍 Airon, 22925 Nuevo Centro de Población Padre Kino, B.C.
    </div>
    <div class="search-bar">
      <input type="text" placeholder="Buscar productos, servicios...">
      <button>🔍</button>
    </div>
    <div class="header-actions">
      <a href="#" class="btn-auth btn-login" onclick="showModal('login')">Iniciar sesión</a>
      <a href="#" class="btn-auth btn-register" onclick="showModal('register')">Registrarse</a>
      <div class="cart-btn">🛒 <span id="cart-count">0</span> objetos</div>
    </div>
  </div>
  <nav>
    <a href="#" class="active" onclick="showPage('home')">Inicio</a>
    <a href="#" onclick="showPage('comida')">Comida</a>
    <a href="#" onclick="showPage('entretenimiento')">Entretenimiento</a>
    <a href="#" onclick="showPage('delivery')">Delivery</a>
    <a href="#" onclick="showPage('snacks')">Snacks & Rápida</a>
    <a href="#" onclick="showPage('nosotros')">Acerca de nosotros</a>
    <a href="#" onclick="showPage('contacto')">Contacto</a>
    <a href="#" onclick="showPage('faq')">FAQ</a>
    <a href="#" onclick="showPage('sitemap')">Mapa de Sitio</a>
  </nav>
</header>

<!-- ===== HOME ===== -->
<div id="page-home" class="page-section active">
  <!-- HERO -->
  <section class="hero">
    <div class="hero-roses">
      <span class="rose-deco">🌹</span>
      <span class="rose-deco">🌹</span>
      <span class="rose-deco">🌹</span>
      <span class="rose-deco">🌹</span>
      <span class="rose-deco">🌹</span>
      <span class="rose-deco">🌹</span>
    </div>
    <div class="hero-content">
      <div class="hero-eyebrow">🌹 Bienvenido a nuestro sueño 🌹</div>
      <h1 class="hero-title"><style>img {width: 40%; height: auto; }</style><img src="https://gcdnb.pbrd.co/images/yG3Xy7-Q6mbr.png" alt="DREAM COFFEE" width="100"></h1>
      <p class="hero-subtitle">Donde cada sorbo es un sueño que vale la pena vivir</p>
      <div class="hero-cta">
        <a href="#" class="btn-primary" onclick="showPage('comida')">Ver Menú</a>
        <a href="#" class="btn-secondary" onclick="showPage('delivery')">Pedir a Domicilio</a>
      </div>
    </div>
    <div class="hero-offer">
      <span class="offer-label">✨ Postre del Día</span>
      <span class="offer-emoji">🍮</span>
      <div class="offer-title">Chocoflan + Fresas</div>
      <div class="offer-desc">$60 MXN la rebanada</div>
      <br>
      <span class="offer-label">💑 Oferta Especial</span>
      <div class="offer-title" style="font-size:0.9rem;margin-top:6px;">Postre Gratis</div>
      <div class="offer-desc">para parejas enamoradas</div>
    </div>
  </section>

  <!-- SERVICES OVERVIEW -->
  <section class="section">
    <h2 class="section-title">¿Cuáles son Nuestros <span class="accent">Servicios?</span></h2>
    <div class="gold-line"></div>
    <div class="services-grid">
      <div class="service-card" onclick="showPage('comida')">
        <span class="service-icon">🍰</span>
        <h3>Comida</h3>
        <p>Deliciosos postres y bebidas preparadas con ingredientes de calidad</p>
        <ul>
          <li>Postres Dulces y Salados</li>
          <li>Bebidas Frías y Calientes</li>
          <li>Menú del día</li>
        </ul>
      </div>
      <div class="service-card" onclick="showPage('entretenimiento')">
        <span class="service-icon">🎮</span>
        <h3>Entretenimiento</h3>
        <p>Diversión para todos: juegos, videojuegos y streaming incluido</p>
        <ul>
          <li>Area de Juegos de Mesa</li>
          <li>XBox Series X</li>
          <li>Netflix · Prime · Disney+</li>
        </ul>
      </div>
      <div class="service-card" onclick="showPage('delivery')">
        <span class="service-icon">🛵</span>
        <h3>Entrega a Domicilio</h3>
        <p>Llevamos tus bebidas y postres favoritos hasta tu puerta</p>
        <ul>
          <li>Entrega Express ($20 MXN)</li>
          <li>Entrega Básica (sin costo)</li>
          <li>Consulta tu zona de cobertura</li>
        </ul>
      </div>
      <div class="service-card" onclick="showPage('snacks')">
        <span class="service-icon">🌮</span>
        <h3>Snacks & Comida Rápida</h3>
        <p>Antojitos y snacks perfectos para acompañar tu café o estadía</p>
        <ul>
          <li>Bocadillos Salados</li>
          <li>Opciones Veganas</li>
          <li>Combos especiales</li>
        </ul>
      </div>
    </div>
  </section>
</div>

<!-- ===== COMIDA ===== -->
<div id="page-comida" class="page-section">
  <section class="section">
    <h2 class="section-title">🍰 <span class="accent">Comida</span></h2>
    <p class="section-subtitle">Postres & Bebidas elaboradas con amor</p>
    <div class="gold-line"></div>

    <div class="dept-nav">
      <button class="dept-btn active" onclick="switchSub(this,'postres')">🍮 Postres</button>
      <button class="dept-btn" onclick="switchSub(this,'bebidas')">☕ Bebidas</button>
    </div>

    <!-- POSTRES -->
    <div id="sub-postres" class="dept-panel active">
      <div class="dept-header">
        <h2>🍮 Postres</h2>
        <p>Desde dulces tentaciones hasta opciones saladas. Elaborados diariamente con ingredientes frescos y seleccionados.</p>
      </div>
      <div class="sections-grid">
        <!-- Postres Dulces -->
        <div class="subsection">
          <div class="subsection-header">
            <span class="sub-icon">🍭</span>
            <h3>Postres Dulces</h3>
          </div>
          <div class="items-list">
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🍮</span><div><div class="item-name">Chocoflan + Fresas</div><div class="item-desc">Postre del día · Rebanada individual</div></div></div>
              <div class="item-price">$60 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🎂</span><div><div class="item-name">Pastel de Tres Leches</div><div class="item-desc">Esponjoso y cremoso · Porción</div></div></div>
              <div class="item-price">$55 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🍫</span><div><div class="item-name">Brownie de Chocolate</div><div class="item-desc">Con nuez y cubierta de ganache</div></div></div>
              <div class="item-price">$45 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🍪</span><div><div class="item-name">Galletas de Mantequilla</div><div class="item-desc">3 piezas artesanales</div></div></div>
              <div class="item-price">$30 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🧁</span><div><div class="item-name">Cupcake Decorado</div><div class="item-desc">Sabores del día · con betún artesanal</div></div></div>
              <div class="item-price">$40 MXN</div>
            </div>
          </div>
        </div>
        <!-- Postres Salados -->
        <div class="subsection">
          <div class="subsection-header">
            <span class="sub-icon">🧀</span>
            <h3>Postres Salados</h3>
          </div>
          <div class="items-list">
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🥧</span><div><div class="item-name">Pie de Frutos Rojos</div><div class="item-desc">Masa quebrada · frutos frescos</div></div></div>
              <div class="item-price">$70 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🥐</span><div><div class="item-name">Croissant de Queso</div><div class="item-desc">Masa hojaldrada · queso gouda</div></div></div>
              <div class="item-price">$38 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🧇</span><div><div class="item-name">Waffle Salado</div><div class="item-desc">Con queso crema y jamón serrano</div></div></div>
              <div class="item-price">$65 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🫓</span><div><div class="item-name">Pan Artesanal + Dip</div><div class="item-desc">Pan de la casa con mantequilla de ajo</div></div></div>
              <div class="item-price">$35 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🥨</span><div><div class="item-name">Pretzels con Cheddar</div><div class="item-desc">Horneados · con salsa de queso</div></div></div>
              <div class="item-price">$42 MXN</div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- BEBIDAS -->
    <div id="sub-bebidas" class="dept-panel">
      <div class="dept-header">
        <h2>☕ Bebidas</h2>
        <p>Café de origen, bebidas frías refrescantes y opciones calientes para cada momento del día.</p>
      </div>
      <div class="sections-grid">
        <div class="subsection">
          <div class="subsection-header">
            <span class="sub-icon">☕</span>
            <h3>Bebidas Calientes</h3>
          </div>
          <div class="items-list">
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">☕</span><div><div class="item-name">Café Americano</div><div class="item-desc">Espresso doble · taza grande</div></div></div>
              <div class="item-price">$35 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🥛</span><div><div class="item-name">Cappuccino</div><div class="item-desc">Espresso con leche vaporizada</div></div></div>
              <div class="item-price">$45 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🍫</span><div><div class="item-name">Chocolate Caliente</div><div class="item-desc">Con canela y crema batida</div></div></div>
              <div class="item-price">$40 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🫖</span><div><div class="item-name">Té de Frutas</div><div class="item-desc">Selección de temporada</div></div></div>
              <div class="item-price">$32 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">☕</span><div><div class="item-name">Café de Olla</div><div class="item-desc">Canela · piloncillo · tradicional</div></div></div>
              <div class="item-price">$30 MXN</div>
            </div>
          </div>
        </div>
        <div class="subsection">
          <div class="subsection-header">
            <span class="sub-icon">🧋</span>
            <h3>Bebidas Frías</h3>
          </div>
          <div class="items-list">
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🧊</span><div><div class="item-name">Café Frío (Iced Coffee)</div><div class="item-desc">Espresso · hielo · leche</div></div></div>
              <div class="item-price">$45 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🧋</span><div><div class="item-name">Frappé de Caramelo</div><div class="item-desc">Café · caramelo · crema batida</div></div></div>
              <div class="item-price">$55 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🫐</span><div><div class="item-name">Smoothie de Frutos Rojos</div><div class="item-desc">Fresa · mora · arándano · yogurt</div></div></div>
              <div class="item-price">$50 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🍋</span><div><div class="item-name">Limonada Mineral</div><div class="item-desc">Limón fresco · menta · agua mineral</div></div></div>
              <div class="item-price">$35 MXN</div>
            </div>
            <div class="item-row">
              <div class="item-info"><span class="item-emoji">🥤</span><div><div class="item-name">Frappé de Chocolate</div><div class="item-desc">Cacao · leche · hielo · crema</div></div></div>
              <div class="item-price">$55 MXN</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===== ENTRETENIMIENTO ===== -->
<div id="page-entretenimiento" class="page-section">
  <section class="section">
    <h2 class="section-title">🎮 <span class="accent">Entretenimiento</span></h2>
    <p class="section-subtitle">Diversión sin límites para toda la familia</p>
    <div class="gold-line"></div>

    <div class="dept-nav">
      <button class="dept-btn active" onclick="switchSub(this,'juegos')">🎲 Área de Juegos</button>
      <button class="dept-btn" onclick="switchSub(this,'cybercafe')">💻 Cybercafé</button>
    </div>

    <!-- ÁREA DE JUEGOS -->
    <div id="sub-juegos" class="dept-panel active">
      <div class="dept-header">
        <h2>🎲 Área de Juegos</h2>
        <p>Un espacio donde las risas están garantizadas. Reta a tus amigos o aprende algo nuevo con nuestros juegos didácticos.</p>
      </div>
      <div class="sections-grid">
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">♟️</span><h3>Juegos de Mesa</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">♟️</span><div><div class="item-name">Ajedrez</div><div class="item-desc">Tablero profesional · por partida</div></div></div><div class="item-price">$5 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🁡</span><div><div class="item-name">Dominó</div><div class="item-desc">Juego completo · por sesión</div></div></div><div class="item-price">$5 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🃏</span><div><div class="item-name">Uno</div><div class="item-desc">Cartas originales · hasta 4 jugadores</div></div></div><div class="item-price">$5 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🔴</span><div><div class="item-name">Damas Chinas</div><div class="item-desc">Tablero y fichas · por sesión</div></div></div><div class="item-price">$5 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎯</span><div><div class="item-name">Jenga</div><div class="item-desc">Torre de madera · hasta 6 jugadores</div></div></div><div class="item-price">$5 MXN</div></div>
          </div>
        </div>
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🧩</span><h3>Juegos Didácticos</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">❓</span><div><div class="item-name">Trivia General</div><div class="item-desc">Cultura general · equipos o individual</div></div></div><div class="item-price">$10 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🧩</span><div><div class="item-name">Rompecabezas</div><div class="item-desc">500 a 1000 piezas · temáticas variadas</div></div></div><div class="item-price">$8 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">📝</span><div><div class="item-name">Scrabble</div><div class="item-desc">Vocabulario y estrategia · 2-4 jugadores</div></div></div><div class="item-price">$10 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🔢</span><div><div class="item-name">Sudoku en Mesa</div><div class="item-desc">Nivel principiante a experto</div></div></div><div class="item-price">$5 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎨</span><div><div class="item-name">Pictionary</div><div class="item-desc">Dibujo y adivinanza · por equipo</div></div></div><div class="item-price">$10 MXN</div></div>
          </div>
        </div>
      </div>
    </div>

    <!-- CYBERCAFÉ -->
    <div id="sub-cybercafe" class="dept-panel">
      <div class="dept-header">
        <h2>💻 Cybercafé</h2>
        <p>Tecnología de punta para entretenimiento digital. Consolas de última generación y plataformas de streaming sin costo adicional.</p>
      </div>
      <div class="sections-grid">
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🎮</span><h3>Videojuegos</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎮</span><div><div class="item-name">XBox Series X</div><div class="item-desc">Consola de última generación · 1 hora</div></div></div><div class="item-price">$135 MXN/h</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎯</span><div><div class="item-name">XBox Series X</div><div class="item-desc">2 horas continuas · precio especial</div></div></div><div class="item-price">$250 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">👾</span><div><div class="item-name">XBox Series X</div><div class="item-desc">Tarde completa (3h) · mejor precio</div></div></div><div class="item-price">$350 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🕹️</span><div><div class="item-name">Selección de Juegos</div><div class="item-desc">+50 títulos disponibles · consulta catálogo</div></div></div><div class="item-price">Incluido</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎧</span><div><div class="item-name">Audífonos Gaming</div><div class="item-desc">Headset con micrófono · sonido envolvente</div></div></div><div class="item-price">Incluido</div></div>
          </div>
        </div>
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">📺</span><h3>Streaming</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎬</span><div><div class="item-name">Netflix</div><div class="item-desc">Series y películas · pantalla 4K</div></div></div><div class="item-price">Gratuito</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">📦</span><div><div class="item-name">Prime Video</div><div class="item-desc">Amazon originals y más</div></div></div><div class="item-price">Gratuito</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">✨</span><div><div class="item-name">Disney+</div><div class="item-desc">Marvel · Star Wars · Disney · Pixar</div></div></div><div class="item-price">Gratuito</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🎵</span><div><div class="item-name">Spotify Premium</div><div class="item-desc">Música sin anuncios en el local</div></div></div><div class="item-price">Gratuito</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">📡</span><div><div class="item-name">Wi-Fi Alta Velocidad</div><div class="item-desc">100 Mbps · contraseña al pedir</div></div></div><div class="item-price">Gratuito</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===== DELIVERY ===== -->
<div id="page-delivery" class="page-section">
  <section class="section">
    <h2 class="section-title">🛵 <span class="accent">Delivery</span></h2>
    <p class="section-subtitle">Llevamos el Dream Coffee hasta tu puerta</p>
    <div class="gold-line"></div>

    <div class="delivery-grid" style="margin-bottom:60px;">
      <div class="delivery-card">
        <span class="delivery-icon">⚡</span>
        <h3>Express</h3>
        <div class="price-tag">$20 MXN <span>costo adicional</span></div>
        <p>Entrega prioritaria en el menor tiempo posible. Tu pedido sale en cuanto está listo, con repartidor asignado exclusivamente para ti.</p>
      </div>
      <div class="delivery-card">
        <span class="delivery-icon">🛵</span>
        <h3>Básico</h3>
        <div class="price-tag">Sin costo <span>adicional</span></div>
        <p>Servicio estándar de delivery incluido con tu pedido. Tiempo de entrega estimado según zona de cobertura disponible.</p>
      </div>
    </div>

    <div class="sections-grid" style="margin-bottom:60px;">
      <div class="subsection">
        <div class="subsection-header"><span class="sub-icon">📍</span><h3>Consulta</h3></div>
        <div class="items-list">
          <div class="item-row"><div class="item-info"><span class="item-emoji">🗺️</span><div><div class="item-name">¿Mi dirección está disponible?</div><div class="item-desc">Consulta tu zona de cobertura</div></div></div><div class="item-price">Gratis</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">⏰</span><div><div class="item-name">Plazo de Entrega Básico</div><div class="item-desc">30 – 45 minutos aprox.</div></div></div><div class="item-price">—</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">⚡</span><div><div class="item-name">Plazo de Entrega Express</div><div class="item-desc">15 – 25 minutos aprox.</div></div></div><div class="item-price">—</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">💳</span><div><div class="item-name">Métodos de Pago</div><div class="item-desc">Efectivo · Débito · Crédito</div></div></div><div class="item-price">—</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">📦</span><div><div class="item-name">Pedido Mínimo</div><div class="item-desc">Sin mínimo requerido</div></div></div><div class="item-price">—</div></div>
        </div>
      </div>
      <div class="subsection">
        <div class="subsection-header"><span class="sub-icon">🔄</span><h3>Devoluciones</h3></div>
        <div class="items-list">
          <div class="item-row"><div class="item-info"><span class="item-emoji">❌</span><div><div class="item-name">Producto en mal estado</div><div class="item-desc">Reposición sin costo</div></div></div><div class="item-price">✅</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">🔧</span><div><div class="item-name">Defecto de preparación</div><div class="item-desc">Reposición sin costo</div></div></div><div class="item-price">✅</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">📦</span><div><div class="item-name">Empaque incorrecto</div><div class="item-desc">Reposición sin costo</div></div></div><div class="item-price">✅</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">❓</span><div><div class="item-name">Pedido no correspondiente</div><div class="item-desc">Reposición sin costo</div></div></div><div class="item-price">✅</div></div>
          <div class="item-row"><div class="item-info"><span class="item-emoji">📧</span><div><div class="item-name">Contacto para devoluciones</div><div class="item-desc">dreamcoffee929@gmail.com</div></div></div><div class="item-price">—</div></div>
        </div>
      </div>
    </div>

    <div class="check-form">
      <h3>📍 ¿Llegamos a tu zona?</h3>
      <div class="input-group">
        <input type="text" placeholder="Escribe tu colonia o dirección...">
        <button>Consultar</button>
      </div>
    </div>
  </section>
</div>

<!-- ===== SNACKS & COMIDA RÁPIDA (4to departamento) ===== -->
<div id="page-snacks" class="page-section">
  <section class="section">
    <h2 class="section-title">🌮 <span class="accent">Snacks & Comida Rápida</span></h2>
    <p class="section-subtitle">Antojitos y bocadillos para acompañar tu momento Dream Coffee</p>
    <div class="gold-line"></div>

    <div class="dept-nav">
      <button class="dept-btn active" onclick="switchSub(this,'bocadillos')">🧆 Bocadillos Salados</button>
      <button class="dept-btn" onclick="switchSub(this,'veganos')">🥗 Opciones Veganas</button>
    </div>

    <!-- BOCADILLOS SALADOS -->
    <div id="sub-bocadillos" class="dept-panel active">
      <div class="dept-header">
        <h2>🧆 Bocadillos Salados</h2>
        <p>Snacks y antojitos perfectos para picar mientras disfrutas de tu bebida favorita o una sesión de juego.</p>
      </div>
      <div class="sections-grid">
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🌮</span><h3>Antojitos Mexicanos</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🌮</span><div><div class="item-name">Taquitos Dorados</div><div class="item-desc">3 piezas · papa o frijol · crema y salsa</div></div></div><div class="item-price">$40 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🫔</span><div><div class="item-name">Quesadilla de Queso</div><div class="item-desc">Tortilla de maíz · queso oaxaca</div></div></div><div class="item-price">$35 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🍟</span><div><div class="item-name">Papas a la Francesa</div><div class="item-desc">Crujientes · con aderezo de la casa</div></div></div><div class="item-price">$38 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🌽</span><div><div class="item-name">Elote en Vaso</div><div class="item-desc">Con mayonesa · queso · chile piquín</div></div></div><div class="item-price">$30 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥜</span><div><div class="item-name">Cacahuates Botaneros</div><div class="item-desc">Con chamoy y limón · porción</div></div></div><div class="item-price">$20 MXN</div></div>
          </div>
        </div>
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🥪</span><h3>Bocadillos Internacionales</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥪</span><div><div class="item-name">Sandwich Club</div><div class="item-desc">Jamón · queso · lechuga · tomate</div></div></div><div class="item-price">$55 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🧆</span><div><div class="item-name">Nachos con Dips</div><div class="item-desc">Guacamole · queso fundido · jalapeño</div></div></div><div class="item-price">$60 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🍕</span><div><div class="item-name">Pizza Personal</div><div class="item-desc">6 porciones · queso y pepperoni</div></div></div><div class="item-price">$75 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥚</span><div><div class="item-name">Huevos Rancheros</div><div class="item-desc">Con salsa roja y tortillas</div></div></div><div class="item-price">$50 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🧀</span><div><div class="item-name">Tabla de Quesos</div><div class="item-desc">3 variedades · galletas y mermelada</div></div></div><div class="item-price">$90 MXN</div></div>
          </div>
        </div>
      </div>
    </div>

    <!-- VEGANOS -->
    <div id="sub-veganos" class="dept-panel">
      <div class="dept-header">
        <h2>🥗 Opciones Veganas</h2>
        <p>Porque todos merecen disfrutar Dream Coffee. Opciones 100% de origen vegetal preparadas con el mismo amor y calidad.</p>
      </div>
      <div class="sections-grid">
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🥗</span><h3>Bowls & Ensaladas</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥗</span><div><div class="item-name">Bowl Verde</div><div class="item-desc">Espinaca · aguacate · pepino · aderezo limón</div></div></div><div class="item-price">$65 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🫙</span><div><div class="item-name">Overnight Oats</div><div class="item-desc">Avena · leche de almendra · chía · fruta</div></div></div><div class="item-price">$55 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥑</span><div><div class="item-name">Tostadas de Aguacate</div><div class="item-desc">Pan integral · aguacate · jitomate cherry</div></div></div><div class="item-price">$48 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🌯</span><div><div class="item-name">Wrap Vegetal</div><div class="item-desc">Tortilla · hummus · zanahoria · espinaca</div></div></div><div class="item-price">$52 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🍓</span><div><div class="item-name">Parfait de Fruta</div><div class="item-desc">Granola · yogurt vegano · frutos del bosque</div></div></div><div class="item-price">$45 MXN</div></div>
          </div>
        </div>
        <div class="subsection">
          <div class="subsection-header"><span class="sub-icon">🌱</span><h3>Bebidas Plant-Based</h3></div>
          <div class="items-list">
            <div class="item-row"><div class="item-info"><span class="item-emoji">🥛</span><div><div class="item-name">Latte de Avena</div><div class="item-desc">Espresso · leche de avena vaporizada</div></div></div><div class="item-price">$50 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🌰</span><div><div class="item-name">Latte de Almendra</div><div class="item-desc">Espresso · leche de almendra · canela</div></div></div><div class="item-price">$50 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🍵</span><div><div class="item-name">Matcha Vegano</div><div class="item-desc">Matcha japonés · leche de coco</div></div></div><div class="item-price">$55 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🫐</span><div><div class="item-name">Smoothie Bowl</div><div class="item-desc">Açaí · plátano · leche vegetal · semillas</div></div></div><div class="item-price">$60 MXN</div></div>
            <div class="item-row"><div class="item-info"><span class="item-emoji">🍊</span><div><div class="item-name">Jugo Natural Verde</div><div class="item-desc">Apio · pepino · manzana · limón · jengibre</div></div></div><div class="item-price">$42 MXN</div></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<!-- ===== ACERCA DE NOSOTROS ===== -->
<div id="page-nosotros" class="page-section">
  <section class="section">
    <h2 class="section-title">Acerca de <span class="accent">Nosotros</span></h2>
    <div class="gold-line"></div>
    <div class="about-content">
      <p>Dream Coffee es una cafetería creada con la idea de ofrecer un lugar agradable donde las personas puedan disfrutar de una buena taza de café y pasar un momento agradable. Nuestro objetivo es brindar productos de calidad elaborados con ingredientes seleccionados y preparados con dedicación.</p>
      <p>En Dream Coffee buscamos crear un ambiente cómodo y relajado para que nuestros clientes puedan reunirse con amigos, estudiar o simplemente disfrutar de su bebida favorita. Además del café, ofrecemos diferentes postres y snacks que complementan perfectamente cada bebida.</p>
      <p>Nuestro nombre nace de ese sueño compartido: un lugar donde cada visita se convierta en un recuerdo especial. Inspirados en la armonía entre el café, la música y las relaciones humanas, buscamos que cada cliente se sienta en casa desde el primer sorbo.</p>
      <p>Contamos con un área de entretenimiento única en la zona, donde puedes jugar, ver tu serie favorita o relajarte con una partida de ajedrez mientras disfrutas de tu bebida. Creemos que la experiencia completa es lo que nos hace diferentes.</p>
      <p>Nos encontramos en Airon, 22925 Nuevo Centro de Población Padre Kino, B.C., abiertos de lunes a sábado de 7:00 a.m. a 5:00 p.m. Te esperamos con los brazos abiertos y un café recién preparado.</p>
      <p>¿Tienes alguna duda o quieres conocer más? Escríbenos a <strong style="color:var(--gold)">dreamcoffee929@gmail.com</strong> o llámanos al <strong style="color:var(--gold)">616 166 60 60</strong>. Con gusto te atendemos.</p>
    </div>
  </section>
</div>

<!-- ===== CONTACTO ===== -->
<div id="page-contacto" class="page-section">
  <section class="section">
    <h2 class="section-title">📬 <span class="accent">Contacto</span></h2>
    <div class="gold-line"></div>
    <div class="contact-grid">
      <div class="contact-info">
        <h3>Encuéntranos</h3>
        <div class="contact-item"><span class="icon">📍</span><div class="text"><strong>Dirección</strong>Airon, 22925 Nuevo Centro de Población Padre Kino, B.C.</div></div>
        <div class="contact-item"><span class="icon">📞</span><div class="text"><strong>Teléfono de Atención</strong>616 166 60 60</div></div>
        <div class="contact-item"><span class="icon">📧</span><div class="text"><strong>Correo Electrónico</strong>dreamcoffee929@gmail.com</div></div>
        <div class="contact-item"><span class="icon">🕐</span><div class="text"><strong>Horario de Atención</strong>Lunes a Sábado · 7:00 a.m. – 5:00 p.m.<br>Domingos: Cerrado</div></div>
        <div class="social-links">
          <a href="https://www.facebook.com/groups/1281355040243584" target="_blank" class="social-link" title="Facebook">📘</a>
          <a href="https://www.instagram.com/dreamcoffee929/" target="_blank" class="social-link" title="Instagram">📸</a>
          <a href="https://twitter.com/dreamcoffee929" target="_blank" class="social-link" title="Twitter / X">🐦</a>
          <a href="https://wa.me/526161666060" target="_blank" class="social-link" title="WhatsApp">💬</a>
        </div>
      </div>
      <div>
        <h3 style="font-family:'Playfair Display',serif;color:var(--gold);font-size:1.5rem;margin-bottom:24px;">Formulario de Contacto</h3>
        <div class="form-group"><label>Nombre</label><input type="text" placeholder="Tu nombre completo"></div>
        <div class="form-group"><label>Correo Electrónico <span class="form-required">*</span></label><input type="email" placeholder="tu@correo.com"></div>
        <div class="form-group"><label>Mensaje <span class="form-required">*</span></label><textarea placeholder="Escribe tu mensaje aquí..."></textarea></div>
        <button class="btn-primary" onclick="alert('¡Mensaje enviado! Te contactaremos pronto ☕')">Enviar Mensaje</button>
      </div>
    </div>
  </section>
</div>

<!-- ===== FAQ ===== -->
<div id="page-faq" class="page-section">
  <section class="section">
    <h2 class="section-title">❓ Preguntas <span class="accent">Frecuentes</span></h2>
    <div class="gold-line"></div>
    <div class="faq-list">
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Cuál es el horario de atención? <span class="faq-icon">+</span></button>
        <div class="faq-a">Nuestro horario de atención es de lunes a sábado de 7:00 a.m. a 5:00 p.m. Los domingos permanecemos cerrados para labores de mantenimiento y preparación.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Qué métodos de pago aceptan? <span class="faq-icon">+</span></button>
        <div class="faq-a">Aceptamos pagos en efectivo, tarjetas de débito y crédito. Para pedidos a domicilio también aceptamos los mismos métodos al momento de la entrega.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Ofrecen pedidos para llevar? <span class="faq-icon">+</span></button>
        <div class="faq-a">Sí, todos nuestros productos pueden pedirse para llevar. Utilizamos empaques especiales para garantizar que tu bebida o postre llegue en perfectas condiciones.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Tienen promociones especiales? <span class="faq-icon">+</span></button>
        <div class="faq-a">Sí, constantemente publicamos promociones en nuestras redes sociales (Instagram y Facebook). También tenemos oferta especial: postre gratis para parejas enamoradas y el postre del día con precio especial.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Ofrecen servicio a domicilio? <span class="faq-icon">+</span></button>
        <div class="faq-a">Sí, contamos con servicio a domicilio dentro de la zona cercana a la cafetería. Tenemos dos modalidades: Express ($20 MXN adicional) y Básico (sin costo adicional). Puedes consultar si tu dirección está disponible en la sección de Delivery.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Puedo reservar el área de entretenimiento? <span class="faq-icon">+</span></button>
        <div class="faq-a">Por el momento el área de entretenimiento funciona por orden de llegada. Te recomendamos llegar temprano, especialmente los fines de semana. Puedes llamarnos al 616 166 60 60 para consultar disponibilidad.</div>
      </div>
      <div class="faq-item">
        <button class="faq-q" onclick="toggleFaq(this)">¿Cómo puedo hacer una reclamación? <span class="faq-icon">+</span></button>
        <div class="faq-a">Puedes enviarnos un correo a dreamcoffee929@gmail.com indicando tu nombre, el producto o servicio adquirido y el motivo de tu reclamación. También puedes llamarnos directamente al 616 166 60 60.</div>
      </div>
    </div>
  </section>
</div>

<!-- ===== MAPA DE SITIO ===== -->
<div id="page-sitemap" class="page-section">
  <section class="section">
    <h2 class="section-title">🗺️ Mapa de <span class="accent">Sitio</span></h2>
    <div class="gold-line"></div>
    <div class="sitemap-grid">
      <div class="sitemap-col">
        <h4>🍰 Comida</h4>
        <ul>
          <li><a href="#" onclick="showPage('comida')">Postres Dulces</a></li>
          <li><a href="#" onclick="showPage('comida')">Postres Salados</a></li>
          <li><a href="#" onclick="showPage('comida')">Bebidas Calientes</a></li>
          <li><a href="#" onclick="showPage('comida')">Bebidas Frías</a></li>
        </ul>
      </div>
      <div class="sitemap-col">
        <h4>🎮 Entretenimiento</h4>
        <ul>
          <li><a href="#" onclick="showPage('entretenimiento')">Juegos de Mesa</a></li>
          <li><a href="#" onclick="showPage('entretenimiento')">Juegos Didácticos</a></li>
          <li><a href="#" onclick="showPage('entretenimiento')">Videojuegos</a></li>
          <li><a href="#" onclick="showPage('entretenimiento')">Streaming</a></li>
        </ul>
      </div>
      <div class="sitemap-col">
        <h4>🛵 Entrega a Domicilio</h4>
        <ul>
          <li><a href="#" onclick="showPage('delivery')">¿Mi dirección disponible?</a></li>
          <li><a href="#" onclick="showPage('delivery')">Plazo de entrega</a></li>
          <li><a href="#" onclick="showPage('delivery')">Servicio Express</a></li>
          <li><a href="#" onclick="showPage('delivery')">Servicio Básico</a></li>
        </ul>
      </div>
      <div class="sitemap-col">
        <h4>🌮 Snacks & Rápida</h4>
        <ul>
          <li><a href="#" onclick="showPage('snacks')">Antojitos Mexicanos</a></li>
          <li><a href="#" onclick="showPage('snacks')">Bocadillos Internacionales</a></li>
          <li><a href="#" onclick="showPage('snacks')">Opciones Veganas</a></li>
          <li><a href="#" onclick="showPage('snacks')">Bebidas Plant-Based</a></li>
        </ul>
      </div>
      <div class="sitemap-col">
        <h4>ℹ️ Información</h4>
        <ul>
          <li><a href="#" onclick="showPage('nosotros')">Acerca de Nosotros</a></li>
          <li><a href="#" onclick="showPage('contacto')">Contacto</a></li>
          <li><a href="#" onclick="showPage('faq')">Preguntas Frecuentes</a></li>
          <li><a href="#" onclick="showPage('sitemap')">Mapa de Sitio</a></li>
        </ul>
      </div>
      <div class="sitemap-col">
        <h4>📋 Legal</h4>
        <ul>
          <li><a href="#" onclick="showPage('cookies')">Política de Cookies</a></li>
          <li><a href="#" onclick="showPage('privacidad')">Política de Privacidad</a></li>
          <li><a href="#" onclick="showPage('terminos')">Términos y Condiciones</a></li>
        </ul>
      </div>
    </div>
  </section>
</div>

<!-- ===== POLÍTICA DE COOKIES ===== -->
<div id="page-cookies" class="page-section">
  <section class="section">
    <h2 class="section-title">🍪 Política de <span class="accent">Cookies</span></h2>
    <div class="gold-line"></div>
    <div class="policy-content">
      <p>Si quieres saber más sobre el uso de cookies que realiza este sitio web Dream Coffee estás en el lugar indicado. A continuación, vamos a explicarte qué son exactamente las cookies; qué tipo de cookies utilizamos y para qué; y cómo puedes ejercer tu derecho para configurar tu navegador y desestimar el uso de cualquiera de ellas.</p>
      <h3>¿Qué es una cookie?</h3>
      <p>Una cookie es un fichero que se descarga en tu ordenador al acceder a determinadas páginas web o blogs. Las cookies permiten a esa página, entre otras cosas, almacenar y recuperar información sobre tus hábitos de navegación o de tu equipo, y dependiendo de la información que contengan y de la forma en que utilices tu equipo, pueden utilizarse para reconocerte.</p>
      <h3>Tipos de cookies que utilizamos</h3>
      <ul>
        <li><strong>Cookies técnicas:</strong> Permiten la navegación y el uso de las diferentes opciones del sitio, como el carrito de compras o la sesión de usuario.</li>
        <li><strong>Cookies de personalización:</strong> Permiten acceder al servicio con características predefinidas como el idioma o la configuración regional.</li>
        <li><strong>Cookies de análisis:</strong> Nos permiten cuantificar el número de usuarios y analizar estadísticamente el uso del servicio para mejorarlo.</li>
        <li><strong>Cookies publicitarias:</strong> Permiten gestionar los espacios publicitarios del sitio web adecuando el contenido al uso que realizas.</li>
        <li><strong>Cookies de publicidad comportamental:</strong> Almacenan información del comportamiento del usuario para mostrar publicidad personalizada.</li>
        <li><strong>Cookies de terceros:</strong> Este sitio utiliza Google Analytics para fines estadísticos y de mejora del servicio.</li>
      </ul>
      <h3>Gestionar y rechazar el uso de cookies</h3>
      <p>En cualquier momento puedes adaptar la configuración del navegador para gestionar, desestimar el uso de cookies y ser notificado antes de que se descarguen. Puedes configurar tu navegador para rechazar todas las cookies o únicamente las cookies de terceros.</p>
    </div>
  </section>
</div>

<!-- ===== POLÍTICA DE PRIVACIDAD ===== -->
<div id="page-privacidad" class="page-section">
  <section class="section">
    <h2 class="section-title">🔒 Política de <span class="accent">Privacidad</span></h2>
    <div class="gold-line"></div>
    <div class="policy-content">
      <p>La presente Política de Privacidad establece los términos en que Dream Coffee usa y protege la información proporcionada por sus usuarios al momento de utilizar su sitio web. Esta empresa está comprometida con la seguridad de los datos de sus usuarios.</p>
      <h3>Información que recogemos</h3>
      <p>Nuestro sitio web podrá recoger información personal como: nombre, información de contacto como su dirección de correo electrónico e información demográfica. Así mismo cuando sea necesario podrá ser requerida información específica para procesar algún pedido o realizar una entrega o facturación.</p>
      <h3>Uso de la información recogida</h3>
      <p>Nuestro sitio web emplea la información con el fin de proporcionar el mejor servicio posible, particularmente para mantener un registro de usuarios, de pedidos en caso que aplique, y mejorar nuestros productos y servicios.</p>
      <h3>Control de su información personal</h3>
      <p>En cualquier momento usted puede restringir la recopilación o el uso de la información personal que es proporcionada a nuestro sitio web. Esta página no venderá, cederá ni distribuirá la información personal que es recopilada sin su consentimiento, salvo que sea requerido por un juez con una orden judicial.</p>
      <h3>Seguridad</h3>
      <p>Dream Coffee está altamente comprometido para cumplir con el compromiso de mantener su información segura. Usamos los sistemas más avanzados y los actualizamos constantemente para asegurarnos que no exista ningún acceso no autorizado. La comunicación entre los usuarios y Dream Coffee utiliza un canal seguro con protocolos HTTPS.</p>
    </div>
  </section>
</div>

<!-- ===== TÉRMINOS Y CONDICIONES ===== -->
<div id="page-terminos" class="page-section">
  <section class="section">
    <h2 class="section-title">📜 Términos y <span class="accent">Condiciones</span></h2>
    <div class="gold-line"></div>
    <div class="policy-content">
      <h3>1. Proemio</h3>
      <p>Al ingresar y utilizar este portal de Internet, Dream Coffee, el usuario está aceptando los Términos y condiciones de uso contenidos en este convenio y declara expresamente su aceptación utilizando para tal efecto medios electrónicos.</p>
      <h3>2. Licencia</h3>
      <p>Dream Coffee otorga y concede al usuario el derecho no exclusivo, revocable y no transferible de ver y utilizar el sitio web Dream Coffee de conformidad con los Términos y condiciones de uso aquí estipulados.</p>
      <h3>3. Reglas de uso</h3>
      <p>El usuario reconoce y acepta que la información publicada o contenida en dicho sitio será claramente identificada. Queda prohibido el uso del sitio con fines ilícitos o lesivos que puedan causar perjuicio al normal funcionamiento del mismo.</p>
      <h3>4. Devoluciones</h3>
      <ul>
        <li>Productos en mal estado → Reposición sin costo</li>
        <li>Defectos de preparación → Reposición sin costo</li>
        <li>Empaque de contenido no correspondiente → Reposición sin costo</li>
        <li>Material no correspondiente al pedido → Reposición sin costo</li>
      </ul>
      <h3>5. Contacto Legal</h3>
      <p>Para cualquier asunto legal o reclamación, comuníquese a: <strong style="color:var(--gold)">dreamcoffee929@gmail.com</strong></p>
    </div>
  </section>
</div>

<!-- ===== FOOTER ===== -->
<footer>
  <div class="footer-grid">
    <div class="footer-col">
      <h4>☕ Dream Coffee</h4>
      <p>Un espacio soñado donde el café, el entretenimiento y la calidez se fusionan para crear momentos inolvidables.</p>
      <div class="footer-social">
        <a href="https://www.facebook.com/groups/1281355040243584" target="_blank" title="Facebook">📘</a>
        <a href="https://www.instagram.com/dreamcoffee929/" target="_blank" title="Instagram">📸</a>
        <a href="https://twitter.com/dreamcoffee929" target="_blank" title="Twitter">🐦</a>
        <a href="https://wa.me/526161666060" target="_blank" title="WhatsApp">💬</a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Información</h4>
      <ul>
        <li><a href="#" onclick="showPage('nosotros')">Acerca de Nosotros</a></li>
        <li><a href="#" onclick="showPage('cookies')">Políticas de Cookies</a></li>
        <li><a href="#" onclick="showPage('privacidad')">Políticas de Privacidad</a></li>
        <li><a href="#" onclick="showPage('terminos')">Términos y Condiciones</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contactos</h4>
      <ul>
        <li><a href="#" onclick="showPage('contacto')">Formulario de Contactos</a></li>
        <li><a href="#" onclick="showPage('faq')">Preguntas Frecuentes</a></li>
        <li><a href="#" onclick="showPage('sitemap')">Mapa de Sitio</a></li>
        <li><a href="mailto:dreamcoffee929@gmail.com">dreamcoffee929@gmail.com</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Nuestros Servicios</h4>
      <ul>
        <li><a href="#" onclick="showPage('comida')">Comida & Postres</a></li>
        <li><a href="#" onclick="showPage('entretenimiento')">Entretenimiento</a></li>
        <li><a href="#" onclick="showPage('delivery')">Delivery</a></li>
        <li><a href="#" onclick="showPage('snacks')">Snacks & Rápida</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2026 Dream Coffee · Airon, 22925 Nuevo Centro de Población Padre Kino, B.C.</p>
    <p class="phone">📞 <a href="tel:6161666060" style="color:var(--gold);text-decoration:none;">Llámanos al 616 166 60 60</a></p>
    <p>Lun – Sáb · 7:00 a.m. – 5:00 p.m.</p>
  </div>
</footer>

<!-- LOGIN MODAL -->
<div id="modal-overlay" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,0.8);z-index:2000;display:none;align-items:center;justify-content:center;">
  <div style="background:var(--charcoal);border:1px solid var(--gold);padding:40px;max-width:400px;width:90%;border-radius:2px;position:relative;">
    <button onclick="closeModal()" style="position:absolute;top:16px;right:16px;background:none;border:none;color:var(--blush);font-size:1.5rem;cursor:pointer;">✕</button>
    <h2 id="modal-title" style="font-family:'Playfair Display',serif;color:var(--gold);margin-bottom:24px;font-size:1.5rem;">Iniciar Sesión</h2>
    <div class="form-group"><label>Correo Electrónico</label><input type="email" placeholder="tu@correo.com"></div>
    <div class="form-group"><label>Contraseña</label><input type="password" placeholder="••••••••"></div>
    <button class="btn-primary" style="width:100%;text-align:center;margin-top:8px;" onclick="closeModal()">Entrar</button>
  </div>
</div>

<script>
  // Page navigation
  function showPage(id) {
    document.querySelectorAll('.page-section').forEach(el => el.classList.remove('active'));
    const target = document.getElementById('page-' + id);
    if(target) { target.classList.add('active'); window.scrollTo(0, 0); }
    // Update nav active state
    document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
  }

  // Sub-department tabs
  function switchSub(btn, id) {
    const parent = btn.closest('.page-section');
    parent.querySelectorAll('.dept-btn').forEach(b => b.classList.remove('active'));
    parent.querySelectorAll('.dept-panel').forEach(p => p.classList.remove('active'));
    btn.classList.add('active');
    const panel = document.getElementById('sub-' + id);
    if(panel) panel.classList.add('active');
  }

  // FAQ toggle
  function toggleFaq(btn) {
    const answer = btn.nextElementSibling;
    const isOpen = answer.classList.contains('open');
    document.querySelectorAll('.faq-a').forEach(a => a.classList.remove('open'));
    document.querySelectorAll('.faq-q').forEach(q => q.classList.remove('open'));
    if(!isOpen) { answer.classList.add('open'); btn.classList.add('open'); }
  }

  // Cookie banner
  function closeCookie() { document.getElementById('cookie-banner').style.display = 'none'; }

  // Modal
  function showModal(type) {
    const overlay = document.getElementById('modal-overlay');
    const title = document.getElementById('modal-title');
    title.textContent = type === 'login' ? 'Iniciar Sesión' : 'Crear Cuenta';
    overlay.style.display = 'flex';
    return false;
  }
  function closeModal() { document.getElementById('modal-overlay').style.display = 'none'; }
  document.getElementById('modal-overlay').addEventListener('click', function(e) {
    if(e.target === this) closeModal();
  });

  // Prevent default on all anchor clicks that use onclick
  document.querySelectorAll('a[onclick]').forEach(a => {
    a.addEventListener('click', e => e.preventDefault());
  });
</script>
</body>
</html>
