<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Diagnóstico de Compliance | Durán Sindreu Abogados</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Barlow:wght@300;400;500;600;700&family=Barlow+Condensed:wght@400;600;700;800;900&display=swap" rel="stylesheet">
<!-- Sin dependencias externas para email -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<style>
:root{
  --o:#E8510A;--o2:#C43E00;--ol:#FFF1EB;--op:#FDF6F3;
  --bk:#0D0D0D;--dk:#1C1C1C;--g8:#2E2E2E;--g6:#5A5A5A;--g4:#9A9A9A;--g2:#E8E8E8;--g1:#F5F5F5;
  --wh:#FFFFFF;--red:#C8322B;--amb:#B45309;--grn:#15803D;
  --red-bg:#FEF2F2;--amb-bg:#FFFBEB;--grn-bg:#F0FDF4;
}
*{margin:0;padding:0;box-sizing:border-box;}html{scroll-behavior:smooth;}
body{font-family:'Barlow',sans-serif;background:var(--wh);color:var(--dk);overflow-x:hidden;cursor:none;}
.cur{width:10px;height:10px;background:var(--o);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:width .12s,height .12s;}
.cur2{width:32px;height:32px;border:1.5px solid var(--o);border-radius:50%;position:fixed;top:0;left:0;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);opacity:.3;transition:all .07s ease-out;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:500;background:rgba(255,255,255,.96);backdrop-filter:blur(16px);border-bottom:1px solid var(--g2);padding:0 60px;}
.nav-inner{display:flex;align-items:center;justify-content:space-between;height:68px;}
.logo-main{font-family:'Barlow Condensed',sans-serif;font-size:19px;font-weight:900;letter-spacing:4px;color:var(--bk);text-transform:uppercase;}
.logo-sub{font-size:8.5px;letter-spacing:5px;color:var(--o);text-transform:uppercase;font-weight:600;}
.nav-cta{background:var(--o);color:white;padding:10px 22px;font-family:'Barlow Condensed',sans-serif;font-size:11px;letter-spacing:3px;font-weight:700;text-transform:uppercase;border:none;cursor:none;clip-path:polygon(8px 0,100% 0,calc(100% - 8px) 100%,0 100%);transition:background .2s;}
.nav-cta:hover{background:var(--o2);}

/* HERO */
#hero{min-height:100vh;padding-top:68px;display:grid;grid-template-columns:1.15fr .85fr;overflow:hidden;}
.hero-l{padding:88px 60px 80px;display:flex;flex-direction:column;justify-content:center;}
.eyebrow{display:flex;align-items:center;gap:12px;margin-bottom:26px;opacity:0;animation:fu .8s .3s forwards;}
.eyebrow-line{width:28px;height:1px;background:var(--o);}
.eyebrow-txt{font-family:'Barlow Condensed',sans-serif;font-size:10px;letter-spacing:5px;color:var(--o);text-transform:uppercase;font-weight:700;}
h1{font-family:'Playfair Display',serif;font-size:clamp(38px,4.6vw,64px);font-weight:900;line-height:.93;color:var(--bk);opacity:0;animation:fu .9s .5s forwards;}
h1 em{font-style:italic;color:var(--o);}
.hero-p{margin-top:22px;font-size:15px;font-weight:300;color:var(--g6);line-height:1.8;max-width:450px;opacity:0;animation:fu .9s .7s forwards;}
.hero-actions{margin-top:40px;display:flex;align-items:center;gap:18px;opacity:0;animation:fu .9s .9s forwards;}
.btn-main{background:var(--o);color:white;border:none;padding:17px 42px;font-family:'Barlow Condensed',sans-serif;font-size:12px;letter-spacing:3px;font-weight:800;text-transform:uppercase;cursor:none;clip-path:polygon(12px 0,100% 0,calc(100% - 12px) 100%,0 100%);transition:all .2s;position:relative;overflow:hidden;}
.btn-main::after{content:'';position:absolute;inset:0;background:rgba(255,255,255,.18);transform:translateX(-110%) skewX(-15deg);transition:transform .4s;}
.btn-main:hover::after{transform:translateX(110%) skewX(-15deg);}
.btn-main:hover{background:var(--o2);}
.btn-ghost{font-size:13px;color:var(--g4);text-decoration:none;border-bottom:1px solid var(--g2);padding-bottom:2px;transition:all .2s;cursor:none;}
.btn-ghost:hover{color:var(--o);border-color:var(--o);}
.hero-stats{margin-top:52px;display:flex;gap:36px;padding-top:30px;border-top:1px solid var(--g2);opacity:0;animation:fu .9s 1.1s forwards;}
.stat-n{font-family:'Barlow Condensed',sans-serif;font-size:34px;font-weight:900;color:var(--o);line-height:1;}
.stat-l{font-size:9.5px;letter-spacing:2px;color:var(--g4);text-transform:uppercase;margin-top:3px;}
.hero-r{background:var(--o);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;}
.hero-r::before{content:'';position:absolute;top:-60px;right:-60px;width:360px;height:360px;border-radius:50%;background:rgba(255,255,255,.05);}
.hero-r::after{content:'';position:absolute;bottom:-80px;left:-40px;width:280px;height:280px;border-radius:50%;background:rgba(0,0,0,.07);}
.hero-r-inner{position:relative;z-index:2;padding:52px 42px;color:white;}
.hero-r-label{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:5px;text-transform:uppercase;opacity:.55;margin-bottom:20px;}
.ri{background:rgba(0,0,0,.14);padding:13px 17px;display:flex;align-items:center;gap:12px;border:1px solid rgba(255,255,255,.09);margin-bottom:7px;transition:transform .2s;}
.ri:hover{transform:translateX(4px);}
.ri-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;}
.ri-dot.r{background:#FF8A80;}.ri-dot.a{background:#FFD180;}.ri-dot.g{background:#80E5A8;}
.ri-title{font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;}
.ri-sub{font-size:9.5px;opacity:.55;margin-top:1px;}
.law-pills{display:flex;flex-wrap:wrap;gap:5px;margin-top:20px;}
.lp{background:rgba(255,255,255,.11);padding:3px 8px;font-size:9.5px;letter-spacing:1.5px;font-family:'Barlow Condensed',sans-serif;text-transform:uppercase;}

/* MARCO */
.sec-label{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:5px;font-weight:700;color:var(--o);text-transform:uppercase;display:flex;align-items:center;gap:10px;margin-bottom:12px;}
.sec-label::before{content:'';display:block;width:22px;height:1px;background:var(--o);}
#marco{padding:110px 60px;background:var(--g1);}
.marco-grid{display:grid;grid-template-columns:340px 1fr;gap:76px;margin-top:50px;}
.marco-sticky{position:sticky;top:88px;}
.marco-h2{font-family:'Playfair Display',serif;font-size:38px;font-weight:900;line-height:1.05;color:var(--bk);}
.marco-h2 em{font-style:italic;color:var(--o);}
.marco-intro{margin-top:14px;font-size:13.5px;color:var(--g6);line-height:1.78;}
.marco-alert{margin-top:24px;padding:16px 20px;background:var(--o);color:white;}
.ma-label{font-family:'Barlow Condensed',sans-serif;font-size:8.5px;letter-spacing:3px;text-transform:uppercase;opacity:.7;margin-bottom:5px;}
.ma-text{font-size:12.5px;line-height:1.6;}
.marco-cards{display:flex;flex-direction:column;gap:2px;}
.mcard{background:white;padding:28px 32px;border-left:3px solid var(--g2);transition:all .22s;cursor:none;box-shadow:0 1px 2px rgba(0,0,0,.05);}
.mcard:hover{border-left-color:var(--o);transform:translateX(5px);box-shadow:0 4px 14px rgba(0,0,0,.09);}
.mc-num{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:3px;color:var(--o);text-transform:uppercase;margin-bottom:6px;}
.mc-title{font-family:'Barlow Condensed',sans-serif;font-size:16px;font-weight:800;color:var(--bk);text-transform:uppercase;margin-bottom:8px;}
.mc-text{font-size:13px;color:var(--g6);line-height:1.72;}
.mc-law{margin-top:10px;display:inline-block;padding:3px 8px;background:var(--ol);font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:2px;color:var(--o);text-transform:uppercase;font-weight:700;}

/* DIAGNOSTIC */
#diagnostico{padding:76px 0 0;}
.diag-top{padding:0 60px 48px;display:flex;justify-content:space-between;align-items:flex-end;border-bottom:2px solid var(--bk);}
.diag-h2{font-family:'Playfair Display',serif;font-size:46px;font-weight:900;line-height:1;color:var(--bk);}
.diag-h2 em{color:var(--o);font-style:italic;}
.prog-wrap{text-align:right;}
.prog-label{font-size:9.5px;letter-spacing:3px;color:var(--g4);text-transform:uppercase;margin-bottom:8px;}
.prog-track{width:180px;height:3px;background:var(--g2);margin-left:auto;overflow:hidden;}
.prog-fill{height:100%;background:var(--o);width:0%;transition:width .4s;}
.prog-pct{font-family:'Barlow Condensed',sans-serif;font-size:36px;font-weight:900;color:var(--o);margin-top:3px;}
.data-band{background:var(--bk);padding:48px 60px;}
.data-band-label{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:5px;color:var(--o);text-transform:uppercase;margin-bottom:18px;display:flex;align-items:center;gap:10px;}
.data-band-label::before{content:'';width:20px;height:1px;background:var(--o);}
.data-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;}
.df{display:flex;flex-direction:column;gap:6px;}
.df-label{font-size:8.5px;letter-spacing:4px;color:rgba(255,255,255,.3);text-transform:uppercase;font-family:'Barlow Condensed',sans-serif;font-weight:600;}
.df-label span{color:var(--o);}
.df-input{background:rgba(255,255,255,.04);border:none;border-bottom:2px solid rgba(232,81,10,.3);color:white;padding:11px 12px;font-family:'Barlow',sans-serif;font-size:13.5px;outline:none;transition:border-color .2s;cursor:auto;width:100%;}
.df-input:focus{border-bottom-color:var(--o);}
.df-input::placeholder{color:rgba(255,255,255,.18);}
.df-input option{background:#1C1C1C;}
.data-note{margin-top:11px;font-size:10.5px;color:rgba(255,255,255,.2);letter-spacing:.5px;}
.diag-body{padding:0 60px;}
.bwrap{padding:60px 0;border-bottom:1px solid var(--g2);opacity:0;transform:translateY(24px);transition:all .5s;}
.bwrap.in{opacity:1;transform:translateY(0);}
.bhead{display:grid;grid-template-columns:68px 1fr 120px;gap:18px;align-items:start;margin-bottom:36px;}
.bn{font-family:'Barlow Condensed',sans-serif;font-size:76px;font-weight:900;color:rgba(232,81,10,.06);line-height:1;}
.btitle{font-family:'Playfair Display',serif;font-size:25px;font-weight:700;color:var(--bk);margin-bottom:4px;}
.bnorm{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:3px;color:var(--o);text-transform:uppercase;font-weight:600;}
.bdesc{margin-top:8px;font-size:12.5px;color:var(--g6);line-height:1.65;max-width:500px;}
.bscore{background:var(--op);border:1px solid rgba(232,81,10,.14);padding:14px;text-align:center;}
.bscore-n{font-family:'Barlow Condensed',sans-serif;font-size:42px;font-weight:900;color:var(--o);line-height:1;}
.bscore-m{font-size:10.5px;color:var(--g4);margin-top:2px;}
.q{display:grid;grid-template-columns:40px 1fr 186px;align-items:start;padding:20px 24px;background:var(--g1);margin-bottom:2px;transition:all .2s;position:relative;overflow:hidden;}
.q::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;background:var(--o);transform:scaleY(0);transform-origin:bottom;transition:transform .28s;}
.q.done::before{transform:scaleY(1);}
.q.done{background:var(--op);}
.qn{font-family:'Barlow Condensed',sans-serif;font-size:20px;font-weight:900;color:rgba(200,200,200,.8);line-height:1;transition:color .2s;}
.q.done .qn{color:var(--o);}
.qt{font-size:12.5px;color:var(--g6);line-height:1.6;}
.qobs-btn{margin-top:7px;background:none;border:1px dashed var(--g2);color:var(--g4);padding:4px 11px;font-size:10.5px;letter-spacing:.5px;cursor:none;transition:all .2s;font-family:'Barlow',sans-serif;}
.qobs-btn:hover{border-color:var(--o);color:var(--o);}
.qobs{display:none;margin-top:7px;}
.qobs.open{display:block;}
.qobs-ta{width:100%;background:white;border:1px solid var(--g2);border-bottom:2px solid var(--o);color:var(--dk);padding:9px 11px;font-family:'Barlow',sans-serif;font-size:12px;resize:vertical;min-height:56px;outline:none;cursor:auto;}
.qradios{display:flex;gap:2px;justify-content:flex-end;}
.qr{position:relative;}
.qr input{position:absolute;opacity:0;width:0;height:0;}
.qrl{display:flex;flex-direction:column;align-items:center;justify-content:center;width:58px;height:58px;border:2px solid var(--g2);cursor:none;transition:all .18s;gap:2px;}
.qrl:hover{border-color:var(--o);}
.qrv{font-family:'Barlow Condensed',sans-serif;font-size:19px;font-weight:900;color:var(--g4);line-height:1;}
.qrt{font-size:7.5px;letter-spacing:1px;color:var(--g4);text-transform:uppercase;}
.qr:nth-child(1) input:checked~.qrl{background:var(--red-bg);border-color:var(--red);}
.qr:nth-child(1) input:checked~.qrl .qrv,.qr:nth-child(1) input:checked~.qrl .qrt{color:var(--red);}
.qr:nth-child(2) input:checked~.qrl{background:var(--amb-bg);border-color:var(--amb);}
.qr:nth-child(2) input:checked~.qrl .qrv,.qr:nth-child(2) input:checked~.qrl .qrt{color:var(--amb);}
.qr:nth-child(3) input:checked~.qrl{background:var(--grn-bg);border-color:var(--grn);}
.qr:nth-child(3) input:checked~.qrl .qrv,.qr:nth-child(3) input:checked~.qrl .qrt{color:var(--grn);}
.submit-zone{padding:76px 60px;text-align:center;background:var(--bk);}
.sz-h{font-family:'Playfair Display',serif;font-size:32px;font-weight:700;color:white;margin-bottom:9px;}
.sz-h em{color:var(--o);font-style:italic;}
.sz-p{font-size:13.5px;color:rgba(255,255,255,.4);max-width:420px;margin:0 auto 32px;line-height:1.75;}
.sub-btn{background:var(--o);color:white;border:none;padding:19px 64px;font-family:'Barlow Condensed',sans-serif;font-size:14px;letter-spacing:4px;font-weight:900;text-transform:uppercase;cursor:none;clip-path:polygon(14px 0,100% 0,calc(100% - 14px) 100%,0 100%);transition:all .3s;position:relative;overflow:hidden;}
.sub-btn::after{content:'';position:absolute;inset:0;background:linear-gradient(90deg,transparent,rgba(255,255,255,.16),transparent);transform:translateX(-100%);transition:transform .5s;}
.sub-btn:hover::after{transform:translateX(100%);}
.sub-btn:hover{background:var(--o2);}
.sub-btn:disabled{opacity:.28;cursor:not-allowed;}
.sub-note{margin-top:12px;font-size:10.5px;color:rgba(255,255,255,.18);letter-spacing:.5px;}

