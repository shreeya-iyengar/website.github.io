<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shreeya Iyengar Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Alumni+Sans:ital,wght@0,100..900;1,100..900&family=Lexend:wght@100..900&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #25102E;
      --nav-bg: #290a3f;
      --accent-pink: #c9547a;
      --accent-green: #7ed957;
      --accent-cyan: #00d4ff;
      --text: #f0e8ff;
      --text-muted: #c4aee0;
      --btn-bg: #370f69;
      --btn-border: #e05575;
    }
 
    * { margin: 0; padding: 0; box-sizing: border-box; }
 
    body {
      background-color: var(--bg);
      font-family: 'Lexend', sans-serif;
      color: var(--text);
      min-height: 100vh;
    }
 
    /* NAV */
    nav {
      display: flex;
      justify-content: center;
      gap: 24px;
      padding: 24px 40px;
      background: var(--nav-bg);
    }
 
    nav button {
      cursor: pointer;
      color: var(--text);
      font-family: 'Lexend', sans-serif;
      font-size: 1rem;
      font-weight: 500;
      background: var(--btn-bg);
      border: 2px solid var(--btn-border);
      border-radius: 12px;
      padding: 10px 28px;
      transition: background 0.2s, transform 0.2s;
    }
 
    nav button:hover {
      background: var(--accent-pink);
      transform: translateY(-2px);
    }
 
    nav button.active {
      background: var(--accent-pink);
    }
 
    /* PAGES */
    .page { display: none; }
    .page.active { display: block; }
 
    /* ── ABOUT ME PAGE ── */
    .hero {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 60px;
      padding: 60px 80px;
      max-width: 1100px;
      margin: 0 auto;
    }
 
    .image-wrapper {
      position: relative;
      flex-shrink: 0;
      width: 260px;
      height: 300px;
    }
 
    .image-wrapper .blob-green {
      position: absolute;
      top: -18px; right: -18px;
      width: 220px; height: 260px;
      background: var(--accent-green);
      border-radius: 40px;
      z-index: 1;
    }
 
    .image-wrapper .blob-cyan {
      position: absolute;
      bottom: -18px; left: -18px;
      width: 200px; height: 240px;
      background: var(--accent-cyan);
      border-radius: 40px;
      z-index: 1;
    }
 
    .image-wrapper img {
      position: absolute;
      top: 0; left: 0;
      width: 240px; height: 290px;
      object-fit: cover;
      border-radius: 32px;
      z-index: 2;
    }
 
    .hero-text {
      max-width: 480px;
      animation: fadeUp 0.8s ease both;
    }
 
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }
 
    .hero-text h1 {
      font-family: 'Lexend', sans-serif;
      font-size: 3.2rem;
      font-weight: 700;
      color: var(--text);
      margin-bottom: 6px;
    }
 
    .underline-pink {
      display: block;
      width: 120px; height: 4px;
      background: var(--accent-pink);
      border-radius: 4px;
      margin-bottom: 24px;
      animation: growLine 0.6s 0.4s ease both;
      transform-origin: left;
    }
 
    @keyframes growLine {
      from { transform: scaleX(0); }
      to   { transform: scaleX(1); }
    }
 
    .hero-text p {
      font-size: 1rem;
      line-height: 1.75;
      color: var(--text-muted);
      margin-bottom: 16px;
    }
 
    .hero-text p span {
      color: var(--text);
      font-weight: 500;
    }
 
    .hero-text a.email {
      color: var(--accent-pink);
      text-decoration: none;
      font-weight: 500;
    }
 
    .hero-text a.email:hover { text-decoration: underline; }
 
    /* ── RESUME PAGE ── */
    .resume-container {
      max-width: 960px;
      margin: 40px auto;
      padding: 0 24px 60px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
    }
 
    .resume-label {
      background: var(--accent-green);
      color: #1a1a1a;
      font-size: 1.15rem;
      font-weight: 600;
      border-radius: 50px;
      padding: 12px 48px;
    }
 
    .download-btn {
      background: var(--btn-bg);
      border: 2px solid var(--accent-cyan);
      color: var(--accent-cyan);
      font-family: 'Lexend', sans-serif;
      font-size: 0.8rem;
      font-weight: 500;
      border-radius: 10px;
      padding: 6px 18px;
      text-decoration: none;
      transition: background 0.2s, transform 0.2s;
    }
 
    .download-btn:hover {
      background: var(--accent-cyan);
      color: #1a1a1a;
      transform: translateY(-2px);
    }
 
    .pdf-wrapper {
      width: 100%;
      background: #e8e8e8;
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 8px 40px rgba(0,0,0,0.4);
    }
 
    .pdf-wrapper iframe {
      width: 100%;
      height: 90vh;
      border: none;
      display: block;
    }
  </style>
</head>
<body>
 
  <nav>
    <button onclick="showPage('about')" id="btn-about" class="active">About Me</button>
    <button onclick="showPage('projects')" id="btn-projects">Projects</button>
    <button onclick="showPage('resume')" id="btn-resume">Resume</button>
  </nav>
 
  <!-- ABOUT ME PAGE -->
  <div id="page-about" class="page active">
    <section class="hero">
      <div class="image-wrapper">
        <div class="blob-green"></div>
        <div class="blob-cyan"></div>
        <img src="Shreeyacroppedwebsite.png" alt="Shreeya Iyengar">
      </div>
      <div class="hero-text">
        <h1>Hello!</h1>
        <span class="underline-pink"></span>
        <p>My name is <span>Shreeya Iyengar</span>, and I am a sophomore <span>Electrical and Computer Engineering</span> student at Vanderbilt University (graduating May 2029).</p>
        <p>This website is to showcase personal ECE projects and endeavors. I am always open to connecting — whether to discuss ideas, collaborations, or career opportunities! You can contact me at <a href="mailto:shreeya.iyengar@vanderbilt.edu" class="email">shreeya.iyengar@vanderbilt.edu</a>.</p>
      </div>
    </section>
  </div>
 
  <!-- RESUME PAGE -->
  <div id="page-resume" class="page">
    <div class="resume-container">
      <div class="resume-label">Updated Resume</div>
      <a href="ShreeyaIyengarOfficialResume.pdf" download class="download-btn">⬇ Download Resume</a>
      <div class="pdf-wrapper">
        <!-- Replace "your-resume.pdf" with your actual PDF filename -->
        <iframe src="ShreeyaIyengarOfficialResume.pdf" title="Shreeya Iyengar Resume"></iframe>
      </div>
    </div>
  </div>
 
  <!-- PROJECTS PAGE -->
  <div id="page-projects" class="page">
    <div style="text-align:center; padding: 80px 40px;">
      <h1 style="font-family:'Lexend',sans-serif; font-size:2.5rem;">Projects</h1>
      <p style="color: var(--text-muted); margin-top: 16px;">Coming soon!</p>
    </div>
  </div>
 
  <script>
    function showPage(name) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
      document.getElementById('page-' + name).classList.add('active');
      document.getElementById('btn-' + name).classList.add('active');
    }
  </script>
 
</body>
</html>
