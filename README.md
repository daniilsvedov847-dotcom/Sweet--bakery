# Sweet--bakery
[deepseek_html_20260811_dcdb97.html](https://github.com/user-attachments/files/30946280/deepseek_html_20260811_dcdb97.html)
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.5, user-scalable=yes">
  <title>Sweet Bakery — Домашняя выпечка</title>
  <!-- Шрифты и базовая стилизация -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&family=Playfair+Display:ital,wght@0,600;1,600&display=swap" rel="stylesheet">
  <style>
    /* ----- CSS переменные и сброс ----- */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
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

    /* ----- шапка / навигация ----- */
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
    .logo span {
      font-style: italic;
      color: #d48c6b;
    }
    .nav-links {
      display: flex;
      gap: 2rem;
      flex-wrap: wrap;
      font-weight: 500;
    }
    .nav-links a {
      text-decoration: none;
      color: #3d2a1e;
      transition: color 0.2s;
      border-bottom: 2px solid transparent;
      padding-bottom: 4px;
    }
    .nav-links a:hover {
      color: #b45a3a;
      border-bottom-color: #b45a3a;
    }
    .nav-links a:focus-visible {
      outline: 2px solid #b45a3a;
      outline-offset: 4px;
    }
    .btn {
      display: inline-block;
      background: #b45a3a;
      color: white;
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
    .btn:hover {
      background: #9e4a2e;
      transform: scale(1.02);
    }
    .btn:active {
      transform: scale(0.97);
    }

    /* ----- hero ----- */
    .hero {
      padding: 50px 0 30px;
      background: linear-gradient(145deg, #fceae0 0%, #fefaf5 100%);
      border-radius: 0 0 40px 40px;
    }
    .hero-grid {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 30px;
    }
    .hero-text {
      flex: 1 1 300px;
    }
    .hero-text h1 {
      font-family: 'Playfair Display', serif;
      font-size: 2.8rem;
      color: #2e1e16;
      line-height: 1.2;
    }
    .hero-text h1 i {
      color: #b45a3a;
      font-style: italic;
    }
    .hero-text p {
      font-size: 1.2rem;
      color: #5a3f31;
      margin: 20px 0 30px;
    }
    .hero-badge {
      background: #eacedd;
      padding: 8px 18px;
      border-radius: 60px;
      display: inline-block;
      font-weight: 600;
      color: #7a3f2b;
    }
    .hero-image {
      flex: 1 1 260px;
      text-align: center;
      background: #f6e3d6;
      padding: 30px 20px;
      border-radius: 60px 60px 60px 10px;
      box-shadow: 0 20px 30px -10px rgba(100, 60, 30, 0.2);
    }
    .hero-image .emoji-big {
      font-size: 4.5rem;
      line-height: 1;
    }
    .hero-image p {
      margin-top: 10px;
      font-weight: 500;
    }

    /* ----- секции общие ----- */
    .section {
      padding: 60px 0;
    }
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
      background: white;
      border-radius: 28px;
      padding: 24px 20px;
      box-shadow: 0 12px 30px rgba(90, 50, 30, 0.06);
      transition: 0.2s;
      border: 1px solid #f0e0d6;
    }
    .card:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 35px rgba(90, 50, 30, 0.12);
    }
    .card-icon {
      font-size: 2.8rem;
      margin-bottom: 8px;
    }
    .card h3 {
      font-size: 1.4rem;
      color: #3d2a1e;
    }
    .card p {
      color: #5a4033;
      margin: 10px 0;
    }
    .price-tag {
      font-weight: 700;
      color: #b45a3a;
      font-size: 1.3rem;
    }

    /* прайс-лист */
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
    .price-item:last-child {
      border-bottom: none;
    }
    .price-item strong {
      font-size: 1.1rem;
    }

    /* форма заказа + калькулятор */
    .order-wrap {
      display: flex;
      flex-wrap: wrap;
      gap: 40px;
      background: white;
      border-radius: 40px;
      padding: 30px 30px 40px;
      box-shadow: 0 12px 30px rgba(90, 50, 30, 0.08);
    }
    .order-form {
      flex: 2 1 300px;
    }
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
    .order-form textarea {
      min-height: 80px;
      resize: vertical;
    }
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

    /* галерея (мини) */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 16px;
      margin-top: 20px;
    }
    .gallery-item {
      background: #f6e3d6;
      border-radius: 30px;
      padding: 20px 10px;
      text-align: center;
      font-size: 2.8rem;
      box-shadow: 0 6px 12px rgba(0,0,0,0.02);
      border: 1px solid #f0e0d6;
      transition: 0.15s;
    }
    .gallery-item:hover {
      background: #efd9cb;
    }
    .gallery-item span {
      display: block;
      font-size: 1rem;
      font-weight: 500;
      color: #3d2a1e;
    }

    /* контакты + соцсети */
    .contact-social {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      background: #fff6ed;
      padding: 30px 30px;
      border-radius: 50px;
    }
    .contact-social a {
      color: #3d2a1e;
      text-decoration: none;
      font-weight: 500;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 12px;
      border-radius: 40px;
      background: white;
      box-shadow: 0 2px 6px rgba(0,0,0,0.02);
    }
    .contact-social a:hover {
      background: #b45a3a;
      color: white;
    }
    .social-icons {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }
    .footer {
      text-align: center;
      padding: 30px 0 20px;
      color: #7a5f4e;
      border-top: 1px solid #eeded4;
      margin-top: 20px;
    }

    /* адаптив */
    @media (max-width: 700px) {
      .navbar .container { flex-direction: column; gap: 12px; }
      .nav-links { justify-content: center; gap: 1.2rem; }
      .hero-text h1 { font-size: 2.2rem; }
      .order-wrap { padding: 20px; }
    }
    @media (max-width: 480px) {
      .hero-text h1 { font-size: 1.9rem; }
      .section-title { font-size: 1.8rem; }
    }
  </style>