/* ══ RESULTADOS — LIMPIO Y PREMIUM ══════════════════════════════ */
#resultados{display:none;}
#resultados.show{display:block;}

/* Portada resultado */
.res-cover{background:var(--bk);padding:80px 60px;}
.res-cover-inner{display:grid;grid-template-columns:1fr 340px;gap:60px;align-items:start;}
.res-eyebrow{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:5px;color:var(--o);text-transform:uppercase;display:flex;align-items:center;gap:10px;margin-bottom:14px;}
.res-eyebrow::before{content:'';width:20px;height:1px;background:var(--o);}
.res-h{font-family:'Playfair Display',serif;font-size:52px;font-weight:900;line-height:.92;color:white;}
.res-h em{color:var(--o);font-style:italic;}
.res-company{margin-top:12px;font-family:'Barlow Condensed',sans-serif;font-size:18px;font-weight:700;letter-spacing:3px;color:rgba(255,255,255,.4);text-transform:uppercase;}
.res-chips{margin-top:14px;display:flex;flex-wrap:wrap;gap:5px;}
.rchip{padding:5px 11px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.09);font-size:10.5px;color:rgba(255,255,255,.45);font-family:'Barlow Condensed',sans-serif;letter-spacing:.5px;}
.rchip strong{color:rgba(255,255,255,.75);}
.res-dl{margin-top:28px;display:inline-flex;align-items:center;gap:10px;background:var(--o);color:white;border:none;padding:15px 34px;font-family:'Barlow Condensed',sans-serif;font-size:12px;letter-spacing:3px;font-weight:800;text-transform:uppercase;cursor:none;clip-path:polygon(10px 0,100% 0,calc(100% - 10px) 100%,0 100%);transition:all .2s;position:relative;overflow:hidden;}
.res-dl::after{content:'';position:absolute;inset:0;background:rgba(255,255,255,.14);transform:translateX(-110%) skewX(-15deg);transition:transform .35s;}
.res-dl:hover::after{transform:translateX(110%) skewX(-15deg);}
.res-dl:hover{background:var(--o2);}
.res-dl-note{margin-top:8px;font-size:10px;color:rgba(255,255,255,.25);letter-spacing:.5px;}

/* Gauge panel */
.gauge-panel{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.07);padding:36px;display:flex;flex-direction:column;align-items:center;gap:20px;}
.gauge-outer{position:relative;width:220px;height:220px;}
.gauge-svg{width:100%;height:100%;}
.gauge-center{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;justify-content:center;}
.gauge-score{font-family:'Barlow Condensed',sans-serif;font-size:68px;font-weight:900;line-height:1;}
.gauge-of{font-size:11px;color:rgba(255,255,255,.35);letter-spacing:2px;}
.gauge-pct{font-family:'Barlow Condensed',sans-serif;font-size:14px;font-weight:700;color:rgba(255,255,255,.45);margin-top:2px;}
.risk-badge{padding:10px 26px;font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:900;letter-spacing:4px;text-transform:uppercase;border:1.5px solid;clip-path:polygon(7px 0,100% 0,calc(100% - 7px) 100%,0 100%);}
.risk-badge.alto{border-color:#F87171;color:#F87171;}
.risk-badge.medio{border-color:#FCD34D;color:#FCD34D;}
.risk-badge.bajo{border-color:#4ADE80;color:#4ADE80;}
.gauge-meta{font-family:'Barlow Condensed',sans-serif;font-size:9px;letter-spacing:3px;color:rgba(255,255,255,.2);text-transform:uppercase;text-align:center;line-height:1.8;}

/* Verdict — white, clean */
.verdict-sec{padding:64px 60px;border-bottom:1px solid var(--g2);}
.verdict-inner{display:grid;grid-template-columns:1fr 1fr;gap:60px;max-width:1100px;}
.verdict-label{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:4px;color:var(--o);text-transform:uppercase;display:flex;align-items:center;gap:10px;margin-bottom:12px;}
.verdict-label::before{content:'';width:18px;height:1px;background:var(--o);}
.verdict-h{font-family:'Playfair Display',serif;font-size:26px;font-weight:700;color:var(--bk);line-height:1.2;margin-bottom:12px;}
.verdict-p{font-size:13.5px;color:var(--g6);line-height:1.82;}
.imp-list{display:flex;flex-direction:column;gap:1px;}
.imp-item{display:flex;align-items:flex-start;gap:14px;padding:16px 18px;background:var(--g1);}
.imp-icon{font-size:15px;flex-shrink:0;margin-top:1px;}
.imp-body strong{display:block;font-size:13px;color:var(--bk);margin-bottom:3px;}
.imp-body p{font-size:12.5px;color:var(--g6);line-height:1.55;}

/* Block scores */
.bscores-sec{padding:64px 60px;background:var(--g1);}
.bscores-h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:700;color:var(--bk);margin-bottom:36px;}
.bsc-grid{display:grid;grid-template-columns:1fr 1fr;gap:3px;}
.bsc{background:white;padding:32px;position:relative;overflow:hidden;transition:box-shadow .22s;}
.bsc:hover{box-shadow:0 6px 20px rgba(0,0,0,.09);}
.bsc-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:22px;}
.bsc-meta{}
.bsc-lbl{font-family:'Barlow Condensed',sans-serif;font-size:9px;letter-spacing:4px;color:var(--o);text-transform:uppercase;font-weight:700;margin-bottom:5px;}
.bsc-title{font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--bk);margin-bottom:2px;}
.bsc-norm{font-size:10.5px;color:var(--g4);letter-spacing:.5px;}
.bsc-score-wrap{text-align:right;flex-shrink:0;}
.bsc-num{font-family:'Barlow Condensed',sans-serif;font-size:52px;font-weight:900;line-height:1;}
.bsc-denom{font-size:14px;color:var(--g4);font-weight:400;}
.bsc-pctlbl{font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;margin-top:1px;}
.bsc-rl{font-size:9px;letter-spacing:2px;text-transform:uppercase;opacity:.8;}
.bsc-bar{height:4px;background:var(--g2);overflow:hidden;}
.bsc-fill{height:100%;width:0%;transition:width 1.2s cubic-bezier(.16,1,.3,1) .3s;}
.l-alto .bsc-num,.l-alto .bsc-pctlbl,.l-alto .bsc-rl{color:var(--red);}
.l-alto .bsc-fill{background:var(--red);}
.l-medio .bsc-num,.l-medio .bsc-pctlbl,.l-medio .bsc-rl{color:var(--amb);}
.l-medio .bsc-fill{background:var(--amb);}
.l-bajo .bsc-num,.l-bajo .bsc-pctlbl,.l-bajo .bsc-rl{color:var(--grn);}
.l-bajo .bsc-fill{background:var(--grn);}

