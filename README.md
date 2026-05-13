# bebocafe
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bebo Cafe - Menu</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    font-family: 'Cairo', sans-serif;
    background: #0a0a0a;
    color: #f0e6d3;
    min-height: 100vh;
  }
  .hero {
    background: linear-gradient(135deg, #1a0a00 0%, #2d1500 50%, #1a0a00 100%);
    border-bottom: 2px solid #c8973a;
    padding: 2rem 1rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at center, rgba(200,151,58,0.15) 0%, transparent 70%);
  }
  .hero-logo {
    font-size: 3rem;
    font-weight: 900;
    color: #c8973a;
    letter-spacing: 4px;
    text-shadow: 0 0 30px rgba(200,151,58,0.5);
    position: relative;
  }
  .hero-sub {
    font-size: 1rem;
    color: #a07840;
    letter-spacing: 8px;
    margin-top: 0.3rem;
    position: relative;
  }
  .hero-icons { font-size: 2rem; margin-bottom: 0.5rem; position: relative; }
  .nav {
    background: #111;
    border-bottom: 1px solid #333;
    display: flex;
    justify-content: center;
    gap: 0.5rem;
    padding: 0.75rem;
    flex-wrap: wrap;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .nav-btn {
    background: transparent;
    border: 1px solid #444;
    color: #c8973a;
    padding: 0.4rem 1rem;
    border-radius: 20px;
    cursor: pointer;
    font-family: 'Cairo', sans-serif;
    font-size: 0.85rem;
    transition: all 0.2s;
  }
  .nav-btn:hover, .nav-btn.active {
    background: #c8973a;
    color: #000;
    border-color: #c8973a;
    font-weight: 700;
  }
  .container { max-width: 900px; margin: 0 auto; padding: 1.5rem 1rem; }
  .section { margin-bottom: 2.5rem; }
  .section-title {
    font-size: 1.2rem;
    font-weight: 700;
    color: #c8973a;
    border-bottom: 1px solid #c8973a44;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }
  .items-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 0.75rem;
  }
  .item-card {
    background: #1a1a1a;
    border: 1px solid #2a2a2a;
    border-radius: 10px;
    padding: 0.85rem 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: all 0.2s;
  }
  .item-card:hover {
    border-color: #c8973a66;
    background: #1f1a12;
  }
  .item-name { font-size: 0.9rem; color: #e8d5b5; }
  .item-price {
    font-size: 0.9rem;
    font-weight: 700;
    color: #c8973a;
    white-space: nowrap;
    margin-right: 0.5rem;
  }
  .badge-new {
    background: #c8973a;
    color: #000;
    font-size: 0.65rem;
    font-weight: 700;
    padding: 1px 6px;
    border-radius: 10px;
    margin-right: 4px;
  }
  .qr-section {
    background: #111;
    border: 1px solid #c8973a44;
    border-radius: 16px;
    padding: 2rem;
    text-align: center;
    margin-top: 2rem;
  }
  .qr-title { font-size: 1.1rem; color: #c8973a; margin-bottom: 1rem; font-weight: 700; }
  #qrcode {
    display: inline-block;
    background: white;
    padding: 12px;
    border-radius: 8px;
    margin: 1rem auto;
  }
  .qr-note { font-size: 0.8rem; color: #888; margin-top: 0.75rem; }
  .footer {
    text-align: center;
    padding: 1.5rem;
    border-top: 1px solid #222;
    color: #555;
    font-size: 0.8rem;
  }
  .all-prices { font-size: 0.75rem; color: #666; text-align: center; margin-top: -1rem; margin-bottom: 2rem; }
</style>
</head>
<body>
 
<div class="hero">
  <div class="hero-icons">🎮 ☕</div>
  <div class="hero-logo">BEBO CAFE</div>
  <div class="hero-sub">MENU</div>
</div>
 
<nav class="nav">
  <button class="nav-btn active" onclick="goTo('hot', this)">☕ مشروبات ساخنة</button>
  <button class="nav-btn" onclick="goTo('juices', this)">🍹 عصائر</button>
  <button class="nav-btn" onclick="goTo('milkshakes', this)">🥤 ميلك شيك</button>
  <button class="nav-btn" onclick="goTo('soft', this)">🥤 مشروبات</button>
  <button class="nav-btn" onclick="goTo('snacks', this)">🍟 سناكس</button>
  <button class="nav-btn" onclick="goTo('shisha', this)">💨 شيشة</button>
  <button class="nav-btn" onclick="goTo('qr', this)">📱 QR Code</button>
</nav>
 
<div class="container">
  <p class="all-prices">جميع الأسعار بالجنيه المصري (EGP)</p>
 
  <div class="section" id="hot">
    <div class="section-title">☕ المشروبات الساخنة</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Coffee</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">French Coffee</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Hazelnut Coffee</span><span class="item-price">35 ج</span></div>
      <div class="item-card"><span class="item-name">Hot Chocolate</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Hot Chocolate with Milk</span><span class="item-price">35 ج</span></div>
      <div class="item-card"><span class="item-name">Nescafe</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Nescafe with Milk</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Tea</span><span class="item-price">15 ج</span></div>
      <div class="item-card"><span class="item-name">Tea with Milk</span><span class="item-price">20 ج</span></div>
      <div class="item-card"><span class="item-name">Green Tea</span><span class="item-price">20 ج</span></div>
      <div class="item-card"><span class="item-name">Yanson</span><span class="item-price">20 ج</span></div>
      <div class="item-card"><span class="item-name">Mint</span><span class="item-price">20 ج</span></div>
      <div class="item-card"><span class="item-name">Karkade</span><span class="item-price">20 ج</span></div>
      <div class="item-card"><span class="item-name">Cappuccino</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Zangabeel</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Ginger with Milk</span><span class="item-price">35 ج</span></div>
      <div class="item-card"><span class="item-name">A3shab Mix</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Cinnamon</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Cinnamon with Milk</span><span class="item-price">30 ج</span></div>
      <div class="item-card">
        <span class="item-name"><span class="badge-new">جديد</span>رضعة شادية</span>
        <span class="item-price">60 ج</span>
      </div>
    </div>
  </div>
 
  <div class="section" id="juices">
    <div class="section-title">🍹 العصائر الطازجة</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Banana</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Banana with Milk</span><span class="item-price">35 ج</span></div>
      <div class="item-card"><span class="item-name">Guava</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Guava with Milk</span><span class="item-price">35 ج</span></div>
      <div class="item-card"><span class="item-name">Orange</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Lemon Mint</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Mango</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Strawberry with Milk</span><span class="item-price">30 ج</span></div>
      <div class="item-card">
        <span class="item-name"><span class="badge-new">جديد</span>رضعة شادية</span>
        <span class="item-price">60 ج</span>
      </div>
    </div>
  </div>
 
  <div class="section" id="milkshakes">
    <div class="section-title">🥤 ميلك شيك</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Vanilla</span><span class="item-price">50 ج</span></div>
      <div class="item-card"><span class="item-name">Chocolate</span><span class="item-price">50 ج</span></div>
      <div class="item-card"><span class="item-name">Strawberry</span><span class="item-price">50 ج</span></div>
      <div class="item-card"><span class="item-name">Mango</span><span class="item-price">50 ج</span></div>
      <div class="item-card"><span class="item-name">Oreo</span><span class="item-price">50 ج</span></div>
    </div>
  </div>
 
  <div class="section" id="soft">
    <div class="section-title">🥤 المشروبات الغازية</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Pepsi / Coca-Cola</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">V Cola</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Miranda Apple / Orange</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Sting</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Fayrouz</span><span class="item-price">25 ج</span></div>
      <div class="item-card"><span class="item-name">Fury</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Barrel</span><span class="item-price">30 ج</span></div>
      <div class="item-card"><span class="item-name">Red Bull</span><span class="item-price">70 ج</span></div>
    </div>
  </div>
 
  <div class="section" id="snacks">
    <div class="section-title">🍟 السناكس</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Crunchy Snacks</span><span class="item-price">15 ج</span></div>
    </div>
  </div>
 
  <div class="section" id="shisha">
    <div class="section-title">💨 الشيشة</div>
    <div class="items-grid">
      <div class="item-card"><span class="item-name">Saloom</span><span class="item-price">15 ج</span></div>
      <div class="item-card"><span class="item-name">Kas</span><span class="item-price">15 ج</span></div>
      <div class="item-card"><span class="item-name">Fruit Shisha</span><span class="item-price">60 ج</span></div>
      <div class="item-card"><span class="item-name">Premium Fruit Shisha</span><span class="item-price">75 ج</span></div>
    </div>
  </div>
 
  <div class="qr-section" id="qr">
    <div class="qr-title">📱 امسح الـ QR Code لفتح المنيو</div>
    <div id="qrcode"></div>
    <p class="qr-note">الـ QR Code بيفتح لينك الموقع أوتوماتيك — شاره مع زبايينك!</p>
  </div>
</div>
 
<div class="footer">🎮 Bebo Cafe — جميع الأسعار بالجنيه المصري</div>
 
<script>
  function goTo(id, btn) {
    document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
  }
 
  window.addEventListener('load', function () {
    new QRCode(document.getElementById("qrcode"), {
      text: window.location.href,
      width: 200,
      height: 200,
      colorDark: "#000000",
      colorLight: "#ffffff",
      correctLevel: QRCode.CorrectLevel.M
    });
  });
</script>
</body>
</html>
