import os, zipfile

base = "/mnt/data/dovud_portfolio"
os.makedirs(base, exist_ok=True)

html = r'''<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Dovud — web dasturlashni o‘rganuvchi va zamonaviy veb-loyihalar yaratuvchi. Portfolio, loyihalar va aloqa.">
  <meta name="theme-color" content="#080b10">
  <title>Dovud | Developer Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="ambient ambient-one"></div><div class="ambient ambient-two"></div>
  <header class="site-header">
    <a class="logo" href="#home" aria-label="Dovud bosh sahifa"><span class="logo-mark">D</span><span>DOVUD<span class="accent">.</span></span></a>
    <button class="menu-toggle" aria-label="Menyuni ochish" aria-expanded="false">☰</button>
    <nav class="nav" id="nav">
      <a href="#home" class="active">Bosh sahifa</a><a href="#about">Men haqimda</a><a href="#skills">Ko‘nikmalar</a><a href="#projects">Loyihalar</a><a href="#contact" class="nav-cta">Bog‘lanish <span>↗</span></a>
    </nav>
  </header>

  <main>
    <section class="hero section" id="home">
      <div class="hero-copy reveal">
        <div class="eyebrow"><span class="status-dot"></span> WEB DEVELOPER • O‘RGANISHDA</div>
        <h1>G‘oyalarni<br> <span class="gradient-text">raqamli olamga</span><br>olib chiqaman.</h1>
        <p class="hero-text">Salom! Men Dovudman. Zamonaviy, chiroyli va qulay veb-saytlar yaratishni o‘rganyapman — har bir loyiha yangi tajriba.</p>
        <div class="hero-actions"><a class="button button-primary" href="#projects">Loyihalarimni ko‘rish <span>↘</span></a><a class="button button-ghost" href="#contact">Men bilan bog‘lanish</a></div>
        <div class="hero-stats"><div><strong>04<span>+</span></strong><small>Shaxsiy g‘oyalar</small></div><div><strong>03</strong><small>Asosiy texnologiya</small></div><div><strong>∞</strong><small>Yangi g‘oyalar</small></div></div>
      </div>
      <div class="hero-visual reveal">
        <div class="orbit orbit-a"></div><div class="orbit orbit-b"></div>
        <div class="code-window">
          <div class="window-top"><div class="window-dots"><i></i><i></i><i></i></div><span>developer.js</span><span class="window-lock">⌘</span></div>
          <div class="code-content">
            <div><span class="line-no">01</span><span class="purple">const</span> developer = {</div>
            <div><span class="line-no">02</span>&nbsp;&nbsp;name: <span class="green">'Dovud'</span>,</div>
            <div><span class="line-no">03</span>&nbsp;&nbsp;focus: <span class="green">'Web development'</span>,</div>
            <div><span class="line-no">04</span>&nbsp;&nbsp;skills: [</div>
            <div><span class="line-no">05</span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="orange">'HTML'</span>, <span class="orange">'CSS'</span>,</div>
            <div><span class="line-no">06</span>&nbsp;&nbsp;&nbsp;&nbsp;<span class="orange">'JavaScript'</span></div>
            <div><span class="line-no">07</span>&nbsp;&nbsp;],</div>
            <div><span class="line-no">08</span>&nbsp;&nbsp;dream: <span class="green">'Build something great'</span></div>
            <div><span class="line-no">09</span>};<span class="cursor">▍</span></div>
          </div>
          <div class="code-footer"><span><i class="tiny-dot"></i> Doim o‘rganishda</span><span>UTF-8&nbsp; • &nbsp;JavaScript</span></div>
        </div>
        <div class="floating-chip chip-html"><b>5</b><span>HTML</span></div><div class="floating-chip chip-css"><b>✦</b><span>CSS</span></div><div class="floating-chip chip-js"><b>JS</b><span>JavaScript</span></div>
      </div>
      <a class="scroll-hint" href="#about"><span class="scroll-line"></span> PASTGA TUSHING</a>
    </section>

    <section class="section about-section" id="about">
      <div class="section-heading reveal"><span class="section-index">01 / MEN HAQIMDA</span><h2>O‘rganaman. <span class="gradient-text">Yarataman.</span><br>Rivojlanaman.</h2></div>
      <div class="about-grid">
        <div class="about-card reveal"><div class="about-icon">✳</div><h3>Qiziquvchan fikrlash</h3><p>Har bir yangi g‘oya menga yangi narsani o‘rganish va sinab ko‘rish imkonini beradi.</p></div>
        <div class="about-card reveal"><div class="about-icon">⌘</div><h3>Amaliy loyihalar</h3><p>O‘rganganlarimni kichik veb-loyihalarda sinab, tajribamni bosqichma-bosqich oshiraman.</p></div>
        <div class="about-card reveal"><div class="about-icon">↗</div><h3>Katta maqsadlar</h3><p>Maqsadim — foydali, tezkor va barcha qurilmalarda yaxshi ishlaydigan saytlar yaratish.</p></div>
      </div>
    </section>

    <section class="section skills-section" id="skills">
      <div class="section-heading reveal"><span class="section-index">02 / KO‘NIKMALAR</span><h2>Asboblarim <span class="gradient-text">to‘plami.</span></h2><p class="section-subtitle">Hozir o‘rganayotgan va loyihalarimda ishlatadigan texnologiyalar.</p></div>
      <div class="skills-grid">
        <article class="skill-card reveal"><div class="skill-top"><span class="skill-logo html-logo">5</span><span class="skill-level">01</span></div><h3>HTML5</h3><p>Sayt tuzilishi va semantik teglar</p><div class="skill-track"><span style="width:78%"></span></div><small>O‘rganish jarayonida</small></article>
        <article class="skill-card reveal"><div class="skill-top"><span class="skill-logo css-logo">✦</span><span class="skill-level">02</span></div><h3>CSS3</h3><p>Dizayn, moslashuvchanlik va animatsiya</p><div class="skill-track"><span style="width:65%"></span></div><small>O‘rganish jarayonida</small></article>
        <article class="skill-card reveal"><div class="skill-top"><span class="skill-logo js-logo">JS</span><span class="skill-level">03</span></div><h3>JavaScript</h3><p>Interaktivlik va foydalanuvchi harakatlari</p><div class="skill-track"><span style="width:35%"></span></div><small>Yangi o‘rganilmoqda</small></article>
        <article class="skill-card reveal"><div class="skill-top"><span class="skill-logo git-logo">⌘</span><span class="skill-level">04</span></div><h3>Git & GitHub</h3><p>Kodni saqlash va saytni internetga joylash</p><div class="skill-track"><span style="width:42%"></span></div><small>Amaliyotda</small></article>
      </div>
      <p class="note">Ko‘nikma ko‘rsatkichlari taxminiy va tahrirlash uchun berilgan — o‘z darajangizga moslab o‘zgartiring.</p>
    </section>

    <section class="section projects-section" id="projects">
      <div class="section-heading reveal"><span class="section-index">03 / TANLANGAN LOYIHALAR</span><h2>G‘oyalarim <span class="gradient-text">harakatda.</span></h2><p class="section-subtitle">Quyidagi loyihalar — portfoliodagi ishlarim va rivojlantirmoqchi bo‘lgan g‘oyalarim.</p></div>
      <div class="projects-grid">
        <article class="project-card project-ai reveal"><div class="project-art ai-art"><div class="ai-orb"></div><span class="art-label">AI / CREATIVE</span><span class="art-symbol">✳</span></div><div class="project-info"><div class="project-meta"><span>01 — AI PLATFORM</span><span class="project-arrow">↗</span></div><h3>Dovud AI</h3><p>Sun’iy intellekt va ijodiy texnologiyalarga bag‘ishlangan zamonaviy loyiha g‘oyasi.</p><div class="tags"><span>HTML</span><span>CSS</span><span>JavaScript</span></div><a class="text-link" href="#contact">Loyiha haqida <span>→</span></a></div></article>
        <article class="project-card project-truck reveal"><div class="project-art truck-art"><div class="road-lines"></div><div class="truck-emoji">🚛</div><span class="art-label">AUTOMOTIVE / BLOG</span></div><div class="project-info"><div class="project-meta"><span>02 — TRUCK CULTURE</span><span class="project-arrow">↗</span></div><h3>Truck World</h3><p>Amerika yuk mashinalari, kompaniyalar va ulkan trucklar olami haqidagi sayt.</p><div class="tags"><span>HTML</span><span>CSS</span><span>Responsive</span></div><a class="text-link" href="#contact">Loyiha haqida <span>→</span></a></div></article>
        <article class="project-card project-kidis reveal"><div class="project-art kidis-art"><div class="kidis-stars">✦　✧　✦</div><div class="kidis-word">ki<span>di</span>s<span class="kidis-dot">.</span></div><span class="art-label">EDTECH / LEARNING</span></div><div class="project-info"><div class="project-meta"><span>03 — BOLALAR TA’LIMI</span><span class="project-arrow">↗</span></div><h3>Kidis Learning</h3><p>Bolalarga ingliz va rus tillarini o‘yinlar orqali o‘rgatishga mo‘ljallangan platforma.</p><div class="tags"><span>Education</span><span>JavaScript</span><span>UI Design</span></div><a class="text-link" href="#contact">Loyiha haqida <span>→</span></a></div></article>
        <article class="project-card project-pizza reveal"><div class="project-art pizza-art"><div class="pizza-circle">814<span>✦</span></div><span class="art-label">FOOD / ORDERING</span></div><div class="project-info"><div class="project-meta"><span>04 — FOOD SERVICE</span><span class="project-arrow">↗</span></div><h3>Pizza 814</h3><p>Menyu, buyurtma va aloqa bo‘limlari bo‘lgan pizza xizmati sayti g‘oyasi.</p><div class="tags"><span>HTML</span><span>CSS</span><span>Order UI</span></div><a class="text-link" href="#contact">Loyiha haqida <span>→</span></a></div></article>
      </div>
    </section>

    <section class="contact-section section" id="contact">
      <div class="contact-panel reveal"><div class="contact-glow"></div><div class="contact-copy"><span class="section-index">04 / ALOQA</span><h2>Birgalikda <span class="gradient-text">nimadir</span><br>ajoyib yaratamizmi?</h2><p>Loyiha, taklif yoki hamkorlik haqida gaplashmoqchimisiz? Menga yozing.</p><a class="button button-primary" href="https://t.me/" target="_blank" rel="noreferrer">Telegram orqali yozish <span>↗</span></a></div><div class="contact-decoration"><div class="contact-ring ring-one"></div><div class="contact-ring ring-two"></div><span>D.</span></div></div>
      <div class="contact-details reveal"><div><small>ISMI</small><strong>Dovud</strong></div><div><small>YO‘NALISH</small><strong>Web development</strong></div><div><small>ASOSIY TIL</small><strong>O‘zbekcha</strong></div><button class="copy-email" id="copyEmail" type="button" data-email="EMAILINGIZNI_SHU_YERGA_YOZING">Kontaktni nusxalash <span>⧉</span></button></div>
      <p class="contact-hint">Telegram havolasi va kontakt ma’lumotlarini o‘zingiznikiga almashtirishni unutmang.</p>
    </section>
  </main>

  <footer class="footer"><a class="logo" href="#home"><span class="logo-mark">D</span><span>DOVUD<span class="accent">.</span></span></a><p>G‘oya bilan boshlandi. Mehnat bilan rivojlanadi.</p><span>© <span id="year"></span> Dovud. Barcha huquqlar himoyalangan.</span></footer>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>
  <script src="script.js"></script>
</body>
</html>
'''