/* Plan */
.plan-sec{padding:64px 60px;}
.plan-h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:700;color:var(--bk);margin-bottom:5px;}
.plan-sub{font-size:13.5px;color:var(--g6);line-height:1.7;margin-bottom:36px;}
.plan-cols{display:grid;grid-template-columns:1fr 1fr 1fr;gap:24px;}
.pcol-hd{display:flex;align-items:center;gap:8px;padding-bottom:13px;border-bottom:2px solid;margin-bottom:14px;}
.pcol-dot{width:7px;height:7px;border-radius:50%;}
.pcol-title{font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:800;letter-spacing:2.5px;text-transform:uppercase;}
.pcol-time{font-size:9.5px;color:var(--g4);margin-top:2px;letter-spacing:.5px;}
.alta .pcol-hd{border-color:var(--red);}.alta .pcol-dot{background:var(--red);}.alta .pcol-title{color:var(--red);}
.media .pcol-hd{border-color:var(--amb);}.media .pcol-dot{background:var(--amb);}.media .pcol-title{color:var(--amb);}
.baja .pcol-hd{border-color:var(--grn);}.baja .pcol-dot{background:var(--grn);}.baja .pcol-title{color:var(--grn);}
.pitem{padding:10px 0;border-bottom:1px solid var(--g2);display:flex;gap:7px;}
.pitem-body strong{display:block;font-size:12.5px;color:var(--bk);margin-bottom:2px;}
.pitem-body p{font-size:11.5px;color:var(--g6);line-height:1.5;}

/* ══ SERVICES — PREMIUM ═══════════════════════════════════════════ */
.srv-sec{background:var(--bk);padding:80px 60px;position:relative;overflow:hidden;}
.srv-sec::before{content:'';position:absolute;top:-120px;right:-80px;width:480px;height:480px;border-radius:50%;background:rgba(232,81,10,.04);pointer-events:none;}
.srv-top{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:end;margin-bottom:56px;}
.srv-h{font-family:'Playfair Display',serif;font-size:44px;font-weight:900;line-height:1.0;color:white;}
.srv-h em{font-style:italic;color:var(--o);}
.srv-intro{font-size:13.5px;color:rgba(255,255,255,.45);line-height:1.78;margin-bottom:20px;}
.srv-contact-line{display:flex;align-items:center;gap:14px;}
.srv-contact-dot{width:6px;height:6px;border-radius:50%;background:var(--o);}
.srv-contact-txt{font-family:'Barlow Condensed',sans-serif;font-size:11px;letter-spacing:3px;color:rgba(255,255,255,.35);text-transform:uppercase;}
.srv-contact-txt strong{color:rgba(255,255,255,.65);}
.srv-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:rgba(255,255,255,.04);}
.srv-card{background:var(--bk);padding:32px 26px;border-top:2px solid rgba(255,255,255,.06);transition:all .25s;cursor:none;position:relative;}
.srv-card::after{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:var(--o);transform:scaleX(0);transform-origin:left;transition:transform .3s;}
.srv-card:hover::after{transform:scaleX(1);}
.srv-card:hover{background:rgba(255,255,255,.025);}
.srv-num{font-family:'Barlow Condensed',sans-serif;font-size:11px;letter-spacing:3px;color:rgba(232,81,10,.5);text-transform:uppercase;margin-bottom:16px;font-weight:700;}
.srv-title{font-family:'Barlow Condensed',sans-serif;font-size:15.5px;font-weight:800;letter-spacing:.5px;color:white;text-transform:uppercase;margin-bottom:11px;line-height:1.2;}
.srv-text{font-size:12px;color:rgba(255,255,255,.4);line-height:1.65;}
.srv-law{margin-top:18px;font-family:'Barlow Condensed',sans-serif;font-size:9px;letter-spacing:2.5px;color:rgba(232,81,10,.6);text-transform:uppercase;font-weight:700;}
.srv-cta-strip{margin-top:1px;background:var(--o);padding:32px 60px;display:flex;align-items:center;justify-content:space-between;gap:40px;}
.srv-cta-left strong{font-family:'Barlow Condensed',sans-serif;font-size:18px;font-weight:800;letter-spacing:1px;color:white;text-transform:uppercase;display:block;margin-bottom:3px;}
.srv-cta-left p{font-size:12.5px;color:rgba(255,255,255,.65);}
.srv-cta-btn{background:white;color:var(--o);border:none;padding:15px 38px;font-family:'Barlow Condensed',sans-serif;font-size:12px;letter-spacing:3px;font-weight:900;text-transform:uppercase;cursor:none;clip-path:polygon(10px 0,100% 0,calc(100% - 10px) 100%,0 100%);text-decoration:none;white-space:nowrap;display:inline-block;transition:all .2s;}
.srv-cta-btn:hover{background:var(--ol);}

/* OVERLAY / TOAST */
.overlay{position:fixed;inset:0;background:rgba(13,13,13,.94);z-index:8000;display:none;flex-direction:column;align-items:center;justify-content:center;gap:18px;}
.overlay.show{display:flex;}
.ov-spin{width:44px;height:44px;border:3px solid rgba(232,81,10,.15);border-top-color:var(--o);border-radius:50%;animation:spin .8s linear infinite;}
.ov-text{font-family:'Barlow Condensed',sans-serif;font-size:16px;letter-spacing:4px;color:white;text-transform:uppercase;}
.ov-sub{font-size:11.5px;color:rgba(255,255,255,.3);letter-spacing:.5px;}
.toast{position:fixed;bottom:32px;right:32px;z-index:9100;padding:14px 20px;background:var(--bk);border-left:3px solid var(--o);font-size:13px;color:white;max-width:320px;line-height:1.5;transform:translateX(200px);opacity:0;transition:all .38s cubic-bezier(.16,1,.3,1);}
.toast.show{transform:translateX(0);opacity:1;}
.toast.ok{border-color:var(--grn);}.toast.err{border-color:var(--red);}

footer{padding:40px 60px;background:var(--g1);border-top:1px solid var(--g2);display:flex;align-items:center;justify-content:space-between;}
.fl{font-family:'Barlow Condensed',sans-serif;font-size:16px;font-weight:900;letter-spacing:3px;color:var(--bk);text-transform:uppercase;}
.fl span{color:var(--o);}
.fc{font-size:10.5px;color:var(--g4);text-align:center;line-height:1.65;}
.fr{font-family:'Barlow Condensed',sans-serif;font-size:9.5px;letter-spacing:2px;color:rgba(232,81,10,.55);text-align:right;text-transform:uppercase;line-height:2.1;}

@keyframes fu{from{opacity:0;transform:translateY(22px);}to{opacity:1;transform:translateY(0);}}
@keyframes spin{to{transform:rotate(360deg);}}

@media(max-width:960px){
  nav{padding:0 20px;}#hero{grid-template-columns:1fr;}.hero-r{display:none;}.hero-l{padding:68px 20px 60px;}
  #marco{padding:70px 20px;}.marco-grid{grid-template-columns:1fr;}.marco-sticky{position:static;}
  .diag-top,.diag-body,.data-band,.bscores-sec,.plan-sec,.srv-sec,.submit-zone,.verdict-sec{padding-left:20px;padding-right:20px;}
  .srv-cta-strip{padding:24px 20px;flex-direction:column;gap:16px;}
  .data-grid{grid-template-columns:1fr 1fr;}.bhead{grid-template-columns:52px 1fr;}.bscore{display:none;}
  .q{grid-template-columns:32px 1fr;gap:8px;}.qradios{grid-column:1/-1;margin-top:8px;justify-content:flex-start;}
  .bsc-grid,.plan-cols,.srv-grid{grid-template-columns:1fr;}
  .res-cover-inner{grid-template-columns:1fr;}.gauge-panel{display:none;}
  .verdict-inner{grid-template-columns:1fr;}.srv-top{grid-template-columns:1fr;}
  footer{flex-direction:column;gap:14px;text-align:center;padding:26px 20px;}
}
</style>
</head>
<body>
<div class="cur" id="cur"></div>
<div class="cur2" id="cur2"></div>
<div class="overlay" id="overlay"><div class="ov-spin"></div><div class="ov-text">Generando informe</div><div class="ov-sub">Procesando su diagnóstico de cumplimiento...</div></div>
<div class="toast" id="toast"></div>

<nav>
  <div class="nav-inner">
    <div><div class="logo-main">Durán Sindreu</div><div class="logo-sub">Abogados · Barcelona</div></div>
    <button class="nav-cta" onclick="document.getElementById('diagnostico').scrollIntoView({behavior:'smooth'})">Iniciar diagnóstico</button>
  </div>
</nav>

<section id="hero">
  <div class="hero-l">
    <div class="eyebrow"><div class="eyebrow-line"></div><div class="eyebrow-txt">Evaluación normativa · Sector privado</div></div>
    <h1>Conozca el riesgo<br>legal de su empresa<br>en <em>Compliance</em></h1>
    <p class="hero-p">Evaluación profesional del cumplimiento normativo frente al art. 31 bis CP, Ley 2/2023, legislación de igualdad y anticorrupción. Informe descargable en PDF con plan de acción personalizado.</p>
    <div class="hero-actions">
      <button class="btn-main" onclick="document.getElementById('diagnostico').scrollIntoView({behavior:'smooth'})">Comenzar diagnóstico</button>
      <a class="btn-ghost" href="/cdn-cgi/l/email-protection#f586869a999087b5918087949b869c9b91879080db969a98">Hablar con un abogado</a>
    </div>
    <div class="hero-stats">
      <div><div class="stat-n">24</div><div class="stat-l">Ítems normativos</div></div>
      <div><div class="stat-n">4</div><div class="stat-l">Bloques de riesgo</div></div>
      <div><div class="stat-n">PDF</div><div class="stat-l">Informe descargable</div></div>
    </div>
  </div>
  <div class="hero-r">
    <div class="hero-r-inner">
      <div class="hero-r-label">Áreas de evaluación</div>
      <div class="ri"><div class="ri-dot r"></div><div><div class="ri-title">Compliance Penal</div><div class="ri-sub">Responsabilidad art. 31 bis CP</div></div></div>
      <div class="ri"><div class="ri-dot a"></div><div><div class="ri-title">Canal de Denuncias</div><div class="ri-sub">Obligatorio desde Ley 2/2023</div></div></div>
      <div class="ri"><div class="ri-dot g"></div><div><div class="ri-title">Igualdad y Diversidad</div><div class="ri-sub">LO 3/2007 · Ley 4/2023</div></div></div>
      <div class="ri"><div class="ri-dot r"></div><div><div class="ri-title">Anticorrupción</div><div class="ri-sub">Ley 10/2010 · OCDE</div></div></div>
      <div class="law-pills"><div class="lp">Art. 31 bis CP</div><div class="lp">Ley 2/2023</div><div class="lp">LO 3/2007</div><div class="lp">Ley 10/2010</div><div class="lp">Ley 4/2023</div><div class="lp">ISO 37001</div></div>
    </div>
  </div>
</section>

