<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="color-scheme" content="dark">
<meta name="description" content="Официальный сайт Паджа — Мясника. Программы, полигон, досье и моменты побед.">
<title>PUDGE — официальный сайт Мясника</title>
<link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Cpath d='M60 8 v40 a24 24 0 1 1 -48 -4' fill='none' stroke='%23a4121f' stroke-width='12'/%3E%3Cpath d='M12 24 l14 13 -21 7 z' fill='%23a4121f'/%3E%3C/svg%3E">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Oswald:wght@300;400;500;600;700&family=Russo+One&display=swap" rel="stylesheet">
<style>
/* ============ БАЗА ============ */
:root{
  --bg:#0a0607; --bg2:#100a0c; --panel:#150d10; --panel2:#1a1013;
  --line:#2b1216; --line2:#3a1a20;
  --red:#a4121f; --red-b:#e62333; --red-d:#5a0a13;
  --meat:#d9c3a5; --text:#e9ded7; --muted:#9a8a86;
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth;scroll-padding-top:88px}
body{
  background-color:var(--bg);
  background-image:
    repeating-linear-gradient(115deg, rgba(164,18,31,.03) 0 2px, transparent 2px 9px),
    radial-gradient(60% 40% at 82% 0%, rgba(90,10,19,.28), transparent 60%),
    radial-gradient(50% 40% at 0% 90%, rgba(90,10,19,.2), transparent 60%);
  background-attachment:fixed;
  color:var(--text);
  font:300 15px/1.32 'Oswald',sans-serif;
  overflow-x:hidden;
}
/* зерно плёнки + виньетка — «выраженная текстура» */
body::before{content:"";position:fixed;inset:0;z-index:2000;pointer-events:none;opacity:.055;
  background-image:url("data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20width='140'%20height='140'%3E%3Cfilter%20id='n'%3E%3CfeTurbulence%20type='fractalNoise'%20baseFrequency='0.9'%20numOctaves='2'%20stitchTiles='stitch'/%3E%3C/filter%3E%3Crect%20width='140'%20height='140'%20filter='url(%23n)'%20opacity='0.6'/%3E%3C/svg%3E");}
body::after{content:"";position:fixed;inset:0;z-index:1500;pointer-events:none;
  background:radial-gradient(120% 90% at 50% 18%, transparent 55%, rgba(4,2,3,.5) 100%);}
