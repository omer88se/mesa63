<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Benim Gelişmiş Sitem</title>
  <style>
    :root {
      --bg-color: #ffffff;
      --text-color: #333333;
      --primary-color: #4CAF50;
    }

    [data-theme="dark"] {
      --bg-color: #121212;
      --text-color: #ffffff;
      --primary-color: #90caf9;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background-color: var(--primary-color);
      padding: 20px;
      text-align: center;
      font-size: 2rem;
      color: white;
    }

    nav {
      display: flex;
      background: #333;
      flex-wrap: wrap;
    }

    nav a {
      flex: 1;
      color: white;
      text-decoration: none;
      text-align: center;
      padding: 14px 20px;
      transition: background 0.3s;
    }

    nav a:hover {
      background: #555;
    }

    main {
      flex: 1;
      padding: 20px;
      animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    footer {
      background-color: var(--primary-color);
      color: white;
      text-align: center;
      padding: 10px;
    }

    .theme-toggle {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: var(--primary-color);
      border: none;
      color: white;
      cursor: pointer;
      border-radius: 5px;
      font-size: 1rem;
    }

    .theme-toggle:hover {
      background-color: #388e3c;
    }

    /* SLIDER */
    .slider {
      position: relative;
      max-width: 100%;
      margin: 20px auto;
      overflow: hidden;
      border-radius: 10px;
    }

    .slides {
      display: flex;
      transition: transform 0.5s ease;
    }

    .slides img {
      width: 100%;
      height: 300px;
      object-fit: cover;
    }

    /* KENDI RESMIN */
    .my-photo {
      margin-top: 30px;
      text-align: center;
    }

    .my-photo img {
      width: 300px;
      max-width: 100%;
      height: auto;
      border-radius: 15px;
      transition: transform 0.4s ease, box-shadow 0.4s ease;
    }

    .my-photo img:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(0,0,0,0.3);
    }

    /* PROJECTS */
    .projects {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-top: 40px;
    }

    .card {
      background: var(--primary-color);
      color: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      transition: transform 0.3s;
    }

    .card:hover {
      transform: translateY(-5px);
    }

    /* CONTACT FORM */
    .contact-form {
      margin-top: 40px;
    }

    .contact-form input, .contact-form textarea {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .contact-form button {
      padding: 10px 20px;
      background-color: var(--primary-color);
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
      font-size: 1rem;
    }

    .contact-form button:hover {
      background-color: #388e3c;
    }

    @media (max-width: 600px) {
      nav a {
        flex-basis: 100%;
      }
    }
  </style>
</head>
<body>

<header>
  Benim Gelişmiş Sitem
</header>

<nav>
  <a href="#anasayfa">Ana Sayfa</a>
  <a href="#projeler">Projeler</a>
  <a href="#iletisim">İletişim</a>
</nav>

<main id="anasayfa">
  <h1>Hoş Geldin!</h1>
  <p>Bu benim kendi yaptığım gelişmiş web sitem! 🚀</p>

  <!-- KENDI RESMIN -->
  <div class="my-photo">
    <img src="benimresmim.jpg" alt="Benim Fotoğrafım">
  </div>

  <button class="theme-toggle" onclick="toggleTheme()">🌗 Tema Değiştir</button>

  <!-- SLIDER -->
  <div class="slider">
    <div class="slides" id="slides">
      <img src="https://picsum.photos/id/1015/800/300" alt="Doğa">
      <img src="https://picsum.photos/id/1016/800/300" alt="Şehir">
      <img src="https://picsum.photos/id/1018/800/300" alt="Deniz">
    </div>
  </div>

  <!-- PROJECTS -->
  <section id="projeler">
    <h2>Projelerim</h2>
    <div class="projects">
      <div class="card">
        <h3>Proje 1</h3>
        <p>İlk projem hakkında kısa bilgi.</p>
      </div>
      <div class="card">
        <h3>Proje 2</h3>
        <p>İkinci proje detayları burada.</p>
      </div>
      <div class="card">
        <h3>Proje 3</h3>
        <p>Üçüncü projeye dair açıklamalar.</p>
      </div>
    </div>
  </section>

  <!-- CONTACT FORM -->
  <section id="iletisim" class="contact-form">
    <h2>İletişim</h2>
    <form onsubmit="sendMessage(event)">
      <input type="text" placeholder="Adınız" required>
      <input type="email" placeholder="E-posta" required>
      <textarea rows="5" placeholder="Mesajınız" required></textarea>
      <button type="submit">Gönder</button>
    </form>
  </section>

</main>

<footer>
  &copy; 2025 Benim Gelişmiş Sitem
</footer>

<script>
  function toggleTheme() {
    const currentTheme = document.documentElement.getAttribute('data-theme');
    if (currentTheme === 'dark') {
      document.documentElement.setAttribute('data-theme', 'light');
    } else {
      document.documentElement.setAttribute('data-theme', 'dark');
    }
  }

  if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
    document.documentElement.setAttribute('data-theme', 'dark');
  }

  // Slider otomatik geçiş
  let index = 0;
  function showNextSlide() {
    const slides = document.getElementById('slides');
    index = (index + 1) % slides.children.length;
    slides.style.transform = `translateX(-${index * 100}%)`;
  }
  setInterval(showNextSlide, 3000);

  // Form gönderimi
  function sendMessage(event) {
    event.preventDefault();
    alert("Mesajınız başarıyla gönderildi! 🎉");
  }
</script>

</body>
</html>
