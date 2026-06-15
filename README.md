# Sampaththollawebsite
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sampath Tholla — Full-Stack Developer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

        :root {
            --bg-page:        #060D1A;
            --bg-alt:         #080F1E;
            --bg-card:        #0C1A2E;
            --bg-card-hover:  #102038;
            --accent-purple:  #7B5CF6;
            --accent-cyan:    #06B6D4;
            --accent-emerald: #10B981;
            --accent-amber:   #F59E0B;
            --accent-rose:    #F43F5E;
            --border-subtle:  rgba(123,92,246,0.12);
            --border-accent:  rgba(123,92,246,0.30);
            --text-1:         #E2E8F0;
            --text-2:         #94A3B8;
            --text-3:         #475569;
            --grad-main:      linear-gradient(135deg,#7B5CF6,#06B6D4);
            --shadow-glow:    0 0 32px rgba(123,92,246,0.14);
        }

        html { scroll-behavior: smooth; }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-page);
            color: var(--text-1);
            line-height: 1.7;
            overflow-x: hidden;
        }

        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-track { background: var(--bg-page); }
        ::-webkit-scrollbar-thumb { background: var(--accent-purple); border-radius: 3px; }
        ::selection { background: rgba(123,92,246,0.30); color:#fff; }

        /* ── NAV ── */
        nav {
            position: fixed; top:0; left:0; right:0; z-index:100;
            padding: 1.1rem 2.5rem;
            display: flex; align-items:center; justify-content:space-between;
            transition: all .3s ease;
        }
        nav.scrolled {
            background: rgba(6,13,26,.88);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border-bottom: 1px solid var(--border-subtle);
            padding: .8rem 2.5rem;
        }
        .nav-logo {
            font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:1.3rem;
            background: var(--grad-main); -webkit-background-clip:text;
            -webkit-text-fill-color:transparent; background-clip:text; text-decoration:none;
        }
        .nav-links { display:flex; align-items:center; gap:2rem; list-style:none; }
        .nav-links a {
            color:var(--text-2); text-decoration:none; font-size:.875rem;
            font-weight:500; letter-spacing:.02em; transition:color .2s;
        }
        .nav-links a:hover { color:var(--text-1); }
        .btn-hire {
            background:var(--grad-main); color:#fff !important; padding:.5rem 1.25rem;
            border-radius:7px; font-weight:600 !important; transition:opacity .2s, transform .2s !important;
        }
        .btn-hire:hover { opacity:.88; transform:translateY(-1px); }
        .nav-burger { display:none; background:none; border:none; color:var(--text-1); font-size:1.2rem; cursor:pointer; }

        /* ── HERO ── */
        #hero {
            min-height:100vh; display:flex; align-items:center;
            position:relative; overflow:hidden; padding:9rem 2.5rem 5rem;
        }
        #hero::before {
            content:''; position:absolute; inset:0;
            background-image: radial-gradient(circle, rgba(123,92,246,.14) 1px, transparent 1px);
            background-size:32px 32px;
            mask-image: radial-gradient(ellipse 80% 65% at 50% 50%, black, transparent);
            -webkit-mask-image: radial-gradient(ellipse 80% 65% at 50% 50%, black, transparent);
        }
        .orb {
            position:absolute; border-radius:50%; filter:blur(90px); pointer-events:none;
        }
        .orb-1 { width:420px; height:420px; background:rgba(123,92,246,.11); top:-80px; right:-60px; }
        .orb-2 { width:320px; height:320px; background:rgba(6,182,212,.07); bottom:40px; left:-80px; }

        .hero-content { max-width:820px; position:relative; z-index:1; }

        .eyebrow-pill {
            display:inline-flex; align-items:center; gap:.5rem;
            background:rgba(123,92,246,.10); border:1px solid rgba(123,92,246,.24);
            border-radius:999px; padding:.35rem 1rem; font-family:'Fira Code',monospace;
            font-size:.78rem; color:var(--accent-purple); margin-bottom:1.75rem; letter-spacing:.05em;
        }
        .pill-dot {
            width:7px; height:7px; background:var(--accent-emerald); border-radius:50%;
            animation: blink 2s ease-in-out infinite;
        }
        @keyframes blink { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.4;transform:scale(.75)} }

        .hero-name {
            font-family:'Space Grotesk',sans-serif; font-weight:700;
            font-size:clamp(3.2rem,9vw,6rem); line-height:1.04;
            letter-spacing:-.03em; margin-bottom:1rem;
        }
        .grad { background:var(--grad-main); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; }

        .hero-title {
            font-family:'Space Grotesk',sans-serif; font-size:clamp(1.05rem,2.4vw,1.4rem);
            color:var(--text-2); font-weight:400; margin-bottom:1.5rem;
        }
        .hero-desc {
            font-size:1.05rem; color:var(--text-2); max-width:600px;
            line-height:1.82; margin-bottom:2.5rem;
        }
        .hero-ctas { display:flex; gap:1rem; flex-wrap:wrap; margin-bottom:3rem; }

        .btn-primary {
            display:inline-flex; align-items:center; gap:.5rem;
            background:var(--grad-main); color:#fff; padding:.85rem 1.8rem;
            border-radius:8px; font-weight:600; font-size:.95rem; text-decoration:none;
            transition:transform .2s, box-shadow .2s;
        }
        .btn-primary:hover { transform:translateY(-2px); box-shadow:0 8px 28px rgba(123,92,246,.35); }

        .btn-ghost {
            display:inline-flex; align-items:center; gap:.5rem;
            background:transparent; color:var(--text-1); padding:.85rem 1.8rem;
            border-radius:8px; font-weight:500; font-size:.95rem; text-decoration:none;
            border:1px solid var(--border-accent); transition:background .2s, border-color .2s;
        }
        .btn-ghost:hover { background:rgba(123,92,246,.08); border-color:var(--accent-purple); }

        .hero-chips { display:flex; gap:1.25rem; flex-wrap:wrap; }
        .hero-chip {
            display:inline-flex; align-items:center; gap:.45rem;
            color:var(--text-2); font-size:.83rem; text-decoration:none; transition:color .2s;
        }
        .hero-chip i { color:var(--accent-purple); font-size:.85rem; }
        .hero-chip:hover { color:var(--text-1); }

        /* ── SHARED SECTION ── */
        section { padding:6rem 2.5rem; }
        .bg-alt { background:var(--bg-alt); }
        .container { max-width:1120px; margin:0 auto; }
        .divider { height:1px; background:linear-gradient(to right,transparent,var(--border-subtle),transparent); }

        .s-eye {
            font-family:'Fira Code',monospace; font-size:.75rem; color:var(--accent-cyan);
            letter-spacing:.14em; text-transform:uppercase; display:block; margin-bottom:.75rem;
        }
        .s-title {
            font-family:'Space Grotesk',sans-serif; font-size:clamp(1.7rem,4vw,2.5rem);
            font-weight:700; line-height:1.15; letter-spacing:-.025em; margin-bottom:1rem;
        }
        .s-sub {
            color:var(--text-2); font-size:1.05rem; max-width:560px;
            line-height:1.8; margin-bottom:3.5rem;
        }

        /* ── STRENGTHS ── */
        .strengths-grid {
            display:grid; grid-template-columns:repeat(auto-fit,minmax(230px,1fr)); gap:1.4rem;
        }
        .s-card {
            background:var(--bg-card); border:1px solid var(--border-subtle); border-radius:12px;
            padding:1.75rem; position:relative; overflow:hidden;
            transition:transform .25s, border-color .25s, box-shadow .25s;
        }
        .s-card::after {
            content:''; position:absolute; top:0; left:0; right:0; height:2px;
            background:var(--grad-main); opacity:0; transition:opacity .25s;
        }
        .s-card:hover { transform:translateY(-4px); border-color:var(--border-accent); box-shadow:var(--shadow-glow); }
        .s-card:hover::after { opacity:1; }
        .s-icon {
            width:44px; height:44px; background:rgba(123,92,246,.12); border-radius:10px;
            display:flex; align-items:center; justify-content:center;
            font-size:1.1rem; color:var(--accent-purple); margin-bottom:1.2rem;
        }
        .s-card h3 { font-family:'Space Grotesk',sans-serif; font-weight:600; font-size:1rem; margin-bottom:.5rem; }
        .s-card p { font-size:.875rem; color:var(--text-2); line-height:1.65; }

        /* ── SKILLS ── */
        .skills-grid { display:grid; grid-template-columns:1fr 1fr; gap:1.4rem; }
        @media(max-width:600px){ .skills-grid { grid-template-columns:1fr; } }

        .skill-cat {
            background:var(--bg-card); border:1px solid var(--border-subtle); border-radius:12px;
            padding:1.6rem; transition:border-color .25s;
        }
        .skill-cat:hover { border-color:var(--border-accent); }
        .cat-label {
            font-family:'Fira Code',monospace; font-size:.72rem; color:var(--accent-cyan);
            letter-spacing:.1em; text-transform:uppercase; margin-bottom:1.1rem;
            display:flex; align-items:center; gap:.5rem;
        }
        .cat-label::after { content:''; flex:1; height:1px; background:var(--border-subtle); }
        .badges { display:flex; flex-wrap:wrap; gap:.55rem; }
        .badge {
            display:inline-flex; align-items:center; padding:.35rem .85rem;
            border-radius:6px; font-family:'Fira Code',monospace; font-size:.76rem;
            font-weight:500; border:1px solid; transition:transform .15s; cursor:default;
        }
        .badge:hover { transform:translateY(-2px); }
        .b-purple { background:rgba(123,92,246,.10); color:#A78BFA; border-color:rgba(123,92,246,.24); }
        .b-cyan   { background:rgba(6,182,212,.08);  color:#67E8F9; border-color:rgba(6,182,212,.20); }
        .b-green  { background:rgba(16,185,129,.08); color:#6EE7B7; border-color:rgba(16,185,129,.20); }
        .b-amber  { background:rgba(245,158,11,.08); color:#FCD34D; border-color:rgba(245,158,11,.20); }
        .b-rose   { background:rgba(244,63,94,.08);  color:#FDA4AF; border-color:rgba(244,63,94,.20);  }

        /* ── PROJECTS ── */
        .projects-grid {
            display:grid; grid-template-columns:repeat(auto-fit,minmax(440px,1fr)); gap:1.75rem;
        }
        @media(max-width:500px){ .projects-grid { grid-template-columns:1fr; } }

        .proj-card {
            background:var(--bg-card); border:1px solid var(--border-subtle); border-radius:14px;
            overflow:hidden; transition:transform .25s, border-color .25s, box-shadow .25s;
        }
        .proj-card:hover { transform:translateY(-5px); border-color:var(--border-accent); box-shadow:var(--shadow-glow); }

        .proj-head { padding:1.75rem 1.75rem 1.1rem; border-bottom:1px solid var(--border-subtle); }
        .proj-meta { display:flex; align-items:center; justify-content:space-between; margin-bottom:.75rem; }
        .proj-date { font-family:'Fira Code',monospace; font-size:.73rem; color:var(--text-3); }
        .status-pill {
            display:inline-flex; align-items:center; gap:.35rem; font-size:.73rem;
            color:var(--accent-emerald); background:rgba(16,185,129,.09);
            padding:.22rem .65rem; border-radius:999px; border:1px solid rgba(16,185,129,.20);
        }
        .status-pill .dot { width:5px; height:5px; border-radius:50%; background:var(--accent-emerald); }
        .proj-head h3 { font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:1.15rem; }

        .proj-body { padding:1.25rem 1.75rem 1.75rem; }
        .proj-list { list-style:none; margin-bottom:1.4rem; display:flex; flex-direction:column; gap:.6rem; }
        .proj-list li { display:flex; gap:.7rem; font-size:.875rem; color:var(--text-2); line-height:1.65; }
        .proj-list li::before { content:'▹'; color:var(--accent-purple); flex-shrink:0; margin-top:.05em; }
        .tech-tags { display:flex; flex-wrap:wrap; gap:.45rem; }
        .t-tag {
            font-family:'Fira Code',monospace; font-size:.7rem; color:var(--accent-cyan);
            background:rgba(6,182,212,.07); border:1px solid rgba(6,182,212,.15);
            padding:.18rem .58rem; border-radius:4px;
        }

        /* ── EDUCATION ── */
        .edu-card {
            background:var(--bg-card); border:1px solid var(--border-subtle); border-radius:14px;
            padding:2rem; display:grid; grid-template-columns:auto 1fr; gap:1.75rem; align-items:start;
        }
        @media(max-width:560px){ .edu-card { grid-template-columns:1fr; gap:1rem; } }
        .edu-ico {
            width:56px; height:56px; background:rgba(123,92,246,.12); border-radius:12px;
            display:flex; align-items:center; justify-content:center; font-size:1.4rem;
            color:var(--accent-purple); flex-shrink:0;
        }
        .edu-deg { font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:1.15rem; margin-bottom:.25rem; }
        .edu-uni { color:var(--accent-cyan); font-size:.9rem; font-weight:500; margin-bottom:.6rem; }
        .edu-metas { display:flex; gap:1.5rem; flex-wrap:wrap; }
        .edu-m { display:flex; align-items:center; gap:.4rem; font-size:.84rem; color:var(--text-2); }
        .edu-m i { color:var(--accent-purple); font-size:.78rem; }

        /* ── PLACEHOLDER NOTICE ── */
        .notice {
            display:flex; align-items:flex-start; gap:.85rem; margin-top:1.75rem;
            background:rgba(245,158,11,.06); border:1px solid rgba(245,158,11,.15);
            border-radius:10px; padding:1.2rem 1.5rem;
            font-size:.875rem; color:var(--text-2); line-height:1.65;
        }
        .notice i { color:var(--accent-amber); flex-shrink:0; margin-top:.15rem; }
        .notice strong { color:var(--accent-amber); }

        /* ── CAREER GOALS ── */
        .goals-wrap { text-align:center; }
        .goals-card {
            background:linear-gradient(135deg,rgba(123,92,246,.09),rgba(6,182,212,.05));
            border:1px solid rgba(123,92,246,.22); border-radius:14px;
            padding:2.75rem; max-width:720px; margin:0 auto;
        }
        .goals-card .quote {
            font-family:'Space Grotesk',sans-serif; font-size:clamp(1.1rem,2.4vw,1.3rem);
            font-weight:500; line-height:1.72; color:var(--text-1); margin-bottom:1.5rem;
        }
        .goals-card .detail { color:var(--text-2); font-size:.95rem; line-height:1.8; }

        /* ── OPEN TO ── */
        .open-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(180px,1fr)); gap:1rem; }
        .open-card {
            background:var(--bg-card); border:1px solid var(--border-subtle); border-radius:10px;
            padding:1.25rem 1.5rem; display:flex; align-items:center; gap:.85rem;
            transition:border-color .2s;
        }
        .open-card:hover { border-color:var(--border-accent); }
        .open-icon { font-size:1.2rem; color:var(--accent-purple); flex-shrink:0; }
        .open-text { font-size:.875rem; font-weight:500; color:var(--text-1); }
        .open-sub  { font-size:.78rem; color:var(--text-3); margin-top:.1rem; }

        /* ── CONTACT ── */
        .contact-wrap { display:grid; grid-template-columns:1fr 1.15fr; gap:3.5rem; align-items:start; }
        @media(max-width:700px){ .contact-wrap { grid-template-columns:1fr; } }
        .c-title { font-family:'Space Grotesk',sans-serif; font-weight:700; font-size:2.1rem; letter-spacing:-.025em; margin-bottom:1rem; }
        .c-sub { color:var(--text-2); line-height:1.8; margin-bottom:1.75rem; font-size:.975rem; }
        .c-location { display:flex; align-items:center; gap:.5rem; font-size:.875rem; color:var(--text-2); }
        .c-location i { color:var(--accent-purple); }

        .contact-links { display:flex; flex-direction:column; gap:.9rem; }
        .c-link {
            display:flex; align-items:center; gap:1rem; text-decoration:none;
            padding:1rem 1.25rem; background:var(--bg-card);
            border:1px solid var(--border-subtle); border-radius:10px;
            transition:border-color .2s, transform .2s, box-shadow .2s;
        }
        .c-link:hover { border-color:var(--border-accent); transform:translateX(4px); box-shadow:var(--shadow-glow); }
        .c-ico {
            width:38px; height:38px; border-radius:8px;
            display:flex; align-items:center; justify-content:center; font-size:1rem; flex-shrink:0;
        }
        .ico-email    { background:rgba(239,68,68,.12);  color:#F87171; }
        .ico-phone    { background:rgba(16,185,129,.12); color:#6EE7B7; }
        .ico-linkedin { background:rgba(10,102,194,.15); color:#60A5FA; }
        .ico-github   { background:rgba(255,255,255,.05);color:#E2E8F0; }
        .ico-whatsapp { background:rgba(37,211,102,.12); color:#4ADE80; }

        .c-txt { flex:1; }
        .c-lbl { font-family:'Fira Code',monospace; font-size:.7rem; color:var(--text-3); letter-spacing:.09em; text-transform:uppercase; margin-bottom:.15rem; }
        .c-val { font-size:.9rem; font-weight:500; color:var(--text-1); }
        .c-arr { color:var(--text-3); font-size:.8rem; transition:color .2s, transform .2s; }
        .c-link:hover .c-arr { color:var(--accent-purple); transform:translateX(3px); }

        /* ── FOOTER ── */
        footer {
            padding:2rem; text-align:center; border-top:1px solid var(--border-subtle);
            font-size:.83rem; color:var(--text-3);
        }
        footer span { color:var(--accent-purple); }

        /* ── SCROLL REVEAL ── */
        .reveal { opacity:0; transform:translateY(22px); transition:opacity .65s ease, transform .65s ease; }
        .reveal.in { opacity:1; transform:translateY(0); }

        /* ── RESPONSIVE TWEAKS ── */
        @media(max-width:768px){
            nav { padding:1rem 1.25rem; }
            nav.scrolled { padding:.75rem 1.25rem; }
            .nav-links { display:none; }
            .nav-burger { display:block; }
            #hero { padding:7.5rem 1.25rem 3.5rem; }
            section { padding:4.5rem 1.25rem; }
        }
    </style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
    <a href="#hero" class="nav-logo">ST.</a>
    <ul class="nav-links" id="navLinks">
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#contact" class="btn-hire">Hire Me</a></li>
    </ul>
    <button class="nav-burger" id="burger"><i class="fas fa-bars"></i></button>
</nav>

<!-- HERO -->
<section id="hero">
    <div class="orb orb-1"></div>
    <div class="orb orb-2"></div>
    <div class="hero-content">
        <div class="eyebrow-pill">
            <span class="pill-dot"></span> Available for roles &amp; internships — 2026
        </div>
        <h1 class="hero-name">
            Sampath<br><span class="grad">Tholla</span>
        </h1>
        <p class="hero-title">Full-Stack Developer &nbsp;·&nbsp; ASP.NET Core &amp; Angular</p>
        <p class="hero-desc">
            I build secure, scalable 