::selection{background:var(--red);color:#fff}
::-webkit-scrollbar{width:11px}
::-webkit-scrollbar-track{background:#0c0709}
::-webkit-scrollbar-thumb{background:var(--red-d);border:2px solid #0c0709}
::-webkit-scrollbar-thumb:hover{background:var(--red)}
a{color:inherit;text-decoration:none}
img,svg{display:block}
.svg-defs{position:absolute;width:0;height:0;overflow:hidden}
.container{width:min(1240px,92vw);margin:0 auto}
.up{text-transform:uppercase}
.red{color:var(--red-b)}

/* ============ ШАПКА ============ */
header{position:fixed;top:0;left:0;right:0;z-index:900;height:66px;
  background:rgba(10,6,7,.85);backdrop-filter:blur(10px);border-bottom:1px solid var(--line)}
.hd{height:66px;display:flex;align-items:center;justify-content:space-between;gap:20px}
.logo{display:flex;align-items:center;gap:12px;font:17px 'Russo One';letter-spacing:.08em}
.logo svg{width:26px;height:26px;color:var(--red-b);transition:transform .5s cubic-bezier(.2,.8,.2,1)}
.logo:hover svg{transform:rotate(-40deg)}
.logo small{font:600 9px 'Oswald';letter-spacing:.34em;color:var(--muted);display:block;margin-top:2px}
#mainNav{display:flex;gap:26px}
#mainNav a{font:500 12px 'Oswald';letter-spacing:.18em;color:var(--muted);padding:6px 2px;border-bottom:2px solid transparent;transition:.25s}
#mainNav a:hover{color:var(--text)}
#mainNav a.act{color:var(--red-b);border-color:var(--red-b)}
.hd-cta{display:inline-flex;align-items:center;gap:8px;font:600 11px 'Oswald';letter-spacing:.2em;color:var(--text);
  border:1px solid var(--line2);padding:10px 16px;transition:.25s}
.hd-cta:hover{border-color:var(--red-b);color:var(--red-b)}
#burger{display:none;background:none;border:1px solid var(--line2);width:44px;height:40px;cursor:pointer;position:relative}
#burger span{position:absolute;left:10px;right:10px;height:2px;background:var(--red-b);transition:.3s}
#burger span:nth-child(1){top:12px}#burger span:nth-child(2){top:19px}#burger span:nth-child(3){top:26px}
#burger.act span:nth-child(1){top:19px;transform:rotate(45deg)}
#burger.act span:nth-child(2){opacity:0}
#burger.act span:nth-child(3){top:19px;transform:rotate(-45deg)}

/* ============ КНОПКИ ============ */
.btn{display:inline-flex;align-items:center;gap:12px;font:600 13.5px 'Oswald';letter-spacing:.18em;text-transform:uppercase;
  padding:17px 28px;color:#fff;background:linear-gradient(180deg,#a4121f,#6d0d17);border:1px solid #c2152a;cursor:pointer;
  clip-path:polygon(14px 0,100% 0,100% calc(100% - 14px),calc(100% - 14px) 100%,0 100%,0 14px);
  transition:.25s;text-align:center}
.btn svg{width:17px;height:17px;fill:currentColor;color:currentColor}
.btn:hover{filter:brightness(1.25);transform:translateY(-2px);box-shadow:0 16px 34px -12px rgba(230,35,51,.5)}
.btn.ghost{background:transparent;border-color:var(--line2);color:var(--muted)}
.btn.ghost:hover{border-color:var(--red-b);color:var(--red-b);box-shadow:none;filter:none}
.btn.sm{padding:12px 18px;font-size:12px}

/* ============ СЕКЦИИ ============ */
section{position:relative;padding:96px 0 76px;overflow:hidden}
.kick{display:flex;align-items:center;gap:12px;font:600 12px 'Oswald';letter-spacing:.32em;color:var(--red-b);text-transform:uppercase}
.kick::before{content:"";width:36px;height:2px;background:var(--red)}
.sec-head{position:relative;margin-bottom:46px}
.gnum{position:absolute;top:-52px;left:-8px;font:118px 'Russo One';line-height:1;color:transparent;
  -webkit-text-stroke:1px rgba(230,35,51,.15);pointer-events:none;user-select:none}
.sec-head h2{position:relative;font:clamp(30px,4.6vw,54px)/1.02 'Russo One';text-transform:uppercase;letter-spacing:.02em;margin-top:10px}
.sec-sub{font:600 11px 'Oswald';letter-spacing:.26em;color:var(--muted);text-transform:uppercase;display:block;margin-top:10px}
.splat{position:absolute;color:var(--red);opacity:.07;pointer-events:none}
.s1{width:230px;left:-60px;bottom:-30px;transform:rotate(14deg)}
.s2{width:190px;right:-50px;top:60px;transform:rotate(-24deg)}

/* появление при скролле */
.rv{opacity:0;transform:translateY(26px);transition:opacity .7s cubic-bezier(.2,.7,.2,1),transform .7s cubic-bezier(.2,.7,.2,1);transition-delay:var(--d,0s)}
.rv.in{opacity:1;transform:none}

/* ============ ГЕРОЙ ============ */
#top{min-height:96vh;display:flex;align-items:center;padding:140px 0 60px}
.hero-bg{position:absolute;inset:0;pointer-events:none;
  background:
    radial-gradient(46% 52% at 74% 38%, rgba(164,18,31,.30), transparent 70%),
    radial-gradient(30% 34% at 60% 80%, rgba(90,10,19,.4), transparent 70%),
    radial-gradient(24% 30% at 12% 24%, rgba(90,10,19,.35), transparent 70%);}
#heroEmbers{position:absolute;inset:0;pointer-events:none}
.ember{position:absolute;bottom:-12px;border-radius:50%;background:#ff5560;opacity:0;
  box-shadow:0 0 7px rgba(255,80,96,.9);animation:rise linear infinite}
@keyframes rise{0%{transform:translate(0,0);opacity:0}8%{opacity:.9}100%{transform:translate(34px,-72vh);opacity:0}}
.hero-grid{display:grid;grid-template-columns:1.06fr .94fr;gap:30px;align-items:center;position:relative}
.hero h1{font:clamp(72px,11.4vw,172px)/0.94 'Russo One';text-transform:uppercase;letter-spacing:.01em;margin:16px 0 4px;
  text-shadow:6px 6px 0 #26070c, 0 0 44px rgba(230,35,51,.3)}
.hero h1 .o{color:transparent;-webkit-text-stroke:2.5px var(--red-b)}
.hero-role{font:600 13px 'Oswald';letter-spacing:.42em;color:var(--meat);text-transform:uppercase}
.hero-role b{color:var(--red-b)}
.hero-tag{max-width:560px;margin:20px 0 30px;font:300 16.5px/1.32 'Oswald';color:#cfc1bb}
.hero-tag b{color:var(--text);font-weight:500}
.hero-btns{display:flex;gap:14px;flex-wrap:wrap}
.hero-stats{display:grid;grid-template-columns:repeat(4,1fr);border-block:1px solid var(--line);margin-top:44px}
.hst{padding:16px 18px 14px;border-right:1px solid var(--line)}
.hst:last-child{border-right:0}
.hst b{display:block;font:clamp(20px,2.2vw,30px) 'Russo One';color:var(--red-b)}
.hst span{font:600 9.5px 'Oswald';letter-spacing:.2em;color:var(--muted);text-transform:uppercase}
.hero-art{position:relative}
.hero-art > svg{width:100%;height:auto;filter:drop-shadow(0 34px 60px rgba(164,18,31,.28))}
.chip{position:absolute;font:12px 'Russo One';letter-spacing:.1em;color:var(--text);
  background:rgba(21,13,16,.92);border:1px solid var(--line2);padding:9px 13px;white-space:nowrap;
  box-shadow:0 10px 30px -10px rgba(0,0,0,.7);animation:chip 5.5s ease-in-out infinite alternate}
.chip i{color:var(--red-b);font-style:normal}
.c1{top:4%;left:-4%}.c2{top:42%;right:-6%;animation-delay:-2s}.c3{bottom:8%;left:2%;animation-delay:-3.5s}
@keyframes chip{from{transform:translateY(0)}to{transform:translateY(-14px)}}

/* ============ БЕГУЩАЯ СТРОКА ============ */
.mq{overflow:hidden;border-block:1px solid var(--line);background:#0f080a}
.mq-track{display:flex;width:max-content;animation:mq 30s linear infinite}
.mq-track span{font:15px 'Russo One';letter-spacing:.16em;color:#8d7c78;padding:15px 30px;white-space:nowrap;text-transform:uppercase}
.mq-track span:nth-child(4n+1){color:var(--red-b)}
.mq-track span:nth-child(4n+3){color:var(--meat)}
@keyframes mq{to{transform:translateX(-50%)}}

/* ============ 01 МАНИФЕСТ ============ */
.wel-grid{display:grid;grid-template-columns:1.06fr .94fr;gap:44px;align-items:start}
.manq{border-left:4px solid var(--red);padding:6px 0 6px 22px;margin:22px 0 18px;
  font:500 clamp(20px,2.4vw,27px)/1.16 'Oswald';text-transform:uppercase;letter-spacing:.02em}
.manq b{color:var(--red-b)}
.wel-txt p{color:#c9bbb5;margin-bottom:12px;max-width:600px}
.wel-txt p b{color:var(--text);font-weight:500}
.pos-card{background:var(--panel);border:1px solid var(--line);padding:26px;
  clip-path:polygon(0 0,calc(100% - 18px) 0,100% 18px,100% 100%,18px 100%,0 calc(100% - 18px))}
.pos-card h3{font:15px 'Russo One';letter-spacing:.14em;text-transform:uppercase;margin-bottom:18px;color:var(--meat)}
.pos-item{display:flex;gap:16px;padding:14px 0;border-top:1px dashed var(--line)}
.pos-item svg{width:26px;height:26px;color:var(--red-b);flex:none;margin-top:2px}
.pos-item b{font:600 13px 'Oswald';letter-spacing:.22em;color:var(--red-b);text-transform:uppercase}
.pos-item p{font-size:14px;color:#c2b4ae;margin-top:3px}
.pos-note{margin-top:16px;padding-top:14px;border-top:1px solid var(--line);font-size:13px;color:var(--muted)}
.pos-note b{color:var(--meat);font-weight:500}

.team{margin-top:64px}
.team h3{font:clamp(20px,2.6vw,28px) 'Russo One';text-transform:uppercase;margin:8px 0 6px}
.team-sub{color:var(--muted);font-size:14px;margin-bottom:26px}
.team-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}
.tcard{background:var(--panel);border:1px solid var(--line);padding:24px 22px;transition:.3s;
  clip-path:polygon(0 0,calc(100% - 14px) 0,100% 14px,100% 100%,0 100%)}
.tcard:hover{border-color:rgba(230,35,51,.6);transform:translateY(-6px);box-shadow:0 22px 44px -22px rgba(230,35,51,.4)}
.tc-ico{width:48px;height:48px;display:grid;place-items:center;border:1px solid rgba(230,35,51,.5);
  background:rgba(164,18,31,.12);margin-bottom:16px}
.tc-ico svg{width:26px;height:26px;color:var(--red-b)}
.tc-role{font:600 10px 'Oswald';letter-spacing:.24em;color:var(--red-b);text-transform:uppercase}
.tc-name{font:20px 'Russo One';margin:7px 0 9px}
.tc-quote{font:300 13.5px/1.32 'Oswald';color:#c2b4ae}
.tc-stat{margin-top:14px;padding-top:11px;border-top:1px dashed var(--line);font:500 10.5px 'Oswald';letter-spacing:.12em;color:var(--muted);text-transform:uppercase}

/* ============ 02 ПРОГРАММЫ ============ */
.prog{display:grid;grid-template-columns:350px 1fr;background:var(--panel);border:1px solid var(--line);margin-bottom:26px}
.prog-meta{padding:30px 28px;border-right:1px solid var(--line);position:relative;overflow:hidden}
.prog.alt .prog-meta{border-right:0;border-left:1px solid var(--line);order:2}
.p-num{font:46px 'Russo One';color:transparent;-webkit-text-stroke:1.5px var(--red-b);line-height:1}
.prog-meta h3{font:clamp(21px,2.2vw,27px) 'Russo One';text-transform:uppercase;margin:10px 0 4px}
.p-goal{display:inline-block;margin:8px 0 14px;padding:6px 10px;border:1px solid var(--red);color:var(--red-b);
  font:600 10.5px 'Oswald';letter-spacing:.22em;text-transform:uppercase}
.chips{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:16px}
.chip-s{font:600 10px 'Oswald';letter-spacing:.14em;color:var(--muted);border:1px solid var(--line);padding:5px 9px;text-transform:uppercase}
.pain{display:flex;align-items:center;gap:10px;margin-bottom:16px;font:600 10px 'Oswald';letter-spacing:.2em;color:var(--muted)}
.dots{display:flex;gap:5px}
.dots i{width:10px;height:10px;border-radius:50%;background:#2a1216}
.dots i.on{background:var(--red-b);box-shadow:0 0 8px rgba(230,35,51,.6)}
.p-quote{border-left:3px solid var(--red);padding-left:12px;font:300 14px/1.32 'Oswald';color:#c2b4ae}
.p-quote em{display:block;margin-top:6px;font-style:normal;color:var(--muted);font-size:11.5px;letter-spacing:.14em;text-transform:uppercase}
.p-note{padding:14px 18px;border-top:1px solid var(--line);font-size:13px;color:var(--muted)}
.p-note b{color:var(--red-b);font-weight:600;letter-spacing:.18em;font-size:10.5px;margin-right:8px}
.tbl-wrap{overflow-x:auto}
.tbl{width:100%;border-collapse:collapse;font-size:13.5px;min-width:560px}
.tbl th{font:600 10px 'Oswald';letter-spacing:.22em;color:var(--muted);text-align:left;padding:13px 14px 11px;border-bottom:1px solid var(--line2);text-transform:uppercase}
.tbl td{padding:11px 14px;border-bottom:1px solid rgba(43,18,22,.65);line-height:1.3;vertical-align:top;color:#c9bbb5}
.tbl td:first-child{color:var(--text);font-weight:500}
.tbl .sc{font:13px 'Russo One';color:var(--red-b);white-space:nowrap}
.tbl tr:hover td{background:rgba(164,18,31,.07)}

/* ============ 03 ПОЛИГОН ============ */
.poly-grid{display:grid;grid-template-columns:1fr 300px;gap:18px;align-items:stretch}
.arena{position:relative;height:440px;cursor:crosshair;user-select:none;-webkit-user-select:none;overflow:hidden;
  border:1px solid var(--line);
  background:radial-gradient(90% 110% at 62% 38%, #150a0d, #0a0507 75%)}
.arena::before{content:"";position:absolute;inset:0;pointer-events:none;
  background:
    linear-gradient(rgba(164,18,31,.05) 1px, transparent 1px) 0 0/100% 44px,
    linear-gradient(90deg, rgba(164,18,31,.05) 1px, transparent 1px) 0 0/44px 100%}
.launcher{position:absolute;left:0;top:50%;transform:translateY(-50%);width:76px;height:76px;border-radius:50%;
  border:2px solid var(--red);background:radial-gradient(circle at 38% 32%, #1e1215, #0a0507);display:grid;place-items:center;z-index:9}
.launcher svg{width:32px;height:32px;color:#c9ced6;filter:drop-shadow(0 0 5px rgba(230,35,51,.5))}
.launcher::after{content:"";position:absolute;inset:-12px;border:1px solid rgba(230,35,51,.5);border-radius:50%;animation:pulse 2.4s ease-out infinite}
@keyframes pulse{0%{transform:scale(.82);opacity:.9}70%{transform:scale(1.28);opacity:0}100%{opacity:0}}
#arenaChain{position:absolute;height:5px;transform-origin:0 50%;display:none;z-index:6;pointer-events:none;border-radius:3px;
  background:repeating-linear-gradient(90deg,#5b616a 0 12px,#23262c 12px 18px)}
#arenaTip{position:absolute;width:46px;height:46px;display:none;z-index:7;pointer-events:none;
  color:#c9ced6;filter:drop-shadow(0 0 6px rgba(230,35,51,.65))}
#arenaTip svg{width:100%;height:100%}
.meat-track{position:absolute;width:48px;height:44px;z-index:5;transition:opacity .3s;animation:drift var(--dd,7s) ease-in-out infinite alternate}
@keyframes drift{from{margin-left:0}to{margin-left:44px}}
.meat{width:100%;height:100%;position:relative;
  background:radial-gradient(circle at 35% 30%, #e5697a, #a4121f 48%, #47070f 84%);
  border-radius:47% 53% 52% 48% / 58% 46% 54% 42%;
  box-shadow:inset -6px -9px 14px rgba(0,0,0,.55), 0 0 20px rgba(228,35,51,.35);
  animation:bob 2.7s ease-in-out infinite alternate}
.meat::after{content:"";position:absolute;top:-5px;right:7px;width:10px;height:10px;border-radius:50%;
  background:#e9ded7;box-shadow:-15px 3px 0 -2px #e9ded7}
@keyframes bob{from{transform:translateY(0) rotate(-7deg)}to{transform:translateY(-16px) rotate(8deg)}}
.splash{position:absolute;z-index:8;pointer-events:none;transform:translate(-50%,-50%);animation:spl .55s ease-out forwards}
.splash svg{width:130px;height:auto;color:var(--red-b)}
@keyframes spl{0%{transform:translate(-50%,-50%) scale(.35);opacity:1}100%{transform:translate(-50%,-50%) scale(1.45);opacity:0}}
.ftext{position:absolute;z-index:9;pointer-events:none;font:15px 'Russo One';white-space:nowrap;transform:translate(-50%,-50%);animation:fu .9s ease-out forwards}
@keyframes fu{from{opacity:1}to{transform:translate(-50%,-160%);opacity:0}}
.hud{position:absolute;top:12px;left:14px;z-index:9;display:flex;gap:18px;pointer-events:none;
  font:600 11px 'Oswald';letter-spacing:.18em;color:var(--muted);text-transform:uppercase}
.hud b{color:var(--text)}
.hint{position:absolute;bottom:12px;right:14px;z-index:9;pointer-events:none;font:300 11.5px 'Oswald';letter-spacing:.06em;color:#7c6d69}
.poly-side{background:var(--panel);border:1px solid var(--line);padding:24px;display:flex;flex-direction:column;gap:14px}
.ps-row{display:flex;justify-content:space-between;align-items:baseline;border-bottom:1px dashed var(--line);padding-bottom:10px}
.ps-row span{font:600 10.5px 'Oswald';letter-spacing:.2em;color:var(--muted);text-transform:uppercase}
.ps-row b{font:30px 'Russo One';color:var(--red-b)}
.ps-row b.dim{color:var(--text)}
.poly-side p{font-size:13px;color:var(--muted);line-height:1.35}
.poly-side p b{color:var(--meat);font-weight:500}

/* ============ 04 ДОСЬЕ ============ */
.dos-top{display:grid;grid-template-columns:1.08fr .92fr;gap:48px;margin-bottom:64px}
.dos-top h3{font:16px 'Russo One';letter-spacing:.14em;text-transform:uppercase;color:var(--meat);margin-bottom:22px}
.skill{display:grid;grid-template-columns:158px 1fr 46px;gap:14px;align-items:center;margin-bottom:13px}
.skill span{font:500 12px 'Oswald';letter-spacing:.1em;color:#c2b4ae;text-transform:uppercase}
.bar{height:12px;background:#1c1013;border:1px solid var(--line)}
.bar i{display:block;height:100%;width:0;background:repeating-linear-gradient(-45deg,var(--red) 0 10px,#6d0d17 10px 20px);
  transition:width 1.2s cubic-bezier(.2,.7,.2,1)}
.skill b{font:14px 'Russo One';color:var(--red-b);text-align:right}
.pos-line{margin-top:20px;padding-top:16px;border-top:1px solid var(--line);font-size:13.5px;color:var(--muted)}
.pos-line b{color:var(--text);font-weight:500}
.cnt-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.cbox{border:1px solid var(--line);background:var(--panel);padding:20px 20px 16px;transition:.3s}
.cbox:hover{border-color:rgba(230,35,51,.5)}
.cbox b{display:block;font:clamp(26px,2.6vw,34px) 'Russo One';color:var(--red-b);line-height:1}
.cbox span{display:block;margin-top:7px;font:600 10px 'Oswald';letter-spacing:.2em;color:var(--muted);text-transform:uppercase}
.dos-note{grid-column:1/-1;font-size:13px;color:var(--muted);padding:6px 2px 0}
.dos-note b{color:var(--meat);font-weight:500}
.wins h3{font:16px 'Russo One';letter-spacing:.14em;text-transform:uppercase;color:var(--meat);margin-bottom:22px}
.wins-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:16px;margin-bottom:64px}
.win{position:relative;border:1px solid var(--line);background:var(--panel);padding:22px 22px 18px;transition:.3s}
.win:hover{border-color:rgba(230,35,51,.55);transform:translateY(-4px)}
.win .yr{position:absolute;top:18px;right:18px;font:14px 'Russo One';color:var(--red-b);border:1px solid var(--line2);padding:4px 9px}
.win h4{font:17px 'Russo One';text-transform:uppercase;margin-bottom:8px;padding-right:80px}
.win p{font-size:13.5px;color:#b9aba5;max-width:92%}
.ph-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.ph{position:relative;aspect-ratio:3/4;border:1px solid var(--line);overflow:hidden;background:#0d0709}
.ph .scene{position:absolute;inset:-4%;width:108%;height:108%;transition:transform .6s cubic-bezier(.2,.7,.2,1)}
.ph:hover .scene{transform:scale(1.045)}
.ph.bw .scene{filter:grayscale(1) contrast(1.38) brightness(.96)}
.ph.col .scene{filter:saturate(1.3) contrast(1.14)}
.ph.cine .scene{filter:contrast(1.42) saturate(1.12) hue-rotate(-8deg)}
.ph::before{content:"";position:absolute;inset:0;z-index:2;pointer-events:none;
  background:repeating-linear-gradient(0deg, rgba(255,255,255,.022) 0 1px, transparent 1px 3px)}
.tagc{position:absolute;top:10px;left:10px;z-index:3;font:600 9.5px 'Oswald';letter-spacing:.18em;
  background:rgba(10,6,7,.82);border:1px solid var(--line2);color:var(--red-b);padding:5px 8px;text-transform:uppercase}
.ph-ico{position:absolute;top:10px;right:10px;z-index:3;width:24px;height:24px;color:var(--red-b);opacity:.9}
.ph figcaption{position:absolute;left:0;right:0;bottom:0;z-index:3;padding:36px 14px 14px;
  background:linear-gradient(transparent, rgba(5,3,4,.94))}
.ph figcaption h4{font:15px 'Russo One';text-transform:uppercase}
.ph figcaption p{font-size:12px;color:var(--muted);margin-top:4px}

/* ============ CTA ============ */
#cta{padding:0}
.cta-box{background:linear-gradient(120deg,#4d0a12,#7d0f1a 55%,#4d0a12);border:1px solid #b01325;position:relative;overflow:hidden;
  padding:70px 40px;text-align:center;
  clip-path:polygon(0 0,calc(100% - 26px) 0,100% 26px,100% 100%,26px 100%,0 calc(100% - 26px))}
.cta-box::before{content:"";position:absolute;inset:0;opacity:.14;pointer-events:none;
  background:radial-gradient(50% 80% at 20% 20%, #ff5560, transparent 60%),radial-gradient(40% 70% at 85% 80%, #2c0810, transparent 60%)}
.cta-box h2{position:relative;font:clamp(24px,3.6vw,44px)/1.08 'Russo One';text-transform:uppercase;max-width:900px;margin:0 auto 16px}
.cta-box p{position:relative;color:#e8c9c4;max-width:640px;margin:0 auto 30px;font-size:15px}
.cta-btns{position:relative;display:flex;gap:14px;justify-content:center;flex-wrap:wrap}
.cta-btns .btn{background:linear-gradient(180deg,#150d10,#0a0607);border-color:#2b1216}
.cta-btns .btn:hover{border-color:var(--red-b)}
.cta-btns .btn.ghost{background:transparent}

/* ============ ПОДВАЛ ============ */
footer{border-top:1px solid var(--line);background:#0c0709;padding:56px 0 0}
.ft-grid{display:grid;grid-template-columns:1.2fr 1fr 1fr;gap:40px;padding-bottom:44px}
.ft-grid h4{font:600 11px 'Oswald';letter-spacing:.26em;color:var(--red-b);text-transform:uppercase;margin-bottom:14px}
.ft-grid p,.ft-grid li{font-size:13.5px;color:var(--muted);line-height:1.4}
.ft-grid ul{list-style:none}
.ft-grid li{padding:5px 0;border-bottom:1px dashed rgba(43,18,22,.6)}
.ft-grid li a{transition:.2s}
.ft-grid li a:hover{color:var(--red-b)}
.ft-logo{display:flex;align-items:center;gap:12px;font:17px 'Russo One';margin-bottom:14px}
.ft-logo svg{width:24px;height:24px;color:var(--red-b)}
.ft-bottom{border-top:1px solid var(--line);padding:18px 0;display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap;
  font:400 11.5px 'Oswald';letter-spacing:.08em;color:#6f5f5b}

/* ============ АДАПТИВ ============ */
@media (max-width:1100px){
  .hero-grid{grid-template-columns:1fr}
  .hero-art{max-width:560px;margin:10px auto 0}
  .team-grid{grid-template-columns:1fr 1fr}
  .prog{grid-template-columns:1fr}
  .prog-meta{border-right:0!important;border-bottom:1px solid var(--line)}
  .prog.alt .prog-meta{order:0;border-left:0}
  .poly-grid{grid-template-columns:1fr}
  .dos-top{grid-template-columns:1fr}
}
@media (max-width:900px){
  #mainNav{display:none}
  #mainNav.open{display:flex;position:fixed;top:66px;left:0;right:0;flex-direction:column;gap:4px;
    background:rgba(10,6,7,.97);border-bottom:1px solid var(--line);padding:18px 5vw 24px;z-index:890}
  #mainNav.open a{padding:12px 4px;border-bottom:1px dashed var(--line);font-size:14px}
  #burger{display:block}
  .hd-cta{display:none}
  .wel-grid{grid-template-columns:1fr}
  .wins-grid{grid-template-columns:1fr}
  .ph-grid{grid-template-columns:1fr 1fr}
  .hero-stats{grid-template-columns:1fr 1fr}
  .hst:nth-child(2){border-right:0}
  .hst:nth-child(-n+2){border-bottom:1px solid var(--line)}
}
@media (max-width:600px){
  .team-grid{grid-template-columns:1fr}
  .ph-grid{grid-template-columns:1fr}
  .cnt-grid{grid-template-columns:1fr}
  .arena{height:380px}
  .skill{grid-template-columns:110px 1fr 40px;gap:9px}
}
@media (prefers-reduced-motion: reduce){
  *,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important}
  .ember{display:none}
}
</style>
</head>
<body>

<!-- ============ SVG-БИБЛИОТЕКА: иконки + авторская сцена «Падж» ============ -->
<svg class="svg-defs" aria-hidden="true" focusable="false">
  <defs>
    <radialGradient id="gGlow" cx="50%" cy="42%" r="60%">
      <stop offset="0" stop-color="#e0202f" stop-opacity=".9"/>
      <stop offset=".45" stop-color="#7d0f1a" stop-opacity=".42"/>
      <stop offset="1" stop-color="#7d0f1a" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="gCore" cx="50%" cy="50%" r="55%">
      <stop offset="0" stop-color="#ff6a72"/>
      <stop offset=".45" stop-color="#c81625"/>
      <stop offset="1" stop-color="#7a0a12" stop-opacity="0"/>
    </radialGradient>
    <linearGradient id="gMetal" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0" stop-color="#e6eaf1"/>
      <stop offset=".5" stop-color="#8f959f"/>
      <stop offset="1" stop-color="#3c4048"/>
    </linearGradient>
    <filter id="fB18" x="-60%" y="-60%" width="220%" height="220%"><feGaussianBlur stdDeviation="18"/></filter>
    <filter id="fB8" x="-40%" y="-40%" width="180%" height="180%"><feGaussianBlur stdDeviation="8"/></filter>
    <filter id="fB3" x="-40%" y="-40%" width="180%" height="180%"><feGaussianBlur stdDeviation="3"/></filter>

    <symbol id="i-hook" viewBox="0 0 100 100">
      <path d="M60 4 h18 v10 h-8 v32 a26 26 0 1 1 -52 -4" fill="none" stroke="currentColor" stroke-width="12" stroke-linecap="square"/>
      <path d="M18 26 l15 13 -22 8 z" fill="currentColor"/>
    </symbol>
    <symbol id="i-cleaver" viewBox="0 0 100 100">
      <path d="M8 26 h58 a8 8 0 0 1 8 8 v20 a16 16 0 0 1 -16 16 H8 z" fill="currentColor"/>
      <circle cx="26" cy="42" r="6" fill="#0a0607"/>
      <rect x="74" y="32" width="22" height="11" rx="3" transform="rotate(14 74 32)" fill="currentColor"/>
    </symbol>
    <symbol id="i-flame" viewBox="0 0 100 100">
      <path d="M50 6 C58 26 82 36 82 60 A32 32 0 1 1 18 60 C18 44 32 40 37 22 C41 34 50 36 50 22 Z" fill="currentColor"/>
    </symbol>
    <symbol id="i-dumb" viewBox="0 0 100 100">
      <g fill="currentColor">
        <rect x="4" y="38" width="14" height="24" rx="3"/><rect x="82" y="38" width="14" height="24" rx="3"/>
        <rect x="18" y="28" width="11" height="44" rx="2"/><rect x="71" y="28" width="11" height="44" rx="2"/>
        <rect x="29" y="45" width="42" height="10" rx="4"/>
      </g>
    </symbol>
    <symbol id="i-heart" viewBox="0 0 100 100">
      <path d="M50 88 C22 66 8 50 8 33 A21 21 0 0 1 50 24 A21 21 0 0 1 92 33 C92 50 78 66 50 88 Z" fill="currentColor"/>
    </symbol>
    <symbol id="i-kettle" viewBox="0 0 100 100">
      <path d="M32 34 a19 15 0 0 1 36 0" fill="none" stroke="currentColor" stroke-width="9"/>
      <circle cx="50" cy="62" r="29" fill="currentColor"/>
    </symbol>
    <symbol id="i-trophy" viewBox="0 0 100 100">
      <g fill="currentColor">
        <path d="M30 8 h40 v20 a20 20 0 0 1 -40 0 z"/>
        <rect x="44" y="44" width="12" height="16"/>
        <rect x="30" y="60" width="40" height="10" rx="2"/>
        <rect x="24" y="72" width="52" height="12" rx="3"/>
      </g>
      <path d="M30 14 H12 a18 18 0 0 0 18 16 M70 14 h18 a18 18 0 0 1 -18 16" fill="none" stroke="currentColor" stroke-width="7"/>
    </symbol>
    <symbol id="i-skull" viewBox="0 0 100 100">
      <path d="M50 6 a34 32 0 0 1 34 32 c0 13 -7 22 -15 28 v10 a9 9 0 0 1 -9 9 H40 a9 9 0 0 1 -9 -9 V66 C23 60 16 51 16 38 A34 32 0 0 1 50 6 Z" fill="currentColor"/>
      <circle cx="37" cy="40" r="7.5" fill="#0a0607"/><circle cx="63" cy="40" r="7.5" fill="#0a0607"/>
      <rect x="43" y="64" width="5" height="12" fill="#0a0607"/><rect x="54" y="64" width="5" height="12" fill="#0a0607"/>
    </symbol>
    <symbol id="i-chain" viewBox="0 0 100 100">
      <g fill="none" stroke="currentColor" stroke-width="9">
        <rect x="35" y="4" width="30" height="56" rx="15"/>
        <rect x="35" y="40" width="30" height="56" rx="15"/>
      </g>
    </symbol>
    <symbol id="i-splat" viewBox="0 0 220 140">
      <g fill="currentColor">
        <circle cx="46" cy="66" r="30"/><circle cx="88" cy="50" r="16"/><circle cx="122" cy="76" r="22"/>
        <circle cx="164" cy="54" r="11"/><circle cx="188" cy="82" r="7"/><circle cx="80" cy="96" r="9"/>
        <path d="M46 96 q5 20 0 34 q-5 -14 0 -34 z"/><path d="M122 98 q4 16 0 28 q-4 -12 0 -28 z"/>
      </g>
    </symbol>
  </defs>

  <!-- Сцена: силуэт Мясника. Главный объект резкий, фон размыт. Переиспользуется в герое и «фото» -->
  <g id="pudgeScene">
    <ellipse cx="150" cy="140" rx="130" ry="90" fill="#54101c" opacity=".5" filter="url(#fB18)"/>
    <ellipse cx="520" cy="130" rx="150" ry="100" fill="#2c0810" opacity=".65" filter="url(#fB18)"/>
    <ellipse cx="320" cy="240" rx="235" ry="195" fill="url(#gGlow)" opacity=".5" filter="url(#fB18)"/>
    <ellipse cx="320" cy="412" rx="240" ry="50" fill="#000" opacity=".55" filter="url(#fB18)"/>
    <!-- красный контурный свет (аура) -->
    <g fill="#e62333" opacity=".38" filter="url(#fB8)" transform="translate(-4,-5)">
      <circle cx="322" cy="122" r="36"/>
      <ellipse cx="324" cy="306" rx="122" ry="96"/>
      <path d="M216 196 Q322 138 428 196 L440 258 Q322 296 204 258 Z"/>
      <circle cx="214" cy="200" r="46"/><circle cx="428" cy="200" r="46"/>
      <path d="M198 190 C150 176 128 148 126 118" fill="none" stroke="#e62333" stroke-width="40" stroke-linecap="round"/>
      <path d="M446 198 C488 228 500 268 486 306" fill="none" stroke="#e62333" stroke-width="42" stroke-linecap="round"/>
    </g>
    <!-- цепи -->
    <path d="M244 246 C236 300 246 336 268 364" fill="none" stroke="#43424a" stroke-width="7" stroke-dasharray="12 8" stroke-linecap="round"/>
    <path d="M404 250 C418 298 412 336 394 362" fill="none" stroke="#43424a" stroke-width="7" stroke-dasharray="12 8" stroke-linecap="round"/>
    <!-- крюк в левой руке -->
    <line x1="124" y1="24" x2="124" y2="92" stroke="#6a6f79" stroke-width="6" stroke-dasharray="10 7"/>
    <path d="M124 96 v40 a24 24 0 1 1 -48 -4" fill="none" stroke="url(#gMetal)" stroke-width="11" stroke-linecap="round"/>
    <path d="M76 112 l14 13 -21 8 z" fill="#c9ced6"/>
    <circle cx="74" cy="122" r="6" fill="#ff4a55" opacity=".9" filter="url(#fB3)"/>
    <!-- тесак в правой руке -->
    <g transform="rotate(38 488 308)">
      <rect x="470" y="300" width="34" height="12" rx="3" fill="#221713"/>
      <path d="M500 296 h58 l4 28 q-30 16 -62 8 z" fill="url(#gMetal)"/>
      <circle cx="512" cy="306" r="5" fill="#0b0507"/>
      <path d="M502 330 q28 12 58 6" fill="none" stroke="#a4121f" stroke-width="3.5"/>
    </g>
    <!-- фигура -->
    <g fill="#0b0507">
      <ellipse cx="276" cy="396" rx="46" ry="20"/><ellipse cx="366" cy="396" rx="46" ry="20"/>
      <path d="M198 190 C150 176 128 148 126 118" fill="none" stroke="#0b0507" stroke-width="40" stroke-linecap="round"/>
      <path d="M446 198 C488 228 500 268 486 306" fill="none" stroke="#0b0507" stroke-width="42" stroke-linecap="round"/>
      <circle cx="214" cy="200" r="46"/><circle cx="428" cy="200" r="46"/>
      <path d="M216 196 Q322 138 428 196 L440 258 Q322 296 204 258 Z"/>
      <ellipse cx="324" cy="306" rx="122" ry="96"/>
      <circle cx="322" cy="122" r="36"/><ellipse cx="322" cy="152" rx="26" ry="16"/>
      <path d="M292 100 L302 62 L312 94 L324 58 L334 92 L346 70 L352 102 Z"/>
      <circle cx="124" cy="114" r="20"/><circle cx="488" cy="308" r="21"/>
    </g>
    <!-- швы, красное ядро, глаза -->
    <path d="M266 320 Q324 346 382 324" fill="none" stroke="#8f1520" stroke-width="3.5"/>
    <g stroke="#8f1520" stroke-width="3">
      <path d="M292 330 l-5 11"/><path d="M320 336 l-4 11"/><path d="M348 332 l-4 10"/><path d="M372 328 l-4 9"/>
    </g>
    <path d="M300 92 q22 -14 44 0" fill="none" stroke="#8f1520" stroke-width="3"/>
    <ellipse cx="324" cy="286" rx="52" ry="38" fill="url(#gCore)" opacity=".95"/>
    <ellipse cx="324" cy="286" rx="30" ry="22" fill="#ff5a63" opacity=".5" filter="url(#fB3)"/>
    <circle cx="310" cy="122" r="7" fill="#ff3040" opacity=".8" filter="url(#fB3)"/>
    <circle cx="334" cy="122" r="7" fill="#ff3040" opacity=".8" filter="url(#fB3)"/>
    <g fill="#ffd7da"><circle cx="310" cy="122" r="3"/><circle cx="334" cy="122" r="3"/></g>
    <!-- искры -->
    <g fill="#ff6a72" opacity=".85">
      <circle cx="200" cy="120" r="2.5"/><circle cx="252" cy="78" r="2"/><circle cx="420" cy="88" r="3"/>
      <circle cx="502" cy="200" r="2.5"/><circle cx="168" cy="262" r="2"/><circle cx="556" cy="318" r="2.5"/><circle cx="362" cy="58" r="2"/>
    </g>
  </g>
</svg>

<!-- ============ ШАПКА ============ -->
<header>
  <div class="container hd">
    <a class="logo" href="#top">
      <svg viewBox="0 0 100 100"><use href="#i-hook"/></svg>
      <span>PUDGE<small>OFFICIAL · ARENA</small></span>
    </a>
    <nav id="mainNav">
      <a href="#welcome">Манифест</a>
      <a href="#programs">Программы</a>
      <a href="#polygon">Полигон</a>
      <a href="#dossier">Досье</a>
      <a href="#cta">Контакт</a>
    </nav>
    <a class="hd-cta" href="#polygon">Записаться крюком</a>
    <button id="burger" aria-label="Меню"><span></span><span></span><span></span></button>
  </div>
</header>

<main>
<!-- ============ ГЕРОЙ ============ -->
<section id="top" class="hero">
  <div class="hero-bg"></div>
  <div id="heroEmbers"></div>
  <div class="container hero-grid">
    <div>
      <div class="kick rv">Официальный сайт · Поля Бесконечной Бойни</div>
      <h1 class="rv" style="--d:.05s">PUD<span class="o">GE</span></h1>
      <div class="hero-role rv" style="--d:.1s"><b>Мясник</b> · Тренер · Машина</div>
      <p class="hero-tag rv" style="--d:.15s">
        Один крюк решил больше судеб, чем все переговоры мира. Здесь — мои <b>программы</b>,
        мой <b>штат</b> и <b>полигон</b>, где твой клик превращается в мясо.
        Официальная страница. Неофициальная власть.
      </p>
      <div class="hero-btns rv" style="--d:.2s">
        <a class="btn" href="#programs"><svg viewBox="0 0 100 100"><use href="#i-kettle"/></svg>Выбрать программу</a>
        <a class="btn ghost" href="#polygon"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg>Бросить крюк</a>
      </div>
      <div class="hero-stats rv" style="--d:.25s">
        <div class="hst"><b class="num" data-to="12482">0</b><span>Крюков брошено</span></div>
        <div class="hst"><b class="num" data-to="80">0</b><span>% точности</span></div>
        <div class="hst"><b class="num" data-to="1204">0</b><span>Казней</span></div>
        <div class="hst"><b class="num" data-to="4812">0</b><span>Кг свежего мяса</span></div>
      </div>
    </div>
    <div class="hero-art rv" style="--d:.15s">
      <svg viewBox="0 0 640 440" role="img" aria-label="Силуэт Мясника с крюком в красной ауре"><use href="#pudgeScene"/></svg>
      <div class="chip c1">АУРА <i>+96</i></div>
      <div class="chip c2">КРЮК <i>ГОТОВ</i></div>
      <div class="chip c3">СВЕЖЕЕ МЯСО <i>+1</i></div>
    </div>
  </div>
</section>

<!-- бегущая строка -->
<div class="mq" aria-hidden="true">
  <div class="mq-track">
    <span>Свежее мясо</span><span>✕</span><span>Один крюк — одна жизнь</span><span>✕</span>
    <span>Аура решает</span><span>✕</span><span>Тяжело — значит твоё</span><span>✕</span>
    <span>100/100 массы</span><span>✕</span><span>Фон всегда размыт</span><span>✕</span>
    <span>Свежее мясо</span><span>✕</span><span>Один крюк — одна жизнь</span><span>✕</span>
    <span>Аура решает</span><span>✕</span><span>Тяжело — значит твоё</span><span>✕</span>
    <span>100/100 массы</span><span>✕</span><span>Фон всегда размыт</span><span>✕</span>
  </div>
</div>

<!-- ============ 01 МАНИФЕСТ / ПРИВЕТСТВИЕ ============ -->
<section id="welcome">
  <svg class="splat s1" viewBox="0 0 220 140"><use href="#i-splat"/></svg>
  <div class="container">
    <div class="sec-head rv">
      <span class="gnum">01</span>
      <div class="kick">Приветствие</div>
      <h2>Манифест <span class="red">мяса</span></h2>
      <span class="sec-sub">Позиционирование · Представление · Штат</span>
    </div>

    <div class="wel-grid">
      <div class="wel-txt rv">
        <div class="manq">«Я — гора мяса, крюка и <b>авторитета</b>. Меня не обходят — вокруг меня просто перестают ходить.»</div>
        <p>Двенадцать лет на полях Бесконечной Бойни. Двенадцать тысяч брошенных крюков. Ни одного извинения.</p>
        <p>Мой зал — <b>«Здание Мясника»</b> — это место, где из рыхлого крипа делают плоть, которую боятся банить.
        Здесь нет зеркал для селфи: зеркала нужны, чтобы видеть, кто отстал от графика.</p>
        <p>Я не мотивирую лозунгами. Я мотивирую <b>наведением</b>: крюк уже летит, осталось решить — ты на нём или рядом.</p>
      </div>

      <div class="pos-card rv" style="--d:.1s">
        <h3>Позиционирование</h3>
        <div class="pos-item">
          <svg viewBox="0 0 100 100"><use href="#i-flame"/></svg>
          <div><b>Аура</b><p>Вхожу в комнату — она темнеет и становится честнее.</p></div>
        </div>
        <div class="pos-item">
          <svg viewBox="0 0 100 100"><use href="#i-hook"/></svg>
          <div><b>Власть</b><p>Сначала крюк. Потом разговоры. Иногда — только крюк.</p></div>
        </div>
        <div class="pos-item">
          <svg viewBox="0 0 100 100"><use href="#i-kettle"/></svg>
          <div><b>Сила</b><p>100/100 массы. Остальные параметры — производные массы.</p></div>
        </div>
        <div class="pos-note"><b>Представление:</b> главный объект всегда в фокусе. Фон размывается сам собой — это не боке, это аура.</div>
      </div>
    </div>

    <div class="team rv">
      <div class="kick">Команда персонажа</div>
      <h3>Штат «Здания Мясника»</h3>
      <p class="team-sub">Четверо профессионалов, которые держат зал, дисциплину и твою мотивацию на крюке.</p>
      <div class="team-grid">
        <div class="tcard">
          <div class="tc-ico"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg></div>
          <div class="tc-role">Главный тренер · Владелец</div>
          <div class="tc-name">ПАДЖ</div>
          <p class="tc-quote">«Крюк не промахивается. Промахивается тот, кто дёргается.»</p>
          <div class="tc-stat">Стаж: 12 482 броска · Аура: +96</div>
        </div>
        <div class="tcard">
          <div class="tc-ico"><svg viewBox="0 0 100 100"><use href="#i-cleaver"/></svg></div>
          <div class="tc-role">Кардио-директор</div>
          <div class="tc-name">АКСА</div>
          <p class="tc-quote">«Жир сгорит сам. Или я помогу. Слово „не могу" вырезаю на первом занятии.»</p>
          <div class="tc-stat">Сушек проведено: 3 313 · Отказов: 0</div>
        </div>
        <div class="tcard">
          <div class="tc-ico"><svg viewBox="0 0 100 100"><use href="#i-dumb"/></svg></div>
          <div class="tc-role">Директор по прогрессии</div>
          <div class="tc-name">ОГРЕ-МАГИ</div>
          <p class="tc-quote">«Каждый подход — дважды. Всё остальное — тоже дважды. Мультикаст не терпит лени.»</p>
          <div class="tc-stat">Мультикаст: x2 · Подходов фактически: x2</div>
        </div>
        <div class="tcard">
          <div class="tc-ico"><svg viewBox="0 0 100 100"><use href="#i-heart"/></svg></div>
          <div class="tc-role">Реабилитация и восстановление</div>
          <div class="tc-name">ЛАЙФСТИЛЕР</div>
          <p class="tc-quote">«Ваши травмы — мой обед. Так что не травмируйтесь.»</p>
          <div class="tc-stat">Восстановление: 100% · Травмы считает завтраком</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ 02 ПРОГРАММЫ ============ -->
<section id="programs">
  <svg class="splat s2" viewBox="0 0 220 140"><use href="#i-splat"/></svg>
  <div class="container">
    <div class="sec-head rv">
      <span class="gnum">02</span>
      <div class="kick">Программы</div>
      <h2>Кузница <span class="red">туши</span></h2>
      <span class="sec-sub">Цель: масса · Цель: сушка · Цель: база</span>
    </div>

    <!-- ПРОГРАММА 01 -->
    <article class="prog rv">
      <div class="prog-meta">
        <div class="p-num">01</div>
        <h3>«Свежее мясо»</h3>
        <span class="p-goal">Цель: набор мышечной массы</span>
        <div class="chips">
          <span class="chip-s">12 недель</span><span class="chip-s">4 занятия / нед</span>
          <span class="chip-s">Инвентарь: крюк, цепь, якоря</span>
        </div>
        <div class="pain">Нагрузка <span class="dots"><i class="on"></i><i class="on"></i><i class="on"></i><i class="on"></i><i></i></span></div>
        <p class="p-quote">«Масса — это броня. Кую лично.»<em>— Падж, главный тренер</em></p>
      </div>
      <div>
        <div class="tbl-wrap">
          <table class="tbl">
            <thead><tr><th>Упражнение</th><th>Схема</th><th>Отдых</th><th>Примечание мясника</th></tr></thead>
            <tbody>
              <tr><td>Тяга крюка в себя</td><td class="sc">5×8</td><td>120 с</td><td>Старт с 25 метров; дотягивай до щелчка в лопатках</td></tr>
              <tr><td>Жим туши лёжа</td><td class="sc">4×10</td><td>90 с</td><td>Туша не должна двигаться — двигаешься ты</td></tr>
              <tr><td>Присед с цепью на плечах</td><td class="sc">5×6</td><td>150 с</td><td>Цепь тёплая — значит, хват не подводит</td></tr>
              <tr><td>Шраги с якорями</td><td class="sc">4×12</td><td>90 с</td><td>Плечи к ушам, как у крипа, увидевшего меня</td></tr>
              <tr><td>Подъём мяса на бицепс</td><td class="sc">3×12</td><td>60 с</td><td>Вес выбирается на кухне. Моими руками</td></tr>
            </tbody>
          </table>
        </div>
        <div class="p-note"><b>Питание</b>6 приёмов пищи. Мясо — 2 г на кг веса. Вода — пока не перестанешь быть мясом.</div>
      </div>
    </article>

    <!-- ПРОГРАММА 02 -->
    <article class="prog alt rv">
      <div class="prog-meta">
        <div class="p-num">02</div>
        <h3>«Сушка на крюке»</h3>
        <span class="p-goal">Цель: снижение жира</span>
        <div class="chips">
          <span class="chip-s">8 недель</span><span class="chip-s">5 занятий / нед</span>
          <span class="chip-s">Дефицит 20%</span>
        </div>
        <div class="pain">Нагрузка <span class="dots"><i class="on"></i><i class="on"></i><i class="on"></i><i class="on"></i><i class="on"></i></span></div>
        <p class="p-quote">«Жир горит. Или горишь ты. Выбирай до подхода.»<em>— Аксa, кардио-директор</em></p>
      </div>
      <div>
        <div class="tbl-wrap">
          <table class="tbl">
            <thead><tr><th>Упражнение</th><th>Схема</th><th>Отдых</th><th>Примечание мясника</th></tr></thead>
            <tbody>
              <tr><td>Круговая «Вокруг котла»</td><td class="sc">5 кругов</td><td>60 с</td><td>Котёл кипит — ты тоже</td></tr>
              <tr><td>Спринт «От Рошана»</td><td class="sc">8×30 с</td><td>30 с</td><td>Беги так, будто он тебя увидел</td></tr>
              <tr><td>Скалолазание по цепям</td><td class="sc">4×40 с</td><td>40 с</td><td>Вниз — только на моём крюке</td></tr>
              <tr><td>Планка «Мёртвая туша»</td><td class="sc">3×60 с</td><td>45 с</td><td>Туша не дрожит. Атлет — тем более</td></tr>
              <tr><td>Скакалка с якорем</td><td class="sc">3×100</td><td>60 с</td><td>Якорь не крутится — крутишься ты</td></tr>
            </tbody>
          </table>
        </div>
        <div class="p-note"><b>Питание</b>Дефицит 20%. Последний приём — за 3 часа до сна. Булки — нет. Булок нет.</div>
      </div>
    </article>

    <!-- ПРОГРАММА 03 -->
    <article class="prog rv">
      <div class="prog-meta">
        <div class="p-num">03</div>
        <h3>«Куй крюк»</h3>
        <span class="p-goal">Цель: общая физподготовка</span>
        <div class="chips">
          <span class="chip-s">Бессрочно</span><span class="chip-s">3 занятия / нед</span>
          <span class="chip-s">Уровень: с нуля</span>
        </div>
        <div class="pain">Нагрузка <span class="dots"><i class="on"></i><i class="on"></i><i class="on"></i><i></i><i></i></span></div>
        <p class="p-quote">«Сначала цепь. Потом слава. Иногда наоборот — но это не по программе.»<em>— Падж, главный тренер</em></p>
      </div>
      <div>
        <div class="tbl-wrap">
          <table class="tbl">
            <thead><tr><th>Упражнение</th><th>Схема</th><th>Отдых</th><th>Примечание мясника</th></tr></thead>
            <tbody>
              <tr><td>Висение на цепи</td><td class="sc">5×макс</td><td>90 с</td><td>Разжал пальцы — начинаешь заново</td></tr>
              <tr><td>Метание крюка в мишень</td><td class="sc">100 бросков</td><td>—</td><td>Точность важнее силы. Но и сила важна</td></tr>
              <tr><td>Блинк-отжимания</td><td class="sc">4×8</td><td>90 с</td><td>Взрыв вверх. Приземляйся мягко — тушу жалко</td></tr>
              <tr><td>Фермерская прогулка с якорями</td><td class="sc">4×40 м</td><td>120 с</td><td>Спина прямая, как приговор</td></tr>
              <tr><td>Переноска туши на плечах</td><td class="sc">3×20 м</td><td>90 с</td><td>Туша симулирует усталость. Не верь</td></tr>
            </tbody>
          </table>
        </div>
        <div class="p-note"><b>Питание</b>Без дефицита. Ешь как атлет: мясо, злость, дисциплина. Подходит новичкам — особенно тем, кто «просто зашёл посмотреть».</div>
      </div>
    </article>
  </div>
</section>

<!-- ============ 03 ПОЛИГОН ============ -->
<section id="polygon">
  <div class="container">
    <div class="sec-head rv">
      <span class="gnum">03</span>
      <div class="kick">Интерактив</div>
      <h2>Бросок <span class="red">крюка</span></h2>
      <span class="sec-sub">Клик по залу — крюк летит в точку. Поймай мясо — пополни счёт</span>
    </div>

    <div class="poly-grid rv">
      <div class="arena" id="arena" aria-label="Полигон: кликайте по залу, чтобы бросить крюк">
        <div class="hud"><span>Мясо: <b id="sCore">0</b></span><span>Промахи: <b id="sMiss">0</b></span><span>Точность: <b id="sAcc">—</b></span></div>
        <div class="launcher" id="launcher"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg></div>
        <div class="meat-track"><div class="meat"></div></div>
        <div class="meat-track"><div class="meat"></div></div>
        <div class="meat-track"><div class="meat"></div></div>
        <div class="meat-track"><div class="meat"></div></div>
        <div id="arenaChain"></div>
        <div id="arenaTip"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg></div>
        <div class="hint">Подсказка: мясо — валюта зала. Кликай, пока не поймал.</div>
      </div>

      <aside class="poly-side">
        <div class="ps-row"><span>Сырое мясо</span><b id="psCore">0</b></div>
        <div class="ps-row"><span>Промахи</span><b class="dim" id="psMiss">0</b></div>
        <div class="ps-row"><span>Точность</span><b class="dim" id="psAcc">—</b></div>
        <p><b>Регламент.</b> 100 кг мяса — уважение. 1 промах — анекдот на вечер. Крюк летит в точку клика и возвращается тем, что смог поймать.</p>
        <button class="btn ghost sm" id="resetPoly">Обнулить кормушку</button>
      </aside>
    </div>
  </div>
</section>

<!-- ============ 04 ДОСЬЕ ============ -->
<section id="dossier">
  <svg class="splat s1" viewBox="0 0 220 140" style="top:40px;bottom:auto;transform:rotate(-14deg)"><use href="#i-splat"/></svg>
  <div class="container">
    <div class="sec-head rv">
      <span class="gnum">04</span>
      <div class="kick">Профили</div>
      <h2>Досье <span class="red">мясника</span></h2>
      <span class="sec-sub">Профессиональный скилл · Моменты побед · Архив</span>
    </div>

    <div class="dos-top">
      <div class="rv" id="skillBars">
        <h3>Профиль скилла</h3>
        <div class="skill"><span>Сила хука</span><div class="bar"><i data-w="98"></i></div><b>98</b></div>
        <div class="skill"><span>Масса</span><div class="bar"><i data-w="100"></i></div><b>100</b></div>
        <div class="skill"><span>Аура страха</span><div class="bar"><i data-w="96"></i></div><b>96</b></div>
        <div class="skill"><span>Танковость</span><div class="bar"><i data-w="95"></i></div><b>95</b></div>
        <div class="skill"><span>Хват</span><div class="bar"><i data-w="93"></i></div><b>93</b></div>
        <div class="skill"><span>Харизма</span><div class="bar"><i data-w="91"></i></div><b>91</b></div>
        <div class="skill"><span>Скорость</span><div class="bar"><i data-w="28"></i></div><b>28</b></div>
        <p class="pos-line"><b>Позиции: 1–5.</b> Не покидаю позицию — это позиция покидает других. Скорость 28/100 и не нужна: всё ценное само приходит на крюк.</p>
      </div>

      <div class="cnt-grid rv" style="--d:.1s">
        <div class="cbox"><b class="num" data-to="12482">0</b><span>Крюков брошено</span></div>
        <div class="cbox"><b class="num" data-to="9941">0</b><span>Попаданий</span></div>
        <div class="cbox"><b class="num" data-to="1204">0</b><span>Казней</span></div>
        <div class="cbox"><b class="num" data-to="4812">0</b><span>Кг мяса собрано</span></div>
        <p class="dos-note"><b>Точность: 80%.</b> Статистика не врёт. Врут враги — обычно на середине полёта моего крюка.</p>
      </div>
    </div>

    <div class="wins rv">
      <h3>Моменты побед</h3>
      <div class="wins-grid">
        <div class="win"><span class="yr">2013</span><h4>Первый крюк</h4><p>Дебют на полях бойни: вытащил вражеского мидера прямо в пятёрку союзников. От броска до казни — 0,4 секунды. Судьи не успели моргнуть.</p></div>
        <div class="win"><span class="yr">2015</span><h4>Хук через карту</h4><p>82 метра. Сквозь туман войны и три стены здравого смысла. Триплкилл, стадион встал — и сел обратно, потому что матч ещё не кончился.</p></div>
        <div class="win"><span class="yr">2019</span><h4>Соло-казнь</h4><p>Один против пяти при 12% здоровья. Ушёл с полным инвентарём чужих артефактов и лёгкой походкой человека, который ничего не должен.</p></div>
        <div class="win"><span class="yr">2023</span><h4>Аркана</h4><p>Вышла аркана — и тёмно-красный стал официальным цветом страха. С тех пор расцветка сайта не обсуждается. Она утверждена крюком.</p></div>
      </div>
    </div>

    <div class="rv">
      <div class="wins"><h3>Фотоархив</h3></div>
      <div class="ph-grid">
        <figure class="ph bw">
          <svg class="scene" viewBox="0 0 640 440" preserveAspectRatio="xMidYMid slice" aria-label="Чёрно-белый портрет"><use href="#pudgeScene"/></svg>
          <span class="tagc">Ч/Б · Контраст 100%</span>
          <svg class="ph-ico" viewBox="0 0 100 100"><use href="#i-hook"/></svg>
          <figcaption><h4>Портрет мясника</h4><p>Свет падает только на меня. Остальное — тьма и чужие очки здоровья.</p></figcaption>
        </figure>
        <figure class="ph col">
          <svg class="scene" viewBox="0 0 640 440" preserveAspectRatio="xMidYMid slice" aria-label="Цветное фото победы"><use href="#pudgeScene"/></svg>
          <span class="tagc">Цвет · Фон размыт</span>
          <svg class="ph-ico" viewBox="0 0 100 100"><use href="#i-trophy"/></svg>
          <figcaption><h4>Победа</h4><p>Фон размыт не боке — просто больше некому быть в фокусе.</p></figcaption>
        </figure>
        <figure class="ph cine">
          <svg class="scene" viewBox="0 0 640 440" preserveAspectRatio="xMidYMid slice" aria-label="Исполнение в игре"><use href="#pudgeScene"/></svg>
          <span class="tagc">Ин-гейм · 0,4 сек</span>
          <svg class="ph-ico" viewBox="0 0 100 100"><use href="#i-skull"/></svg>
          <figcaption><h4>Казнь</h4><p>Крюк летит 0,4 секунды. Казнь — 0,2. Камера не успевает.</p></figcaption>
        </figure>
      </div>
    </div>
  </div>
</section>

<!-- ============ CTA ============ -->
<section id="cta">
  <div class="container">
    <div class="cta-box rv">
      <h2>Первый визит — бесплатно. Второй — по крюку.</h2>
      <p>Запись открывается броском: поймай мясо на полигоне — и администратор (это я) всё поймёт без слов.</p>
      <div class="cta-btns">
        <a class="btn" href="#polygon"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg>Начать с крюка</a>
        <a class="btn ghost" href="#programs">Сначала программы</a>
      </div>
    </div>
  </div>
</section>
</main>

<!-- ============ ПОДВАЛ ============ -->
<footer id="contact">
  <div class="container">
    <div class="ft-grid">
      <div>
        <div class="ft-logo"><svg viewBox="0 0 100 100"><use href="#i-hook"/></svg><span>PUDGE · OFFICIAL</span></div>
        <p>Официальный фан-сайт персонажа Pudge. Не аффилирован с Valve. Dota 2 и Pudge — торговые марки Valve Corporation. Все казни осуществлены строго в игровых целях.</p>
      </div>
      <div>
        <h4>Зал</h4>
        <p>Поля Бесконечной Бойни, цех №13<br>
        Часы работы: от заката до последнего крипа<br>
        Связь: крюком в окно — услышим</p>
      </div>
      <div>
        <h4>Каналы</h4>
        <ul>
          <li><a href="#top">Telegram — «Свежее мясо»</a></li>
          <li><a href="#top">Twitch — HOOKLIVE</a></li>
          <li><a href="#top">Discord — «Кафедра»</a></li>
        </ul>
      </div>
    </div>
    <div class="ft-bottom">
      <span>© <span id="y"></span> ЗДАНИЕ МЯСНИКА. Все права защищены крюком.</span>
      <span>Свет — на главном объекте. Фон — размыт. Дисциплина — на месте.</span>
    </div>
  </div>
</footer>

<script>
(function(){
'use strict';
const $=(s,c)=> (c||document).querySelector(s);
const $$=(s,c)=> Array.prototype.slice.call((c||document).querySelectorAll(s));

/* год в подвале */
 $('#y').textContent=new Date().getFullYear();

/* мобильное меню */
const nav=$('#mainNav'), burger=$('#burger');
burger.addEventListener('click',()=>{nav.classList.toggle('open');burger.classList.toggle('act');});
 $$('#mainNav a').forEach(a=>a.addEventListener('click',()=>{nav.classList.remove('open');burger.classList.remove('act');}));

/* появление при скролле */
const io=new IntersectionObserver(es=>es.forEach(e=>{
  if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target);}
}),{threshold:.14});
 $$('.rv').forEach(el=>io.observe(el));

/* счётчики */
const fmt=n=>Math.round(n).toLocaleString('ru-RU');
const ioN=new IntersectionObserver(es=>es.forEach(e=>{
  if(!e.isIntersecting)return;
  const el=e.target; ioN.unobserve(el);
  const to=+el.dataset.to, t0=performance.now(), D=1400;
  (function tick(now){
    const k=Math.min((now-t0)/D,1), v=to*(1-Math.pow(1-k,3));
    el.textContent=fmt(v);
    if(k<1)requestAnimationFrame(tick);
  })(t0);
}),{threshold:.5});
 $$('.num[data-to]').forEach(el=>ioN.observe(el));

/* полоски скилла */
const sk=$('#skillBars');
if(sk){
  const ioB=new IntersectionObserver(es=>es.forEach(e=>{
    if(!e.isIntersecting)return; ioB.unobserve(e.target);
    $$('.bar i',e.target).forEach(b=>b.style.width=b.dataset.w+'%');
  }),{threshold:.35});
  ioB.observe(sk);
}

/* подсветка активного раздела */
const spy=new IntersectionObserver(es=>es.forEach(e=>{
  if(e.isIntersecting){
    $$('#mainNav a').forEach(a=>a.classList.toggle('act', a.getAttribute('href')==='#'+e.target.id));
  }
}),{rootMargin:'-45% 0px -50% 0px'});
 $$('main section[id]').forEach(s=>spy.observe(s));

/* искры-аура в герое */
const em=$('#heroEmbers');
if(em && !matchMedia('(prefers-reduced-motion: reduce)').matches){
  for(let i=0;i<26;i++){
    const s=document.createElement('i'); s.className='ember';
    s.style.left=(Math.random()*100)+'%';
    s.style.width=s.style.height=(2+Math.random()*2.5)+'px';
    s.style.animationDuration=(6+Math.random()*9)+'s';
    s.style.animationDelay=(-Math.random()*12)+'s';
    em.appendChild(s);
  }
}

/* звук (короткие удары через WebAudio) */
let AC=null;
function tone(f0,f1,d,type,v){
  try{
    AC=AC||new (window.AudioContext||window.webkitAudioContext)();
    if(AC.state==='suspended')AC.resume();
    const o=AC.createOscillator(),g=AC.createGain(),t=AC.currentTime;
    o.type=type; o.frequency.setValueAtTime(f0,t);
    o.frequency.exponentialRampToValueAtTime(Math.max(f1,1),t+d);
    g.gain.setValueAtTime(v,t); g.gain.exponentialRampToValueAtTime(.0001,t+d);
    o.connect(g); g.connect(AC.destination); o.start(t); o.stop(t+d);
  }catch(err){}
}

/* ============ ПОЛИГОН: бросок крюка ============ */
const arena=$('#arena'), chainEl=$('#arenaChain'), tipEl=$('#arenaTip'), launcher=$('#launcher');
const sCore=$('#sCore'), sMiss=$('#sMiss'), sAcc=$('#sAcc');
const psCore=$('#psCore'), psMiss=$('#psMiss'), psAcc=$('#psAcc');
const meats=$$('#arena .meat-track');
let score=0, miss=0, busy=false;

function updAcc(){const t=score+miss; const v=t?Math.round(score/t*100)+'%':'—'; sAcc.textContent=v; psAcc.textContent=v;}
const rand=(a,b)=>a+Math.random()*(b-a);

function posTrack(el){
  const W=arena.clientWidth, H=arena.clientHeight;
  el.style.left=rand(Math.min(130,W*.25), W-76)+'px';
  el.style.top=rand(18,H-76)+'px';
  el.style.setProperty('--dd',rand(5,10).toFixed(2)+'s');
  el.style.animationDelay=(-rand(0,8)).toFixed(2)+'s';
  const m=el.querySelector('.meat');
  if(m)m.style.animationDelay=(-rand(0,3)).toFixed(2)+'s';
}
function posAll(){meats.forEach(posTrack);}

function splash(x,y){
  const d=document.createElement('div'); d.className='splash';
  d.style.left=x+'px'; d.style.top=y+'px';
  d.innerHTML='<svg viewBox="0 0 220 140"><use href="#i-splat"/></svg>';
  arena.appendChild(d);
  d.addEventListener('animationend',()=>d.remove());
}
function floatText(t,x,y,col){
  const d=document.createElement('div'); d.className='ftext';
  d.style.left=x+'px'; d.style.top=y+'px'; d.style.color=col||'var(--red-b)';
  d.textContent=t; arena.appendChild(d);
  d.addEventListener('animationend',()=>d.remove());
}
function origin(){
  const l=launcher.getBoundingClientRect(), a=arena.getBoundingClientRect();
  return {x:l.right-a.left-10, y:l.top+l.height/2-a.top};
}

function throwHook(tx,ty){
  busy=true; chainEl.style.display='block'; tipEl.style.display='block';
  const o=origin(), dx=tx-o.x, dy=ty-o.y;
  const dist=Math.hypot(dx,dy), ang=Math.atan2(dy,dx);
  chainEl.style.left=o.x+'px'; chainEl.style.top=o.y+'px';
  const T1=300,T2=70,T3=420,TOT=T1+T2+T3, t0=performance.now();
  let struck=false, caught=null;
  tone(190,55,.16,'sawtooth',.05);
  function fr(now){
    const t=now-t0; let p;
    if(t<=T1){const k=t/T1; p=1-Math.pow(1-k,3);}
    else if(t<=T1+T2){p=1;}
    else{const k=Math.min((t-T1-T2)/T3,1); p=1-k*k;}
    const hx=o.x+dx*p, hy=o.y+dy*p;
    chainEl.style.width=Math.max(dist*p,2)+'px';
    chainEl.style.transform='translateY(-50%) rotate('+ang+'rad)';
    tipEl.style.left=hx+'px'; tipEl.style.top=hy+'px';
    tipEl.style.transform='translate(-50%,-50%) rotate('+(ang-Math.PI/2+.4)+'rad)';
    if(!struck && p>=1){
      struck=true;
      const ar=arena.getBoundingClientRect(); let best=null, bd=1e9;
      meats.forEach(m=>{
        if(m.dataset.c)return;
        const mr=m.getBoundingClientRect();
        const cx=mr.left+mr.width/2-ar.left, cy=mr.top+mr.height/2-ar.top;
        const dd=Math.hypot(cx-tx,cy-ty);
        if(dd<54 && dd<bd){bd=dd; best=m;}
      });
      if(best){
        best.dataset.c='1'; caught=best;
        score++; sCore.textContent=score; psCore.textContent=score;
        splash(tx,ty); floatText('+1 СВЕЖЕЕ МЯСО',tx,ty);
        tone(95,38,.24,'square',.08); tone(320,140,.09,'triangle',.05);
      }else{
        miss++; sMiss.textContent=miss; psMiss.textContent=miss;
        floatText('МИМО',tx,ty,'#7c6b66');
        tone(140,60,.12,'triangle',.035);
      }
      updAcc();
    }
    if(caught){caught.style.left=(hx-24)+'px'; caught.style.top=(hy-22)+'px';}
    if(t<TOT){requestAnimationFrame(fr);}
    else{
      chainEl.style.display='none'; tipEl.style.display='none';
      if(caught){
        const el=caught; delete el.dataset.c;
        el.style.opacity='0';
        setTimeout(()=>{posTrack(el); el.style.opacity='1';},420);
      }
      busy=false;
    }
  }
  requestAnimationFrame(fr);
}

if(arena){
  posAll();
  let rt; window.addEventListener('resize',()=>{clearTimeout(rt); rt=setTimeout(posAll,200);});
  arena.addEventListener('pointerdown',e=>{
    if(busy)return;
    const r=arena.getBoundingClientRect();
    const x=Math.max(Math.min(e.clientX-r.left, arena.clientWidth-12), 90);
    const y=Math.max(Math.min(e.clientY-r.top, arena.clientHeight-12), 12);
    throwHook(x,y);
  });
  const rb=$('#resetPoly');
  if(rb)rb.addEventListener('click',()=>{
    if(busy)return;
    score=0; miss=0;
    sCore.textContent='0'; sMiss.textContent='0';
    psCore.textContent='0'; psMiss.textContent='0';
    updAcc(); posAll();
  });
}
})();
</script>
</body>
</html>