css = r''' :root{--bg:#080b10;--panel:#0e131b;--panel2:#111923;--text:#f3f6fb;--muted:#9aa7b8;--line:rgba(255,255,255,.09);--green:#b6ff52;--cyan:#55e6d1;--purple:#a68cff;--font:'DM Sans',sans-serif;--display:'Space Grotesk',sans-serif}
*{box-sizing:border-box;margin:0;padding:0}html{scroll-behavior:smooth;scroll-padding-top:95px}body{background:var(--bg);color:var(--text);font-family:var(--font);line-height:1.6;overflow-x:hidden}a{color:inherit;text-decoration:none}button{font:inherit}.ambient{position:absolute;pointer-events:none;filter:blur(95px);opacity:.12;border-radius:50%;z-index:-1}.ambient-one{width:420px;height:420px;background:var(--green);top:120px;right:-220px}.ambient-two{width:350px;height:350px;background:#5c4cff;top:900px;left:-200px}.site-header{height:82px;max-width:1200px;padding:0 28px;margin:auto;display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid var(--line);position:relative;z-index:5}.logo{display:flex;align-items:center;gap:10px;font-family:var(--display);font-weight:700;letter-spacing:2px;font-size:15px}.logo-mark{display:grid;place-items:center;width:34px;height:34px;background:var(--green);color:#10150b;border-radius:10px;font-size:19px;letter-spacing:0;box-shadow:0 0 26px #b6ff5230}.accent{color:var(--green)}.nav{display:flex;align-items:center;gap:31px}.nav a{font-size:12px;color:var(--muted);transition:.25s}.nav a:hover,.nav a.active{color:var(--text)}.nav .nav-cta{border:1px solid #ffffff28;padding:10px 15px;border-radius:8px;color:var(--text)}.nav-cta span{color:var(--green);margin-left:8px}.menu-toggle{display:none;background:transparent;border:1px solid var(--line);color:var(--text);border-radius:8px;padding:7px 11px}.section{max-width:1200px;margin:auto;padding:120px 28px}.hero{min-height:700px;display:grid;grid-template-columns:1.05fr .95fr;align-items:center;gap:55px;position:relative;padding-top:95px;padding-bottom:115px}.eyebrow,.section-index{font-size:10px;letter-spacing:2.4px;font-weight:700;color:var(--green)}.eyebrow{display:inline-flex;align-items:center;gap:10px;border:1px solid #b6ff5233;border-radius:100px;padding:9px 13px;background:#b6ff5208}.status-dot,.tiny-dot{width:7px;height:7px;border-radius:50%;background:var(--green);box-shadow:0 0 12px var(--green)}h1,h2,h3{font-family:var(--display);line-height:1.13;letter-spacing:-1.5px}h1{font-size:clamp(43px,5.5vw,72px);font-weight:600;margin:26px 0 20px} .gradient-text{background:linear-gradient(100deg,var(--green),var(--cyan));-webkit-background-clip:text;background-clip:text;color:transparent}.hero-text{max-width:500px;color:var(--muted);font-size:14px;line-height:1.9}.hero-actions{display:flex;gap:12px;flex-wrap:wrap;margin-top:30px}.button{display:inline-flex;align-items:center;gap:18px;justify-content:center;padding:14px 18px;border-radius:9px;font-size:12px;font-weight:700;transition:transform .25s,box-shadow .25s}.button:hover{transform:translateY(-3px)}.button-primary{background:var(--green);color:#10150b;box-shadow:0 8px 30px #b6ff5218}.button-primary:hover{box-shadow:0 10px 35px #b6ff5235}.button-ghost{border:1px solid var(--line);color:var(--text)}.button span{font-size:16px}.hero-stats{display:flex;gap:37px;margin-top:52px}.hero-stats div{display:flex;flex-direction:column;gap:3px}.hero-stats strong{font-family:var(--display);font-size:24px}.hero-stats strong span{color:var(--green)}.hero-stats small{font-size:10px;color:var(--muted)}.hero-visual{height:440px;position:relative;display:grid;place-items:center}.orbit{position:absolute;border:1px solid #b6ff5218;border-radius:50%;aspect-ratio:1;animation:spin 30s linear infinite}.orbit-a{width:430px}.orbit-b{width:350px;border-style:dashed;animation-direction:reverse;animation-duration:42s}.code-window{width:min(100%,420px);position:relative;z-index:2;background:#0c1118;border:1px solid #ffffff1b;border-radius:15px;box-shadow:0 30px 90px #0009,0 0 70px #b6ff5209;overflow:hidden;transform:perspective(1000px) rotateY(-5deg) rotateX(2deg);animation:float 6s ease-in-out infinite}.window-top{height:43px;border-bottom:1px solid var(--line);display:flex;align-items:center;padding:0 15px;gap:12px;color:#728092;font-size:10px}.window-dots{display:flex;gap:5px}.window-dots i{width:7px;height:7px;border-radius:50%;background:#ff6f68}.window-dots i:nth-child(2){background:#ffd166}.window-dots i:nth-child(3){background:#6ee7a0}.window-top>span:nth-child(2){margin:auto}.window-lock{color:var(--green)}.code-content{font:12px/2.1 ui-monospace,SFMono-Regular,Consolas,monospace;padding:22px 12px 23px;white-space:nowrap}.line-no{display:inline-block;width:30px;color:#4b596a;text-align:right;margin-right:15px}.purple{color:#c2a2ff}.green{color:#b6ff86}.orange{color:#ffc078}.cursor{color:var(--green);animation:blink 1s steps(2) infinite}.code-footer{display:flex;justify-content:space-between;border-top:1px solid var(--line);padding:12px 15px;color:#718093;font-size:9px}.code-footer span:first-child{display:flex;align-items:center;gap:7px}.tiny-dot{width:5px;height:5px}.floating-chip{position:absolute;z-index:3;background:#111923;border:1px solid #ffffff1c;border-radius:12px;box-shadow:0 12px 35px #0007;padding:10px 13px;display:flex;align-items:center;gap:9px;font-size:10px;color:var(--muted);animation:float 5s ease-in-out infinite}.floating-chip b{font-family:var(--display);font-size:17px}.chip-html{top:57px;left:4px}.chip-html b{color:#ff805e}.chip-css{right:0;top:104px;animation-delay:-1.5s}.chip-css b{color:#6c9cff}.chip-js{bottom:45px;left:20px;animation-delay:-2.5s}.chip-js b{color:#f8d65c}.scroll-hint{position:absolute;bottom:28px;left:28px;display:flex;align-items:center;gap:12px;color:#778395;font-size:9px;letter-spacing:2px}.scroll-line{height:1px;width:38px;background:var(--green)}.section-heading{margin-bottom:45px}.section-heading h2,.contact-copy h2{font-size:clamp(34px,4vw,52px);margin-top:18px}.section-subtitle{color:var(--muted);font-size:13px;margin-top:15px;max-width:570px}.about-section{padding-top:80px}.about-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:15px}.about-card{background:linear-gradient(140deg,#111923,#0b0f15);border:1px solid var(--line);border-radius:13px;padding:26px;transition:.3s}.about-card:hover,.skill-card:hover,.project-card:hover{border-color:#b6ff5255;transform:translateY(-5px)}.about-icon{width:39px;height:39px;border-radius:10px;background:#b6ff5212;color:var(--green);display:grid;place-items:center;font-size:22px;margin-bottom:22px}.about-card h3{font-size:17px;letter-spacing:-.5px;margin-bottom:11px}.about-card p,.project-info p{font-size:12px;line-height:1.85;color:var(--muted)}.skills-section{padding-top:70px}.skills-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:13px}.skill-card{background:var(--panel);border:1px solid var(--line);border-radius:13px;padding:22px 20px;transition:.3s}.skill-top{display:flex;justify-content:space-between;align-items:center;margin-bottom:24px}.skill-logo{width:43px;height:43px;display:grid;place-items:center;border-radius:10px;font-family:var(--display);font-size:22px;font-weight:700}.html-logo{background:#ff805e18;color:#ff805e}.css-logo{background:#6c9cff18;color:#6c9cff}.js-logo{background:#f8d65c18;color:#f8d65c;font-size:16px}.git-logo{background:#ff8b6c18;color:#ff8b6c}.skill-level{font-size:10px;color:#5d6a7a}.skill-card h3{font-size:18px;letter-spacing:-.5px}.skill-card p{min-height:38px;font-size:11px;color:var(--muted);margin:8px 0 20px}.skill-track{height:3px;background:#ffffff12;border-radius:9px;overflow:hidden}.skill-track span{height:100%;display:block;background:linear-gradient(90deg,var(--green),var(--cyan));border-radius:9px}.skill-card small{display:block;font-size:9px;color:#778395;margin-top:10px}.note{font-size:10px;color:#667386;margin-top:18px}.projects-section{padding-top:75px}.projects-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:18px}.project-card{background:var(--panel);border:1px solid var(--line);border-radius:15px;overflow:hidden;transition:.3s}.project-art{height:230px;position:relative;overflow:hidden;display:grid;place-items:center}.art-label{position:absolute;top:18px;left:19px;font-size:9px;letter-spacing:2px;color:#ffffffa6}.ai-art{background:radial-gradient(ellipse at 50% 65%,#304b2c,#111a1c 45%,#0b1018 75%)}.ai-orb{width:145px;height:145px;border-radius:50%;background:radial-gradient(circle at 30% 25%,#e2ffc0,#a7ff4c 18%,#3b8c66 45%,#102d3b 70%);box-shadow:0 0 50px #a7ff4c45, inset -20px -20px 35px #07131d;position:relative;animation:float 6s ease-in-out infinite}.ai-orb:after{content:"";position:absolute;inset:-22px;border:1px solid #b6ff5260;border-radius:50%;transform:rotateX(65deg) rotateZ(-25deg)}.art-symbol{position:absolute;right:24px;bottom:5px;font-size:100px;color:#b6ff5210}.truck-art{background:linear-gradient(160deg,#172635,#0c121a 70%)}.truck-emoji{font-size:104px;filter:drop-shadow(0 15px 16px #0008);z-index:1;animation:truckFloat 4s ease-in-out infinite}.road-lines{position:absolute;bottom:0;width:130%;height:70px;background:repeating-linear-gradient(90deg,transparent 0 55px,#b6ff5240 55px 90px,transparent 90px 145px);transform:perspective(100px) rotateX(35deg);opacity:.7}.kidis-art{background:radial-gradient(circle at 50% 50%,#40306e,#17182f 70%)}.kidis-stars{position:absolute;top:25px;left:0;right:0;text-align:center;color:#ffe98b;letter-spacing:10px}.kidis-word{font-family:var(--display);font-weight:700;font-size:74px;letter-spacing:-6px;color:#fff;text-shadow:0 5px 35px #a68cff66}.kidis-word span{color:#a9ffcf}.kidis-dot{color:#ffe98b}.pizza-art{background:radial-gradient(circle at center,#65261e,#211317 65%,#101015)}.pizza-circle{width:130px;height:130px;border-radius:50%;border:2px solid #ff8a66;display:grid;place-items:center;font-family:var(--display);font-size:42px;font-weight:700;color:#fff3e8;box-shadow:0 0 0 10px #ff8a6614,0 0 60px #ff5a3333;position:relative}.pizza-circle span{position:absolute;right:10px;top:10px;color:#ffc06a;font-size:17px}.project-info{padding:22px 23px 24px}.project-meta{display:flex;justify-content:space-between;color:#778395;font-size:9px;letter-spacing:1.3px}.project-arrow{font-size:18px;color:var(--green)}.project-info h3{font-size:23px;margin:14px 0 8px;letter-spacing:-.8px}.project-info p{max-width:440px;min-height:45px}.tags{display:flex;gap:7px;flex-wrap:wrap;margin:18px 0}.tags span{border:1px solid var(--line);border-radius:5px;padding:5px 8px;font-size:9px;color:#b2bdcb}.text-link{display:inline-flex;align-items:center;gap:10px;font-size:11px;font-weight:700;color:var(--green);margin-top:3px}.text-link span{transition:transform .2s}.text-link:hover span{transform:translateX(4px)}.contact-section{padding-top:75px;padding-bottom:70px}.contact-panel{min-height:330px;background:linear-gradient(115deg,#131d23,#10151d 65%);border:1px solid #b6ff5225;border-radius:18px;padding:48px;position:relative;overflow:hidden;display:flex;align-items:center}.contact-copy{position:relative;z-index:2}.contact-copy h2{font-size:clamp(33px,4vw,48px)}.contact-copy p{font-size:12px;color:var(--muted);max-width:440px;margin:17px 0 25px}.contact-decoration{position:absolute;right:7%;top:50%;transform:translateY(-50%);width:250px;height:250px;display:grid;place-items:center}.contact-decoration>span{font-family:var(--display);font-weight:700;font-size:90px;color:var(--green);text-shadow:0 0 50px #b6ff5255}.contact-ring{position:absolute;border:1px solid #b6ff5245;border-radius:50%;width:100%;height:100%;animation:spin 24s linear infinite}.ring-two{width:75%;height:75%;border-color:#55e6d14a;animation-direction:reverse;animation-duration:17s}.contact-glow{position:absolute;width:280px;height:280px;right:8%;background:var(--green);filter:blur(120px);opacity:.1}.contact-details{display:grid;grid-template-columns:1fr 1fr 1fr auto;gap:25px;padding:27px 3px;border-bottom:1px solid var(--line)}.contact-details div{display:flex;flex-direction:column;gap:7px}.contact-details small{font-size:9px;color:#758295;letter-spacing:1.5px}.contact-details strong{font-size:12px;font-weight:500}.copy-email{align-self:center;border:1px solid var(--line);border-radius:8px;padding:10px 12px;background:transparent;color:var(--text);font-size:10px;cursor:pointer}.copy-email span{color:var(--green);margin-left:9px}.contact-hint{font-size:10px;color:#697688;margin-top:12px}.footer{max-width:1200px;margin:auto;padding:25px 28px 35px;display:flex;align-items:center;justify-content:space-between;gap:20px;border-top:1px solid var(--line);color:#697688;font-size:10px}.footer p{margin-right:auto;margin-left:20px}.footer .logo{color:var(--text);font-size:12px}.footer .logo-mark{width:28px;height:28px;font-size:15px}.toast{position:fixed;bottom:25px;left:50%;transform:translate(-50%,20px);background:#17221b;border:1px solid #b6ff5255;color:var(--green);border-radius:9px;padding:11px 16px;font-size:12px;opacity:0;pointer-events:none;transition:.3s;z-index:20}.toast.show{opacity:1;transform:translate(-50%,0)}.reveal{opacity:0;transform:translateY(22px);transition:opacity .7s ease,transform .7s ease}.reveal.visible{opacity:1;transform:translateY(0)}@keyframes spin{to{transform:rotate(360deg)}}@keyframes float{0%,100%{translate:0 0}50%{translate:0 -10px}}@keyframes truckFloat{0%,100%{transform:translateY(0) rotate(-1deg)}50%{transform:translateY(-7px) rotate(1deg)}}@keyframes blink{50%{opacity:0}}
@media(max-width:900px){.hero{gap:20px;grid-template-columns:1fr 1fr}.hero-stats{gap:22px}.orbit-a{width:340px}.orbit-b{width:280px}.code-content{font-size:10px}.skills-grid{grid-template-columns:repeat(2,1fr)}.contact-decoration{right:-3%;opacity:.65}.contact-details{grid-template-columns:repeat(2,1fr)}}
@media(max-width:680px){.site-header{height:70px;padding:0 20px}.menu-toggle{display:block}.nav{display:none;position:absolute;top:69px;left:12px;right:12px;padding:17px;background:#0e131b;border:1px solid var(--line);border-radius:12px;flex-direction:column;align-items:stretch;gap:0;box-shadow:0 20px 40px #0009}.nav.open{display:flex}.nav a{padding:13px 10px}.nav .nav-cta{margin-top:5px;text-align:center}.section{padding:82px 20px}.hero{display:flex;flex-direction:column;align-items:stretch;gap:10px;padding-top:65px;padding-bottom:105px}.hero h1{font-size:clamp(42px,12vw,62px)}.hero-text{font-size:13px}.hero-visual{height:370px;margin-top:20px}.code-window{width:min(100%,390px)}.code-content{font-size:10px;padding:17px 7px}.line-no{width:20px;margin-right:8px}.orbit-a{width:320px}.orbit-b{width:260px}.chip-html{left:0;top:25px}.chip-css{right:0;top:65px}.chip-js{left:5px;bottom:20px}.scroll-hint{left:20px;bottom:25px}.about-section{padding-top:60px}.about-grid{grid-template-columns:1fr}.about-card{padding:22px}.about-icon{margin-bottom:14px}.section-heading{margin-bottom:30px}.section-heading h2,.contact-copy h2{font-size:36px}.skills-grid{gap:10px}.skill-card{padding:16px 14px}.skill-card p{font-size:10px}.projects-grid{grid-template-columns:1fr;gap:14px}.project-art{height:200px}.project-info{padding:20px}.contact-panel{padding:30px 23px;min-height:370px;align-items:flex-start}.contact-copy h2{font-size:34px}.contact-decoration{width:155px;height:155px;right:-15px;top:auto;bottom:-25px;transform:none;opacity:.38}.contact-decoration>span{font-size:60px}.contact-details{gap:22px 12px}.footer{padding:24px 20px;flex-wrap:wrap}.footer p{order:3;width:100%;margin:0}.footer>span{font-size:9px}}@media(prefers-reduced-motion:reduce){*,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;scroll-behavior:auto!important;transition-duration:.01ms!important}.reveal{opacity:1;transform:none}}
'''

