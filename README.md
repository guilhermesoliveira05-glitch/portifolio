# portifolio

<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Portfólio — Guilherme dos Santos</title>
  <meta name="description" content="Portfólio de projetos — Home, Sobre, Contato e Catálogo" />
  <style>
    /* ---------------------- Reset simples ---------------------- */
    :root{
      --bg:#0f1724; /* escuro */
      --card:#0b1220;
      --muted:#98a0b3;
      --accent:#7c3aed;
      --glass: rgba(255,255,255,0.04);
      --radius:14px;
      --maxw:1100px;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      background:linear-gradient(180deg,var(--bg),#071026 120%);
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      padding:24px 16px;
      display:flex;
      justify-content:center;
    }
    .wrap{width:100%;max-width:var(--maxw)}

    /* ---------------------- Header / Nav ---------------------- */
    header{
      display:flex;align-items:center;justify-content:space-between;
      gap:16px;margin-bottom:28px;
    }
    .brand{display:flex;align-items:center;gap:12px}
    .logo{
      width:52px;height:52px;border-radius:12px;background:linear-gradient(135deg,var(--accent),#5eead4);
      display:flex;align-items:center;justify-content:center;font-weight:700;color:#041025;font-size:20px;box-shadow:0 6px 18px rgba(124,58,237,0.18)
    }
    .brand h1{font-size:18px;margin:0}
    nav{display:flex;gap:12px;align-items:center}
    nav a{
      color:var(--muted);text-decoration:none;padding:8px 12px;border-radius:10px;font-weight:600;font-size:14px
    }
    nav a.active{background:var(--glass);color:var(--accent);box-shadow:inset 0 0 0 1px rgba(255,255,255,0.02)}

    /* ---------------------- Hero / Home ---------------------- */
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border-radius:var(--radius); padding:22px}
    .hero{
      display:grid;grid-template-columns:1fr 320px;gap:20px;align-items:center;margin-bottom:20px
    }
    .intro h2{margin:0 0 8px 0;font-size:28px}
    .intro p{margin:0;color:var(--muted)}
    .profile{
      display:flex;flex-direction:column;align-items:center;gap:12px;padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005));
    }
    .avatar{width:120px;height:120px;border-radius:20px;background:linear-gradient(180deg,#0b1220,#071026);display:flex;align-items:center;justify-content:center;font-size:36px}
    .skills{display:flex;gap:8px;flex-wrap:wrap;justify-content:center}
    .chip{background:rgba(255,255,255,0.03);padding:6px 10px;border-radius:999px;font-size:13px;color:var(--muted)}

    /* ---------------------- About ---------------------- */
    .about{display:grid;grid-template-columns:1fr 1fr;gap:18px;align-items:start}
    .about p{color:var(--muted)}

    /* ---------------------- Catalog ---------------------- */
    .projects{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px}
    .project{
      background:linear-gradient(180deg,rgba(255,255,255,0.01), rgba(255,255,255,0.02));padding:14px;border-radius:12px;min-height:160px;display:flex;flex-direction:column;gap:10px
    }
    .project .thumb{height:110px;border-radius:10px;background:linear-gradient(90deg,var(--accent),#06b6d4);display:flex;align-items:center;justify-content:center;font-weight:700}
    .project h3{margin:0 0 4px 0}
    .project p{margin:0;color:var(--muted);font-size:14px}

    /* ---------------------- Contact ---------------------- */
    .contact-grid{display:grid;grid-template-columns:1fr 360px;gap:16px}
    form{display:flex;flex-direction:column;gap:10px}
    label{font-size:13px}
    input,textarea{background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.03);padding:12px;border-radius:10px;color:inherit}
    button{background:linear-gradient(90deg,var(--accent),#06b6d4);border:none;padding:12px 16px;border-radius:10px;color:#041025;font-weight:700;cursor:pointer}

    /* ---------------------- Footer ---------------------- */
    footer{margin-top:28px;color:var(--muted);font-size:13px;padding:10px 4px;text-align:center}

    /* ---------------------- Page router ---------------------- */
    section.page{display:none}
    section.page.active{display:block}

    /* ---------------------- Responsive ---------------------- */
    @media (max-width:880px){
      .hero{grid-template-columns:1fr}
      .about, .contact-grid{grid-template-columns:1fr}
      header{flex-direction:column;align-items:flex-start;gap:12px}
      .profile{flex-direction:row;justify-content:space-between}
      nav{flex-wrap:wrap}
    }
  </style>
</head>

<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo">GS</div>
        <div>
          <h1>Guilherme dos Santos</h1>
          <div style="font-size:12px;color:var(--muted)">Designer de Som • Desenvolvedor • Criador</div>
        </div>
      </div>
      <nav aria-label="Navegação principal">
        <a href="#home" data-link="home" class="active">Home</a>
        <a href="#sobre" data-link="sobre">Sobre</a>
        <a href="#catalogo" data-link="catalogo">Catálogo</a>
        <a href="#contato" data-link="contato">Contato</a>
      </nav>
    </header>

    <!-- HOME -->
    <main>
        <section id="home" class="page active card" aria-labelledby="home-title">
        <div class="hero">
          <div class="intro">
            <h2 id="home-title">Olá — eu sou Guilherme dos Santos</h2>
            <p>Crio Trilhas Sonoras, efeitos sonoros e jogos. Abaixo você encontra alguns projetos e formas de contato.</p>
            <div style="margin-top:14px;display:flex;gap:10px">
              <a href="#catalogo" data-link="catalogo" style="text-decoration:none"><button>Ver projetos</button></a>
              <a href="#contato" data-link="contato" style="text-decoration:none"><button style="background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted)">Me chamar</button></a>
            </div>
          </div>

          <aside class="profile">
            <div class="avatar">GS</div>
            <div style="text-align:center">
              <div style="font-weight:700">Guilherme dos Santos</div>
              <div style="font-size:13px;color:var(--muted)">Designer de Som • Game Design • Áudio para Jogos</div>
            </div>
            <div class="skills">
              <div class="chip">Audacity</div>
              <div class="chip">LMMS</div>
              <div class="chip">Unity</div>
            </div>
          </aside>
        </div>
      </section>

      <!-- SOBRE -->
      <section id="sobre" class="page card" aria-labelledby="sobre-title">
        <h2 id="sobre-title">Sobre</h2>
        <div class="about">
          <div>
            <p>Sou designer de som e desenvolvedor com foco em jogos, interfaces e narrativa.</p>
            <p>Trabalho com protótipos, som e design de experiência imersiva.</p>
          </div>

          <div>
            <h3>Serviços</h3>
            <ul>
              <li>Prototipação de jogos</li>
              <li>Sound design e trilhas</li>
            </ul>

            
          </div>
        </div>
      </section>

      <!-- ====================== CATÁLOGO NOVO ====================== -->
      <section id="catalogo" class="page card" aria-labelledby="catalogo-title">
        <h2 id="catalogo-title">Catálogo de Projetos</h2>
        <p style="color:var(--muted)">Projetos de Jogos.</p>

<!-- JOGOS -->
<h3 style="margin-top:28px">Jogos</h3>
<div class="projects" style="margin-top:12px">

  <!-- CARD 1 -->
  <article class="project">
    <img class="thumb" src="https://img.itch.zone/aW1nLzE2Mjc5MjIxLnBuZw==/347x500/1qF9K5.png" 
         alt="Thumb do jogo Freelancer Fiasco"
         style="object-fit:cover;width:100%;height:110px;border-radius:10px">
    <div>
      <h3>Freelancer Fiasco</h3>
      <p>Jogo de plataforma: seu primeiro dia de trabalho virou um caos total.</p>
      <p><a href="https://vilemort.itch.io/freelancer-fiasco" target="_blank" style="color:var(--accent)">Ver jogo</a></p>
    </div>
  </article>

  <!-- CARD 2 -->
  <article class="project">
    <img class="thumb" src="https://img.itch.zone/aW1nLzIxODI1NTcyLnBuZw==/315x250%23c/7%2Fw5M5.png" 
         alt="Thumb do jogo OniricDogs"
         style="object-fit:cover;width:100%;height:110px;border-radius:10px">
    <div>
      <h3>OniricDogs</h3>
      <p>Explore um mapa meio confuso para sair desse sonho.</p>
      <p><a href="https://vilemort.itch.io/oniric-dogs" target="_blank" style="color:var(--accent)">Ver jogo</a></p>
    </div>
  </article>

  <!-- CARD 3 -->
  <article class="project">
    <img class="thumb" src="https://img.itch.zone/aW1nLzI0MTE4ODAxLnBuZw==/315x250%23c/%2BlQX1R.png" 
         alt="Thumb do jogo Jogador 47"
         style="object-fit:cover;width:100%;height:110px;border-radius:10px">
    <div>
      <h3>Jogador 47</h3>
      <p>Jogador Nº 47 é uma adaptação em primeira pessoa inspirada no universo de Jogador Nº 1, misturando FPS com exploração de dungeon ao estilo Dungeons & Dragons.</p>
      <p><a href="https://arezoel.itch.io/jogador-n47" target="_blank" style="color:var(--accent)">Ver jogo</a></p>
    </div>
  </article>

</div> <!-- fim dos cards -->
</section> <!-- fim do catálogo -->

        <!-- CONTATO -->
      <section id="contato" class="page card" aria-labelledby="contato-title">
        <h2 id="contato-title">Contato</h2>
        <div class="contact-grid">
          <form>
            <label for="nome">Nome</label>
            <input type="text" id="nome" name="nome" placeholder="Seu nome" required>
            
            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="seu@email.com" required>
            
            <label for="mensagem">Mensagem</label>
            <textarea id="mensagem" name="mensagem" rows="5" placeholder="Sua mensagem..." required></textarea>
            
            <button type="submit">Enviar</button>
          </form>

          <aside style="padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.005))">
            <h3>Onde me encontrar</h3>
            <p>Email: <a href="mailto:guilherme.soliveira05@gmail.com">guilherme.soliveira05@gmail.com</a></p>
            <p>LinkedIn: <a href="#">guilherme dos santos</a></p>
            <p>GitHub: <a href="#">@guilhermesoliveira05-glitch</a></p>
            <div style="margin-top:12px">
              <h4 style="margin:0 0 6px 0">Localização</h4>
              <p style="margin:0;color:var(--muted)">Brasil</p>
            </div>
          </aside>
        </div>
      </section>

    </main>

    <footer>
      © <span id="year">2025</span> — Guilherme dos Santos.
    </footer>
  </div>

  <script>
    const links = document.querySelectorAll('nav a[data-link]');
    const pages = document.querySelectorAll('section.page');

    function activate(name){
      pages.forEach(p=>p.classList.toggle('active', p.id===name));
      links.forEach(l=>l.classList.toggle('active', l.dataset.link===name));
    }
    function route(){
      const hash = location.hash.replace('#','') || 'home';
      activate(hash);
    }
    window.addEventListener('hashchange',route);
    route();

    document.getElementById('year').textContent = new Date().getFullYear();
  </script>

</body>
</html>  
