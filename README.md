# Sweet--bakery
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.5, user-scalable=yes">
  <title>Sweet Bakery — Домашняя выпечка</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&family=Playfair+Display:ital,wght@0,600;1,600&display=swap" rel="stylesheet">
  <style>
    /* ---------- базовые стили ---------- */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Inter', sans-serif;
      background: #fefaf5;
      color: #2e1e16;
      line-height: 1.5;
      scroll-behavior: smooth;
    }
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }
    img { max-width: 100%; height: auto; display: block; border-radius: 20px; }

    /* ---------- шапка ---------- */
    .navbar {
      background: #fff6ed;
      box-shadow: 0 4px 20px rgba(90, 50, 30, 0.08);
      padding: 16px 0;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .navbar .container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }
    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.8rem;
      font-weight: 600;
      color: #b45a3a;
      letter-spacing: -0.5px;
    }
    .logo span { font-style: italic; color: #d48c6b; }
    .nav-links {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      font-weight: 500;
    }
    .nav-links a {
      text-decoration: none;
      color: #3d2a1e;
      transition: 0.2s;
      border-bottom: 2px solid transparent;
      padding-bottom: 4px;
    }
    .nav-links a:hover { color: #b45a3a; border-bottom-color: #b45a3a; }
    .btn {
      display: inline-block;
      background: #b45a3a;
      color: #fff;
      padding: 10px 28px;
      border-radius: 40px;
      text-decoration: none;
      font-weight: 600;
      border: none;
      cursor: pointer;
      transition: background 0.2s, transform 0.1s;
      box-shadow: 0 4px 10px rgba(180, 90, 58, 0.3);
      font-size: 1rem;
    }
    .btn:hover { background: #9e4a2e; transform: scale(1.02); }
    .btn:active { transform: scale(0.97); }

    /* ---------- слайдер (hero) ---------- */
    .hero-slider {
      position: relative;
      overflow: hidden;
      border-radius: 30px;
      margin: 30px 0 20px;
      box-shadow: 0 20px 40px rgba(90, 50, 30, 0.15);
      background: #fceae0;
    }
    .slides {
      display: flex;
      transition: transform 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }
    .slide {
      flex: 0 0 100%;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      padding: 30px 40px;
      min-height: 320px;
      gap: 20px;
    }
    .slide-text { flex: 1 1 240px; }
    .slide-text h2 {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem;
      color: #2e1e16;
    }
    .slide-text p { font-size: 1.1rem; color: #5a3f31; margin: 10px 0 20px; }
    .slide-img {
      flex: 1 1 200px;
      text-align: center;
    }
    .slide-img img {
      width: 100%;
      max-width: 280px;
      border-radius: 40px;
      box-shadow: 0 12px 25px rgba(0,0,0,0.1);
      aspect-ratio: 1/1;
      object-fit: cover;
    }
    .slider-controls {
      position: absolute;
      bottom: 20px;
      right: 30px;
      display: flex;
      gap: 12px;
    }
    .slider-controls button {
      background: rgba(255,255,255,0.8);
      border: none;
      border-radius: 50%;
      width: 44px;
      height: 44px;
      font-size: 1.4rem;
      cursor: pointer;
      backdrop-filter: blur(4px);
      transition: 0.2s;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    .slider-controls button:hover { background: #fff; transform: scale(1.05); }

    /* ---------- секции ---------- */
    .section { padding: 60px 0; }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: 2.2rem;
      margin-bottom: 30px;
      color: #2e1e16;
      position: relative;
    }
    .section-title:after {
      content: '';
      display: block;
      width: 70px;
      height: 4px;
      background: #b45a3a;
      margin-top: 10px;
      border-radius: 4px;
    }
    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 30px;
    }
    .card {
      background: #fff;
      border-radius: 28px;
      padding: 20px 20px 25px;
      box-shadow: 0 12px 30px rgba(90, 50, 30, 0.06);
      transition: 0.25s;
      border: 1px solid #f0e0d6;
      display: flex;
      flex-direction: column;
      opacity: 0;
      transform: translateY(30px);
      animation: fadeUp 0.6s forwards;
    }
    .card:nth-child(2) { animation-delay: 0.1s; }
    .card:nth-child(3) { animation-delay: 0.2s; }
    .card:nth-child(4) { animation-delay: 0.3s; }
    @keyframes fadeUp {
      to { opacity: 1; transform: translateY(0); }
    }
    .card:hover { transform: translateY(-8px) scale(1.01); box-shadow: 0 20px 40px rgba(90,50,30,0.12); }
    .card img {
      border-radius: 20px;
      width: 100%;
      aspect-ratio: 1/1;
      object-fit: cover;
      margin-bottom: 14px;
    }
    .card h3 { font-size: 1.4rem; color: #3d2a1e; }
    .card p { color: #5a4033; margin: 8px 0; flex: 1; }
    .price-tag { font-weight: 700; color: #b45a3a; font-size: 1.3rem; }

    /* ---------- прайс ---------- */
    .price-list {
      background: #fff9f2;
      border-radius: 40px;
      padding: 20px 30px;
      box-shadow: inset 0 0 0 1px #f0e0d6;
    }
    .price-item {
      display: flex;
      justify-content: space-between;
      padding: 14px 0;
      border-bottom: 1px dashed #e6d3c8;
      flex-wrap: wrap;
    }
    .price-item:last-child { border-bottom: none; }
    .price-item strong { font-size: 1.1rem; }

    /* ---------- форма + калькулятор ---------- */
    .order-wrap {
      display: flex;
      flex-wrap: wrap;
      gap: 40px;
      background: #fff;
      border-radius: 40px;
      padding: 30px 30px 40px;
      box-shadow: 0 12px 30px rgba(90,50,30,0.08);
    }
    .order-form { flex: 2 1 300px; }
    .order-form label {
      font-weight: 600;
      display: block;
      margin-top: 18px;
      margin-bottom: 4px;
    }
    .order-form input, .order-form select, .order-form textarea {
      width: 100%;
      padding: 12px 16px;
      border-radius: 30px;
      border: 1px solid #dfccc0;
      font-family: inherit;
      background: #fefaf5;
      transition: 0.2s;
      font-size: 1rem;
    }
    .order-form input:focus, .order-form select:focus, .order-form textarea:focus {
      outline: 2px solid #b45a3a;
      border-color: transparent;
    }

    /* сообщения от Formspree */
    .fs-messages {
      margin-top: 20px;
    }
    .fs-success, .fs-error {
      display: none;
      padding: 14px 20px;
      border-radius: 30px;
      font-weight: 500;
    }
    .fs-success { background: #d4edda; color: #155724; }
    .fs-error { background: #f8d7da; color: #721c24; }
    .fs-error ul { margin: 0; padding-left: 20px; }

    .calc-box {
      flex: 1 1 240px;
      background: #f9eee7;
      border-radius: 30px;
      padding: 24px 20px;
      align-self: flex-start;
    }
    .calc-box h4 {
      font-size: 1.5rem;
      font-family: 'Playfair Display', serif;
      margin-bottom: 16px;
    }
    .calc-row {
      display: flex;
      justify-content: space-between;
      padding: 6px 0;
      border-bottom: 1px solid #e6d3c8;
    }
    .calc-total {
      font-weight: 700;
      font-size: 1.6rem;
      color: #b45a3a;
      margin-top: 16px;
      border-top: 2px solid #b45a3a;
      padding-top: 16px;
      text-align: right;
    }

    /* ---------- галерея ---------- */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 16px;
      margin-top: 20px;
    }
    .gallery-item {
      border-radius: 30px;
      overflow: hidden;
      box-shadow: 0 6px 15px rgba(0,0,0,0.05);
      transition: 0.2s;
      cursor: pointer;
      border: 2px solid transparent;
    }
    .gallery-item:hover {
      transform: scale(1.02);
      border-color: #b45a3a;
    }
    .gallery-item img {
      width: 100%;
      aspect-ratio: 1/1;
      object-fit: cover;
      display: block;
    }

    /* ---------- контакты ---------- */
    .contact-social {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      background: #fff6ed;
      padding: 30px 30px;
      border-radius: 50px;
      margin-top: 30px;
    }
    .contact-social a {
      color: #3d2a1e;
      text-decoration: none;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 16px;
      border-radius: 40px;
      background: #fff;
      box-shadow: 0 2px 6px rgba(0,0,0,0.02);
    }
    .contact-social a:hover { background: #b45a3a; color: #fff; }
    .social-icons { display: flex; gap: 12px; flex-wrap: wrap; }

    .footer {
      text-align: center;
      padding: 30px 0 20px;
      color: #7a5f4e;
      border-top: 1px solid #eeded4;
      margin-top: 20px;
    }

    /* ---------- адаптив ---------- */
    @media (max-width: 700px) {
      .navbar .container { flex-direction: column; gap: 12px; }
      .nav-links { justify-content: center; gap: 1.2rem; }
      .slide { flex-direction: column; text-align: center; padding: 20px; }
      .slider-controls { right: 10px; bottom: 10px; }
      .slide-img img { max-width: 200px; }
      .order-wrap { padding: 20px; }
    }
    @media (max-width: 480px) {
      .hero-slider { border-radius: 16px; }
      .slide-text h2 { font-size: 1.6rem; }
    }
  </style>
</head>
<body>
  <!-- Шапка -->
  <nav class="navbar">
    <div class="container">
      <div class="logo">Sweet <span>Bakery</span></div>
      <div class="nav-links">
        <a href="#catalog">Каталог</a>
        <a href="#prices">Прайс</a>
        <a href="#order">Заказ</a>
        <a href="#gallery">Галерея</a>
        <a href="#contacts">Контакты</a>
      </div>
    </div>
  </nav>

  <!-- Слайдер (главная) -->
  <div class="container">
    <div class="hero-slider" id="slider">
      <div class="slides" id="slides">
        <div class="slide" style="background: #fceae0;">
          <div class="slide-text">
            <span style="background:#b45a3a;color:#fff;padding:4px 16px;border-radius:30px;font-weight:600;">Новинка</span>
            <h2>Торт «Медовый рай»</h2>
            <p>Нежные коржи с кремом из сметаны и натуральным мёдом. Идеальный выбор для семейного чаепития.</p>
            <a href="#order" class="btn">Заказать</a>
          </div>
          <div class="slide-img">
            <img src="https://images.unsplash.com/photo-1578985545063-69928b1d9585?w=400&h=400&fit=crop&crop=center" alt="Медовый торт">
          </div>
        </div>
        <div class="slide" style="background: #f5e6dc;">
          <div class="slide-text">
            <span style="background:#b45a3a;color:#fff;padding:4px 16px;border-radius:30px;font-weight:600;">Хит сезона</span>
            <h2>Ягодный мусс</h2>
            <p>Лёгкий, воздушный, с кислинкой малины и черники. Без выпечки — идеален для лета.</p>
            <a href="#order" class="btn">Заказать</a>
          </div>
          <div class="slide-img">
            <img src="https://images.unsplash.com/photo-1587313427220-4649e5bb6d01?w=400&h=400&fit=crop&crop=center" alt="Ягодный мусс">
          </div>
        </div>
        <div class="slide" style="background: #f0e3d9;">
          <div class="slide-text">
            <span style="background:#b45a3a;color:#fff;padding:4px 16px;border-radius:30px;font-weight:600;">Для сладкоежек</span>
            <h2>Капкейки с маскарпоне</h2>
            <p>Нежные кексы с кремом из маскарпоне и ягодами. Набор из 6 штук — отличный подарок.</p>
            <a href="#order" class="btn">Заказать</a>
          </div>
          <div class="slide-img">
            <img src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=400&h=400&fit=crop&crop=center" alt="Капкейки">
          </div>
        </div>
      </div>
      <div class="slider-controls">
        <button id="prevSlide" aria-label="Назад">◀</button>
        <button id="nextSlide" aria-label="Вперёд">▶</button>
      </div>
    </div>
  </div>

  <!-- Каталог -->
  <section class="section" id="catalog">
    <div class="container">
      <h2 class="section-title">Наш каталог</h2>
      <div class="card-grid">
        <div class="card">
          <img src="https://images.unsplash.com/photo-1578985545063-69928b1d9585?w=400&h=400&fit=crop&crop=center" alt="Торт">
          <h3>🎂 Торты</h3>
          <p>Бисквитные, муссовые, с ягодами и фруктами. От 1 кг.</p>
          <span class="price-tag">от 2500 ₽</span>
        </div>
        <div class="card">
          <img src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=400&h=400&fit=crop&crop=center" alt="Капкейки">
          <h3>🧁 Пирожные</h3>
          <p>Эклеры, макаруны, тарталетки, капкейки — наборы 6/12 шт.</p>
          <span class="price-tag">от 1200 ₽</span>
        </div>
        <div class="card">
          <img src="https://images.unsplash.com/photo-1599785209707-a456fc1337bb?w=400&h=400&fit=crop&crop=center" alt="Печенье">
          <h3>🍪 Печенье & десерты</h3>
          <p>Имбирное, овсяное, брауни, чизкейки, павлова.</p>
          <span class="price-tag">от 800 ₽</span>
        </div>
        <div class="card">
          <img src="https://images.unsplash.com/photo-1587313427220-4649e5bb6d01?w=400&h=400&fit=crop&crop=center" alt="Авторские десерты">
          <h3>🍫 Авторские наборы</h3>
          <p>Коробки конфет, трюфели, меренга, сезонные новинки.</p>
          <span class="price-tag">от 1500 ₽</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Прайс-лист -->
  <section class="section" id="prices">
    <div class="container">
      <h2 class="section-title">Прайс-лист (базовый)</h2>
      <div class="price-list">
        <div class="price-item"><strong>Торт «Классический» (бисквит, крем)</strong> <span>1 кг — 2500 ₽</span></div>
        <div class="price-item"><strong>Торт «Муссовый» (ягоды/шоколад)</strong> <span>1 кг — 2900 ₽</span></div>
        <div class="price-item"><strong>Пирожные (набор 6 шт.)</strong> <span>от 1200 ₽</span></div>
        <div class="price-item"><strong>Печенье имбирное (12 шт.)</strong> <span>900 ₽</span></div>
        <div class="price-item"><strong>Чизкейк Нью-Йорк</strong> <span>1.2 кг — 2800 ₽</span></div>
        <div class="price-item"><strong>Капкейки (6 шт.)</strong> <span>1100 ₽</span></div>
      </div>
    </div>
  </section>

  <!-- Форма заказа + калькулятор -->
  <section class="section" id="order">
    <div class="container">
      <h2 class="section-title">Заказ и бронирование</h2>
      <div class="order-wrap">
        <div class="order-form">
          <!-- Форма теперь с data-атрибутами для Formspree -->
          <form id="orderForm">
            <label for="name">Ваше имя *</label>
            <input type="text" id="name" name="name" placeholder="Например, Анна" required data-fs-field>

            <label for="phone">Телефон *</label>
            <input type="tel" id="phone" name="phone" placeholder="+7 900 123-45-67" required data-fs-field>

            <label for="dessert">Выберите десерт</label>
            <select id="dessert" name="dessert" data-fs-field>
              <option value="Торт классический">Торт классический (2500 ₽/кг)</option>
              <option value="Торт муссовый">Торт муссовый (2900 ₽/кг)</option>
              <option value="Пирожные набор">Пирожные набор 6шт (1200 ₽)</option>
              <option value="Печенье имбирное">Печенье имбирное (900 ₽)</option>
              <option value="Чизкейк">Чизкейк (2800 ₽)</option>
            </select>

            <label for="weight">Вес / количество</label>
            <input type="number" id="weight" name="weight" value="1" min="1" step="1" data-fs-field>

            <label for="date">Желаемая дата</label>
            <input type="date" id="date" name="date" data-fs-field>

            <label for="comment">Комментарий (пожелания, декор)</label>
            <textarea id="comment" name="comment" placeholder="Например: надпись «С днём рождения!», без орехов" data-fs-field></textarea>

            <!-- Блоки для сообщений Formspree -->
            <div class="fs-messages">
              <div data-fs-success class="fs-success">✅ Спасибо! Ваша заявка принята. Мы свяжемся с вами в ближайшее время.</div>
              <div data-fs-error class="fs-error"></div>
            </div>

            <button type="submit" data-fs-submit-btn class="btn" style="margin-top: 18px; width: 100%;">📩 Отправить заявку</button>
          </form>
          <p style="margin-top: 14px; color: #7a5f4e; font-size: 0.9rem;">* После отправки мы свяжемся с вами для подтверждения.</p>
        </div>

        <!-- Калькулятор -->
        <div class="calc-box">
          <h4>🧮 Калькулятор</h4>
          <div class="calc-row"><span>Выбран десерт</span> <span id="calcDessertName">Торт классический</span></div>
          <div class="calc-row"><span>Цена за ед.</span> <span id="calcPrice">2500 ₽</span></div>
          <div class="calc-row"><span>Количество</span> <span id="calcQty">1</span></div>
          <div class="calc-total" id="calcTotal">2500 ₽</div>
          <p style="font-size:0.85rem; margin-top: 8px; color:#5a4033;">* Ориентировочная стоимость, итог уточнит менеджер.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Галерея с фотографиями -->
  <section class="section" id="gallery">
    <div class="container">
      <h2 class="section-title">Сладкая галерея</h2>
      <div class="gallery-grid">
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1578985545063-69928b1d9585?w=400&h=400&fit=crop&crop=center" alt="Торт"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1587313427220-4649e5bb6d01?w=400&h=400&fit=crop&crop=center" alt="Ягодный торт"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1606313564200-e75d5e30476c?w=400&h=400&fit=crop&crop=center" alt="Капкейки"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1599785209707-a456fc1337bb?w=400&h=400&fit=crop&crop=center" alt="Печенье"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1551024506-0bccd828d307?w=400&h=400&fit=crop&crop=center" alt="Пирожное"></div>
        <div class="gallery-item"><img src="https://images.unsplash.com/photo-1607920591413-4ec007e70023?w=400&h=400&fit=crop&crop=center" alt="Чизкейк"></div>
      </div>
    </div>
  </section>

  <!-- Контакты -->
  <section class="section" id="contacts">
    <div class="container">
      <div class="contact-social">
        <div>
          <strong>📞 Связь с нами</strong><br>
          <a href="tel:+79001234567">+7 900 123-45-67</a><br>
          <a href="mailto:hello@sweetbakery.ru">hello@sweetbakery.ru</a>
        </div>
        <div class="social-icons">
          <a href="#">📸 Instagram</a>
          <a href="#">📱 Telegram</a>
          <a href="#">📘 VK</a>
          <a href="#">🧑‍🍳 WhatsApp</a>
        </div>
      </div>
    </div>
  </section>

  <footer class="footer">
    <div class="container">
      <p>🍞 Sweet Bakery — выпечка с душой. 2026</p>
    </div>
  </footer>

  <!-- Подключаем скрипт Formspree AJAX -->
  <script src="https://unpkg.com/@formspree/ajax@1" defer></script>

  <!-- Основные скрипты сайта -->
  <script>
    (function() {
      // ---------- Инициализация Formspree ----------
      // Ждём загрузки скрипта, затем инициализируем форму
      document.addEventListener('DOMContentLoaded', function() {
        if (typeof window.formspree !== 'undefined') {
          window.formspree('initForm', {
            formElement: '#orderForm',
            formId: 'xyegwbqj'   // ваш endpoint
          });
        } else {
          console.warn('Formspree script not loaded');
        }
      });

      // ---------- Слайдер ----------
      const slides = document.getElementById('slides');
      const prevBtn = document.getElementById('prevSlide');
      const nextBtn = document.getElementById('nextSlide');
      let currentIndex = 0;
      const totalSlides = slides.children.length;

      function goTo(index) {
        if (index < 0) index = totalSlides - 1;
        if (index >= totalSlides) index = 0;
        currentIndex = index;
        slides.style.transform = `translateX(-${currentIndex * 100}%)`;
      }

      prevBtn.addEventListener('click', () => goTo(currentIndex - 1));
      nextBtn.addEventListener('click', () => goTo(currentIndex + 1));

      let autoSlide = setInterval(() => goTo(currentIndex + 1), 5000);
      const slider = document.getElementById('slider');
      slider.addEventListener('mouseenter', () => clearInterval(autoSlide));
      slider.addEventListener('mouseleave', () => {
        autoSlide = setInterval(() => goTo(currentIndex + 1), 5000);
      });

      // ---------- Калькулятор ----------
      const dessertSelect = document.getElementById('dessert');
      const weightInput = document.getElementById('weight');
      const calcDessertName = document.getElementById('calcDessertName');
      const calcPrice = document.getElementById('calcPrice');
      const calcQty = document.getElementById('calcQty');
      const calcTotal = document.getElementById('calcTotal');

      const priceMap = {
        'Торт классический': { name: 'Торт классический', price: 2500 },
        'Торт муссовый': { name: 'Торт муссовый', price: 2900 },
        'Пирожные набор': { name: 'Пирожные набор', price: 1200 },
        'Печенье имбирное': { name: 'Печенье имбирное', price: 900 },
        'Чизкейк': { name: 'Чизкейк', price: 2800 }
      };

      function updateCalculator() {
        const key = dessertSelect.value;
        const data = priceMap[key];
        if (!data) return;
        const qty = parseInt(weightInput.value, 10) || 1;
        const total = data.price * qty;
        calcDessertName.textContent = data.name;
        calcPrice.textContent = data.price + ' ₽';
        calcQty.textContent = qty;
        calcTotal.textContent = total + ' ₽';
      }

      dessertSelect.addEventListener('change', updateCalculator);
      weightInput.addEventListener('input', updateCalculator);
      updateCalculator();

      // ---------- Плавный скролл ----------
      document.querySelectorAll('.nav-links a').forEach(link => {
        link.addEventListener('click', function(e) {
          const targetId = this.getAttribute('href');
          if (targetId && targetId.startsWith('#')) {
            const targetEl = document.querySelector(targetId);
            if (targetEl) {
              e.preventDefault();
              const topOffset = targetEl.getBoundingClientRect().top + window.pageYOffset - 80;
              window.scrollTo({ top: topOffset, behavior: 'smooth' });
            }
          }
        });
      });

      // ---------- Клик по галерее (увеличение) ----------
      document.querySelectorAll('.gallery-item img').forEach(img => {
        img.addEventListener('click', function() {
          const src = this.getAttribute('src');
          const overlay = document.createElement('div');
          overlay.style.cssText = `
            position: fixed; top:0; left:0; width:100%; height:100%;
            background: rgba(0,0,0,0.7); display:flex; justify-content:center; align-items:center;
            z-index:999; cursor:pointer; backdrop-filter: blur(4px);
          `;
          const bigImg = document.createElement('img');
          bigImg.src = src;
          bigImg.style.cssText = `
            max-width: 80%; max-height: 80%; border-radius: 30px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5);
          `;
          overlay.appendChild(bigImg);
          overlay.addEventListener('click', () => overlay.remove());
          document.body.appendChild(overlay);
        });
      });

    })();
  </script>
</body>
</html>