js = r'''const menuButton = document.querySelector('.menu-toggle');
const nav = document.querySelector('.nav');

menuButton.addEventListener('click', () => {
  const isOpen = nav.classList.toggle('open');
  menuButton.setAttribute('aria-expanded', String(isOpen));
  menuButton.textContent = isOpen ? '✕' : '☰';
});

document.querySelectorAll('.nav a').forEach(link => {
  link.addEventListener('click', () => {
    nav.classList.remove('open');
    menuButton.setAttribute('aria-expanded', 'false');
    menuButton.textContent = '☰';
  });
});

const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
      revealObserver.unobserve(entry.target);
    }
  });
}, { threshold: 0.12 });
document.querySelectorAll('.reveal').forEach(element => revealObserver.observe(element));

const sections = document.querySelectorAll('main section[id]');
const navLinks = document.querySelectorAll('.nav a[href^="#"]');
const sectionObserver = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      navLinks.forEach(link => link.classList.toggle('active', link.getAttribute('href') === `#${entry.target.id}`));
    }
  });
}, { rootMargin: '-35% 0px -55% 0px' });
sections.forEach(section => sectionObserver.observe(section));

document.getElementById('year').textContent = new Date().getFullYear();

const copyButton = document.getElementById('copyEmail');
const toast = document.getElementById('toast');
let toastTimer;
copyButton.addEventListener('click', async () => {
  const contact = copyButton.dataset.email;
  if (!contact || contact === 'EMAILINGIZNI_SHU_YERGA_YOZING') {
    showToast('Avval kontakt ma’lumotini script.js ichida emas, index.html ichida almashtiring.');
    return;
  }
  try {
    await navigator.clipboard.writeText(contact);
    showToast('Kontakt nusxalandi!');
  } catch {
    showToast('Kontakt: ' + contact);
  }
});
function showToast(message) {
  toast.textContent = message;
  toast.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => toast.classList.remove('show'), 3200);
}
'''

