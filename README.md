# -<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>كتاب تلوين الفواكه</title>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700;900&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --mint:    #A8D8C8;
      --peach:   #F4A97F;
      --lemon:   #F6E06B;
      --berry:   #D9607A;
      --leaf:    #6DAE74;
      --cream:   #FDF8F2;
      --ink:     #2E2E2E;
    }

    body {
      font-family: 'Tajawal', sans-serif;
      background: var(--cream);
      color: var(--ink);
      overflow-x: hidden;
    }

    /* ─── HERO ─────────────────────────────────────── */
    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 60px 24px 40px;
      overflow: hidden;
    }

    /* big watercolour blobs */
    .blob {
      position: absolute;
      border-radius: 50%;
      opacity: 0.18;
      filter: blur(60px);
      pointer-events: none;
    }
    .blob-1 { width: 520px; height: 520px; background: var(--mint);  top: -140px; right: -120px; }
    .blob-2 { width: 400px; height: 400px; background: var(--lemon); bottom: -80px; left: -100px; }
    .blob-3 { width: 300px; height: 300px; background: var(--peach); top: 50%;  left: 50%; transform: translate(-50%,-50%); }

    .hero-eyebrow {
      font-size: 0.85rem;
      font-weight: 700;
      letter-spacing: 0.22em;
      color: var(--leaf);
      text-transform: uppercase;
      margin-bottom: 18px;
    }

    .hero-title {
      font-size: clamp(2.8rem, 8vw, 5.5rem);
      font-weight: 900;
      line-height: 1.1;
      color: var(--ink);
      position: relative;
    }

    .hero-title span {
      position: relative;
      display: inline-block;
    }
    /* scribble underline on key word */
    .hero-title span::after {
      content: '';
      display: block;
      position: absolute;
      bottom: -6px; left: 0; right: 0;
      height: 6px;
      background: var(--peach);
      border-radius: 3px;
    }

    .hero-sub {
      margin-top: 24px;
      font-size: clamp(1rem, 2.5vw, 1.35rem);
      font-weight: 400;
      color: #555;
      max-width: 560px;
      line-height: 1.7;
    }

    /* floating fruit emojis */
    .fruits-row {
      display: flex;
      gap: 16px;
      justify-content: center;
      flex-wrap: wrap;
      margin: 36px 0 32px;
    }
    .fruit-chip {
      background: #fff;
      border: 2.5px solid #e8e0d8;
      border-radius: 999px;
      padding: 10px 22px;
      font-size: 1.5rem;
      box-shadow: 0 4px 14px rgba(0,0,0,.06);
      animation: float 3.5s ease-in-out infinite;
    }
    .fruit-chip:nth-child(2) { animation-delay: .5s; }
    .fruit-chip:nth-child(3) { animation-delay: 1s;  }
    .fruit-chip:nth-child(4) { animation-delay: 1.5s;}
    .fruit-chip:nth-child(5) { animation-delay: 2s;  }
    @keyframes float {
      0%,100% { transform: translateY(0);   }
      50%      { transform: translateY(-8px);}
    }

    .cta-btn {
      display: inline-block;
      background: var(--berry);
      color: #fff;
      font-family: 'Tajawal', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      padding: 16px 44px;
      border-radius: 999px;
      border: none;
      cursor: pointer;
      box-shadow: 0 8px 24px rgba(217,96,122,.35);
      transition: transform .18s, box-shadow .18s;
      text-decoration: none;
    }
    .cta-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 14px 30px rgba(217,96,122,.45);
    }

    .badge {
      margin-top: 18px;
      font-size: 0.82rem;
      color: #888;
    }

    /* ─── FEATURES ──────────────────────────────────── */
    .features {
      background: #fff;
      padding: 72px 24px;
    }
    .section-label {
      text-align: center;
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: .2em;
      color: var(--leaf);
      text-transform: uppercase;
      margin-bottom: 12px;
    }
    .section-title {
      text-align: center;
      font-size: clamp(1.6rem, 4vw, 2.4rem);
      font-weight: 900;
      margin-bottom: 48px;
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 24px;
      max-width: 960px;
      margin: 0 auto;
    }
    .card {
      background: var(--cream);
      border-radius: 20px;
      padding: 32px 24px;
      text-align: center;
      border: 2px solid #ede8e0;
    }
    .card-icon {
      font-size: 2.6rem;
      margin-bottom: 16px;
    }
    .card h3 {
      font-size: 1.1rem;
      font-weight: 700;
      margin-bottom: 8px;
    }
    .card p {
      font-size: 0.9rem;
      color: #666;
      line-height: 1.65;
    }

    /* ─── SHOWCASE STRIP ────────────────────────────── */
    .strip {
      background: var(--mint);
      padding: 56px 24px;
      text-align: center;
    }
    .strip h2 {
      font-size: clamp(1.4rem,3.5vw,2rem);
      font-weight: 900;
      margin-bottom: 10px;
    }
    .strip p {
      max-width: 520px;
      margin: 0 auto 32px;
      color: #3a5a4a;
      line-height: 1.7;
    }
    .color-swatches {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .swatch {
      width: 48px; height: 48px;
      border-radius: 50%;
      border: 3px solid rgba(255,255,255,.7);
      box-shadow: 0 4px 12px rgba(0,0,0,.12);
    }

    /* ─── TESTIMONIAL ───────────────────────────────── */
    .testimonial {
      padding: 72px 24px;
      max-width: 720px;
      margin: 0 auto;
      text-align: center;
    }
    .stars { font-size: 1.5rem; margin-bottom: 20px; }
    .quote {
      font-size: clamp(1.05rem, 2.5vw, 1.3rem);
      font-weight: 700;
      line-height: 1.65;
      color: var(--ink);
      font-style: italic;
    }
    .quote-author {
      margin-top: 20px;
      font-size: 0.85rem;
      color: #888;
    }

    /* ─── FOOTER CTA ────────────────────────────────── */
    .footer-cta {
      background: var(--ink);
      color: #fff;
      text-align: center;
      padding: 72px 24px;
    }
    .footer-cta h2 {
      font-size: clamp(1.8rem, 5vw, 3rem);
      font-weight: 900;
      margin-bottom: 16px;
    }
    .footer-cta p {
      font-size: 1rem;
      opacity: .7;
      margin-bottom: 36px;
      max-width: 480px;
      margin-left: auto;
      margin-right: auto;
      line-height: 1.7;
    }
    .cta-btn-light {
      background: var(--lemon);
      color: var(--ink);
    }
    .cta-btn-light:hover {
      box-shadow: 0 14px 30px rgba(246,224,107,.5);
    }

    .footer-note {
      margin-top: 32px;
      font-size: 0.75rem;
      opacity: .4;
    }

    @media (prefers-reduced-motion: reduce) {
      .fruit-chip { animation: none; }
    }
  </style>
</head>
<body>

<!-- ═══ HERO ═══════════════════════════════════════ -->
<section class="hero">
  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>

  <p class="hero-eyebrow">✦ جديد &nbsp;·&nbsp; مناسب لجميع الأعمار ✦</p>

  <h1 class="hero-title">
    كتاب تلوين<br>
    <span>الفواكه</span> 🍉
  </h1>

  <p class="hero-sub">
    رحلة ممتعة بالألوان مع أجمل الفواكه!<br>
    رسومات لطيفة تُنمّي الإبداع وتُقوّي مهارة الطفل.
  </p>

  <div class="fruits-row">
    <div class="fruit-chip">🍉</div>
    <div class="fruit-chip">🍊</div>
    <div class="fruit-chip">🍌</div>
    <div class="fruit-chip">🍐</div>
    <div class="fruit-chip">🍎</div>
  </div>

  <a class="cta-btn" href="https://alfan.link/rayanfacts6@gmail.com" target="_blank">احصل على نسختك الآن</a>
  <p class="badge">📦 متوفر بالنسخة الورقية والرقمية</p>
</section>

<!-- ═══ FEATURES ════════════════════════════════════ -->
<section class="features">
  <p class="section-label">لماذا هذا الكتاب؟</p>
  <h2 class="section-title">مميّزات تجعله مختلفاً</h2>

  <div class="cards">
    <div class="card">
      <div class="card-icon">🎨</div>
      <h3>رسومات احترافية</h3>
      <p>تصاميم بسيطة وجذابة مناسبة لأيدي الأطفال الصغيرة.</p>
    </div>
    <div class="card">
      <div class="card-icon">🧠</div>
      <h3>تنمية المهارات</h3>
      <p>يُعزّز التركيز والإدراك البصري والتناسق الحركي.</p>
    </div>
    <div class="card">
      <div class="card-icon">🌿</div>
      <h3>تعلّم عبر اللعب</h3>
      <p>يُعرّف الطفل بأسماء الفواكه وألوانها بأسلوب ممتع.</p>
    </div>
    <div class="card">
      <div class="card-icon">✏️</div>
      <h3>مرن وسهل الاستخدام</h3>
      <p>يناسب أقلام التلوين والألوان المائية والكراسات.</p>
    </div>
  </div>
</section>

<!-- ═══ COLOUR STRIP ════════════════════════════════ -->
<section class="strip">
  <h2>لوّن بكل الأشكال والألوان 🖍️</h2>
  <p>
    من البطيخ الأخضر المخطط إلى التفاح الأحمر الساطع —
    كل صفحة هي فرصة لابتكار لوحة فنية فريدة.
  </p>
  <div class="color-swatches">
    <div class="swatch" style="background:#E63946;"></div>
    <div class="swatch" style="background:#F4A261;"></div>
    <div class="swatch" style="background:#F6E06B;"></div>
    <div class="swatch" style="background:#6DAE74;"></div>
    <div class="swatch" style="background:#A8DADC;"></div>
    <div class="swatch" style="background:#D9607A;"></div>
  </div>
</section>

<!-- ═══ TESTIMONIAL ═════════════════════════════════ -->
<section class="testimonial">
  <div class="stars">⭐⭐⭐⭐⭐</div>
  <p class="quote">
    "ابنتي لا تتركه من بين يديها! الرسومات رائعة والأوراق عالية الجودة.
     أفضل هدية أطفال اشتريتها هذا العام."
  </p>
  <p class="quote-author">— أم سارة، 6 سنوات</p>
</section>

<!-- ═══ FOOTER CTA ═══════════════════════════════════ -->
<section class="footer-cta">
  <h2>هديةٌ تُلهم طفلك 🎁</h2>
  <p>
    سواء كان عيد ميلاد أو مناسبة مدرسية، كتاب تلوين الفواكه
    هو الهدية المثالية التي تجمع بين المتعة والتعليم.
  </p>
  <a class="cta-btn cta-btn-light" href="https://alfan.link/rayanfacts6@gmail.com" target="_blank">اطلبه الآن بسعر خاص</a>
  <p class="footer-note">© 2026 كتاب تلوين الفواكه · جميع الحقوق محفوظة</p>
</section>

</body>
</html>