</head>
<body>
  <!-- Навигация -->
  <nav class="navbar">
    <div class="container">
      <div class="logo">Sweet <span>Bakery</span></div>
      <div class="nav-links">
        <a href="#catalog">Каталог</a>
        <a href="#prices">Прайс</a>
        <a href="#order">Заказ</a>
        <a href="#contacts">Контакты</a>
      </div>
    </div>
  </nav>

  <!-- Главная (hero) -->
  <section class="hero" id="home">
    <div class="container hero-grid">
      <div class="hero-text">
        <span class="hero-badge">🔥 Свежая выпечка каждый день</span>
        <h1>Домашние торты <br>и <i>сладкие</i> мгновения</h1>
        <p>Натуральные ингредиенты, авторские рецепты и любовь к деталям. Для вас и ваших близких.</p>
        <a href="#order" class="btn">🍰 Заказать сейчас</a>
      </div>
      <div class="hero-image">
        <div class="emoji-big">🧁</div>
        <p>Акция: при заказе от 2 кг — <strong>десерт в подарок</strong></p>
      </div>
    </div>
  </section>

  <!-- Каталог товаров -->
  <section class="section" id="catalog">
    <div class="container">
      <h2 class="section-title">Наш каталог</h2>
      <div class="card-grid">
        <div class="card"><div class="card-icon">🎂</div><h3>Торты</h3><p>Бисквитные, муссовые, с ягодами и фруктами. От 1 кг.</p><span class="price-tag">от 2500 ₽</span></div>
        <div class="card"><div class="card-icon">🧁</div><h3>Пирожные</h3><p>Эклеры, макаруны, тарталетки, капкейки — наборы 6/12 шт.</p><span class="price-tag">от 1200 ₽</span></div>
        <div class="card"><div class="card-icon">🍪</div><h3>Печенье & десерты</h3><p>Имбирное, овсяное, брауни, чизкейки, павлова.</p><span class="price-tag">от 800 ₽</span></div>
        <div class="card"><div class="card-icon">🍫</div><h3>Авторские наборы</h3><p>Коробки конфет, трюфели, меренга, сезонные новинки.</p><span class="price-tag">от 1500 ₽</span></div>
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
        <div class="price-item"><strong>Чизкейк Нью-Йорк</strong> <span>вес 1.2 кг — 2800 ₽</span></div>
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
          <form id="orderForm">
            <label for="name">Ваше имя *</label>
            <input type="text" id="name" placeholder="Например, Анна" required>

            <label for="phone">Телефон *</label>
            <input type="tel" id="phone" placeholder="+7 900 123-45-67" required>

            <label for="dessert">Выберите десерт</label>
            <select id="dessert">
              <option value="tort">Торт классический (2500 ₽/кг)</option>
              <option value="mousse">Торт муссовый (2900 ₽/кг)</option>
              <option value="pie">Пирожные набор 6шт (1200 ₽)</option>
              <option value="cookie">Печенье имбирное (900 ₽)</option>
              <option value="cheese">Чизкейк (2800 ₽)</option>
            </select>

            <label for="weight">Вес / количество</label>
            <input type="number" id="weight" value="1" min="1" step="1">

            <label for="comment">Комментарий (дата, пожелания)</label>
            <textarea id="comment" placeholder="К какому часу, декор и т.д."></textarea>

            <button type="submit" class="btn" style="margin-top: 18px; width: 100%;">📩 Отправить заявку</button>
          </form>
          <p style="margin-top: 14px; color: #7a5f4e; font-size: 0.9rem;">* После отправки мы свяжемся с вами для подтверждения.</p>
        </div>

        <!-- Калькулятор стоимости -->
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

  <!-- Галерея (мини) + соцсети -->
  <section class="section" id="contacts">
    <div class="container">
      <h2 class="section-title">Сладкая галерея</h2>
      <div class="gallery-grid">
        <div class="gallery-item">🍰<span>Торт «Нежность»</span></div>
        <div class="gallery-item">🧁<span>Капкейки</span></div>
        <div class="gallery-item">🍪<span>Печенье</span></div>
        <div class="gallery-item">🍫<span>Трюфели</span></div>
        <div class="gallery-item">🥧<span>Пирог</span></div>
        <div class="gallery-item">🍮<span>Павлова</span></div>
      </div>

      <div style="margin-top: 40px;" class="contact-social">
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

  <!-- JavaScript: калькулятор и форма -->
  <script>
    (function() {
      // Элементы калькулятора
      const dessertSelect = document.getElementById('dessert');
      const weightInput = document.getElementById('weight');
      const calcDessertName = document.getElementById('calcDessertName');
      const calcPrice = document.getElementById('calcPrice');
      const calcQty = document.getElementById('calcQty');
      const calcTotal = document.getElementById('calcTotal');

      // Справочник цен (базовые цены за единицу)
      const priceMap = {
        'tort': { name: 'Торт классический', price: 2500 },
        'mousse': { name: 'Торт муссовый', price: 2900 },
        'pie': { name: 'Пирожные набор', price: 1200 },
        'cookie': { name: 'Печенье имбирное', price: 900 },
        'cheese': { name: 'Чизкейк', price: 2800 }
      };

      function updateCalculator() {
        const key = dessertSelect.value;
        const data = priceMap[key];
        const qty = parseInt(weightInput.value, 10) || 1;
        const total = data.price * qty;

        calcDessertName.textContent = data.name;
        calcPrice.textContent = data.price + ' ₽';
        calcQty.textContent = qty;
        calcTotal.textContent = total + ' ₽';
      }

      dessertSelect.addEventListener('change', updateCalculator);
      weightInput.addEventListener('input', updateCalculator);
      // начальный вызов
      updateCalculator();

      // Форма — пример интерактивности (без реальной отправки)
      const form = document.getElementById('orderForm');
      form.addEventListener('submit', function(e) {
        e.preventDefault();
        const name = document.getElementById('name').value.trim();
        if (!name) {
          alert('Пожалуйста, введите ваше имя.');
          return;
        }
        alert('✅ Спасибо, ' + name + '! Ваша заявка принята. Мы свяжемся с вами в ближайшее время.');
        form.reset();
        // обновим калькулятор после сброса
        setTimeout(updateCalculator, 50);
      });

      // Плавный скролл для навигации (без дополнительных библиотек)
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
    })();
  </script>
</body>
</html>