readme = '''# Dovud Portfolio

Zamonaviy, moslashuvchan portfolio sayti. HTML, CSS va JavaScript alohida fayllarda.

## Ishga tushirish
1. ZIP faylni chiqarib oling.
2. `index.html` faylini brauzerda oching.
3. Kodni tahrirlash uchun papkani VS Code’da oching.

## O‘zingizga moslash
- `index.html` ichida ism, loyiha tavsiflari va aloqa havolasini yangilang.
- Telegram tugmasidagi `https://t.me/` manzilini o‘z profilingiz havolasiga almashtiring.
- Kontaktni nusxalash tugmasidagi `data-email` qiymatini haqiqiy kontakt bilan almashtiring.
- `style.css` ichida ranglar `:root` qismida boshqariladi.

## GitHub Pages orqali internetga chiqarish
1. GitHub’da yangi repository yarating.
2. `index.html`, `style.css`, `script.js` fayllarini repository’ga yuklang.
3. Repository → Settings → Pages bo‘limiga kiring.
4. Build and deployment ichida `Deploy from a branch` ni tanlang, `main` va `/ (root)` ni belgilang, Save bosing.
5. Bir oz kuting — GitHub Pages sayt havolasini ko‘rsatadi.

Eslatma: loyiha kartalari portfolioda namuna sifatida berilgan. Har bir loyiha tayyor va internetda ishlayapti deb da’vo qilmaydi; haqiqiy havolalaringiz bo‘lsa, ularni qo‘shing.
'''
for name, content in [("index.html", html), ("style.css", css), ("script.js", js), ("README.md", readme)]:
    with open(os.path.join(base, name), "w", encoding="utf-8") as f:
        f.write(content)

zip_path = "/mnt/data/Dovud_Portfolio.zip"
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for name in ["index.html", "style.css", "script.js", "README.md"]:
        z.write(os.path.join(base, name), arcname=f"Dovud_Portfolio/{name}")

print("Tayyor fayllar:")
print(zip_path)
print(os.path.join(base, "index.html"))
