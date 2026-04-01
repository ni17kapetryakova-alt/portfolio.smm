<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ника — СММ специалист</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700;900&display=swap');

  *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --black: #0a0a0a;
    --white: #fff;
    --gray1: #111;
    --gray2: #1a1a1a;
    --gray3: #333;
    --gray4: #555;
    --gray5: #888;
    --accent: #fff;
  }

  html { scroll-behavior: smooth; }
  body { background: var(--black); color: var(--white); font-family: 'Inter', sans-serif; overflow-x: hidden; }

  a { color: inherit; text-decoration: none; }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    background: rgba(10,10,10,0.92); backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--gray2);
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 40px; height: 56px;
  }
  .nav-logo { font-size: 13px; font-weight: 900; letter-spacing: 2px; text-transform: uppercase; }
  .nav-links { display: flex; gap: 32px; }
  .nav-links a { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: var(--gray5); transition: color 0.2s; }
  .nav-links a:hover { color: var(--white); }
  .nav-cta { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; border: 1.5px solid var(--gray3); padding: 8px 16px; transition: border-color 0.2s; }
  .nav-cta:hover { border-color: var(--white); }
  .burger { display: none; flex-direction: column; gap: 5px; cursor: pointer; }
  .burger span { display: block; width: 22px; height: 2px; background: var(--white); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh; padding-top: 56px;
    display: grid; grid-template-columns: 1fr 1fr;
    background: #000;
  }
  .hero-photo {
    position: relative; overflow: hidden;
  }
  .hero-photo img { width: 100%; height: 100%; object-fit: cover; object-position: top center; display: block; }
  .hero-photo::after {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(to right, transparent 60%, #000 100%);
  }
  .hero-content {
    display: flex; flex-direction: column; justify-content: center;
    padding: 80px 60px 80px 40px;
  }
  .hero-badge { font-size: 10px; font-weight: 700; letter-spacing: 3px; text-transform: uppercase; color: var(--gray5); margin-bottom: 24px; }
  .hero-title { font-size: clamp(52px, 7vw, 96px); font-weight: 900; text-transform: uppercase; line-height: 0.9; letter-spacing: -3px; margin-bottom: 24px; }
  .hero-title span { display: block; font-size: clamp(28px, 4vw, 52px); letter-spacing: -1px; }
  .hero-sub { font-size: 15px; color: var(--gray5); line-height: 1.6; max-width: 340px; margin-bottom: 40px; }
  .hero-btn {
    display: inline-block; padding: 16px 32px;
    background: var(--white); color: var(--black);
    font-size: 11px; font-weight: 900; letter-spacing: 3px; text-transform: uppercase;
    transition: background 0.2s;
  }
  .hero-btn:hover { background: #e0e0e0; }
  .hero-stats { display: flex; gap: 32px; margin-top: 48px; padding-top: 32px; border-top: 1px solid var(--gray2); }
  .stat-num { font-size: 28px; font-weight: 900; letter-spacing: -1px; }
  .stat-label { font-size: 11px; color: var(--gray5); margin-top: 2px; line-height: 1.4; }

  /* ── SECTIONS ── */
  section { padding: 80px 40px; max-width: 1080px; margin: 0 auto; }
  .section-label { font-size: 10px; font-weight: 700; letter-spacing: 3px; text-transform: uppercase; color: var(--gray4); margin-bottom: 20px; }
  .section-title { font-size: clamp(36px, 6vw, 72px); font-weight: 900; text-transform: uppercase; letter-spacing: -2px; line-height: 0.95; margin-bottom: 32px; }
  .section-divider { height: 1px; background: var(--gray2); margin: 0 40px; }

  /* ── ABOUT ── */
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: start; }
  .about-text { font-size: 15px; color: var(--gray5); line-height: 1.7; }
  .about-text strong { color: var(--white); font-weight: 700; }
  .services-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2px; background: var(--gray2); margin-top: 0; }
  .service-item { background: var(--black); padding: 24px; }
  .service-name { font-size: 12px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 8px; }
  .service-desc { font-size: 12px; color: var(--gray5); line-height: 1.5; }

  /* ── PORTFOLIO ── */
  .portfolio-section { padding: 80px 40px; max-width: 1080px; margin: 0 auto; }
  .cases { display: flex; flex-direction: column; gap: 2px; }
  .case-item {
    display: grid; grid-template-columns: 1fr auto;
    align-items: center; padding: 20px 24px;
    background: var(--gray1); border: 1px solid var(--gray2);
    transition: background 0.2s; cursor: pointer;
  }
  .case-item:hover { background: var(--gray2); }
  .case-num { font-size: 10px; font-weight: 700; letter-spacing: 2px; color: var(--gray4); margin-bottom: 6px; }
  .case-title { font-size: 14px; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; }
  .case-sub { font-size: 12px; color: var(--gray5); margin-top: 3px; }
  .case-arrow { font-size: 18px; color: var(--gray4); }

  /* ── CASE PAGES ── */
  .case-page { display: none; }
  .case-page.active { display: block; }
  .case-hero { background: var(--gray1); padding: 60px 40px; border-bottom: 1px solid var(--gray2); max-width: 100%; }
  .case-hero-inner { max-width: 1080px; margin: 0 auto; }
  .case-back { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: var(--gray5); cursor: pointer; margin-bottom: 32px; display: inline-flex; align-items: center; gap: 8px; transition: color 0.2s; }
  .case-back:hover { color: var(--white); }
  .case-client { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: var(--gray4); margin-bottom: 12px; }
  .case-h1 { font-size: clamp(32px, 5vw, 64px); font-weight: 900; text-transform: uppercase; letter-spacing: -2px; line-height: 0.95; margin-bottom: 16px; }
  .case-tagline { font-size: 14px; color: var(--gray5); }

  .case-body { max-width: 1080px; margin: 0 auto; padding: 60px 40px; }
  .case-cols { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; margin-bottom: 48px; }
  .case-block-title { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: var(--gray4); margin-bottom: 12px; padding-bottom: 8px; border-bottom: 1px solid var(--gray2); }
  .case-text { font-size: 14px; color: var(--gray5); line-height: 1.7; }
  .case-list { list-style: none; display: flex; flex-direction: column; gap: 8px; }
  .case-list li { font-size: 14px; color: var(--gray5); line-height: 1.5; display: flex; align-items: flex-start; gap: 8px; }
  .case-list li::before { content: '—'; opacity: 0.4; flex-shrink: 0; }

  .results-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 2px; background: var(--gray2); margin-bottom: 48px; }
  .result-item { background: var(--black); padding: 24px; }
  .result-num { font-size: 32px; font-weight: 900; letter-spacing: -1px; margin-bottom: 4px; }
  .result-label { font-size: 12px; color: var(--gray5); line-height: 1.4; }

  .platform-section { margin-bottom: 48px; }
  .platform-title { font-size: 20px; font-weight: 900; text-transform: uppercase; letter-spacing: -0.5px; margin-bottom: 20px; padding-bottom: 12px; border-bottom: 1px solid var(--gray2); }

  /* ── PRICES ── */
  .prices-section { padding: 80px 40px; max-width: 1080px; margin: 0 auto; }
  .packages { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 2px; background: var(--gray2); }
  .package { background: var(--black); padding: 34px 28px; position: relative; }
  .package.featured { background: var(--white); color: var(--black); }
  .pkg-tag { font-size: 10px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: var(--gray4); margin-bottom: 10px; }
  .package.featured .pkg-tag { color: #999; }
  .pkg-name { font-size: 26px; font-weight: 900; text-transform: uppercase; letter-spacing: -1px; margin-bottom: 4px; }
  .pkg-sub { font-size: 12px; color: var(--gray5); margin-bottom: 20px; }
  .package.featured .pkg-sub { color: #888; }
  .pkg-price { font-size: 38px; font-weight: 900; letter-spacing: -2px; line-height: 1; margin-bottom: 6px; }
  .pkg-price em { font-size: 14px; font-weight: 400; font-style: normal; opacity: 0.4; }
  .pkg-desc { font-size: 12px; opacity: 0.45; margin-bottom: 24px; line-height: 1.5; }
  .pkg-divider { height: 1px; background: var(--gray2); margin-bottom: 20px; }
  .package.featured .pkg-divider { background: #ddd; }
  .pkg-features { list-style: none; display: flex; flex-direction: column; gap: 10px; margin-bottom: 28px; }
  .pkg-features li { font-size: 13px; line-height: 1.4; display: flex; gap: 8px; }
  .pkg-features li::before { content: '—'; opacity: 0.3; flex-shrink: 0; }
  .pkg-btn { display: block; width: 100%; padding: 14px; text-align: center; font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; border: 1.5px solid var(--gray3); color: var(--white); background: transparent; cursor: pointer; transition: border-color 0.2s; }
  .pkg-btn:hover { border-color: var(--white); }
  .package.featured .pkg-btn { background: #000; color: #fff; border-color: #000; }
  .pkg-badge { position: absolute; top: 18px; right: 18px; background: #000; color: #fff; font-size: 9px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; padding: 5px 9px; }

  .addons { display: grid; grid-template-columns: repeat(auto-fit, minmax(155px, 1fr)); gap: 2px; background: var(--gray2); margin-top: 2px; }
  .addon { background: var(--black); padding: 20px 22px; }
  .addon-name { font-size: 12px; color: var(--gray5); margin-bottom: 6px; }
  .addon-price { font-size: 18px; font-weight: 900; letter-spacing: -0.5px; }
  .addon-price em { font-size: 11px; font-weight: 400; font-style: normal; opacity: 0.4; }

  .notes { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 0; margin-top: 32px; }
  .note { border-left: 2px solid var(--gray2); padding: 14px 18px; }
  .note-title { font-size: 10px; font-weight: 700; letter-spacing: 1.5px; text-transform: uppercase; color: var(--gray4); margin-bottom: 6px; }
  .note-text { font-size: 12px; color: var(--gray5); line-height: 1.5; }

  /* ── CONTACTS / CTA ── */
  .cta-section { background: var(--white); color: var(--black); padding: 80px 40px; text-align: center; }
  .cta-title { font-size: clamp(40px, 8vw, 80px); font-weight: 900; text-transform: uppercase; letter-spacing: -3px; line-height: 0.9; margin-bottom: 16px; }
  .cta-sub { font-size: 14px; color: #777; margin-bottom: 36px; }
  .cta-links { display: flex; justify-content: center; gap: 28px; flex-wrap: wrap; }
  .cta-link { font-size: 11px; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: #000; border-bottom: 1.5px solid #000; padding-bottom: 2px; transition: opacity 0.2s; }
  .cta-link:hover { opacity: 0.4; }

  /* ── FOOTER ── */
  footer { background: #000; padding: 24px 40px; display: flex; justify-content: space-between; align-items: center; border-top: 1px solid var(--gray2); }
  .footer-logo { font-size: 12px; font-weight: 900; letter-spacing: 2px; text-transform: uppercase; }
  .footer-copy { font-size: 11px; color: var(--gray4); }

  /* ── MOBILE ── */
  @media (max-width: 768px) {
    nav { padding: 0 20px; }
    .nav-links { display: none; }
    .nav-cta { display: none; }
    .burger { display: flex; }

    .hero { grid-template-columns: 1fr; min-height: auto; }
    .hero-photo { height: 55vw; max-height: 340px; }
    .hero-photo::after { background: linear-gradient(to bottom, transparent 60%, #000 100%); }
    .hero-content { padding: 32px 20px 60px; }
    .hero-stats { gap: 20px; flex-wrap: wrap; }
    .hero-title { letter-spacing: -2px; }

    section, .portfolio-section, .prices-section { padding: 60px 20px; }
    .section-divider { margin: 0 20px; }

    .about-grid { grid-template-columns: 1fr; gap: 32px; }
    .case-cols { grid-template-columns: 1fr; gap: 32px; }
    .case-body { padding: 40px 20px; }
    .case-hero { padding: 40px 20px; }

    .packages { grid-template-columns: 1fr; }
    .addons { grid-template-columns: repeat(2, 1fr); }
    .notes { grid-template-columns: 1fr 1fr; }

    footer { flex-direction: column; gap: 8px; text-align: center; padding: 20px; }
    .cta-section { padding: 60px 20px; }
  }

  @media (max-width: 480px) {
    .addons { grid-template-columns: 1fr; }
    .notes { grid-template-columns: 1fr; }
    .results-grid { grid-template-columns: repeat(2, 1fr); }
    .services-grid { grid-template-columns: 1fr; }
  }

  /* mobile nav open */
  .nav-open .nav-links {
    display: flex; flex-direction: column; position: fixed;
    top: 56px; left: 0; right: 0; background: #000;
    padding: 24px; gap: 20px; border-bottom: 1px solid var(--gray2);
  }
  .nav-open .nav-links a { font-size: 14px; }
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <div class="nav-logo">Ника · СММ</div>
  <div class="nav-links">
    <a href="#about">Обо мне</a>
    <a href="#portfolio">Портфолио</a>
    <a href="#prices">Прайс</a>
    <a href="#contacts">Контакты</a>
  </div>
  <a href="https://t.me/vrnk_sss" class="nav-cta">Связаться</a>
  <div class="burger" onclick="toggleNav()"><span></span><span></span><span></span></div>
</nav>

<!-- MAIN PAGE -->
<div id="main-page">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-photo">
      <!-- Замени src на свою фотографию -->
      <div style="width:100%;height:100%;background:linear-gradient(135deg,#1a1a1a 0%,#0a0a0a 100%);display:flex;align-items:center;justify-content:center;">
        <span style="font-size:13px;color:#333;letter-spacing:2px;text-transform:uppercase;">[https://ibb.co/Fkb6FGzH]</span>
      </div>
    </div>
    <div class="hero-content">
      
      <div class="hero-badge">СММ специалист · @vrnk.sss</div>
      <div class="hero-title">
        СММ
        <span>Специалист</span>
      </div>
      <div class="hero-sub">Привлекаю клиентов через Reels и контент-стратегии. Без слива бюджета на рекламу.</div>
      <a href="https://t.me/vrnk_sss" class="hero-btn">Связаться →</a>
      <div class="hero-stats">
        <div><div class="stat-num">2+</div><div class="stat-label">года опыта в SMM</div></div>
        <div><div class="stat-num">3</div><div class="stat-label">успешных кейса</div></div>
        <div><div class="stat-num">×32</div><div class="stat-label">рост охватов</div></div>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="section-divider"></div>
  <section id="about">
    <div class="section-label">Обо мне</div>
    <div class="about-grid">
      <div>
        <div class="section-title">Как я<br>помогаю</div>
        <div class="about-text">
          Привет! Я Ника, профессиональный маркетолог социальных сетей с опытом работы <strong>более 2 лет.</strong> Помогаю бизнесу эффективно продвигаться в социальных сетях, создавая контент и стратегии, которые привлекают клиентов и увеличивают продажи.
        </div>
      </div>
      <div class="services-grid">
        <div class="service-item">
          <div class="service-name">Стратегия</div>
          <div class="service-desc">Разработка эффективной стратегии для продвижения проекта в соц. сетях</div>
        </div>
        <div class="service-item">
          <div class="service-name">Контент</div>
          <div class="service-desc">Съёмка, монтаж (сторис, рилс, лента), план постинга, разработка дизайна</div>
        </div>
        <div class="service-item">
          <div class="service-name">Сопровождение</div>
          <div class="service-desc">Упаковка аккаунта, план продвижения, контент-план, автоворонка и настройка чат-ботов</div>
        </div>
        <div class="service-item">
          <div class="service-name">Продвижение</div>
          <div class="service-desc">Органическое продвижение через короткие ролики + таргет ВК (если нужен быстрый рост)</div>
        </div>
      </div>
    </div>
  </section>

  <!-- PORTFOLIO -->
  <div class="section-divider"></div>
  <section id="portfolio" class="portfolio-section">
    <div class="section-label">Портфолио</div>
    <div class="section-title">Кейсы</div>
    <div class="cases">
      <div class="case-item" onclick="openCase('case1')">
        <div>
          <div class="case-num">Кейс №1</div>
          <div class="case-title">Инфобизнес / Эксперты / Онлайн-образование</div>
          <div class="case-sub">Степан Некипелов — эксперт по продажам</div>
        </div>
        <div class="case-arrow">→</div>
      </div>
      <div class="case-item" onclick="openCase('case2')">
        <div>
          <div class="case-num">Кейс №2</div>
          <div class="case-title">Автобизнес / Интернет-торговля</div>
          <div class="case-sub">Car Please — импорт автомобилей из Азии</div>
        </div>
        <div class="case-arrow">→</div>
      </div>
      <div class="case-item" onclick="openCase('case3')">
        <div>
          <div class="case-num">Кейс №3</div>
          <div class="case-title">Корпоративная культура / Привлечение сотрудников</div>
          <div class="case-sub">ООО ПО «Трубное Решение» — HR-брендинг</div>
        </div>
        <div class="case-arrow">→</div>
      </div>
    </div>
  </section>

  <!-- PRICES -->
  <div class="section-divider"></div>
  <section id="prices" class="prices-section">
    <div class="section-label">Стоимость</div>
    <div class="section-title">Прайс</div>
    <div class="packages">
      <div class="package">
        <div class="pkg-tag">Пакет 01</div>
        <div class="pkg-name">Малый</div>
        <div class="pkg-sub">для малого бизнеса</div>
        <div class="pkg-price">20 000 <em>₽/мес</em></div>
        <div class="pkg-desc">1 платформа. Первые результаты без большого бюджета.</div>
        <div class="pkg-divider"></div>
        <ul class="pkg-features">
          <li>Контент-стратегия + анализ ЦА</li>
          <li>Ведение 1 платформы (Instagram или ВК)</li>
          <li>6 постов + сторис в месяц</li>
          <li>2 Reels/видео в месяц</li>
          <li>Оформление профиля</li>
          <li>Ежемесячный отчёт</li>
        </ul>
        <a href="https://t.me/vrnk_sss" class="pkg-btn">Выбрать →</a>
      </div>
      <div class="package featured">
        <div class="pkg-badge">Популярный</div>
        <div class="pkg-tag">Пакет 02</div>
        <div class="pkg-name">Средний</div>
        <div class="pkg-sub">для среднего бизнеса</div>
        <div class="pkg-price">40 000 <em>₽/мес</em></div>
        <div class="pkg-desc">2 платформы. Полное ведение + органический рост.</div>
        <div class="pkg-divider"></div>
        <ul class="pkg-features">
          <li>Контент-стратегия + анализ ЦА по болям</li>
          <li>Ведение 2 платформ (Instagram + Telegram или ВК)</li>
          <li>10 постов + сторис в месяц</li>
          <li>6 Reels/видео в месяц</li>
          <li>Чат-бот для сбора заявок</li>
          <li>Ежемесячный отчёт + созвон</li>
        </ul>
        <a href="https://t.me/vrnk_sss" class="pkg-btn">Выбрать →</a>
      </div>
      <div class="package">
        <div class="pkg-tag">Пакет 03</div>
        <div class="pkg-name">Крупный</div>
        <div class="pkg-sub">для крупного бизнеса</div>
        <div class="pkg-price">70 000 <em>₽/мес</em></div>
        <div class="pkg-desc">3 платформы. Комплексное продвижение с рекламой и воронкой.</div>
        <div class="pkg-divider"></div>
        <ul class="pkg-features">
          <li>Всё из пакета Средний</li>
          <li>3 платформы на выбор</li>
          <li>14 постов + сторис в месяц</li>
          <li>10 Reels/видео в месяц</li>
          <li>Таргетированная реклама ВКонтакте</li>
          <li>Воронка продаж + визуальный стиль</li>
        </ul>
        <a href="https://t.me/vrnk_sss" class="pkg-btn">Выбрать →</a>
      </div>
    </div>
    <div class="addons">
      <div class="addon"><div class="addon-name">Стратегия (разово)</div><div class="addon-price">15 000 <em>₽</em></div></div>
      <div class="addon"><div class="addon-name">Таргет ВК</div><div class="addon-price">от 20 000 <em>₽/мес</em></div></div>
      <div class="addon"><div class="addon-name">Чат-бот + воронка</div><div class="addon-price">от 15 000 <em>₽</em></div></div>
      <div class="addon"><div class="addon-name">1 Reels под ключ</div><div class="addon-price">5 000 <em>₽/шт</em></div></div>
      <div class="addon"><div class="addon-name">Аудит аккаунта</div><div class="addon-price">7 000 <em>₽</em></div></div>
    </div>
    <div class="notes">
      <div class="note"><div class="note-title">Оплата</div><div class="note-text">100% предоплата. Договор на каждый проект.</div></div>
      <div class="note"><div class="note-title">Старт</div><div class="note-text">Через 3–5 дней после оплаты и брифинга.</div></div>
      <div class="note"><div class="note-title">Реклама</div><div class="note-text">Бюджет на рекламу оплачивается клиентом отдельно.</div></div>
      <div class="note"><div class="note-title">Результат</div><div class="note-text">KPI фиксируем на старте. Ежемесячный отчёт.</div></div>
    </div>
  </section>

  <!-- CTA -->
  <div id="contacts" class="cta-section">
    <div class="cta-title">Обсудим<br>проект?</div>
    <div class="cta-sub">Напишите — отвечу в течение часа и предложу решение под ваш бизнес</div>
    <div class="cta-links">
      <a href="https://t.me/vrnk_sss" class="cta-link">Telegram: @vrnk_sss</a>
      <a href="https://wa.me/79818256236" class="cta-link">WhatsApp: +7 (981) 825-62-36</a>
      <a href="https://instagram.com/vrnk.sss" class="cta-link">Instagram: @vrnk.sss</a>
    </div>
  </div>

  <footer>
    <div class="footer-logo">Ника · СММ специалист</div>
    <div class="footer-copy">@vrnk.sss · 2026</div>
  </footer>

</div><!-- /main-page -->

<!-- CASE 1: Некипелов -->
<div id="case1" class="case-page">
  <div class="case-hero">
    <div class="case-hero-inner">
      <div class="case-back" onclick="closeCase()">← На главную</div>
      <div class="case-client">Кейс №1 · Инфобизнес / Эксперты / Онлайн-образование</div>
      <div class="case-h1">Степан<br>Некипелов</div>
      <div class="case-tagline">Эксперт по продажам — личный бренд с нуля</div>
    </div>
  </div>
  <div class="case-body">
    <div class="case-cols">
      <div>
        <div class="case-block-title">Цель</div>
        <div class="case-text">Выстроить личный бренд эксперта с нуля. Привлечь подписчиков. Запустить продажу курсов.</div>
      </div>
      <div>
        <div class="case-block-title">Что было сделано</div>
        <ul class="case-list">
          <li>Разработка стратегии для привлечения аудитории без рекламного бюджета</li>
          <li>Разработка визуального оформления</li>
          <li>Фото/видео съёмка для блога</li>
          <li>Запуск платной подписки в канал и курсов</li>
        </ul>
      </div>
    </div>

    <div class="case-block-title" style="margin-bottom:16px">Результат</div>
    <div class="results-grid" style="margin-bottom:48px">
      <div class="result-item"><div class="result-num">+7 322</div><div class="result-label">подписчика за 4 месяца</div></div>
      <div class="result-item"><div class="result-num">+155,9%</div><div class="result-label">средний органический рост охватов в месяц</div></div>
      <div class="result-item"><div class="result-num">7,23%</div><div class="result-label">конверсия из 318 заявок на платную подписку</div></div>
      <div class="result-item"><div class="result-num">5 оплат</div><div class="result-label">курса по 150 000 ₽ после первого запуска</div></div>
    </div>

    <div class="platform-section">
      <div class="platform-title">Продвижение через Reels</div>
      <div class="case-cols">
        <div>
          <div class="case-block-title">Охваты</div>
          <div class="case-text">Один Reels набрал <strong style="color:#fff">489 тыс. просмотров</strong>, 99,8% — неподписчики. Общие просмотры профиля за месяц: <strong style="color:#fff">1 408 378</strong>.</div>
        </div>
        <div>
          <div class="case-block-title">Вирусность</div>
          <div class="case-text">Генерация виральных полезных Reels: <strong style="color:#fff">1 300 пересылок</strong> и <strong style="color:#fff">1 700 сохранений</strong> на один Reels.</div>
        </div>
      </div>
    </div>

    <div class="platform-section">
      <div class="platform-title">Воронки и чат-боты</div>
      <div class="case-text" style="margin-bottom:16px">Создание Reels-воронок для получения заявок через комментарии. Заявки автоматически подгружаются в CRM.</div>
      <div class="results-grid">
        <div class="result-item"><div class="result-num">788</div><div class="result-label">клиентов · конверсия 67%</div></div>
        <div class="result-item"><div class="result-num">154</div><div class="result-label">клиентов · конверсия 74%</div></div>
        <div class="result-item"><div class="result-num">268</div><div class="result-label">клиентов · конверсия 63%</div></div>
      </div>
    </div>

    <div style="text-align:center;margin-top:48px">
      <div class="case-back" onclick="closeCase()" style="display:inline-flex;justify-content:center">← На главную</div>
    </div>
  </div>
</div>

<!-- CASE 2: Car Please -->
<div id="case2" class="case-page">
  <div class="case-hero">
    <div class="case-hero-inner">
      <div class="case-back" onclick="closeCase()">← На главную</div>
      <div class="case-client">Кейс №2 · Автобизнес / Интернет-торговля</div>
      <div class="case-h1">Car Please</div>
      <div class="case-tagline">Импорт автомобилей из Азии</div>
    </div>
  </div>
  <div class="case-body">
    <div class="case-cols">
      <div>
        <div class="case-block-title">Цель</div>
        <div class="case-text">Привлечь подписчиков во всех соц. сетях. Увеличить количество лидов.</div>
      </div>
      <div>
        <div class="case-block-title">Что было сделано</div>
        <ul class="case-list">
          <li>Разработка стратегии для увеличения охватов и получения лидов без бюджета на рекламу</li>
          <li>Проведён анализ ЦА с сегментацией по болям</li>
          <li>Написание сценариев для видео</li>
        </ul>
      </div>
    </div>

    <div class="case-block-title" style="margin-bottom:16px">Результат</div>
    <div class="results-grid" style="margin-bottom:48px">
      <div class="result-item"><div class="result-num">+3 661</div><div class="result-label">подписчик за месяц (в 3х соц. сетях)</div></div>
      <div class="result-item"><div class="result-num">+21 142%</div><div class="result-label">органический рост охватов за последний месяц</div></div>
      <div class="result-item"><div class="result-num">43 лида</div><div class="result-label">с соц. сетей в месяц</div></div>
      <div class="result-item"><div class="result-num">244 тыс.</div><div class="result-label">просмотров на один Reels</div></div>
    </div>

    <div class="platform-section">
      <div class="platform-title">Instagram</div>
      <div class="case-cols">
        <div>
          <div class="case-block-title">До</div>
          <div class="case-text">Не более 300 просмотров. Охваченные аккаунты: 3 014. Подписчики: 9 505.</div>
        </div>
        <div>
          <div class="case-block-title">После</div>
          <div class="case-text">Не менее 1 000 просмотров. Охваченные аккаунты: <strong style="color:#fff">234 726 (+21 142%)</strong>. Подписчики: <strong style="color:#fff">307 203</strong>. +19 лидов на заказ авто.</div>
        </div>
      </div>
    </div>

    <div class="platform-section">
      <div class="platform-title">TikTok</div>
      <div class="case-cols">
        <div>
          <div class="case-block-title">До</div>
          <div class="case-text">Не более 1 000 просмотров на видео.</div>
        </div>
        <div>
          <div class="case-block-title">После</div>
          <div class="case-text">Не менее 10 000 просмотров. Конверсия в Direct: 3–5 заявок в неделю. Средний ER (вовлечённость): +120%.</div>
        </div>
      </div>
    </div>

    <div class="platform-section">
      <div class="platform-title">Telegram</div>
      <div class="case-text">Оформление стало единым. Разработаны и подобраны emoji в стилистике компании. Добавили живого контента. Посты-карусели адаптированы под Telegram для визуального удобства.</div>
    </div>

    <div style="text-align:center;margin-top:48px">
      <div class="case-back" onclick="closeCase()" style="display:inline-flex;justify-content:center">← На главную</div>
    </div>
  </div>
</div>

<!-- CASE 3: Трубное Решение -->
<div id="case3" class="case-page">
  <div class="case-hero">
    <div class="case-hero-inner">
      <div class="case-back" onclick="closeCase()">← На главную</div>
      <div class="case-client">Кейс №3 · Корпоративная культура / Привлечение сотрудников / Рекрутинг</div>
      <div class="case-h1">ООО ПО<br>«Трубное<br>Решение»</div>
      <div class="case-tagline">HR-брендинг</div>
    </div>
  </div>
  <div class="case-body">
    <div class="case-cols">
      <div>
        <div class="case-block-title">Цель</div>
        <div class="case-text">Получение откликов на вакансию менеджера по продажам.</div>
      </div>
      <div>
        <div class="case-block-title">Что было сделано</div>
        <ul class="case-list">
          <li>Разработка стратегии для увеличения откликов без рекламного бюджета</li>
          <li>Проведён анализ ЦА с сегментацией по болям</li>
          <li>Разработка дизайн-концепта, съёмка/монтаж</li>
        </ul>
      </div>
    </div>

    <div class="case-block-title" style="margin-bottom:16px">Результат</div>
    <div class="results-grid" style="margin-bottom:48px">
      <div class="result-item"><div class="result-num">+50%</div><div class="result-label">прирост откликов на вакансию</div></div>
      <div class="result-item"><div class="result-num">+106,6%</div><div class="result-label">органический рост охватов за последний месяц</div></div>
      <div class="result-item"><div class="result-num">+1 332</div><div class="result-label">подписчика за год</div></div>
      <div class="result-item"><div class="result-num">132</div><div class="result-label">отклика на вакансию с одного Reels</div></div>
    </div>

    <div class="platform-section">
      <div class="platform-title">Продвижение через Reels</div>
      <div class="case-cols">
        <div>
          <div class="case-block-title">Охваты</div>
          <div class="case-text">Один Reels о вакансии набрал <strong style="color:#fff">103 875 просмотров</strong>, 99,7% — неподписчики. Средняя статистика профиля: <strong style="color:#fff">76 865 просмотров</strong> в месяц.</div>
        </div>
        <div>
          <div class="case-block-title">Вовлечённость</div>
          <div class="case-text">Сотрудники компании вовлеклись в процесс и стали репостить публикации со своим участием, тем самым повышая узнаваемость бренда.</div>
        </div>
      </div>
    </div>

    <div class="platform-section">
      <div class="platform-title">До / После — визуальная концепция</div>
      <ul class="case-list">
        <li>Более чёткая цель и фокус на вакансии</li>
        <li>Упрощённый и более читаемый текст</li>
        <li>Добавлена прямая ссылка для отклика</li>
        <li>Обновлён дизайн, который лучше соответствует атмосфере в коллективе</li>
        <li>Создана более доверительная атмосфера, соответствующая целям проекта</li>
      </ul>
    </div>

    <div style="text-align:center;margin-top:48px">
      <div class="case-back" onclick="closeCase()" style="display:inline-flex;justify-content:center">← На главную</div>
    </div>
  </div>
</div>

<script>
function openCase(id) {
  document.getElementById('main-page').style.display = 'none';
  document.querySelectorAll('.case-page').forEach(p => p.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  window.scrollTo(0,0);
}
function closeCase() {
  document.querySelectorAll('.case-page').forEach(p => p.classList.remove('active'));
  document.getElementById('main-page').style.display = 'block';
  window.scrollTo(0,0);
}
function toggleNav() {
  document.body.classList.toggle('nav-open');
}
document.querySelectorAll('.nav-links a').forEach(a => {
  a.addEventListener('click', () => document.body.classList.remove('nav-open'));
});
</script>
</body>
</html>
