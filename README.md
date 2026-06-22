# Nocta-Store
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NOCTA STORE — Marketplace de Produtos Digitais para Roblox</title>
  <meta name="description" content="NOCTA STORE: marketplace premium de Robux, gamepasses, contas e serviços para Roblox. Entrega instantânea e suporte 24/7." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    /* ---------- 1. Design Tokens ---------- */
    :root {
      --bg:#070a1a; --bg-elev:#0b1024; --surface:#0f1530; --surface-2:#131a3a;
      --border:rgba(77,163,255,0.10); --border-hover:rgba(77,163,255,0.32);
      --text:#eaf0ff; --text-dim:#8a93b4; --text-mute:#5a6388;
      --neon:#4da3ff; --neon-2:#2b7fe0;
      --neon-soft:rgba(77,163,255,0.14); --neon-glow:rgba(77,163,255,0.35);
      --radius:14px; --radius-lg:20px;
      --shadow-sm:0 1px 2px rgba(0,0,0,0.4);
      --shadow-md:0 10px 30px -10px rgba(0,0,0,0.6);
      --shadow-glow:0 0 0 1px var(--border-hover), 0 20px 50px -20px var(--neon-glow);
      --transition:220ms cubic-bezier(0.4,0,0.2,1);
      --container:1200px;
    }

    /* ---------- 2. Reset / Base ---------- */
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth;-webkit-text-size-adjust:100%}
    body{font-family:'Inter',-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;background:var(--bg);color:var(--text);line-height:1.6;min-height:100vh;-webkit-font-smoothing:antialiased;overflow-x:hidden}
    img,svg{display:block;max-width:100%}
    a{color:inherit;text-decoration:none}
    button{font-family:inherit;cursor:pointer;border:none;background:none;color:inherit}
    ::selection{background:var(--neon);color:var(--bg)}

    /* ---------- 3. Layout ---------- */
    .container{width:100%;max-width:var(--container);margin-inline:auto;padding-inline:24px}

    /* HEADER */
    .header{position:sticky;top:0;z-index:50;background:rgba(7,10,26,0.72);backdrop-filter:saturate(160%) blur(14px);-webkit-backdrop-filter:saturate(160%) blur(14px);border-bottom:1px solid var(--border)}
    .header-inner{height:72px;display:flex;align-items:center;justify-content:space-between;gap:24px}
    .logo{display:inline-flex;align-items:center;gap:10px;font-weight:700;font-size:17px;letter-spacing:.02em;color:var(--text)}
    .logo-mark{width:28px;height:28px;border-radius:8px;background:linear-gradient(135deg,var(--neon),var(--neon-2));display:grid;place-items:center;box-shadow:0 4px 12px -2px var(--neon-glow)}
    .logo-mark svg{width:16px;height:16px;color:#07090f}
    .logo .accent{color:var(--neon);font-weight:600}
    .nav{display:flex;align-items:center;gap:4px}
    .nav a{position:relative;padding:8px 14px;font-size:14px;font-weight:500;color:var(--text-dim);border-radius:8px;transition:color var(--transition),background var(--transition)}
    .nav a:hover{color:var(--text);background:rgba(255,255,255,.03)}
    .nav a.active{color:var(--text)}
    .nav a.active::after{content:'';position:absolute;left:14px;right:14px;bottom:2px;height:2px;background:var(--neon);border-radius:2px}
    .header-cta{display:flex;align-items:center;gap:10px}
    .btn{display:inline-flex;align-items:center;justify-content:center;gap:8px;padding:10px 18px;border-radius:10px;font-size:14px;font-weight:600;letter-spacing:.01em;transition:transform var(--transition),background var(--transition),box-shadow var(--transition),border-color var(--transition);border:1px solid transparent;white-space:nowrap}
    .btn-primary{background:var(--neon);color:#061026;box-shadow:0 6px 18px -6px var(--neon-glow)}
    .btn-primary:hover{background:#6db4ff;transform:translateY(-1px);box-shadow:0 10px 24px -6px var(--neon-glow)}
    .btn-ghost{background:transparent;color:var(--text);border-color:var(--border)}
    .btn-ghost:hover{border-color:var(--border-hover);background:rgba(255,255,255,.02)}
    .btn-lg{padding:14px 26px;font-size:15px;border-radius:12px}
    .menu-toggle{display:none;width:40px;height:40px;border-radius:10px;border:1px solid var(--border);align-items:center;justify-content:center}
    .menu-toggle svg{width:20px;height:20px;color:var(--text)}

    /* HERO */
    .hero{position:relative;padding:120px 0 120px;text-align:center;overflow:hidden;isolation:isolate}
    .hero-bg{position:absolute;inset:0;z-index:-1;background:radial-gradient(60% 50% at 50% 0%,rgba(77,163,255,.18),transparent 70%),radial-gradient(40% 40% at 80% 60%,rgba(43,127,224,.12),transparent 70%),radial-gradient(40% 40% at 20% 70%,rgba(77,163,255,.08),transparent 70%);pointer-events:none}
    .hero-bg::after{content:'';position:absolute;inset:0;background-image:linear-gradient(rgba(77,163,255,.05) 1px,transparent 1px),linear-gradient(90deg,rgba(77,163,255,.05) 1px,transparent 1px);background-size:56px 56px;mask-image:radial-gradient(ellipse 70% 60% at 50% 40%,#000 30%,transparent 75%);-webkit-mask-image:radial-gradient(ellipse 70% 60% at 50% 40%,#000 30%,transparent 75%);opacity:.55}
    .eyebrow{display:inline-flex;align-items:center;gap:8px;padding:6px 14px 6px 10px;background:var(--neon-soft);border:1px solid var(--border-hover);border-radius:999px;font-size:12.5px;font-weight:500;color:var(--neon);letter-spacing:.04em;text-transform:uppercase}
    .eyebrow .dot{width:6px;height:6px;border-radius:50%;background:var(--neon);box-shadow:0 0 8px var(--neon)}
    .hero h1{margin-top:28px;font-size:clamp(44px,7.5vw,88px);line-height:1.02;letter-spacing:-.035em;font-weight:800}
    .hero h1 .grad{background:linear-gradient(180deg,#fff 0%,#b9d4ff 60%,var(--neon) 100%);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;color:transparent}
    .hero p{margin:22px auto 0;max-width:620px;font-size:clamp(15px,1.5vw,18px);color:var(--text-dim)}
    .hero-actions{margin-top:36px;display:inline-flex;gap:12px;flex-wrap:wrap;justify-content:center}
    .hero-meta{margin-top:48px;display:inline-flex;align-items:center;gap:22px;flex-wrap:wrap;justify-content:center;color:var(--text-mute);font-size:13px}
    .hero-meta .check{display:inline-flex;align-items:center;gap:6px}
    .hero-meta svg{width:14px;height:14px;color:var(--neon)}

    /* SECTIONS */
    .section{padding:100px 0}
    .section-head{display:flex;align-items:end;justify-content:space-between;gap:24px;margin-bottom:48px}
    .section-head .title h2{font-size:clamp(28px,3.4vw,40px);letter-spacing:-.02em;font-weight:700;line-height:1.15}
    .section-head .title p{margin-top:10px;color:var(--text-dim);font-size:15px;max-width:520px}
    .section-head .link{display:inline-flex;align-items:center;gap:6px;font-size:14px;color:var(--neon);font-weight:500;padding:6px 0;border-bottom:1px solid transparent;transition:border-color var(--transition)}
    .section-head .link:hover{border-bottom-color:var(--neon)}
    .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:20px}

    .card{position:relative;display:flex;flex-direction:column;padding:28px;background:linear-gradient(180deg,var(--surface) 0%,var(--bg-elev) 100%);border:1px solid var(--border);border-radius:var(--radius-lg);transition:transform var(--transition),box-shadow var(--transition),border-color var(--transition);overflow:hidden}
    .card::before{content:'';position:absolute;inset:0;background:radial-gradient(120% 60% at 50% 0%,var(--neon-soft),transparent 60%);opacity:0;transition:opacity var(--transition);pointer-events:none}
    .card:hover{transform:translateY(-4px);border-color:var(--border-hover);box-shadow:var(--shadow-glow)}
    .card:hover::before{opacity:1}
    .card-icon{width:48px;height:48px;border-radius:12px;display:grid;place-items:center;background:var(--neon-soft);border:1px solid var(--border-hover);color:var(--neon);margin-bottom:22px}
    .card-icon svg{width:22px;height:22px}
    .card h3{font-size:19px;font-weight:700;letter-spacing:-.01em}
    .card .tag{display:inline-block;margin-left:8px;font-size:11px;font-weight:600;color:var(--neon);background:var(--neon-soft);padding:3px 8px;border-radius:999px;vertical-align:middle}
    .card p{margin-top:10px;color:var(--text-dim);font-size:14.5px;flex:1}
    .card-action{margin-top:24px;display:inline-flex;align-items:center;gap:6px;font-size:14px;font-weight:600;color:var(--text);padding:10px 0;border-bottom:1px solid transparent;align-self:flex-start;transition:color var(--transition),gap var(--transition)}
    .card-action svg{width:14px;height:14px;transition:transform var(--transition)}
    .card:hover .card-action{color:var(--neon);gap:10px}
    .card:hover .card-action svg{transform:translateX(2px)}

    /* SEGURANÇA */
    .security{position:relative}
    .security-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px}
    .sec-card{position:relative;padding:26px;background:var(--surface);border:1px solid var(--border);border-radius:var(--radius-lg);transition:transform var(--transition),border-color var(--transition),box-shadow var(--transition)}
    .sec-card:hover{transform:translateY(-3px);border-color:var(--border-hover);box-shadow:var(--shadow-glow)}
    .sec-card .ico{width:44px;height:44px;border-radius:12px;display:grid;place-items:center;background:var(--neon-soft);border:1px solid var(--border-hover);color:var(--neon);margin-bottom:18px}
    .sec-card .ico svg{width:20px;height:20px}
    .sec-card h3{font-size:17px;font-weight:700;letter-spacing:-.01em}
    .sec-card p{margin-top:8px;font-size:14px;color:var(--text-dim)}
    .pill-row{margin-top:40px;display:flex;flex-wrap:wrap;gap:10px;justify-content:center}
    .pill{display:inline-flex;align-items:center;gap:8px;padding:8px 14px;border-radius:999px;background:var(--surface);border:1px solid var(--border);font-size:13px;color:var(--text-dim);transition:color var(--transition),border-color var(--transition)}
    .pill:hover{color:var(--text);border-color:var(--border-hover)}
    .pill svg{width:14px;height:14px;color:var(--neon)}

    /* PAGAMENTO */
    .pay-wrap{display:grid;grid-template-columns:1.1fr 1fr;gap:56px;align-items:center}
    .pay-list{display:flex;flex-direction:column;gap:22px;margin-top:28px}
    .pay-item{display:flex;gap:16px;align-items:flex-start}
    .pay-item .ico{flex-shrink:0;width:40px;height:40px;border-radius:10px;display:grid;place-items:center;background:var(--neon-soft);border:1px solid var(--border-hover);color:var(--neon)}
    .pay-item .ico svg{width:18px;height:18px}
    .pay-item h4{font-size:15.5px;font-weight:600}
    .pay-item p{font-size:14px;color:var(--text-dim);margin-top:2px}
    .pay-card{padding:32px;background:linear-gradient(180deg,var(--surface) 0%,var(--bg-elev) 100%);border:1px solid var(--border);border-radius:var(--radius-lg);box-shadow:var(--shadow-md)}
    .pay-card-label{font-size:12px;text-transform:uppercase;letter-spacing:.08em;color:var(--text-mute);margin-bottom:16px}
    .pay-methods{display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
    .pay-method{display:flex;align-items:center;gap:10px;padding:14px;background:var(--bg-elev);border:1px solid var(--border);border-radius:12px;font-size:13.5px;font-weight:500;color:var(--text);transition:border-color var(--transition)}
    .pay-method:hover{border-color:var(--border-hover)}
    .pay-method .badge{width:32px;height:32px;border-radius:8px;background:var(--neon-soft);color:var(--neon);display:grid;place-items:center;font-size:11px;font-weight:700}
    .pay-method .badge svg{width:16px;height:16px}

    /* SUPORTE CTA */
    .support-cta{position:relative;padding:56px 40px;border-radius:var(--radius-lg);background:radial-gradient(80% 120% at 100% 0%,rgba(77,163,255,.18),transparent 60%),linear-gradient(180deg,var(--surface) 0%,var(--bg-elev) 100%);border:1px solid var(--border-hover);overflow:hidden;text-align:center}
    .support-cta::after{content:'';position:absolute;inset:-1px;border-radius:inherit;padding:1px;background:linear-gradient(135deg,var(--neon-glow),transparent 60%);-webkit-mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);mask:linear-gradient(#000 0 0) content-box,linear-gradient(#000 0 0);-webkit-mask-composite:xor;mask-composite:exclude;pointer-events:none}
    .support-icon{width:64px;height:64px;margin:0 auto 20px;border-radius:16px;display:grid;place-items:center;background:var(--neon-soft);border:1px solid var(--border-hover);color:var(--neon)}
    .support-icon svg{width:28px;height:28px}
    .support-cta h2{font-size:clamp(26px,3.4vw,36px);font-weight:700;letter-spacing:-.02em}
    .support-cta p{margin:12px auto 28px;color:var(--text-dim);max-width:520px;font-size:15px}
    .btn-discord{background:#5865F2;color:#fff;box-shadow:0 6px 18px -6px rgba(88,101,242,.6)}
    .btn-discord:hover{background:#6e7bff;transform:translateY(-1px)}

    /* FOOTER */
    .footer{border-top:1px solid var(--border);padding:28px 0;color:var(--text-mute);font-size:13.5px}
    .footer-inner{display:flex;justify-content:space-between;align-items:center;gap:16px;flex-wrap:wrap}
    .footer .logo{font-size:14px}
    .footer-links{display:flex;gap:22px}
    .footer-links a:hover{color:var(--text)}

    /* RESPONSIVO */
    @media (max-width:860px){
      .nav{display:none}
      .menu-toggle{display:inline-flex}
      .header-cta .btn-ghost{display:none}
      .hero{padding:90px 0}
      .section{padding:72px 0}
      .section-head{flex-direction:column;align-items:start}
      .pay-wrap{grid-template-columns:1fr;gap:32px}
      .support-cta{padding:44px 24px}
    }
    @media (max-width:480px){
      .hero-meta{gap:14px;font-size:12.5px}
      .card{padding:24px}
    }

    /* Reveal on scroll */
    .reveal{opacity:0;transform:translateY(14px);transition:opacity 600ms ease,transform 600ms ease}
    .reveal.in{opacity:1;transform:none}
    @media (prefers-
reduced-motion:reduce){
      .reveal{opacity:1;transform:none;transition:none}
      *{animation:none!important;transition:none!important}
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header class="header">
    <div class="container header-inner">
      <a href="#" class="logo" aria-label="NOCTA STORE">
        <span class="logo-mark" aria-hidden="true">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M13 2 3 14h7l-1 8 10-12h-7l1-8Z"/></svg>
        </span>
        NOCTA <span class="accent">STORE</span>
      </a>

      <nav class="nav" aria-label="Navegação principal">
        <a href="#" class="active">Início</a>
        <a href="#destaques">Jogos</a>
        <a href="#destaques">Catálogo</a>
        <a href="#suporte">Suporte</a>
      </nav>

      <div class="header-cta">
        <button class="btn btn-ghost" type="button">Entrar</button>
        <button class="btn btn-primary" type="button">Criar conta</button>
        <button class="menu-toggle" type="button" aria-label="Abrir menu">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="4" y1="7" x2="20" y2="7"/><line x1="4" y1="12" x2="20" y2="12"/><line x1="4" y1="17" x2="20" y2="17"/></svg>
        </button>
      </div>
    </div>
  </header>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-bg" aria-hidden="true"></div>
    <div class="container">
      <span class="eyebrow reveal"><span class="dot"></span> Marketplace oficial Roblox</span>
      <h1 class="reveal"><span class="grad">NOCTA STORE</span></h1>
      <p class="reveal">
        O marketplace premium de produtos digitais para Roblox. Robux, gamepasses,
        contas e serviços com entrega instantânea, segurança verificada e suporte 24/7.
      </p>
      <div class="hero-actions reveal">
        <a href="#destaques" class="btn btn-primary btn-lg">
          Explorar Catálogo
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M13 5l7 7-7 7"/></svg>
        </a>
        <a href="#suporte" class="btn btn-ghost btn-lg">Falar com suporte</a>
      </div>
      <div class="hero-meta reveal">
        <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Entrega instantânea</span>
        <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Pagamento seguro</span>
        <span class="check"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg> Suporte 24/7</span>
      </div>
    </div>
  </section>

  <!-- SEGURANÇA -->
  <section class="section security" id="seguranca">
    <div class="container">
      <div class="section-head" style="justify-content:center;text-align:center;">
        <div class="title" style="margin:0 auto;">
          <h2 class="reveal">Sua Segurança é Nossa Prioridade</h2>
          <p class="reveal" style="margin-left:auto;margin-right:auto;">
            Desenvolvemos um sistema completo de proteção para que você possa negociar com
            tranquilidade. Cada transação é monitorada e protegida.
          </p>
        </div>
      </div>
      <div class="security-grid" id="securityGrid"></div>
      <div class="pill-row reveal" id="pillRow"></div>
    </div>
  </section>

  <!-- PAGAMENTO -->
  <section class="section" id="pagamento" style="padding-top:0;">
    <div class="container">
      <div class="pay-wrap">
        <div>
          <h2 class="reveal" style="font-size:clamp(28px,3.4vw,40px);letter-spacing:-0.02em;font-weight:700;">
            Pagamento Flexível
          </h2>
          <p class="reveal" style="margin-top:12px;color:var(--text-dim);max-width:480px;">
            Aceitamos as principais formas de pagamento do mercado para sua conveniência e segurança.
          </p>
          <div class="pay-list" id="payList"></div>
        </div>
        <div class="pay-card reveal">
          <div class="pay-card-label">Formas de pagamento aceitas</div>
          <div class="pay-methods" id="payMethods"></div>
        </div>
      </div>
    </div>
  </section>

  <!-- SUPORTE -->
  <section class="section" id="suporte-section" style="padding-top:0;">
    <div class="container">
      <div class="support-cta reveal">
        <div class="support-icon" aria-hidden="true">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"/>
          </svg>
        </div>
        <h2>Suporte Humanizado</h2>
        <p>Nossa equipe está sempre pronta para ajudar você. Atendimento rápido e exclusivo via Discord.</p>
        <a href="#" class="btn btn-discord btn-lg">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.369A19.79 19.79 0 0 0 16.558 3.2a.07.07 0 0 0-.073.035c-.211.375-.444.864-.608 1.249a18.27 18.27 0 0 0-5.487 0 12.6 12.6 0 0 0-.617-1.249.07.07 0 0 0-.073-.035A19.74 19.74 0 0 0 5.94 4.37a.06.06 0 0 0-.03.025C2.51 9.046 1.65 13.58 2.07 18.057a.08.08 0 0 0 .03.054 19.9 19.9 0 0 0 5.993 3.03.07.07 0 0 0 .078-.027 14.3 14.3 0 0 0 1.226-1.994.07.07 0 0 0-.04-.099 13.1 13.1 0 0 1-1.872-.891.07.07 0 0 1-.007-.117c.126-.094.252-.192.372-.291a.07.07 0 0 1 .074-.01c3.927 1.793 8.18 1.793 12.062 0a.07.07 0 0 1 .075.009c.12.099.246.198.373.292a.07.07 0 0 1-.006.117 12.3 12.3 0 0 1-1.873.891.07.