<section id="marco">
  <div class="sec-label">Marco normativo obligatorio</div>
  <div class="marco-grid">
    <div class="marco-sticky">
      <h2 class="marco-h2">¿Por qué su empresa necesita un <em>modelo de compliance</em>?</h2>
      <p class="marco-intro">La legislación española y europea ha endurecido las obligaciones para las empresas del sector privado. El incumplimiento genera consecuencias penales, laborales y reputacionales de primer orden.</p>
      <div class="marco-alert"><div class="ma-label">Consecuencias del incumplimiento</div><div class="ma-text">Multas de hasta <strong>10 veces el beneficio</strong> obtenido, inhabilitación, intervención judicial y responsabilidad penal personal de administradores.</div></div>
    </div>
    <div class="marco-cards">
      <div class="mcard"><div class="mc-num">Bloque 01</div><div class="mc-title">Compliance Penal Corporativo</div><div class="mc-text">El art. 31 bis CP establece la responsabilidad penal de las personas jurídicas. Un modelo bien implantado puede eximir completamente a la empresa. Sin él, los administradores responden personalmente.</div><div class="mc-law">Art. 31 bis Código Penal</div></div>
      <div class="mcard"><div class="mc-num">Bloque 02</div><div class="mc-title">Canal Interno de Denuncias</div><div class="mc-text">La Ley 2/2023 obliga a empresas de más de 50 empleados a disponer de un canal de información seguro y confidencial. Sanciones de hasta 1.000.000 € por incumplimiento.</div><div class="mc-law">Ley 2/2023 · Directiva 2019/1937</div></div>
      <div class="mcard"><div class="mc-num">Bloque 03</div><div class="mc-title">Igualdad, Diversidad y Acoso</div><div class="mc-text">Empresas de más de 50 trabajadores deben contar con Plan de Igualdad registrado, protocolo de acoso y formación. La Ley 4/2023 añade obligaciones LGTBI específicas.</div><div class="mc-law">LO 3/2007 · Ley 15/2022 · Ley 4/2023</div></div>
      <div class="mcard"><div class="mc-num">Bloque 04</div><div class="mc-title">Anticorrupción y Blanqueo</div><div class="mc-text">La Ley 10/2010 y los estándares OCDE exigen diligencia debida, tolerancia cero al soborno, controles sobre regalos y hospitalidades, y auditorías externas periódicas.</div><div class="mc-law">Ley 10/2010 · OCDE · ISO 37001</div></div>
    </div>
  </div>
</section>

<section id="diagnostico">
  <div class="diag-top">
    <div><div class="sec-label">Diagnóstico profesional</div><h2 class="diag-h2">Evaluación de<br><em>Cumplimiento</em></h2></div>
    <div class="prog-wrap"><div class="prog-label">Progreso</div><div class="prog-track"><div class="prog-fill" id="pf"></div></div><div class="prog-pct" id="pp">0%</div></div>
  </div>
  <div class="data-band">
    <div class="data-band-label">Sus datos</div>
    <div class="data-grid">
      <div class="df"><div class="df-label">Empresa / Razón social <span>*</span></div><input class="df-input" id="f1" type="text" placeholder="Denominación social" oninput="chk()"></div>
      <div class="df"><div class="df-label">Nombre del responsable <span>*</span></div><input class="df-input" id="f2" type="text" placeholder="Nombre y apellidos" oninput="chk()"></div>
      <div class="df"><div class="df-label">Cargo / Función</div><input class="df-input" id="f3" type="text" placeholder="Director General, CEO..."></div>
      <div class="df"><div class="df-label">Email de contacto <span>*</span></div><input class="df-input" id="f4" type="email" placeholder="correo@empresa.com" oninput="chk()"></div>
      <div class="df"><div class="df-label">Teléfono de contacto</div><input class="df-input" id="f5" type="tel" placeholder="+34 600 000 000"></div>
      <div class="df"><div class="df-label">Sector de actividad <span>*</span></div><select class="df-input" id="f6" onchange="chk()"><option value="">— Seleccionar —</option><option>Banca y servicios financieros</option><option>Servicios jurídicos y consultoría</option><option>Industria y manufactura</option><option>Tecnología y software</option><option>Sanidad y farmacia</option><option>Construcción e inmobiliario</option><option>Distribución y comercio</option><option>Energía y utilities</option><option>Seguros</option><option>Hostelería y turismo</option><option>Transporte y logística</option><option>Alimentación y bebidas</option><option>Otro</option></select></div>
      <div class="df"><div class="df-label">Número de empleados <span>*</span></div><select class="df-input" id="f7" onchange="chk()"><option value="">— Seleccionar —</option><option value="<50">Menos de 50</option><option value="50-249">50 – 249</option><option value="250-499">250 – 499</option><option value="500-999">500 – 999</option><option value="1000+">Más de 1.000</option></select></div>
      <div class="df"><div class="df-label">Facturación anual</div><select class="df-input" id="f8"><option value="">— Seleccionar —</option><option>Menos de 2M €</option><option>2M – 10M €</option><option>10M – 50M €</option><option>50M – 200M €</option><option>Más de 200M €</option></select></div>
      <div class="df"><div class="df-label">¿Tiene compliance actual?</div><select class="df-input" id="f9"><option value="">— Seleccionar —</option><option>Sí, completo y actualizado</option><option>Sí, pero desactualizado</option><option>Parcialmente implantado</option><option>No disponemos de ninguno</option><option>En proceso de implantación</option></select></div>
    </div>
    <div class="data-note">* Campos obligatorios</div>
  </div>
  <div class="diag-body">
    <div class="bwrap" id="bw1"><div class="bhead"><div class="bn">01</div><div><div class="btitle">Cumplimiento Penal Corporativo</div><div class="bnorm">Art. 31 bis Código Penal</div><div class="bdesc">Evalúa el modelo de prevención de delitos, el compliance officer, el mapa de riesgos y los mecanismos de control interno.</div></div><div class="bscore"><div class="bscore-n"><span id="sb1">0</span></div><div class="bscore-m">de 14 pts</div></div></div><div id="qz1"></div></div>
    <div class="bwrap" id="bw2"><div class="bhead"><div class="bn">02</div><div><div class="btitle">Sistema Interno de Información</div><div class="bnorm">Ley 2/2023 · Canal de Denuncias</div><div class="bdesc">Evalúa el canal de denuncias, el Responsable del SII, las garantías de confidencialidad y el procedimiento de gestión.</div></div><div class="bscore"><div class="bscore-n"><span id="sb2">0</span></div><div class="bscore-m">de 10 pts</div></div></div><div id="qz2"></div></div>
    <div class="bwrap" id="bw3"><div class="bhead"><div class="bn">03</div><div><div class="btitle">Igualdad, No Discriminación y Acoso</div><div class="bnorm">LO 3/2007 · RDL 6/2019 · Ley 4/2023</div><div class="bdesc">Evalúa los protocolos de acoso, el Plan de Igualdad registrado, la Comisión de Igualdad y los protocolos LGTBI.</div></div><div class="bscore"><div class="bscore-n"><span id="sb3">0</span></div><div class="bscore-m">de 12 pts</div></div></div><div id="qz3"></div></div>
    <div class="bwrap" id="bw4"><div class="bhead"><div class="bn">04</div><div><div class="btitle">Prevención de Corrupción y Blanqueo</div><div class="bnorm">Ley 10/2010 · OCDE · ISO 37001</div><div class="bdesc">Evalúa las políticas anticorrupción, los procedimientos KYC, el manual PBC/FT y la existencia de auditorías externas.</div></div><div class="bscore"><div class="bscore-n"><span id="sb4">0</span></div><div class="bscore-m">de 12 pts</div></div></div><div id="qz4"></div></div>
  </div>
  <div class="submit-zone">
    <h2 class="sz-h">Generar mi <em>informe de riesgo</em></h2>
    <p class="sz-p">Recibirá un informe PDF profesional con membrete Durán Sindreu, nivel de riesgo, análisis por bloque y plan de acción priorizado.</p>
    <button class="sub-btn" id="subBtn" onclick="submitDiag()" disabled>Generar y descargar informe PDF</button>
    <div class="sub-note">Complete todos los ítems y los campos obligatorios para continuar</div>
  </div>
</section>

<!-- RESULTADOS -->
<section id="resultados">
  <div class="res-cover">
    <div class="res-cover-inner">
      <div>
        <div class="res-eyebrow">Informe de cumplimiento normativo</div>
        <div class="res-h">Diagnóstico de<br><em>Riesgo</em></div>
        <div class="res-company" id="rEmpresa"></div>
        <div class="res-chips" id="rMeta"></div>
        <button class="res-dl" onclick="downloadPDF()">⬇&nbsp; Descargar informe PDF</button>
        <div class="res-dl-note">Informe profesional con membrete Durán Sindreu · 4 páginas</div>
      </div>
      <div class="gauge-panel">
        <div class="gauge-outer">
          <svg class="gauge-svg" viewBox="0 0 220 220">
            <circle cx="110" cy="110" r="86" fill="none" stroke="rgba(255,255,255,.04)" stroke-width="22"/>
            <circle cx="110" cy="110" r="86" fill="none" stroke="rgba(255,255,255,.06)" stroke-width="22" stroke-dasharray="269.9 539.8" stroke-dashoffset="67.5" stroke-linecap="round" transform="rotate(-210 110 110)"/>
            <circle cx="110" cy="110" r="86" fill="none" id="garc" stroke="#E8510A" stroke-width="22" stroke-dasharray="0 539.8" stroke-dashoffset="-67.5" stroke-linecap="round" transform="rotate(-210 110 110)" style="transition:stroke-dasharray 1.6s cubic-bezier(.16,1,.3,1)"/>
          </svg>
          <div class="gauge-center">
            <div class="gauge-score" id="gScore" style="color:#E8510A">0</div>
            <div class="gauge-of">de 40 pts</div>
            <div class="gauge-pct" id="gPct">0%</div>
          </div>
        </div>
        <div class="risk-badge" id="rBadge"></div>
        <div class="gauge-meta" id="gMeta"></div>
      </div>
    </div>
  </div>

  <div class="verdict-sec">
    <div class="verdict-inner">
      <div>
        <div class="verdict-label">Análisis de riesgo</div>
        <h3 class="verdict-h" id="vH"></h3>
        <p class="verdict-p" id="vP"></p>
      </div>
      <div class="imp-list" id="vImps"></div>
    </div>
  </div>

  <div class="bscores-sec">
    <div class="sec-label">Resultado por bloque</div>
    <h3 class="bscores-h2">Detalle del cumplimiento normativo</h3>
    <div class="bsc-grid" id="bscGrid"></div>
  </div>

  <div class="plan-sec">
    <div class="sec-label">Plan de acción</div>
    <h3 class="plan-h2">Medidas a implantar</h3>
    <p class="plan-sub">Basado en su diagnóstico, estas son las acciones prioritarias para reducir el riesgo normativo y proteger a sus administradores.</p>
    <div class="plan-cols" id="planGrid"></div>
  </div>

  <div class="srv-sec">
    <div class="srv-top">
      <div>
        <div class="sec-label" style="color:rgba(232,81,10,.7)">Durán Sindreu Abogados · Barcelona</div>
        <h3 class="srv-h">Le acompañamos en la<br><em>implantación completa</em></h3>
      </div>
      <div>
        <p class="srv-intro">Nuestro equipo especializado en Compliance Penal, Derecho Laboral y Anticorrupción dispone de la experiencia, metodología y herramientas para implantar su modelo con plenas garantías jurídicas y de exención.</p>
        <div class="srv-contact-line"><div class="srv-contact-dot"></div><div class="srv-contact-txt">Contacto directo · <strong><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5f2c2c30333a2d1f3b2a2d3e312c36313b2d3a2a713c3032">[email&#160;protected]</a></strong></div></div>
      </div>
    </div>
    <div class="srv-grid">
      <div class="srv-card"><div class="srv-num">01 / Servicio</div><div class="srv-title">Modelo de Compliance Penal</div><div class="srv-text">Diseño e implantación del modelo de prevención de delitos adaptado a su sector, perfil de riesgo y estructura corporativa. Cumplimiento pleno del art. 31 bis CP.</div><div class="srv-law">Art. 31 bis CP · UNE 19601</div></div>
      <div class="srv-card"><div class="srv-num">02 / Servicio</div><div class="srv-title">Canal Interno de Denuncias</div><div class="srv-text">Implementación técnica y jurídica del canal, reglamento interno de tramitación y designación o apoyo al Responsable del SII. Conformidad total con la Ley 2/2023.</div><div class="srv-law">Ley 2/2023 · Dir. 2019/1937</div></div>
      <div class="srv-card"><div class="srv-num">03 / Servicio</div><div class="srv-title">Plan de Igualdad y Diversidad</div><div class="srv-text">Diagnóstico retributivo, negociación con la representación legal de los trabajadores y registro del Plan. Protocolos de acoso y planes LGTBI conformes a Ley 4/2023.</div><div class="srv-law">LO 3/2007 · Ley 4/2023</div></div>
      <div class="srv-card"><div class="srv-num">04 / Servicio</div><div class="srv-title">Anticorrupción y PBC/FT</div><div class="srv-text">Políticas de tolerancia cero, procedimientos KYC, manual PBC/FT, formación certificada a directivos y acompañamiento hacia certificación ISO 37001.</div><div class="srv-law">Ley 10/2010 · ISO 37001</div></div>
    </div>
    <div class="srv-cta-strip">
      <div class="srv-cta-left">
        <strong>Solicite una propuesta personalizada</strong>
        <p>Respuesta en menos de 24 horas · Sin compromiso</p>
      </div>
      <a href="/cdn-cgi/l/email-protection#daa9a9b5b6bfa89abeafa8bbb4a9b3b4bea8bfaff4b9b5b7e5a9afb8b0bfb9aee789b5b6b3b9b3aeafbeffe8eabebfffe8eaaaa8b5aaafbfa9aebbffe8ea99b5b7aab6b3bbb4b9bffcb8b5bea3e792bfffe8eaa8bfbbb6b3a0bbbeb5ffe8eabfb6ffe8eabeb3bbbdb4ff99e9ff98e9a9aeb3b9b5ffe8eabebfffe8eab9b5b7aab6b3bbb4b9bfffe8eaa3ffe8eab7bfffe8eabdafa9aebba8ff99e9ff9b9ebbffe8eaa8bfb9b3b8b3a8ffe8eaafb4bbffe8eaaaa8b5aaafbfa9aebbffe8eaaabfa8a9b5b4bbb6b3a0bbbebbf4" class="srv-cta-btn">Contactar con el equipo</a>
    </div>
  </div>
