<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Careers — Hearth &amp; Home</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  /* ============ Base ============ */
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #faf7f2;
    --surface: #ffffff;
    --surface-2: #f4efe7;
    --ink: #16221c;
    --muted: #6b7a72;
    --line: #e6e0d6;
    --line-strong: #d6cec0;
    --accent: #1f6f54;
    --accent-dark: #155841;
    --accent-soft: #e7f2ec;
    --amber: #d98634;
    --amber-soft: #fdf1e0;
    --rose-soft: #fbe9e4;
    --blue-soft: #e8eef7;
    --radius: 18px;
    --max: 1180px;
    --nav-h: 74px;
    --shadow-sm: 0 1px 2px rgba(22, 34, 28, .05), 0 10px 26px -16px rgba(22, 34, 28, .25);
    --shadow-md: 0 24px 60px -28px rgba(22, 34, 28, .4);
  }

  html { scroll-behavior: smooth; scroll-padding-top: 96px; }

  body {
    font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', sans-serif;
    background: var(--bg);
    color: var(--ink);
    line-height: 1.65;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }

  body::before {
    content: "";
    position: fixed;
    inset: 0;
    background:
      radial-gradient(620px 420px at 8% -6%, rgba(31, 111, 84, .10), transparent 70%),
      radial-gradient(560px 380px at 96% 2%, rgba(217, 134, 52, .10), transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  img, svg { display: block; max-width: 100%; }
  a { color: inherit; text-decoration: none; }
  button { font: inherit; color: inherit; cursor: pointer; border: none; background: none; }
  ul { list-style: none; }
  input, textarea { font: inherit; }

  .container {
    width: 100%;
    max-width: var(--max);
    margin-inline: auto;
    padding-inline: 22px;
    position: relative;
    z-index: 1;
  }

  h1, h2, h3 {
    font-family: 'Fraunces', Georgia, serif;
    font-weight: 600;
    letter-spacing: -.02em;
    line-height: 1.12;
  }

  /* ============ Buttons ============ */
  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    padding: 13px 24px;
    border-radius: 999px;
    font-weight: 600;
    font-size: .93rem;
    letter-spacing: -.01em;
    transition: transform .18s ease, background .2s ease, border-color .2s ease, box-shadow .2s ease, color .2s ease;
    white-space: nowrap;
  }
  .btn:active { transform: translateY(1px) scale(.995); }

  .btn-primary {
    background: var(--accent);
    color: #fff;
    box-shadow: 0 12px 26px -14px rgba(31, 111, 84, .9);
  }
  .btn-primary:hover { background: var(--accent-dark); box-shadow: 0 16px 30px -14px rgba(31, 111, 84, 1); }

  .btn-ghost {
    border: 1px solid var(--line-strong);
    background: var(--surface);
    color: var(--ink);
  }
  .btn-ghost:hover { border-color: var(--ink); background: #fff; }

  .btn-sm { padding: 10px 20px; font-size: .86rem; }

  /* ============ Navbar ============ */
  .nav {
    position: sticky;
    top: 0;
    z-index: 60;
    height: var(--nav-h);
    display: flex;
    align-items: center;
    border-bottom: 1px solid transparent;
    transition: background .3s ease, border-color .3s ease, backdrop-filter .3s ease;
  }
  .nav.scrolled {
    background: rgba(250, 247, 242, .82);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom-color: var(--line);
  }

  .nav-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    width: 100%;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Fraunces', serif;
    font-weight: 700;
    font-size: 1.14rem;
    letter-spacing: -.02em;
  }
  .logo-mark {
    width: 34px; height: 34px;
    border-radius: 10px;
    background: linear-gradient(145deg, var(--accent), #2e8f6d);
    color: #fff;
    display: grid; place-items: center;
    box-shadow: 0 8px 18px -10px rgba(31, 111, 84, .9);
  }
  .logo em { font-style: normal; color: var(--muted); font-weight: 500; }

  .nav-links { display: flex; align-items: center; gap: 4px; }
  .nav-links a {
    padding: 9px 14px;
    border-radius: 999px;
    font-size: .9rem;
    font-weight: 500;
    color: var(--muted);
    transition: color .18s ease, background .18s ease;
  }
  .nav-links a:hover { color: var(--ink); background: rgba(22, 34, 28, .05); }

  .nav-actions { display: flex; align-items: center; gap: 10px; }

  .burger {
    display: none;
    width: 42px; height: 42px;
    border: 1px solid var(--line-strong);
    border-radius: 11px;
    background: var(--surface);
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 5px;
  }
  .burger span {
    width: 17px; height: 2px;
    border-radius: 2px;
    background: var(--ink);
    transition: transform .3s ease, opacity .25s ease;
  }
  .burger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .burger.open span:nth-child(2) { opacity: 0; }
  .burger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  .mobile-menu {
    position: fixed;
    inset: var(--nav-h) 0 auto 0;
    z-index: 55;
    background: rgba(250, 247, 242, .98);
    backdrop-filter: blur(18px);
    -webkit-backdrop-filter: blur(18px);
    border-bottom: 1px solid var(--line);
    padding: 12px 22px 24px;
    display: grid;
    gap: 2px;
    opacity: 0;
    visibility: hidden;
    transform: translateY(-10px);
    transition: opacity .25s ease, transform .25s ease, visibility .25s;
  }
  .mobile-menu.open { opacity: 1; visibility: visible; transform: translateY(0); }
  .mobile-menu a {
    padding: 13px 10px;
    border-radius: 12px;
    font-weight: 500;
    color: var(--muted);
  }
  .mobile-menu a:hover { background: rgba(22, 34, 28, .05); color: var(--ink); }
  .mobile-menu .btn { margin-top: 10px; width: 100%; }

  /* ============ Hero ============ */
  .hero { padding: 62px 0 70px; }

  .hero-grid {
    display: grid;
    grid-template-columns: 1.05fr .95fr;
    gap: 56px;
    align-items: center;
  }

  .pill {
    display: inline-flex;
    align-items: center;
    gap: 9px;
    padding: 7px 15px 7px 10px;
    border-radius: 999px;
    background: var(--accent-soft);
    border: 1px solid rgba(31, 111, 84, .2);
    color: var(--accent-dark);
    font-size: .79rem;
    font-weight: 600;
    margin-bottom: 22px;
  }
  .pill .dot {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--accent);
    animation: pulse 2.2s infinite;
  }
  @keyframes pulse {
    0% { box-shadow: 0 0 0 0 rgba(31, 111, 84, .5); }
    70% { box-shadow: 0 0 0 9px rgba(31, 111, 84, 0); }
    100% { box-shadow: 0 0 0 0 rgba(31, 111, 84, 0); }
  }

  h1 {
    font-size: clamp(2.1rem, 5vw, 3.4rem);
    margin-bottom: 20px;
  }
  h1 .accent {
    position: relative;
    color: var(--accent);
    white-space: nowrap;
  }
  h1 .accent::after {
    content: "";
    position: absolute;
    left: 2%;
    right: 2%;
    bottom: .06em;
    height: .16em;
    border-radius: 999px;
    background: var(--amber);
    opacity: .35;
    z-index: -1;
  }

  .hero-sub {
    color: var(--muted);
    font-size: 1.04rem;
    max-width: 520px;
    margin-bottom: 30px;
  }

  .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; }

  .hero-note {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 24px;
    font-size: .84rem;
    color: var(--muted);
  }
  .avatars { display: flex; }
  .avatars span {
    width: 28px; height: 28px;
    border-radius: 50%;
    border: 2px solid var(--bg);
    margin-left: -8px;
    display: grid; place-items: center;
    font-size: .66rem;
    font-weight: 700;
    color: var(--accent-dark);
    background: var(--accent-soft);
  }
  .avatars span:nth-child(1) { margin-left: 0; background: var(--amber-soft); color: #95551a; }
  .avatars span:nth-child(2) { background: var(--rose-soft); color: #9c4a34; }
  .avatars span:nth-child(3) { background: var(--blue-soft); color: #33557f; }

  /* Hero collage */
  .collage {
    position: relative;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
  }
  .tile {
    aspect-ratio: 1 / 1;
    border-radius: 22px;
    display: grid;
    place-items: center;
    border: 1px solid rgba(22, 34, 28, .06);
    box-shadow: var(--shadow-sm);
    transition: transform .3s ease;
  }
  .tile:hover { transform: translateY(-4px); }
  .tile svg { width: 46%; height: 46%; color: rgba(22, 34, 28, .62); }

  .tile-1 { background: linear-gradient(150deg, #fdf1e0, #f8e2c6); }
  .tile-2 { background: linear-gradient(150deg, #e7f2ec, #d3e8dc); }
  .tile-3 { background: linear-gradient(150deg, #fbe9e4, #f6d9d0); }
  .tile-4 { background: linear-gradient(150deg, #e8eef7, #d8e3f3); }

  .collage-badge {
    position: absolute;
    left: -14px;
    bottom: -18px;
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: 15px;
    padding: 13px 17px;
    box-shadow: var(--shadow-md);
    display: flex;
    align-items: center;
    gap: 11px;
  }
  .collage-badge .dot {
    width: 9px; height: 9px; border-radius: 50%;
    background: var(--accent);
    flex: 0 0 9px;
  }
  .collage-badge strong { display: block; font-size: .87rem; letter-spacing: -.01em; }
  .collage-badge small { font-size: .74rem; color: var(--muted); }

  /* ============ Stats ============ */
  .stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--line);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    overflow: hidden;
    box-shadow: var(--shadow-sm);
  }
  .stat {
    background: var(--surface);
    padding: 26px 20px;
    text-align: center;
  }
  .stat strong {
    display: block;
    font-family: 'Fraunces', serif;
    font-size: 1.65rem;
    font-weight: 700;
    letter-spacing: -.02em;
  }
  .stat span { font-size: .82rem; color: var(--muted); }

  /* ============ Sections ============ */
  .section { padding: 82px 0; }
  .sec-head { max-width: 640px; margin-bottom: 42px; }
  .eyebrow {
    font-size: .76rem;
    font-weight: 700;
    letter-spacing: .16em;
    text-transform: uppercase;
    color: var(--amber);
    margin-bottom: 12px;
  }
  h2 { font-size: clamp(1.6rem, 3.3vw, 2.35rem); margin-bottom: 14px; }
  .sec-head p { color: var(--muted); }

  /* ============ Values / Perks ============ */
  .perks-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .perk {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    padding: 26px 24px;
    transition: transform .22s ease, box-shadow .22s ease, border-color .22s ease;
  }
  .perk:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-sm);
    border-color: var(--line-strong);
  }
  .perk-icon {
    width: 44px; height: 44px;
    border-radius: 13px;
    display: grid; place-items: center;
    background: var(--accent-soft);
    color: var(--accent-dark);
    margin-bottom: 16px;
  }
  .perk:nth-child(2n) .perk-icon { background: var(--amber-soft); color: #a1652a; }
  .perk:nth-child(3n) .perk-icon { background: var(--blue-soft); color: #33557f; }
  .perk h3 { font-size: 1.04rem; margin-bottom: 7px; }
  .perk p { font-size: .9rem; color: var(--muted); }

  /* ============ Jobs ============ */
  .jobs-toolbar {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 22px;
  }

  .tabs {
    display: flex;
    gap: 7px;
    overflow-x: auto;
    padding-bottom: 4px;
    scrollbar-width: none;
  }
  .tabs::-webkit-scrollbar { display: none; }

  .tab {
    padding: 9px 16px;
    border-radius: 999px;
    font-size: .85rem;
    font-weight: 600;
    color: var(--muted);
    background: var(--surface);
    border: 1px solid var(--line);
    white-space: nowrap;
    transition: all .18s ease;
  }
  .tab:hover { color: var(--ink); border-color: var(--line-strong); }
  .tab.active {
    background: var(--accent);
    border-color: var(--accent);
    color: #fff;
    box-shadow: 0 8px 20px -12px rgba(31, 111, 84, .9);
  }

  .search-wrap { position: relative; flex: 1 1 240px; max-width: 290px; }
  .search-wrap svg {
    position: absolute;
    left: 15px; top: 50%;
    transform: translateY(-50%);
    width: 16px; height: 16px;
    stroke: var(--muted);
    pointer-events: none;
  }
  .search {
    width: 100%;
    padding: 12px 16px 12px 42px;
    border-radius: 999px;
    background: var(--surface);
    border: 1px solid var(--line);
    color: var(--ink);
    font-size: .88rem;
    outline: none;
    transition: border-color .2s ease, box-shadow .2s ease;
  }
  .search::placeholder { color: #a1aaa4; }
  .search:focus { border-color: var(--accent); box-shadow: 0 0 0 4px rgba(31, 111, 84, .1); }

  .result-count { font-size: .82rem; color: var(--muted); margin-bottom: 14px; }
  .result-count b { color: var(--ink); }

  .job-list { display: grid; gap: 12px; }

  .job {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    overflow: hidden;
    transition: border-color .22s ease, box-shadow .22s ease;
  }
  .job:hover { border-color: var(--line-strong); }
  .job.open { border-color: rgba(31, 111, 84, .45); box-shadow: var(--shadow-sm); }

  .job-head {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 18px;
    padding: 20px 22px;
    text-align: left;
  }
  .job-main { flex: 1; min-width: 0; }
  .job-title { font-family: 'Inter', sans-serif; font-size: 1.02rem; font-weight: 700; letter-spacing: -.015em; margin-bottom: 7px; }
  .job-meta {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 8px;
    font-size: .77rem;
    color: var(--muted);
  }
  .tag {
    padding: 3px 10px;
    border-radius: 999px;
    background: var(--surface-2);
    border: 1px solid var(--line);
    white-space: nowrap;
  }
  .tag.dept { color: var(--accent-dark); background: var(--accent-soft); border-color: rgba(31, 111, 84, .22); }
  .tag.new { color: #95551a; background: var(--amber-soft); border-color: rgba(217, 134, 52, .3); font-weight: 600; }

  .job-arrow {
    width: 34px; height: 34px;
    flex: 0 0 34px;
    border-radius: 50%;
    display: grid; place-items: center;
    border: 1px solid var(--line);
    color: var(--muted);
    transition: transform .3s ease, border-color .3s ease, color .3s ease, background .3s ease;
  }
  .job.open .job-arrow {
    transform: rotate(180deg);
    border-color: rgba(31, 111, 84, .5);
    background: var(--accent-soft);
    color: var(--accent-dark);
  }

  .job-body {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows .35s cubic-bezier(.4, 0, .2, 1);
  }
  .job.open .job-body { grid-template-rows: 1fr; }
  .job-body-inner { overflow: hidden; }
  .job-body-content {
    padding: 18px 22px 22px;
    border-top: 1px solid var(--line);
  }
  .job-body-content p { color: var(--muted); font-size: .9rem; margin-bottom: 16px; }

  .chip-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }
  .chip {
    font-size: .75rem;
    font-weight: 600;
    padding: 5px 12px;
    border-radius: 999px;
    background: var(--blue-soft);
    color: #33557f;
  }

  .job-actions { display: flex; flex-wrap: wrap; gap: 10px; }

  .empty {
    text-align: center;
    padding: 58px 20px;
    border: 1px dashed var(--line-strong);
    border-radius: var(--radius);
    color: var(--muted);
    background: var(--surface);
  }
  .empty strong { display: block; color: var(--ink); font-size: 1.02rem; margin-bottom: 6px; font-family: 'Inter', sans-serif; }

  /* ============ Process ============ */
  .process {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
  }
  .step {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    padding: 24px 22px;
    position: relative;
  }
  .step-num {
    font-family: 'Fraunces', serif;
    font-size: .95rem;
    font-weight: 700;
    width: 32px; height: 32px;
    border-radius: 50%;
    display: grid; place-items: center;
    background: var(--accent);
    color: #fff;
    margin-bottom: 14px;
  }
  .step h3 { font-size: 1rem; margin-bottom: 6px; }
  .step p { font-size: .87rem; color: var(--muted); }

  /* ============ Testimonials ============ */
  .quotes {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .quote {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: var(--radius);
    padding: 26px 24px;
    display: flex;
    flex-direction: column;
    gap: 18px;
    transition: transform .22s ease, box-shadow .22s ease;
  }
  .quote:hover { transform: translateY(-4px); box-shadow: var(--shadow-sm); }
  .quote p { font-size: .93rem; color: #38473f; }
  .quote p::before { content: "“"; color: var(--amber); font-family: 'Fraunces', serif; font-size: 1.6rem; line-height: 0; vertical-align: -.2em; margin-right: 2px; }
  .quote-author { display: flex; align-items: center; gap: 11px; margin-top: auto; }
  .quote-avatar {
    width: 38px; height: 38px;
    border-radius: 50%;
    display: grid; place-items: center;
    font-size: .8rem;
    font-weight: 700;
    background: var(--accent-soft);
    color: var(--accent-dark);
    flex: 0 0 38px;
  }
  .quote-author strong { display: block; font-size: .87rem; }
  .quote-author small { color: var(--muted); font-size: .78rem; }

  /* ============ CTA ============ */
  .cta-wrap {
    border-radius: 24px;
    border: 1px solid rgba(31, 111, 84, .18);
    background:
      radial-gradient(560px 260px at 12% 0%, rgba(31, 111, 84, .12), transparent 70%),
      radial-gradient(520px 260px at 88% 100%, rgba(217, 134, 52, .16), transparent 70%),
      var(--surface);
    padding: 58px 40px;
    text-align: center;
    box-shadow: var(--shadow-sm);
  }
  .cta-wrap h2 { margin-bottom: 12px; }
  .cta-wrap p { color: var(--muted); max-width: 520px; margin: 0 auto 28px; }
  .cta-actions { display: flex; flex-wrap: wrap; gap: 12px; justify-content: center; }

  /* ============ Footer ============ */
  footer {
    border-top: 1px solid var(--line);
    padding: 48px 0 32px;
    margin-top: 30px;
  }
  .footer-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    justify-content: space-between;
    margin-bottom: 34px;
  }
  .footer-brand { max-width: 290px; }
  .footer-brand p { color: var(--muted); font-size: .87rem; margin-top: 14px; }
  .footer-cols { display: flex; flex-wrap: wrap; gap: 56px; }
  .footer-col h4 {
    font-size: .75rem;
    text-transform: uppercase;
    letter-spacing: .13em;
    color: var(--muted);
    margin-bottom: 14px;
    font-weight: 700;
  }
  .footer-col a {
    display: block;
    font-size: .88rem;
    color: var(--ink);
    opacity: .78;
    padding: 5px 0;
    transition: opacity .18s ease, color .18s ease;
  }
  .footer-col a:hover { opacity: 1; color: var(--accent); }

  .footer-bottom {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: space-between;
    align-items: center;
    padding-top: 22px;
    border-top: 1px solid var(--line);
    font-size: .81rem;
    color: var(--muted);
  }

  /* ============ Modal ============ */
  .modal {
    position: fixed;
    inset: 0;
    z-index: 100;
    display: grid;
    place-items: center;
    padding: 20px;
    opacity: 0;
    visibility: hidden;
    transition: opacity .25s ease, visibility .25s;
  }
  .modal.open { opacity: 1; visibility: visible; }

  .modal-backdrop {
    position: absolute;
    inset: 0;
    background: rgba(18, 28, 23, .45);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
  }

  .modal-card {
    position: relative;
    width: 100%;
    max-width: 500px;
    max-height: 90vh;
    overflow-y: auto;
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: 22px;
    padding: 30px;
    box-shadow: var(--shadow-md);
    transform: translateY(16px) scale(.98);
    transition: transform .3s cubic-bezier(.2, .8, .3, 1);
  }
  .modal.open .modal-card { transform: translateY(0) scale(1); }

  .modal-close {
    position: absolute;
    top: 16px; right: 16px;
    width: 34px; height: 34px;
    border-radius: 50%;
    display: grid; place-items: center;
    border: 1px solid var(--line);
    color: var(--muted);
    background: var(--surface);
    transition: all .18s ease;
  }
  .modal-close:hover { background: var(--surface-2); color: var(--ink); }

  .modal-card h3 { font-size: 1.32rem; margin-bottom: 6px; }
  .modal-role { font-size: .86rem; font-weight: 600; color: var(--accent); margin-bottom: 22px; }

  .field { margin-bottom: 15px; }
  .field label {
    display: block;
    font-size: .79rem;
    font-weight: 600;
    color: var(--muted);
    margin-bottom: 7px;
  }
  .field input,
  .field textarea {
    width: 100%;
    padding: 12px 14px;
    border-radius: 11px;
    background: var(--bg);
    border: 1px solid var(--line);
    color: var(--ink);
    font-size: .9rem;
    outline: none;
    transition: border-color .2s ease, box-shadow .2s ease, background .2s ease;
  }
  .field input:focus,
  .field textarea:focus {
    border-color: var(--accent);
    background: #fff;
    box-shadow: 0 0 0 4px rgba(31, 111, 84, .1);
  }
  .field textarea { resize: vertical; min-height: 90px; }
  .field input::placeholder,
  .field textarea::placeholder { color: #a6aea8; }

  .row-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }

  .form-note { font-size: .76rem; color: var(--muted); margin-top: 12px; text-align: center; }

  .success { text-align: center; padding: 24px 6px; }
  .success .check {
    width: 62px; height: 62px;
    margin: 0 auto 18px;
    border-radius: 50%;
    display: grid; place-items: center;
    background: var(--accent-soft);
    border: 1px solid rgba(31, 111, 84, .35);
    color: var(--accent-dark);
  }
  .success h3 { margin-bottom: 8px; }
  .success p { color: var(--muted); font-size: .9rem; }

  /* ============ Reveal ============ */
  .reveal {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity .7s cubic-bezier(.2, .8, .3, 1), transform .7s cubic-bezier(.2, .8, .3, 1);
  }
  .reveal.in { opacity: 1; transform: none; }

  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; }
    .reveal { opacity: 1; transform: none; }
  }

  /* ============ Responsive ============ */
  @media (max-width: 1000px) {
    .nav-links, .nav-actions .btn-ghost { display: none; }
    .burger { display: flex; }
    .hero-grid { grid-template-columns: 1fr; gap: 46px; }
    .collage { max-width: 430px; }
    .perks-grid { grid-template-columns: repeat(2, 1fr); }
    .process { grid-template-columns: repeat(2, 1fr); }
    .quotes { grid-template-columns: 1fr; }
    .stats { grid-template-columns: repeat(2, 1fr); }
  }

  @media (max-width: 640px) {
    :root { --nav-h: 66px; }
    .hero { padding: 42px 0 54px; }
    .section { padding: 58px 0; }
    .perks-grid { grid-template-columns: 1fr; }
    .process { grid-template-columns: 1fr; }
    .stat { padding: 20px 14px; }
    .stat strong { font-size: 1.35rem; }
    .jobs-toolbar { flex-direction: column; align-items: stretch; }
    .search-wrap { max-width: none; }
    .job-head { padding: 16px; gap: 12px; }
    .job-body-content { padding: 16px; }
    .row-2 { grid-template-columns: 1fr; }
    .modal-card { padding: 24px 20px; }
    .cta-wrap { padding: 42px 22px; }
    .footer-cols { gap: 32px; }
    .footer-bottom { justify-content: flex-start; }
    .hero-actions .btn { flex: 1 1 auto; }
    .collage-badge { left: 8px; bottom: -14px; }
  }
</style>
</head>
<body>

<!-- ================= NAV ================= -->
<header class="nav" id="nav">
  <div class="container nav-inner">
    <a href="#" class="logo">
      <span class="logo-mark">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 10.5 12 3l9 7.5"/><path d="M5 9.5V21h14V9.5"/><path d="M9.5 21v-6h5v6"/></svg>
      </span>
      Hearth<em>&amp;Home</em>
    </a>

    <nav class="nav-links">
      <a href="#openings">Open roles</a>
      <a href="#benefits">Benefits</a>
      <a href="#process">Hiring process</a>
      <a href="#people">Our people</a>
    </nav>

    <div class="nav-actions">
      <a href="#openings" class="btn btn-ghost btn-sm">Refer a friend</a>
      <a href="#openings" class="btn btn-primary btn-sm">View openings</a>
      <button class="burger" id="burger" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
</header>

<div class="mobile-menu" id="mobileMenu">
  <a href="#openings">Open roles</a>
  <a href="#benefits">Benefits</a>
  <a href="#process">Hiring process</a>
  <a href="#people">Our people</a>
  <a href="#openings" class="btn btn-primary">View openings</a>
</div>

<main>
  <!-- ================= HERO ================= -->
  <section class="hero">
    <div class="container hero-grid">
      <div>
        <div class="pill"><span class="dot"></span> 12 open roles across 6 teams</div>
        <h1>Help every home feel <span class="accent">better</span>.</h1>
        <p class="hero-sub">
          We design, source and deliver the everyday things that make a house a home —
          and we're growing our team of store, warehouse, design and support people.
        </p>
        <div class="hero-actions">
          <a href="#openings" class="btn btn-primary">
            Browse open roles
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
          </a>
          <a href="#benefits" class="btn btn-ghost">Why work here</a>
        </div>
        <div class="hero-note">
          <div class="avatars"><span>AM</span><span>JT</span><span>RK</span><span>+</span></div>
          <span>Trusted by 500+ team members across 68 stores</span>
        </div>
      </div>

      <div class="collage reveal">
        <div class="tile tile-1">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M8 3h8l-1 9H9L8 3Z"/><path d="M12 12v7"/><path d="M8.5 21h7"/>
          </svg>
        </div>
        <div class="tile tile-2">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M4 9h13v6a4 4 0 0 1-4 4H8a4 4 0 0 1-4-4V9Z"/><path d="M17 10h2a2.5 2.5 0 0 1 0 5h-2"/><path d="M7 5.5c0-1 1-1.5 1-2.5"/>
          </svg>
        </div>
        <div class="tile tile-3">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M7 11V7a2 2 0 0 1 2-2h6a2 2 0 0 1 2 2v4"/><path d="M5 11h14v6a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2v-6Z"/><path d="M5 14h14"/>
          </svg>
        </div>
        <div class="tile tile-4">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M12 21V11"/><path d="M12 12c0-4 3-7 7-7 0 4-3 7-7 7Z"/><path d="M12 15c0-3-2.5-5.5-5.5-5.5C6.5 12.5 9 15 12 15Z"/>
          </svg>
        </div>
        <div class="collage-badge">
          <span class="dot"></span>
          <div>
            <strong>Hiring now</strong>
            <small>12 roles · 6 teams</small>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= STATS ================= -->
  <section class="container">
    <div class="stats reveal">
      <div class="stat"><strong>68</strong><span>Stores nationwide</span></div>
      <div class="stat"><strong>1.4M</strong><span>Households served</span></div>
      <div class="stat"><strong>4.8/5</strong><span>Customer rating</span></div>
      <div class="stat"><strong>92%</strong><span>Team retention</span></div>
    </div>
  </section>

  <!-- ================= BENEFITS ================= -->
  <section class="section" id="benefits">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Benefits</div>
        <h2>Good work deserves good support</h2>
        <p>Whether you're on the shop floor, in the warehouse or behind a screen, these are the things we offer everyone — no tiers, no fine print.</p>
      </div>

      <div class="perks-grid">
        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.7l-1-1.1a5.5 5.5 0 0 0-7.8 7.8l8.8 8.8 8.8-8.8a5.5 5.5 0 0 0 0-7.8Z"/></svg>
          </div>
          <h3>Health cover from day one</h3>
          <p>Medical, dental and vision for you and your dependents, plus free annual check-ups.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M6 2 3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4Z"/><path d="M3 6h18"/><path d="M16 10a4 4 0 0 1-8 0"/></svg>
          </div>
          <h3>30% staff discount</h3>
          <p>On everything we sell, all year round — including furniture and large appliances.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9 9 9 0 0 0-9 9Z"/><path d="M12 7v5l3 2"/></svg>
          </div>
          <h3>Flexible scheduling</h3>
          <p>Self-managed shift swaps for store teams and hybrid hours for office roles.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10 12 5 2 10l10 5 10-5Z"/><path d="M6 12v5c0 1.7 2.7 3 6 3s6-1.3 6-3v-5"/></svg>
          </div>
          <h3>Learning stipend</h3>
          <p>$1,500 a year for courses and certifications, plus paid study days for exams.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 21V11"/><path d="M12 12c0-4 3-7 7-7 0 4-3 7-7 7Z"/><path d="M12 15c0-3-2.5-5.5-5.5-5.5C6.5 12.5 9 15 12 15Z"/></svg>
          </div>
          <h3>Paid volunteer days</h3>
          <p>Three days a year to support local housing and community projects near you.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20V10M10 20V4M16 20v-7M22 20v-4"/></svg>
          </div>
          <h3>Clear growth paths</h3>
          <p>Published pay bands and promotion criteria for every role. No mystery boxes.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= OPEN ROLES ================= -->
  <section class="section" id="openings">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Open positions</div>
        <h2>Find your place on the team</h2>
        <p>Filter by team or search by keyword. Every application is read by a real person within 48 hours.</p>
      </div>

      <div class="jobs-toolbar reveal">
        <div class="tabs" id="tabs">
          <button class="tab active" data-filter="all">All roles</button>
          <button class="tab" data-filter="retail">Retail</button>
          <button class="tab" data-filter="logistics">Warehouse &amp; Delivery</button>
          <button class="tab" data-filter="care">Customer Care</button>
          <button class="tab" data-filter="design">Design &amp; Buying</button>
          <button class="tab" data-filter="marketing">Marketing</button>
          <button class="tab" data-filter="corporate">Corporate</button>
        </div>

        <div class="search-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="7"/><path d="m20 20-3.5-3.5"/></svg>
          <input type="search" class="search" id="search" placeholder="Search roles, cities, skills…" aria-label="Search roles" />
        </div>
      </div>

      <div class="result-count" id="resultCount"></div>
      <div class="job-list" id="jobList"></div>
    </div>
  </section>

  <!-- ================= PROCESS ================= -->
  <section class="section" id="process">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Hiring process</div>
        <h2>Four steps, about two weeks</h2>
        <p>No 6-round marathons. We keep it short, transparent and respectful of your time.</p>
      </div>

      <div class="process">
        <div class="step reveal">
          <div class="step-num">1</div>
          <h3>Apply</h3>
          <p>Send your details through the form. We reply to every applicant within 48 hours.</p>
        </div>
        <div class="step reveal">
          <div class="step-num">2</div>
          <h3>Intro chat</h3>
          <p>A 25-minute call with our talent team about your experience and what you're after.</p>
        </div>
        <div class="step reveal">
          <div class="step-num">3</div>
          <h3>Meet the team</h3>
          <p>A practical conversation with the hiring manager — no trick questions, no unpaid tasks.</p>
        </div>
        <div class="step reveal">
          <div class="step-num">4</div>
          <h3>Offer</h3>
          <p>Full details on pay, schedule and benefits in writing, then a warm welcome.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= PEOPLE ================= -->
  <section class="section" id="people">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Our people</div>
        <h2>What it's actually like here</h2>
        <p>Honest words from the people who build, pack, design and sell every day.</p>
      </div>

      <div class="quotes">
        <div class="quote reveal">
          <p>I started as a weekend sales assistant and I'm now running my own store. The promotion criteria were on paper from day one — no guessing.</p>
          <div class="quote-author">
            <span class="quote-avatar">AM</span>
            <div>
              <strong>Amara M.</strong>
              <small>Store Manager · Austin</small>
            </div>
          </div>
        </div>

        <div class="quote reveal">
          <p>The warehouse team gets real input on layout and process. My idea for a new packing station cut our dispatch time by a third.</p>
          <div class="quote-author">
            <span class="quote-avatar">JT</span>
            <div>
              <strong>Jonas T.</strong>
              <small>Warehouse Team Lead · Dallas</small>
            </div>
          </div>
        </div>

        <div class="quote reveal">
          <p>I design homeware that ships to 1.4 million households. That scale, with a small team and short approval chains, is rare.</p>
          <div class="quote-author">
            <span class="quote-avatar">RK</span>
            <div>
              <strong>Rina K.</strong>
              <small>Product Designer · Remote</small>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= CTA ================= -->
  <section class="section" style="padding-top:0">
    <div class="container">
      <div class="cta-wrap reveal">
        <h2>Nothing quite fits? Write to us anyway.</h2>
        <p>We're always interested in thoughtful people. Tell us what you'd bring to Hearth &amp; Home and we'll keep you in mind.</p>
        <div class="cta-actions">
          <button class="btn btn-primary" data-role="General application">Send a general application</button>
          <a href="#openings" class="btn btn-ghost">See all roles</a>
        </div>
      </div>
    </div>
  </section>
</main>

<!-- ================= FOOTER ================= -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <a href="#" class="logo">
          <span class="logo-mark">
            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 10.5 12 3l9 7.5"/><path d="M5 9.5V21h14V9.5"/><path d="M9.5 21v-6h5v6"/></svg>
          </span>
          Hearth<em>&amp;Home</em>
        </a>
        <p>Everyday things for every room — designed thoughtfully, made to last, delivered with care.</p>
      </div>

      <div class="footer-cols">
        <div class="footer-col">
          <h4>Careers</h4>
          <a href="#openings">Open roles</a>
          <a href="#benefits">Benefits</a>
          <a href="#process">Hiring process</a>
          <a href="#people">Our people</a>
        </div>
        <div class="footer-col">
          <h4>Company</h4>
          <a href="#">About us</a>
          <a href="#">Sustainability</a>
          <a href="#">Press</a>
          <a href="#">Contact</a>
        </div>
        <div class="footer-col">
          <h4>Follow</h4>
          <a href="#">Instagram</a>
          <a href="#">LinkedIn</a>
          <a href="#">Pinterest</a>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <span>© 2025 Hearth &amp; Home Retail. All rights reserved.</span>
      <span>Equal opportunity employer · Privacy · Terms</span>
    </div>
  </div>
</footer>

<!-- ================= APPLY MODAL ================= -->
<div class="modal" id="applyModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
  <div class="modal-backdrop" data-close-modal></div>

  <div class="modal-card">
    <button class="modal-close" data-close-modal aria-label="Close">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M18 6 6 18M6 6l12 12"/></svg>
    </button>

    <div id="formView">
      <h3 id="modalTitle">Apply now</h3>
      <div class="modal-role" id="modalRole">Position</div>

      <form id="applyForm" novalidate>
        <div class="row-2">
          <div class="field">
            <label for="fname">First name</label>
            <input type="text" id="fname" name="fname" placeholder="Alex" required />
          </div>
          <div class="field">
            <label for="lname">Last name</label>
            <input type="text" id="lname" name="lname" placeholder="Morgan" required />
          </div>
        </div>

        <div class="field">
          <label for="email">Email address</label>
          <input type="email" id="email" name="email" placeholder="alex@example.com" required />
        </div>

        <div class="field">
          <label for="phone">Phone number</label>
          <input type="tel" id="phone" name="phone" placeholder="(555) 123-4567" />
        </div>

        <div class="field">
          <label for="message">Why this role?</label>
          <textarea id="message" name="message" placeholder="Tell us briefly about your experience…"></textarea>
        </div>

        <button type="submit" class="btn btn-primary" style="width:100%">Submit application</button>
        <p class="form-note">We read every application. Expect a reply within 48 hours.</p>
      </form>
    </div>

    <div class="success" id="successView" style="display:none">
      <div class="check">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>
      </div>
      <h3>Application received</h3>
      <p>Thanks for applying to Hearth &amp; Home. Our talent team will be in touch within 48 hours.</p>
    </div>
  </div>
</div>

<script>
/* ============================================================
   JOB DATA — swap these for your real openings
============================================================ */
const jobs = [
  {
    id: 1,
    title: "Store Manager",
    dept: "retail",
    deptLabel: "Retail",
    location: "Austin, TX",
    type: "Full-time",
    isNew: true,
    desc: "Lead a team of 14 in our flagship store. You'll own the P&L, coach the floor team, and shape how customers experience the brand in person.",
    tags: ["Team leadership", "P&L ownership", "Visual standards"]
  },
  {
    id: 2,
    title: "Warehouse Team Lead",
    dept: "logistics",
    deptLabel: "Warehouse & Delivery",
    location: "Dallas, TX",
    type: "Full-time",
    isNew: false,
    desc: "Run the night shift for our main distribution centre. You'll manage 20+ pickers and packers, improve throughput and keep safety standards tight.",
    tags: ["Shift management", "Process improvement", "Safety"]
  },
  {
    id: 3,
    title: "Customer Care Specialist",
    dept: "care",
    deptLabel: "Customer Care",
    location: "Remote · US",
    type: "Full-time",
    isNew: true,
    desc: "Be the voice of Hearth & Home across chat, email and phone. Solve delivery issues, handle returns and turn frustrated customers into fans.",
    tags: ["Zendesk", "Empathy", "Problem solving"]
  },
  {
    id: 4,
    title: "Product Designer — Homeware",
    dept: "design",
    deptLabel: "Design & Buying",
    location: "Remote · US",
    type: "Full-time",
    isNew: false,
    desc: "Design textiles, storage and kitchen pieces from concept to factory-ready specs. You'll work with our sourcing team and visit suppliers twice a year.",
    tags: ["CAD", "Materials", "Trend research"]
  },
  {
    id: 5,
    title: "Junior Buyer — Home Textiles",
    dept: "design",
    deptLabel: "Design & Buying",
    location: "New York, NY",
    type: "Full-time",
    isNew: false,
    desc: "Support the buying team across bedding, curtains and rugs. Negotiate costs, track margins and help plan seasonal ranges.",
    tags: ["Negotiation", "Excel", "Range planning"]
  },
  {
    id: 6,
    title: "E-commerce Merchandiser",
    dept: "marketing",
    deptLabel: "Marketing",
    location: "Remote · US",
    type: "Full-time",
    isNew: true,
    desc: "Own how products appear online — categories, bundles, on-site search and seasonal campaigns. Small tweaks, measurable revenue impact.",
    tags: ["Shopify", "Analytics", "A/B testing"]
  },
  {
    id: 7,
    title: "Delivery Driver",
    dept: "logistics",
    deptLabel: "Warehouse & Delivery",
    location: "Austin, TX",
    type: "Full-time",
    isNew: false,
    desc: "Deliver furniture and appliances to customers' homes with care. You'll be the final, most memorable part of the customer experience.",
    tags: ["CDL preferred", "Customer facing", "Furniture assembly"]
  },
  {
    id: 8,
    title: "Sustainability & Sourcing Analyst",
    dept: "corporate",
    deptLabel: "Corporate",
    location: "Remote · US",
    type: "Full-time",
    isNew: false,
    desc: "Measure and reduce the footprint of our supply chain. You'll build supplier scorecards and report progress to the leadership team quarterly.",
    tags: ["Data analysis", "Supply chain", "Reporting"]
  },
  {
    id: 9,
    title: "Social Media Coordinator",
    dept: "marketing",
    deptLabel: "Marketing",
    location: "Remote · US",
    type: "Contract",
    isNew: true,
    desc: "Create short-form video and photography for our channels. You'll shoot real homes, real customers and our newest product drops.",
    tags: ["Short-form video", "Copywriting", "Instagram / TikTok"]
  },
  {
    id: 10,
    title: "Visual Merchandiser",
    dept: "retail",
    deptLabel: "Retail",
    location: "Chicago, IL",
    type: "Full-time",
    isNew: false,
    desc: "Design in-store displays across 12 regional stores. You'll translate seasonal themes into layouts that make people stop and browse.",
    tags: ["Store displays", "Seasonal resets", "Travel"]
  },
  {
    id: 11,
    title: "Retail Sales Assistant",
    dept: "retail",
    deptLabel: "Retail",
    location: "Austin, TX",
    type: "Part-time",
    isNew: true,
    desc: "Help customers find the right pieces for their space. Weekend and evening shifts available, with a clear path into full-time roles.",
    tags: ["Customer service", "Flexible shifts", "Entry level"]
  },
  {
    id: 12,
    title: "Customer Care Team Lead",
    dept: "care",
    deptLabel: "Customer Care",
    location: "Remote · US",
    type: "Full-time",
    isNew: false,
    desc: "Lead a pod of 8 care specialists. You'll own quality scores, coach on tricky cases and work with logistics to fix root causes.",
    tags: ["Coaching", "Quality", "Cross-functional"]
  }
];

/* ============================================================
   JOB LIST RENDERING
============================================================ */
const jobList = document.getElementById('jobList');
const tabsEl = document.getElementById('tabs');
const searchEl = document.getElementById('search');
const resultCount = document.getElementById('resultCount');

const chevron = `<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="m6 9 6 6 6-6"/></svg>`;

function jobHTML(job) {
  return `
    <article class="job" data-dept="${job.dept}">
      <button class="job-head" aria-expanded="false">
        <div class="job-main">
          <div class="job-title">${job.title}</div>
          <div class="job-meta">
            <span class="tag dept">${job.deptLabel}</span>
            <span class="tag">${job.location}</span>
            <span class="tag">${job.type}</span>
            ${job.isNew ? '<span class="tag new">New</span>' : ''}
          </div>
        </div>
        <span class="job-arrow" aria-hidden="true">${chevron}</span>
      </button>

      <div class="job-body">
        <div class="job-body-inner">
          <div class="job-body-content">
            <p>${job.desc}</p>
            <div class="chip-row">
              ${job.tags.map(t => `<span class="chip">${t}</span>`).join('')}
            </div>
            <div class="job-actions">
              <button class="btn btn-primary btn-sm apply-btn" data-role="${job.title}">Apply now</button>
              <button class="btn btn-ghost btn-sm save-btn">Save role</button>
            </div>
          </div>
        </div>
      </div>
    </article>
  `;
}

function renderJobs() {
  const activeTab = document.querySelector('.tab.active').dataset.filter;
  const q = searchEl.value.trim().toLowerCase();

  const filtered = jobs.filter(job => {
    const matchesDept = activeTab === 'all' || job.dept === activeTab;
    const haystack = `${job.title} ${job.deptLabel} ${job.location} ${job.type} ${job.tags.join(' ')}`.toLowerCase();
    const matchesQuery = !q || haystack.includes(q);
    return matchesDept && matchesQuery;
  });

  resultCount.innerHTML = `Showing <b>${filtered.length}</b> open role${filtered.length === 1 ? '' : 's'}`;

  if (!filtered.length) {
    jobList.innerHTML = `
      <div class="empty">
        <strong>No matching roles right now</strong>
        Try another keyword or clear the filters — new roles open most weeks.
      </div>`;
    return;
  }

  jobList.innerHTML = filtered.map(jobHTML).join('');
}

/* Tabs */
tabsEl.addEventListener('click', e => {
  const tab = e.target.closest('.tab');
  if (!tab) return;
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  tab.classList.add('active');
  renderJobs();
});

/* Search (debounced) */
let searchTimer;
searchEl.addEventListener('input', () => {
  clearTimeout(searchTimer);
  searchTimer = setTimeout(renderJobs, 140);
});

/* Accordion + apply + save (event delegation) */
jobList.addEventListener('click', e => {
  const applyBtn = e.target.closest('.apply-btn');
  if (applyBtn) {
    openModal(applyBtn.dataset.role);
    return;
  }

  const saveBtn = e.target.closest('.save-btn');
  if (saveBtn) {
    const saved = saveBtn.dataset.saved === '1';
    saveBtn.dataset.saved = saved ? '0' : '1';
    saveBtn.textContent = saved ? 'Save role' : 'Saved ✓';
    saveBtn.style.color = saved ? '' : 'var(--accent-dark)';
    saveBtn.style.borderColor = saved ? '' : 'rgba(31,111,84,.5)';
    return;
  }

  const head = e.target.closest('.job-head');
  if (!head) return;

  const card = head.closest('.job');
  const isOpen = card.classList.contains('open');

  document.querySelectorAll('.job.open').forEach(j => {
    j.classList.remove('open');
    j.querySelector('.job-head').setAttribute('aria-expanded', 'false');
  });

  if (!isOpen) {
    card.classList.add('open');
    head.setAttribute('aria-expanded', 'true');
  }
});

renderJobs();

/* ============================================================
   MODAL
============================================================ */
const modal = document.getElementById('applyModal');
const modalRole = document.getElementById('modalRole');
const formView = document.getElementById('formView');
const successView = document.getElementById('successView');
const applyForm = document.getElementById('applyForm');
let lastFocused = null;

function openModal(role) {
  lastFocused = document.activeElement;
  modalRole.textContent = role;
  formView.style.display = 'block';
  successView.style.display = 'none';
  applyForm.reset();
  applyForm.querySelectorAll('input, textarea').forEach(el => el.style.borderColor = '');
  modal.classList.add('open');
  document.body.style.overflow = 'hidden';
  setTimeout(() => document.getElementById('fname').focus(), 130);
}

function closeModal() {
  modal.classList.remove('open');
  document.body.style.overflow = '';
  if (lastFocused) lastFocused.focus();
}

document.querySelectorAll('[data-close-modal]').forEach(el => {
  el.addEventListener('click', closeModal);
});

document.addEventListener('keydown', e => {
  if (e.key === 'Escape' && modal.classList.contains('open')) closeModal();
});

document.querySelector('[data-role]').addEventListener('click', e => {
  openModal(e.currentTarget.dataset.role);
});

/* Form validation + success */
applyForm.addEventListener('submit', e => {
  e.preventDefault();

  const required = ['fname', 'lname', 'email'];
  let valid = true;

  required.forEach(id => {
    const input = document.getElementById(id);
    if (!input.value.trim()) {
      input.style.borderColor = '#d0453c';
      valid = false;
    } else {
      input.style.borderColor = '';
    }
  });

  const email = document.getElementById('email');
  if (email.value.trim() && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value)) {
    email.style.borderColor = '#d0453c';
    valid = false;
  }

  if (!valid) return;

  formView.style.display = 'none';
  successView.style.display = 'block';
  setTimeout(closeModal, 2800);
});

/* ============================================================
   NAVBAR / MOBILE MENU / SCROLL
============================================================ */
const nav = document.getElementById('nav');
const burger = document.getElementById('burger');
const mobileMenu = document.getElementById('mobileMenu');

window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 12);
}, { passive: true });

burger.addEventListener('click', () => {
  const open = burger.classList.toggle('open');
  mobileMenu.classList.toggle('open', open);
  burger.setAttribute('aria-expanded', String(open));
});

mobileMenu.addEventListener('click', e => {
  if (e.target.tagName === 'A') {
    burger.classList.remove('open');
    mobileMenu.classList.remove('open');
    burger.setAttribute('aria-expanded', 'false');
  }
});

/* ============================================================
   SCROLL REVEAL
============================================================ */
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      setTimeout(() => entry.target.classList.add('in'), i * 60);
      io.unobserve(entry.target);
    }
  });
}, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });

revealEls.forEach(el => io.observe(el));
</script>
</body>
</html>