</section>

<footer>
  <div class="fl">DURÁN <span>SINDREU</span></div>
  <div class="fc">Herramienta orientativa. No sustituye el asesoramiento jurídico personalizado.<br>© 2025 Durán Sindreu Abogados · Barcelona · Todos los derechos reservados.</div>
  <div class="fr">Art. 31 bis CP · Ley 2/2023<br>LO 3/2007 · Ley 10/2010<br>Ley 15/2022 · Ley 4/2023</div>
</footer>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
const BLOCKS=[
  {id:1,max:14,name:'Cumplimiento Penal',questions:[
    {n:1,t:'La entidad dispone de un modelo de prevención de delitos, corrupción y fraude completo y actualizado, conforme al art. 31 bis CP.'},
    {n:2,t:'Existe un órgano o responsable de compliance con autonomía, independencia funcional y medios suficientes.'},
    {n:3,t:'Se ha elaborado un mapa de riesgos penales y controles asociados, revisado al menos una vez al año.'},
    {n:4,t:'La organización dispone de un Código de Conducta o Ético aprobado, accesible y exigible a toda la plantilla y terceros.'},
    {n:5,t:'Existen protocolos financieros y operativos que previenen desviaciones, irregularidades o pagos indebidos.'},
    {n:6,t:'La entidad cuenta con un régimen disciplinario o sancionador interno específico ante incumplimientos del modelo.'},
    {n:7,t:'Se ejecuta anualmente un plan de formación en cumplimiento normativo para toda la plantilla y dirección.'},
  ]},
  {id:2,max:10,name:'Canal de Denuncias',questions:[
    {n:8,t:'La entidad dispone de un canal interno de información/denuncias accesible, confidencial y técnicamente seguro.'},
    {n:9,t:'Se ha designado formalmente al Responsable del SII con independencia y formación acreditada.'},
    {n:10,t:'Existe un reglamento o procedimiento documentado para la recepción, tramitación y cierre de informaciones.'},
    {n:11,t:'Se garantiza la confidencialidad, anonimato y prohibición de represalias conforme a los arts. 29–32 Ley 2/2023.'},
    {n:12,t:'Se elabora un informe anual de funcionamiento del canal con registro de actuaciones y mejoras implementadas.'},
  ]},
  {id:3,max:12,name:'Igualdad y No Discriminación',questions:[
    {n:13,t:'La entidad dispone de un protocolo de prevención y actuación frente al acoso sexual y por razón de sexo (obligatorio >50 empleados).'},
    {n:14,t:'Existe un Plan de Igualdad registrado y vigente, con diagnóstico, objetivos, medidas y sistema de seguimiento (obligatorio >50 empleados).'},
    {n:15,t:'Se ha constituido una Comisión de Igualdad paritaria para el seguimiento y evaluación del Plan.'},
    {n:16,t:'La organización cuenta con protocolos contra la discriminación por orientación sexual, identidad de género o características sexuales.'},
    {n:17,t:'Se imparte formación obligatoria en igualdad, no discriminación y prevención del acoso a toda la plantilla.'},
    {n:18,t:'Existe un registro confidencial de situaciones de acoso o discriminación con seguimiento de casos y medidas correctoras.'},
  ]},
  {id:4,max:12,name:'Anticorrupción y Blanqueo',questions:[
    {n:19,t:'La organización ha aprobado una política de tolerancia cero frente al soborno y la corrupción, publicada y comunicada.'},
    {n:20,t:'Se aplican procedimientos de diligencia debida (KYC) a clientes, proveedores y colaboradores relevantes.'},
    {n:21,t:'Se dispone de un manual o procedimiento PBC/FT revisado al menos cada 2 años y comunicado al personal afectado.'},
    {n:22,t:'Existen protocolos sobre regalos, hospitalidades, donaciones, conflictos de interés y relaciones con el sector público.'},
    {n:23,t:'Se imparte formación específica en integridad y anticorrupción a la alta dirección y mandos intermedios.'},
    {n:24,t:'Se ha realizado o está prevista una auditoría externa o revisión independiente del modelo de cumplimiento.'},
  ]},
];

let SC={},OB={},LAST=null;

// Cursor
const c1=document.getElementById('cur'),c2=document.getElementById('cur2');
document.addEventListener('mousemove',e=>{c1.style.left=e.clientX+'px';c1.style.top=e.clientY+'px';setTimeout(()=>{c2.style.left=e.clientX+'px';c2.style.top=e.clientY+'px';},55);});
document.addEventListener('mousedown',()=>c1.style.transform='translate(-50%,-50%) scale(2)');
document.addEventListener('mouseup',()=>c1.style.transform='translate(-50%,-50%) scale(1)');
document.querySelectorAll('button,a,.mcard,.srv-card').forEach(el=>{
  el.addEventListener('mouseenter',()=>{c1.style.width='16px';c1.style.height='16px';c2.style.width='44px';c2.style.height='44px';});
  el.addEventListener('mouseleave',()=>{c1.style.width='10px';c1.style.height='10px';c2.style.width='32px';c2.style.height='32px';});
});

function renderQ(){
  BLOCKS.forEach(b=>{
    const w=document.getElementById('qz'+b.id);
    b.questions.forEach(q=>{
      const d=document.createElement('div');d.className='q';d.id='q'+q.n;
      d.innerHTML=`<div class="qn">${String(q.n).padStart(2,'0')}</div><div><div class="qt">${q.t}</div><button class="qobs-btn" onclick="togObs(${q.n})">+ Observación</button><div class="qobs" id="ob${q.n}"><textarea class="qobs-ta" placeholder="Observación..." onchange="OB[${q.n}]=this.value"></textarea></div></div><div class="qradios">${[0,1,2].map(v=>`<div class="qr"><input type="radio" name="q${q.n}" id="q${q.n}r${v}" value="${v}" onchange="setScore(${q.n},${v})"><label class="qrl" for="q${q.n}r${v}"><span class="qrv">${v}</span><span class="qrt">${v===0?'No':v===1?'Parcial':'Sí'}</span></label></div>`).join('')}</div>`;
      w.appendChild(d);
    });
  });
}
function togObs(n){document.getElementById('ob'+n).classList.toggle('open');}
function setScore(n,v){
  SC[n]=v;document.getElementById('q'+n).classList.add('done');
  BLOCKS.forEach((b,i)=>{let s=0;b.questions.forEach(q=>s+=SC[q.n]??0);document.getElementById('sb'+(i+1)).textContent=s;});
  const done=Object.keys(SC).length,p=Math.round(done/24*100);
  document.getElementById('pf').style.width=p+'%';document.getElementById('pp').textContent=p+'%';chk();
}
function chk(){
  const ok=Object.keys(SC).length===24&&['f1','f2','f4'].every(id=>document.getElementById(id).value.trim())&&['f6','f7'].every(id=>document.getElementById(id).value);
  document.getElementById('subBtn').disabled=!ok;
}
['f1','f2','f4','f6','f7'].forEach(id=>{['input','change'].forEach(ev=>document.getElementById(id)?.addEventListener(ev,chk));});
document.querySelectorAll('.bwrap').forEach(el=>new IntersectionObserver(es=>es.forEach(e=>{if(e.isIntersecting)e.target.classList.add('in');}),{threshold:.07}).observe(el));

function collect(){
  const bs=BLOCKS.map(b=>{let s=0;b.questions.forEach(q=>s+=SC[q.n]??0);return{score:s,max:b.max,pct:Math.round(s/b.max*100)};});
  const total=bs.reduce((a,b)=>a+b.score,0),pct=Math.round(total/40*100);
  return{
    empresa:document.getElementById('f1').value.trim(),nombre:document.getElementById('f2').value.trim(),
    cargo:document.getElementById('f3').value.trim(),email:document.getElementById('f4').value.trim(),
    tel:document.getElementById('f5').value.trim(),sector:document.getElementById('f6').value,
    empleados:document.getElementById('f7').value,facturacion:document.getElementById('f8').value,
    compliance:document.getElementById('f9').value,
    date:new Date().toLocaleDateString('es-ES',{day:'2-digit',month:'long',year:'numeric'}),
    SC,OB,bs,total,pct,risk:pct<=40?'ALTO':pct<=69?'MEDIO':'BAJO'
  };
}

async function submitDiag(){
  const d=collect();
  document.getElementById('overlay').classList.add('show');
  await new Promise(r=>setTimeout(r,900));
  LAST=d;
  buildResults(d);
  document.getElementById('overlay').classList.remove('show');
  document.getElementById('resultados').classList.add('show');
  setTimeout(()=>{
    document.getElementById('resultados').scrollIntoView({behavior:'smooth'});
    animateResults(d);
    // Abre el cliente de correo con todos los datos pre-rellenados
    openMailto(d);
  },400);
}

function openMailto(d){
  const alta=[],media=[];
  if(d.bs[0].pct<50){alta.push('• Modelo prevención delitos (art. 31 bis CP)');alta.push('• Mapa de riesgos penales');}
  else if(d.bs[0].pct<80)media.push('• Actualización modelo compliance');
  if(SC[2]===0||SC[2]===undefined)alta.push('• Designar Compliance Officer');
  if(d.bs[1].pct<50){alta.push('• Canal de denuncias (Ley 2/2023)');alta.push('• Designar Responsable SII');}
  else if(d.bs[1].pct<80)media.push('• Completar reglamento del canal');
  if(d.bs[2].pct<50&&d.empleados!=='<50'){alta.push('• Protocolo de acoso sexual');alta.push('• Plan de Igualdad registrado');}
  else if(d.bs[2].pct<80){media.push('• Comisión de Igualdad paritaria');media.push('• Protocolos LGTBI (Ley 4/2023)');}
  if(d.bs[3].pct<50){alta.push('• Política anticorrupción tolerancia cero');alta.push('• Procedimientos KYC');}
  else if(d.bs[3].pct<80)media.push('• Manual PBC/FT actualizado');

  const subject = `🔔 Diagnóstico Compliance — ${d.empresa} — RIESGO ${d.risk}`;
  const body = [
    `NUEVO DIAGNÓSTICO DE COMPLIANCE`,
    `Fecha: ${d.date}`,
    ``,
    `━━━ DATOS DE LA EMPRESA ━━━`,
    `Empresa:        ${d.empresa}`,
    `Responsable:    ${d.nombre}${d.cargo ? ' · '+d.cargo : ''}`,
    `Email:          ${d.email}`,
    `Teléfono:       ${d.tel||'No indicado'}`,
    `Sector:         ${d.sector}`,
    `Empleados:      ${d.empleados}`,
    `Facturación:    ${d.facturacion||'No indicada'}`,
    `Compliance act: ${d.compliance||'No indicado'}`,
    ``,
    `━━━ RESULTADO ━━━`,
    `NIVEL DE RIESGO: ${d.risk}`,
    `Puntuación total: ${d.total}/40 puntos (${d.pct}%)`,
    ``,
    `Bloque 1 — Compliance Penal:      ${d.bs[0].score}/14 pts (${d.bs[0].pct}%)`,
    `Bloque 2 — Canal de Denuncias:    ${d.bs[1].score}/10 pts (${d.bs[1].pct}%)`,
    `Bloque 3 — Igualdad y No Discrim: ${d.bs[2].score}/12 pts (${d.bs[2].pct}%)`,
    `Bloque 4 — Anticorrupción/PBC:    ${d.bs[3].score}/12 pts (${d.bs[3].pct}%)`,
    ``,
    `━━━ PLAN DE ACCIÓN ━━━`,
    `PRIORIDAD ALTA (0–6 meses):`,
    ...(alta.length ? alta : ['• Sin acciones críticas pendientes']),
    ``,
    `PRIORIDAD MEDIA (6–12 meses):`,
    ...(media.length ? media : ['• Mantenimiento y mejora continua']),
    ``,
    `━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━`,
    `Diagnóstico generado en duransindreu.com/compliance`,
  ].join('\n');

  const mailto = `mailto:ssoler@duransindreu.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
  window.location.href = mailto;
  showToast('✉ Abriendo tu cliente de correo con los datos...','ok');
}

function buildResults(d){
  const RC=d.risk==='ALTO'?'#F87171':d.risk==='MEDIO'?'#FCD34D':'#4ADE80';
  document.getElementById('rEmpresa').textContent=d.empresa.toUpperCase();
  document.getElementById('rMeta').innerHTML=[
    d.nombre&&`<div class="rchip"><strong>${d.nombre}</strong></div>`,
    d.cargo&&`<div class="rchip">${d.cargo}</div>`,
    d.sector&&`<div class="rchip">${d.sector}</div>`,
    d.empleados&&`<div class="rchip">${d.empleados} empleados</div>`,
    `<div class="rchip">${d.date}</div>`
  ].filter(Boolean).join('');
  document.getElementById('rBadge').textContent=d.risk==='ALTO'?'⚠ Riesgo Alto':d.risk==='MEDIO'?'◉ Riesgo Medio':'✓ Cumplimiento Avanzado';
  document.getElementById('rBadge').className='risk-badge '+(d.risk==='ALTO'?'alto':d.risk==='MEDIO'?'medio':'bajo');
  document.getElementById('gScore').style.color=RC;
  document.getElementById('gMeta').innerHTML=`Diagnóstico realizado el ${d.date}<br>Art. 31 bis CP · Ley 2/2023 · LO 3/2007 · Ley 10/2010`;

  const V={
    ALTO:{h:'Riesgo penal, laboral y reputacional significativo',p:'La organización presenta déficits normativos que exponen a la persona jurídica y sus administradores a responsabilidad penal directa (art. 31 bis CP), sanciones laborales de hasta 225.018 € e impacto reputacional severo. Se requiere actuación inmediata.',imps:[
      {i:'⚠️',t:'Riesgo penal corporativo',d:'La ausencia de un modelo adecuado elimina la eximente del art. 31 bis CP, exponiendo a la empresa y directivos a penas de multa e inhabilitación.'},
      {i:'💼',t:'Riesgo laboral',d:'Incumplimientos en igualdad y canal de denuncias pueden dar lugar a sanciones de hasta 225.018 € en inspecciones de trabajo.'},
      {i:'📊',t:'Riesgo reputacional y comercial',d:'La ausencia de compliance puede bloquear licitaciones públicas, comprometer relaciones financieras y dañar la imagen corporativa.'}
    ]},
    MEDIO:{h:'Sistema parcialmente implantado: lagunas de riesgo identificadas',p:'La organización ha iniciado el cumplimiento pero presenta deficiencias relevantes. Estas lagunas pueden materializarse en inspecciones o contingencias laborales. Se recomienda un plan de implantación progresivo y supervisado.',imps:[
      {i:'⚡',t:'Vulnerabilidades identificadas',d:'Existen áreas sin cobertura normativa completa que pueden ser objeto de inspección o reclamación por la Fiscalía o Inspección de Trabajo.'},
      {i:'📋',t:'Formación y cultura de cumplimiento',d:'La formación continua y actualización de protocolos son esenciales para consolidar el modelo y garantizar su efectividad.'},
      {i:'🔄',t:'Actualización y auditoría',d:'Se recomienda auditoría externa del modelo y actualización especialmente en igualdad LGTBI y canal de denuncias.'}
    ]},
    BAJO:{h:'Cumplimiento avanzado: modelo integrado de compliance',p:'La organización cuenta con un sistema robusto que proporciona sólida base de defensa ante contingencias legales. Se recomienda mantener la actualización periódica y planificar certificaciones externas.',imps:[
      {i:'✅',t:'Eximente art. 31 bis CP activa',d:'El modelo implantado puede activar la eximente de responsabilidad penal, protegiendo a la empresa y a sus administradores.'},
      {i:'🏆',t:'Ventaja competitiva diferencial',d:'Un compliance robusto supone ventaja frente a clientes, inversores y en procesos de licitación pública y ESG reporting.'},
      {i:'🔍',t:'Siguiente paso: certificación',d:'Avance hacia la certificación UNE 19601 o ISO 37001 para acreditar formalmente el cumplimiento.'}
    ]}
  };
  const v=V[d.risk];
  document.getElementById('vH').textContent=v.h;
  document.getElementById('vP').textContent=v.p;
  document.getElementById('vImps').innerHTML=v.imps.map(i=>`<div class="imp-item"><div class="imp-icon">${i.i}</div><div class="imp-body"><strong>${i.t}</strong><p>${i.d}</p></div></div>`).join('');

  const BN=['Cumplimiento Penal Corporativo','Sistema Interno de Información','Igualdad y No Discriminación','Anticorrupción y Blanqueo'];
  const BNORM=['Art. 31 bis Código Penal','Ley 2/2023 · Canal de Denuncias','LO 3/2007 · Ley 4/2023','Ley 10/2010 · OCDE · ISO 37001'];
  document.getElementById('bscGrid').innerHTML=d.bs.map((b,i)=>{
    const lvl=b.pct<=40?'alto':b.pct<=69?'medio':'bajo';
    const lbl=b.pct<=40?'Riesgo alto':b.pct<=69?'Riesgo medio':'Avanzado';
    return`<div class="bsc l-${lvl}"><div class="bsc-top"><div class="bsc-meta"><div class="bsc-lbl">Bloque ${String(i+1).padStart(2,'0')}</div><div class="bsc-title">${BN[i]}</div><div class="bsc-norm">${BNORM[i]}</div></div><div class="bsc-score-wrap"><div class="bsc-num">${b.score}<span class="bsc-denom">/${b.max}</span></div><div class="bsc-pctlbl">${b.pct}%</div><div class="bsc-rl">${lbl}</div></div></div><div class="bsc-bar"><div class="bsc-fill" data-p="${b.pct}"></div></div></div>`;
  }).join('');
  buildPlan(d);
}

function buildPlan(d){
  const alta=[],media=[],baja=[
    {t:'Auditoría externa del modelo',d:'Revisión independiente para validar efectividad y detectar áreas de mejora.'},
    {t:'Certificación UNE 19601 / ISO 37001',d:'Acreditar formalmente el cumplimiento para ventajas competitivas y ESG.'},
    {t:'Sistema de Gestión de la Diversidad',d:'Implementar conforme Ley 15/2022. Diferencial en captación de talento.'}
  ];
  if(d.bs[0].pct<50){alta.push({t:'Modelo prevención delitos (art. 31 bis CP)',d:'Prioridad máxima. Elimina la responsabilidad penal directa de administradores.'});alta.push({t:'Mapa de riesgos penales',d:'Identificar y documentar los riesgos penales con revisión anual obligatoria.'});}
  else if(d.bs[0].pct<80)media.push({t:'Actualización del modelo de compliance',d:'Revisar y completar el modelo conforme a estándares y jurisprudencia actuales.'});
  if(SC[2]===0||SC[2]===undefined)alta.push({t:'Designar Compliance Officer',d:'Responsable con autonomía funcional, independencia y medios suficientes.'});
  if(d.bs[1].pct<50){alta.push({t:'Canal de denuncias (Ley 2/2023)',d:'Obligatorio >50 empleados. Sanciones hasta 1.000.000 €. Urgente.'});alta.push({t:'Responsable del SII',d:'Designación formal del Responsable del Sistema Interno de Información.'});}
  else if(d.bs[1].pct<80)media.push({t:'Completar reglamento del canal',d:'Documentar el procedimiento completo de tramitación y cierre.'});
  if(d.bs[2].pct<50&&d.empleados!=='<50'){alta.push({t:'Protocolo de acoso sexual',d:'Obligatorio >50 empleados. Aprobación, comunicación y formación.'});alta.push({t:'Plan de Igualdad registrado',d:'Multas hasta 225.018 €. Negociar y registrar en Ministerio de Igualdad.'});}
  else if(d.bs[2].pct<80){media.push({t:'Comisión de Igualdad paritaria',d:'Constituir y establecer sistema de seguimiento y evaluación.'});media.push({t:'Protocolos LGTBI (Ley 4/2023)',d:'Adaptar a las nuevas exigencias de la Ley 4/2023.'});}
  if(d.bs[3].pct<50){alta.push({t:'Política anticorrupción tolerancia cero',d:'Aprobar, publicar y comunicar formalmente a toda la organización.'});alta.push({t:'Procedimientos KYC',d:'Diligencia debida sobre clientes, proveedores y colaboradores.'});}
  else if(d.bs[3].pct<80)media.push({t:'Manual PBC/FT actualizado',d:'Revisar cada 2 años. Formación anticorrupción a directivos.'});

  const mk=(items,cls,title,time)=>`<div class="${cls}"><div class="pcol-hd"><div class="pcol-dot"></div><div><div class="pcol-title">${title}</div><div class="pcol-time">${time}</div></div></div>${items.map(i=>`<div class="pitem"><div style="font-size:12px;flex-shrink:0;margin-top:2px">${cls==='alta'?'🔴':cls==='media'?'🟠':'🟢'}</div><div class="pitem-body"><strong>${i.t}</strong><p>${i.d}</p></div></div>`).join('')}</div>`;
  document.getElementById('planGrid').innerHTML=
    mk(alta.length?alta:[{t:'Sin acciones críticas pendientes',d:'El nivel de cumplimiento es adecuado en este horizonte.'}],'alta','Prioridad Alta','0 – 6 meses')+
    mk(media.length?media:[{t:'Mantenimiento y mejora continua',d:'Revisar y actualizar periódicamente los protocolos existentes.'}],'media','Prioridad Media','6 – 12 meses')+
    mk(baja,'baja','Prioridad Baja','12 – 24 meses');
}

function animateResults(d){
  const RC=d.risk==='ALTO'?'#F87171':d.risk==='MEDIO'?'#FCD34D':'#4ADE80';
  const circ=2*Math.PI*86, sweep=circ*.75, filled=sweep*(d.pct/100);
  document.getElementById('garc').setAttribute('stroke-dasharray',`${filled} ${circ}`);
  document.getElementById('garc').setAttribute('stroke',RC);
  let c=0;const iv=setInterval(()=>{c++;document.getElementById('gScore').textContent=c;if(c>=d.total)clearInterval(iv);},48);
  document.getElementById('gPct').textContent=d.pct+'%';
  setTimeout(()=>{
    document.querySelectorAll('.bsc-fill').forEach(el=>el.style.width=el.dataset.p+'%');
  },400);
}

// ── PDF GENERATION ──────────────────────────────────────────────
async function downloadPDF(){
  if(!LAST){showToast('Genera el informe primero','err');return;}
  const d=LAST;
  showToast('Generando PDF...','');
  const {jsPDF}=window.jspdf;
  const pdf=new jsPDF({orientation:'portrait',unit:'mm',format:'a4'});
  const W=210,H=297;
  const o=[232,81,10],bk=[13,13,13],wh=[255,255,255],g6=[90,90,90],g2=[232,232,232],g1=[245,245,245];
  const red=[200,50,43],amb=[180,83,9],grn=[21,128,61];
  const RC=d.risk==='ALTO'?red:d.risk==='MEDIO'?amb:grn;

  // P1 — PORTADA
  pdf.setFillColor(...bk);pdf.rect(0,0,W,H,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,W,11,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,6,H,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);
  pdf.text('DURÁN SINDREU ABOGADOS · INFORME DE DIAGNÓSTICO DE COMPLIANCE · CONFIDENCIAL',W/2,7.5,{align:'center'});
  pdf.setFillColor(255,255,255,12);pdf.roundedRect(12,20,108,12,2,2,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(9);pdf.text('DURÁN SINDREU ABOGADOS',15,27);
  pdf.setFontSize(6.5);pdf.setFont('helvetica','normal');pdf.setTextColor(255,255,255,130);pdf.text('COMPLIANCE · PENAL CORPORATIVO · LABORAL · BARCELONA',15,33);
  pdf.setFillColor(255,255,255,10);pdf.roundedRect(132,20,66,12,2,2,'F');
  pdf.setTextColor(...o);pdf.setFontSize(7);pdf.setFont('helvetica','bold');pdf.text('DIAGNÓSTICO CONFIDENCIAL',165,27,{align:'center'});pdf.text(d.date,165,33,{align:'center'});
  pdf.setTextColor(...o);pdf.setFont('helvetica','bold');pdf.setFontSize(8);pdf.text('INFORME DE DIAGNÓSTICO DE CUMPLIMIENTO NORMATIVO',12,56);
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(36);pdf.text('Diagnóstico de',12,73);
  pdf.setTextColor(...o);pdf.text('Riesgo en',12,88);
  pdf.setTextColor(...wh);pdf.text('Compliance',12,103);
  pdf.setFillColor(255,255,255,7);pdf.roundedRect(12,117,186,36,2,2,'F');
  pdf.setDrawColor(...o);pdf.setLineWidth(.5);pdf.line(12,117,12,153);
  pdf.setTextColor(255,255,255,100);pdf.setFontSize(6.5);pdf.setFont('helvetica','bold');pdf.text('EMPRESA EVALUADA',16,125);
  pdf.setTextColor(...wh);pdf.setFontSize(18);pdf.setFont('helvetica','bold');pdf.text(d.empresa.substring(0,28).toUpperCase(),16,135);
  pdf.setFontSize(8.5);pdf.setFont('helvetica','normal');pdf.setTextColor(255,255,255,150);
  pdf.text(`${d.nombre}${d.cargo?' · '+d.cargo:''}`,16,143);pdf.text(`${d.sector} · ${d.empleados} empleados`,16,150);
  pdf.setFillColor(...RC);pdf.roundedRect(12,165,186,46,3,3,'F');
  pdf.setTextColor(...bk);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text('NIVEL DE RIESGO EN COMPLIANCE NORMATIVO',105,174,{align:'center'});
  pdf.setFontSize(42);pdf.text(d.risk,105,200,{align:'center'});
  pdf.setFontSize(12);pdf.text(`${d.total} / 40 PUNTOS · ${d.pct}%`,105,210,{align:'center'});
  pdf.setTextColor(255,255,255,50);pdf.setFontSize(6.5);pdf.setFont('helvetica','normal');
  pdf.text('Art. 31 bis CP · Ley 2/2023 · LO 3/2007 · Ley 10/2010 · Ley 4/2023 · ISO 37001',12,232);
  pdf.setDrawColor(255,255,255,15);pdf.setLineWidth(.2);pdf.line(12,238,198,238);
  pdf.text('Este informe ha sido generado mediante la herramienta de autodiagnóstico de Durán Sindreu Abogados y tiene carácter orientativo.',105,244,{align:'center'});
  pdf.setFillColor(...o);pdf.rect(0,H-10,W,10,'F');
  pdf.setTextColor(...wh);pdf.setFontSize(7);pdf.setFont('helvetica','bold');pdf.text('ssoler@duransindreu.com · Barcelona',W/2,H-3,{align:'center'});

  // P2 — RESUMEN EJECUTIVO
  pdf.addPage();pdf.setFillColor(...g1);pdf.rect(0,0,W,H,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,W,11,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text('DURÁN SINDREU ABOGADOS · INFORME DE COMPLIANCE',W/2,7.5,{align:'center'});
  pdf.setFillColor(...bk);pdf.rect(0,11,W,25,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(16);pdf.text('Resumen Ejecutivo',12,23);
  pdf.setTextColor(...o);pdf.setFontSize(7.5);pdf.text(d.empresa.toUpperCase(),12,31);
  let y=45;
  const VT={ALTO:'La organización presenta déficits normativos significativos que exponen tanto a la persona jurídica como a sus administradores a responsabilidad penal directa (art. 31 bis CP), sanciones laborales de hasta 225.018 € e impacto reputacional severo. Se requiere actuación inmediata y asesoramiento jurídico especializado.',MEDIO:'La organización ha iniciado el proceso de cumplimiento normativo pero presenta deficiencias relevantes en áreas específicas. Estas lagunas representan un riesgo moderado que puede materializarse en inspecciones o contingencias laborales. Se recomienda un plan de implantación progresivo y supervisado.',BAJO:'La organización cuenta con un sistema de compliance robusto que proporciona sólida base de defensa ante contingencias legales. Se recomienda mantener la actualización periódica y planificar la obtención de certificaciones externas para consolidar el liderazgo en gobernanza corporativa.'};
  pdf.setFillColor(...wh);pdf.roundedRect(12,y,186,26,2,2,'F');
  pdf.setDrawColor(...RC);pdf.setLineWidth(.7);pdf.line(12,y,12,y+26);
  pdf.setTextColor(...g6);pdf.setFontSize(7.5);pdf.setFont('helvetica','normal');
  pdf.text(pdf.splitTextToSize(VT[d.risk],172).slice(0,4),16,y+7);y+=34;
  pdf.setTextColor(...bk);pdf.setFont('helvetica','bold');pdf.setFontSize(11);pdf.text('Resultado por bloque normativo',12,y);y+=9;
  const BN2=['Cumplimiento Penal Corporativo','Sistema Interno de Información','Igualdad y No Discriminación','Anticorrupción y Blanqueo'];
  const BNO=['Art. 31 bis CP','Ley 2/2023','LO 3/2007 · Ley 4/2023','Ley 10/2010 · OCDE'];
  d.bs.forEach((b,i)=>{
    const brc=b.pct<=40?red:b.pct<=69?amb:grn;
    const brl=b.pct<=40?'RIESGO ALTO':b.pct<=69?'RIESGO MEDIO':'AVANZADO';
    pdf.setFillColor(...wh);pdf.roundedRect(12,y,186,25,2,2,'F');
    pdf.setFillColor(...brc);pdf.roundedRect(12,y,3,25,1,1,'F');
    pdf.setTextColor(150,150,150);pdf.setFontSize(6.5);pdf.setFont('helvetica','bold');pdf.text(`BLOQUE ${String(i+1).padStart(2,'0')}`,17,y+7);
    pdf.setTextColor(...bk);pdf.setFontSize(9);pdf.text(BN2[i],17,y+14);
    pdf.setTextColor(...g6);pdf.setFontSize(6.5);pdf.setFont('helvetica','normal');pdf.text(BNO[i],17,y+20);
    pdf.setFillColor(...g2);pdf.roundedRect(17,y+21.5,126,2.5,1,1,'F');
    pdf.setFillColor(...brc);pdf.roundedRect(17,y+21.5,126*(b.pct/100),2.5,1,1,'F');
    pdf.setTextColor(...brc);pdf.setFont('helvetica','bold');pdf.setFontSize(12);pdf.text(`${b.score}`,158,y+14,{align:'right'});
    pdf.setFontSize(6.5);pdf.text(`/${b.max}`,160,y+14);pdf.text(brl,192,y+14,{align:'right'});
    pdf.setFontSize(8);pdf.text(`${b.pct}%`,192,y+21,{align:'right'});
    y+=29;
  });
  pdf.setFillColor(...o);pdf.roundedRect(12,y,186,15,2,2,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(8.5);pdf.text('PUNTUACIÓN TOTAL',15,y+6);
  pdf.setFontSize(12);pdf.text(`${d.total}/40 pts · ${d.pct}% · NIVEL ${d.risk}`,192,y+10,{align:'right'});
  pdf.setFillColor(...o);pdf.rect(0,H-10,W,10,'F');
  pdf.setTextColor(...wh);pdf.setFontSize(7);pdf.setFont('helvetica','normal');pdf.text('ssoler@duransindreu.com',W/2,H-3,{align:'center'});pdf.text('2',W-10,H-3,{align:'right'});

  // P3 — PLAN DE ACCIÓN
  pdf.addPage();pdf.setFillColor(...g1);pdf.rect(0,0,W,H,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,W,11,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text('DURÁN SINDREU ABOGADOS · PLAN DE ACCIÓN PERSONALIZADO',W/2,7.5,{align:'center'});
  pdf.setFillColor(...bk);pdf.rect(0,11,W,25,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(16);pdf.text('Plan de Acción Personalizado',12,23);
  pdf.setTextColor(...o);pdf.setFontSize(7.5);pdf.text(`${d.empresa.toUpperCase()} · ${d.date}`,12,31);
  y=45;
  const acts={alta:[],media:[],baja:[{t:'Auditoría externa del modelo de compliance',d:'Revisión independiente anual para validar la efectividad del modelo y detectar áreas de mejora.'},{t:'Certificación UNE 19601 o ISO 37001',d:'Acreditar formalmente el nivel de cumplimiento para ventajas competitivas, de exención penal y ESG.'},{t:'Sistema de Gestión de la Diversidad',d:'Implementar conforme Ley 15/2022. Diferencial competitivo en captación de talento y reporting ESG.'}]};
  if(d.bs[0].pct<50){acts.alta.push({t:'Modelo de prevención de delitos (art. 31 bis CP)',d:'Elaborar el modelo completo. Prioridad máxima para eliminar la responsabilidad penal directa de administradores.'});acts.alta.push({t:'Mapa de riesgos penales actualizado',d:'Identificar, documentar y priorizar los riesgos penales de la organización. Revisión mínima anual.'});}
  else if(d.bs[0].pct<80)acts.media.push({t:'Actualización y refuerzo del modelo de compliance',d:'Revisar y completar el modelo existente conforme a los últimos estándares jurisprudenciales.'});
  if(SC[2]===0||SC[2]===undefined)acts.alta.push({t:'Designar Compliance Officer con independencia funcional',d:'Nombrar responsable con autonomía real, medios suficientes y reporte directo al órgano de gobierno.'});
  if(d.bs[1].pct<50){acts.alta.push({t:'Canal interno de denuncias (Ley 2/2023)',d:'Obligatorio >50 empleados. Sanciones de hasta 1.000.000 €. Implementación inmediata.'});acts.alta.push({t:'Designar Responsable del SII formalmente',d:'Designar al Responsable del Sistema Interno de Información con las garantías legales requeridas.'});}
  else if(d.bs[1].pct<80)acts.media.push({t:'Completar el reglamento del canal de denuncias',d:'Documentar el procedimiento completo de recepción, tramitación y cierre de informaciones.'});
  if(d.bs[2].pct<50&&d.empleados!=='<50'){acts.alta.push({t:'Protocolo de prevención del acoso sexual y laboral',d:'Obligatorio >50 empleados. Aprobación, comunicación a la plantilla y formación específica.'});acts.alta.push({t:'Plan de Igualdad registrado en el Ministerio',d:'Negociar y registrar el Plan de Igualdad. Multas de hasta 225.018 €.'});}
  else if(d.bs[2].pct<80){acts.media.push({t:'Comisión de Igualdad paritaria',d:'Constituir y establecer sistema de seguimiento, evaluación y revisión del Plan.'});acts.media.push({t:'Protocolos LGTBI (Ley 4/2023)',d:'Adaptar todos los protocolos de no discriminación a la Ley 4/2023.'});}
  if(d.bs[3].pct<50){acts.alta.push({t:'Política de tolerancia cero a corrupción y soborno',d:'Aprobar, publicar y comunicar formalmente la política anticorrupción a toda la organización.'});acts.alta.push({t:'Procedimientos KYC y diligencia debida',d:'Implementar procedimientos de conocimiento del cliente y terceros con registro documentado.'});}
  else if(d.bs[3].pct<80)acts.media.push({t:'Manual PBC/FT actualizado',d:'Revisar el manual cada 2 años y extender la formación anticorrupción a directivos y mandos.'});
  const drawActs=(items,color,title,time)=>{
    if(!items.length)return;
    pdf.setFillColor(...color);pdf.roundedRect(12,y,186,9,2,2,'F');
    pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(8);pdf.text(title,15,y+6.5);
    pdf.setFontSize(7);pdf.text(time,190,y+6.5,{align:'right'});y+=13;
    items.forEach(item=>{
      if(y+17>H-14){pdf.addPage();pdf.setFillColor(...g1);pdf.rect(0,0,W,H,'F');pdf.setFillColor(...o);pdf.rect(0,0,W,11,'F');pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text('DURÁN SINDREU · PLAN DE ACCIÓN (cont.)',W/2,7.5,{align:'center'});y=18;}
      pdf.setFillColor(...wh);pdf.roundedRect(12,y,186,16,1,1,'F');
      pdf.setFillColor(...color);pdf.roundedRect(12,y,3,16,1,1,'F');
      pdf.setTextColor(...bk);pdf.setFont('helvetica','bold');pdf.setFontSize(8);pdf.text(item.t,17,y+6);
      pdf.setTextColor(...g6);pdf.setFont('helvetica','normal');pdf.setFontSize(7);
      pdf.text(pdf.splitTextToSize(item.d,168)[0],17,y+11.5);y+=20;
    });y+=4;
  };
  drawActs(acts.alta,red,'PRIORIDAD ALTA','0 – 6 meses');
  drawActs(acts.media,amb,'PRIORIDAD MEDIA','6 – 12 meses');
  drawActs(acts.baja,grn,'PRIORIDAD BAJA','12 – 24 meses');
  pdf.setFillColor(...o);pdf.rect(0,H-10,W,10,'F');
  pdf.setTextColor(...wh);pdf.setFontSize(7);pdf.setFont('helvetica','normal');pdf.text('ssoler@duransindreu.com',W/2,H-3,{align:'center'});pdf.text('3',W-10,H-3,{align:'right'});

  // P4 — SERVICIOS / CTA
  pdf.addPage();pdf.setFillColor(...bk);pdf.rect(0,0,W,H,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,6,H,'F');
  pdf.setFillColor(...o);pdf.rect(0,0,W,11,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text('DURÁN SINDREU ABOGADOS · SERVICIOS DE COMPLIANCE',W/2,7.5,{align:'center'});
  pdf.setTextColor(...o);pdf.setFont('helvetica','bold');pdf.setFontSize(8);pdf.text('NUESTROS SERVICIOS',12,30);
  pdf.setFontSize(25);pdf.setTextColor(...wh);pdf.text('Le acompañamos en la',12,42);
  pdf.setTextColor(...o);pdf.text('implantación completa',12,53);
  pdf.setTextColor(255,255,255,150);pdf.setFont('helvetica','normal');pdf.setFontSize(9.5);pdf.text('del modelo de compliance de su organización, con plenas garantías jurídicas.',12,63);
  const svcs=[{t:'Modelo Compliance Penal',d:'Diseño e implantación del modelo de prevención de delitos adaptado a su sector y estructura corporativa.',l:'Art. 31 bis CP · UNE 19601'},{t:'Canal de Denuncias',d:'Implementación técnica y jurídica del canal, reglamento y apoyo al Responsable del SII conforme Ley 2/2023.',l:'Ley 2/2023 · Dir. 2019/1937'},{t:'Plan de Igualdad y Diversidad',d:'Diagnóstico, negociación y registro del Plan. Protocolos de acoso y planes LGTBI conforme Ley 4/2023.',l:'LO 3/2007 · Ley 4/2023'},{t:'Anticorrupción y PBC/FT',d:'Políticas, KYC, manual PBC/FT, formación certificada a directivos y acompañamiento hacia ISO 37001.',l:'Ley 10/2010 · ISO 37001'}];
  y=78;
  svcs.forEach((s,i)=>{
    const cx=12+(i%2)*96,cy=y+Math.floor(i/2)*48;
    pdf.setFillColor(255,255,255,7);pdf.roundedRect(cx,cy,90,44,2,2,'F');
    pdf.setFillColor(...o);pdf.roundedRect(cx,cy,90,5,2,2,'F');
    pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(7.5);pdf.text(s.t,cx+3,cy+3.5);
    pdf.setTextColor(255,255,255,145);pdf.setFont('helvetica','normal');pdf.setFontSize(6.5);
    pdf.splitTextToSize(s.d,83).slice(0,4).forEach((l,j)=>pdf.text(l,cx+3,cy+12+j*4.5));
    pdf.setTextColor(...o);pdf.setFontSize(6.5);pdf.setFont('helvetica','bold');pdf.text(s.l,cx+3,cy+40);
  });
  y=182;
  pdf.setFillColor(...o);pdf.roundedRect(12,y,186,32,3,3,'F');
  pdf.setTextColor(...wh);pdf.setFont('helvetica','bold');pdf.setFontSize(11.5);pdf.text('Solicite una propuesta personalizada',105,y+9,{align:'center'});
  pdf.setFontSize(8.5);pdf.setFont('helvetica','normal');pdf.text('Respuesta en menos de 24 horas · Sin compromiso · Equipo especializado en Compliance',105,y+17,{align:'center'});
  pdf.setFont('helvetica','bold');pdf.setFontSize(10);pdf.text('ssoler@duransindreu.com',105,y+26,{align:'center'});
  pdf.setTextColor(255,255,255,40);pdf.setFontSize(7);pdf.setFont('helvetica','normal');
  pdf.setDrawColor(255,255,255,12);pdf.setLineWidth(.15);pdf.line(12,H-26,198,H-26);
  pdf.text('Herramienta orientativa. No sustituye el asesoramiento jurídico profesional personalizado.',105,H-19,{align:'center'});
  pdf.text(`© 2025 Durán Sindreu Abogados · Barcelona · Informe generado el ${d.date}`,105,H-13,{align:'center'});
  pdf.setFillColor(...o);pdf.rect(0,H-10,W,10,'F');
  pdf.setTextColor(...wh);pdf.setFontSize(7);pdf.setFont('helvetica','bold');pdf.text('ssoler@duransindreu.com · Barcelona',W/2,H-3,{align:'center'});pdf.text('4',W-10,H-3,{align:'right'});

  pdf.save(`DS
