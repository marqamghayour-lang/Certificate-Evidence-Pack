<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Muhammad Arqam Ghayour — Make-Up Hour Submission Log</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Fira+Code:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --indigo:#6366f1;--sky:#0ea5e9;--amber:#f59e0b;--red:#ef4444;
  --violet:#8b5cf6;--pink:#ec4899;--teal:#14b8a6;--green:#22c55e;
  --bg:#07080f;--surface:#0d0f1e;--surface2:#131627;
  --text:#e2e8f0;--muted:#64748b;--sub:#94a3b8;
}
html{scroll-behavior:smooth}
body{font-family:'Inter',system-ui,sans-serif;background:var(--bg);color:var(--text);line-height:1.65;overflow-x:hidden;min-height:100vh}

/* CANVAS */
#bg-canvas{position:fixed;inset:0;width:100%;height:100%;pointer-events:none;z-index:0;opacity:.55}

/* LAYOUT */
.wrap{position:relative;z-index:1;max-width:960px;margin:0 auto;padding:0 28px 80px}

/* KEYFRAMES */
@keyframes gradientShift{0%,100%{background-position:0% 50%}50%{background-position:100% 50%}}
@keyframes textShimmer{0%{background-position:0% center}100%{background-position:200% center}}
@keyframes blinkCursor{0%,100%{opacity:1}50%{opacity:0}}
@keyframes pulseBadge{0%,100%{transform:scale(1)}50%{transform:scale(1.07)}}
@keyframes scanDown{0%{top:-4px;opacity:0}5%{opacity:1}95%{opacity:.8}100%{top:100vh;opacity:0}}
@keyframes lineGrow{from{width:0}to{width:56px}}
@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}
@keyframes glow-indigo{0%,100%{box-shadow:0 0 8px #6366f150,0 0 24px #6366f130}50%{box-shadow:0 0 22px #6366f1,0 0 44px #6366f180,0 0 66px #6366f140}}
@keyframes glow-sky   {0%,100%{box-shadow:0 0 8px #0ea5e950,0 0 24px #0ea5e930}50%{box-shadow:0 0 22px #0ea5e9,0 0 44px #0ea5e980}}
@keyframes glow-amber {0%,100%{box-shadow:0 0 8px #f59e0b50,0 0 24px #f59e0b30}50%{box-shadow:0 0 22px #f59e0b,0 0 44px #f59e0b80}}
@keyframes glow-red   {0%,100%{box-shadow:0 0 8px #ef444450,0 0 24px #ef444430}50%{box-shadow:0 0 22px #ef4444,0 0 44px #ef444480}}
@keyframes glow-violet{0%,100%{box-shadow:0 0 8px #8b5cf650,0 0 24px #8b5cf630}50%{box-shadow:0 0 22px #8b5cf6,0 0 44px #8b5cf680}}
@keyframes glow-pink  {0%,100%{box-shadow:0 0 8px #ec489950,0 0 24px #ec489930}50%{box-shadow:0 0 22px #ec4899,0 0 44px #ec489980}}
@keyframes glow-teal  {0%,100%{box-shadow:0 0 8px #14b8a650,0 0 24px #14b8a630}50%{box-shadow:0 0 22px #14b8a6,0 0 44px #14b8a680}}

/* SCANLINE */
.scanline{position:fixed;left:0;right:0;height:3px;background:linear-gradient(90deg,transparent,rgba(99,102,241,.6),rgba(14,165,233,.5),transparent);pointer-events:none;z-index:9999;animation:scanDown 9s ease-in-out infinite}

/* HERO */
.hero{position:relative;text-align:center;padding:80px 20px 56px;overflow:hidden}
.hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 50% 0%,rgba(99,102,241,.18) 0%,transparent 65%),radial-gradient(ellipse at 0% 100%,rgba(14,165,233,.1) 0%,transparent 55%),radial-gradient(ellipse at 100% 100%,rgba(139,92,246,.1) 0%,transparent 55%);pointer-events:none}
.hero-tag{display:inline-block;font-family:'Fira Code',monospace;font-size:.72em;font-weight:600;color:var(--indigo);background:rgba(99,102,241,.1);border:1px solid rgba(99,102,241,.35);border-radius:999px;padding:4px 16px;margin-bottom:22px;letter-spacing:1.5px;text-transform:uppercase}
h1.hero-name{font-size:clamp(2em,5vw,3.4em);font-weight:900;letter-spacing:-1px;background:linear-gradient(135deg,#a5b4fc 0%,#60a5fa 28%,#5eead4 55%,#c084fc 80%,#f9a8d4 100%);background-size:200% auto;-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;animation:textShimmer 5s linear infinite;line-height:1.15;margin-bottom:12px}
.hero-sub{font-size:1em;color:var(--sub);margin-bottom:26px}
.typing-line{font-family:'Fira Code',monospace;font-size:.9em;color:var(--sky);height:1.6em;display:flex;align-items:center;justify-content:center;gap:3px;margin-bottom:34px}
.cursor{display:inline-block;width:2px;height:1.1em;background:var(--sky);border-radius:1px;animation:blinkCursor .75s step-end infinite}
.badges{display:flex;flex-wrap:wrap;gap:10px;justify-content:center}
.badge{display:inline-flex;align-items:center;gap:8px;font-size:.78em;font-weight:700;padding:6px 15px;border-radius:9px;border:1px solid;letter-spacing:.2px}
.badge .dot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.b-id {background:rgba(99,102,241,.12);border-color:rgba(99,102,241,.4);color:#a5b4fc} .b-id .dot{background:var(--indigo)}
.b-sec{background:rgba(14,165,233,.12);border-color:rgba(14,165,233,.4);color:#7dd3fc}.b-sec .dot{background:var(--sky)}
.b-hr {background:rgba(34,197,94,.12); border-color:rgba(34,197,94,.4); color:#86efac}.b-hr  .dot{background:var(--green)}
.b-del{background:rgba(245,158,11,.12);border-color:rgba(245,158,11,.4);color:#fcd34d;animation:pulseBadge 2s ease-in-out infinite}.b-del .dot{background:var(--amber)}

/* DIVIDERS */
.divider{height:1px;background:linear-gradient(90deg,transparent,rgba(99,102,241,.45),rgba(14,165,233,.45),rgba(20,184,166,.45),transparent);margin:44px 0}

/* SECTION TITLES */
h2.sec-title{font-size:1.45em;font-weight:800;color:var(--text);margin-bottom:22px;padding-bottom:13px;border-bottom:2px solid var(--surface2);position:relative}
h2.sec-title::after{content:'';position:absolute;left:0;bottom:-2px;height:2px;width:0;background:linear-gradient(90deg,var(--indigo),var(--sky));border-radius:1px;animation:lineGrow .9s .2s ease forwards}

/* REFERENCE TABLE */
.ref-wrap{overflow-x:auto}
table.ref{width:100%;border-collapse:collapse;font-size:.83em;white-space:nowrap}
table.ref thead tr{background:var(--surface2)}
table.ref th{padding:10px 13px;text-align:left;font-weight:700;font-size:.76em;text-transform:uppercase;letter-spacing:.6px;color:var(--sub);border-bottom:1px solid rgba(255,255,255,.06)}
table.ref td{padding:10px 13px;border-bottom:1px solid rgba(255,255,255,.04);color:var(--text);vertical-align:middle}
table.ref tbody tr{transition:background .2s}
table.ref tbody tr:hover{background:rgba(99,102,241,.07)}
table.ref a{color:var(--sky);text-decoration:none;font-weight:600}
table.ref a:hover{text-decoration:underline}
.num{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;font-size:.73em;font-weight:800;color:#fff}
.st{display:inline-flex;align-items:center;gap:6px;font-weight:700;color:#86efac;font-size:.88em}
.st::before{content:'';width:6px;height:6px;border-radius:50%;background:var(--green);box-shadow:0 0 7px var(--green);flex-shrink:0;animation:pulseBadge 2s ease-in-out infinite}

/* WEEK HEADERS */
.wk-bar{padding:20px 26px;border-radius:14px;margin:40px 0 26px;border:1px solid}
.wk-lbl{font-family:'Fira Code',monospace;font-size:.7em;font-weight:700;letter-spacing:2px;text-transform:uppercase;opacity:.75;margin-bottom:5px}
.wk-bar h2{font-size:1.5em;font-weight:800;margin:0 0 5px;color:inherit}
.wk-bar .wk-sub{font-size:.81em;opacity:.65}
.w5{background:linear-gradient(135deg,rgba(99,102,241,.13),rgba(14,165,233,.07));border-color:rgba(99,102,241,.3);color:#a5b4fc}
.w6{background:linear-gradient(135deg,rgba(20,184,166,.13),rgba(139,92,246,.07));border-color:rgba(20,184,166,.3);color:#5eead4}

/* SPRINT CARDS */
.card{position:relative;background:var(--surface);border-radius:14px;padding:26px;margin-bottom:22px;border:1px solid rgba(255,255,255,.07);overflow:hidden;opacity:0;transform:translateY(20px);transition:transform .3s ease,box-shadow .3s ease}
.card.vis{opacity:1;transform:translateY(0)}
.card:hover{transform:translateY(-4px)}
.card::before{content:'';position:absolute;top:0;left:0;right:0;height:2.5px;background:var(--cc);filter:brightness(1.3)}
.c-indigo{--cc:var(--indigo);border-color:rgba(99,102,241,.22);animation:glow-indigo 4s ease-in-out infinite}
.c-sky    {--cc:var(--sky);   border-color:rgba(14,165,233,.22); animation:glow-sky    4s ease-in-out infinite}
.c-amber  {--cc:var(--amber); border-color:rgba(245,158,11,.22); animation:glow-amber  4s ease-in-out infinite}
.c-red    {--cc:var(--red);   border-color:rgba(239,68,68,.22);  animation:glow-red    4s ease-in-out infinite}
.c-violet {--cc:var(--violet);border-color:rgba(139,92,246,.22); animation:glow-violet 4s ease-in-out infinite}
.c-pink   {--cc:var(--pink);  border-color:rgba(236,72,153,.22); animation:glow-pink   4s ease-in-out infinite}
.c-teal   {--cc:var(--teal);  border-color:rgba(20,184,166,.22); animation:glow-teal   4s ease-in-out infinite}

/* CARD INTERNALS */
.ctop{display:flex;align-items:center;flex-wrap:wrap;gap:8px;margin-bottom:14px}
.mod-tag{font-family:'Fira Code',monospace;font-size:.68em;font-weight:700;padding:3px 10px;border-radius:7px;letter-spacing:.4px;text-transform:uppercase;border:1px solid}
.hrs-tag{font-size:.7em;font-weight:700;color:#93c5fd;background:rgba(14,165,233,.1);border:1px solid rgba(14,165,233,.3);border-radius:7px;padding:3px 10px}
.del-tag{font-size:.68em;font-weight:800;color:#86efac;background:rgba(34,197,94,.1);border:1px solid rgba(34,197,94,.35);border-radius:7px;padding:3px 10px;letter-spacing:.4px;text-transform:uppercase;animation:pulseBadge 2.5s ease-in-out infinite}
.sub-tag{font-size:.68em;color:var(--muted);margin-left:auto}

h3.ctitle{font-size:1.12em;font-weight:800;color:var(--text);margin-bottom:18px;line-height:1.3}

.igrid{display:grid;grid-template-columns:116px 1fr;gap:8px 16px;font-size:.83em;margin-bottom:16px}
.ilbl{font-weight:700;font-size:.74em;text-transform:uppercase;letter-spacing:.5px;color:var(--muted);align-self:start;padding-top:1px}
.ival{color:var(--sub)}
.ival a{color:var(--sky);text-decoration:none;font-weight:600}
.ival a:hover{text-decoration:underline}

.cdiv{height:1px;background:rgba(255,255,255,.05);margin:14px 0}

.cbox{background:rgba(255,255,255,.025);border-radius:9px;padding:15px 17px;border-left:2.5px solid var(--cc)}
.clbl{font-size:.7em;font-weight:800;text-transform:uppercase;letter-spacing:.8px;color:var(--muted);margin-bottom:8px}
.ctxt{font-size:.86em;color:#cbd5e1;line-height:1.78}
.ai-note{margin-top:11px;font-size:.77em;color:#475569;font-style:italic;display:flex;align-items:flex-start;gap:7px}
.ai-note::before{content:'AI';font-style:normal;font-size:.75em;font-weight:800;font-family:'Fira Code',monospace;color:#8b5cf6;background:rgba(139,92,246,.1);border:1px solid rgba(139,92,246,.35);padding:1px 6px;border-radius:4px;flex-shrink:0}

/* SUMMARY STATS */
.stat-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:16px;margin-bottom:28px}
.stat{background:var(--surface);border-radius:13px;padding:22px 16px;text-align:center;border:1px solid rgba(255,255,255,.06);position:relative;overflow:hidden}
.stat::before{content:'';position:absolute;top:0;left:0;right:0;height:2.5px;background:var(--acc)}
.stat-n{font-size:2.5em;font-weight:900;line-height:1;margin-bottom:7px}
.stat-l{font-size:.75em;color:var(--muted);font-weight:600;text-transform:uppercase;letter-spacing:.5px}

/* SUMMARY TABLE */
table.sum{width:100%;border-collapse:collapse;font-size:.87em}
table.sum th{background:var(--surface2);padding:10px 14px;text-align:left;font-size:.76em;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--sub);border-bottom:1px solid rgba(255,255,255,.06)}
table.sum td{padding:12px 14px;border-bottom:1px solid rgba(255,255,255,.04);color:var(--text)}
table.sum tr:hover td{background:rgba(99,102,241,.05)}
table.sum tfoot td{font-weight:800;border-top:1px solid rgba(255,255,255,.1);border-bottom:none}

/* INTEGRITY */
.integrity{margin-top:26px;padding:16px 22px;border-radius:11px;background:linear-gradient(135deg,rgba(34,197,94,.08),rgba(20,184,166,.06));border:1px solid rgba(34,197,94,.25);text-align:center;font-size:.84em;font-weight:600;color:#86efac;animation:glow-teal 5s ease-in-out infinite}

/* FOOTER */
footer{text-align:center;padding:40px 20px 60px;position:relative;z-index:1}
.fbar{height:3px;background:linear-gradient(90deg,var(--indigo),var(--sky),var(--teal),var(--violet),var(--pink),var(--amber));background-size:300% 100%;animation:gradientShift 5s linear infinite;border-radius:2px;margin-bottom:22px}
footer p{font-size:.79em;color:var(--muted)}
</style>
</head>
<body>

<div class="scanline"></div>
<canvas id="bg-canvas"></canvas>

<div class="wrap">

<!-- ══════════════════════════════════════ HERO ══════════════════════════════════════ -->
<header class="hero">
  <div class="hero-tag">YouthxAI &nbsp;·&nbsp; Verified Make-Up Hours &nbsp;·&nbsp; 2026</div>
  <h1 class="hero-name">Muhammad Arqam Ghayour</h1>
  <p class="hero-sub">Make-Up Hour Submission Log &nbsp;·&nbsp; Platform &amp; Web Engineering</p>
  <div class="typing-line">
    <span id="typer"></span><span class="cursor"></span>
  </div>
  <div class="badges">
    <span class="badge b-id"><span class="dot"></span>25I-0006</span>
    <span class="badge b-sec"><span class="dot"></span>Section AI-C</span>
    <span class="badge b-hr"><span class="dot"></span>26 Hours Claimed</span>
    <span class="badge b-del"><span class="dot"></span>7 / 7 Delivered</span>
  </div>
</header>

<div class="divider"></div>

<!-- ══════════════════════════════════ QUICK REF ══════════════════════════════════ -->
<section>
  <h2 class="sec-title">Quick Reference</h2>
  <div class="ref-wrap">
  <table class="ref">
    <thead>
      <tr><th>#</th><th>Sprint</th><th>Date</th><th>Time (PKT)</th><th>Hrs</th><th>Status</th><th>Artifact</th><th>Proof</th></tr>
    </thead>
    <tbody>
      <tr>
        <td><span class="num" style="background:#6366f1">1</span></td>
        <td>Sprint 1: Verified Work Plan</td><td>20 Jul 2026</td><td>10:00 AM – 3:40 PM</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#0ea5e9">2</span></td>
        <td>Sprint 2: Research &amp; Source Log</td><td>23 Jul 2026</td><td>4:00 AM – 8:15 AM</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://github.com/marqamghayour-lang/Research-Source-Log">GitHub</a></td>
        <td><a href="https://drive.google.com/drive/folders/1QXIJXaLfByRDvDSf21UUr5Y2JjWZ1LzO?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#f59e0b">3</span></td>
        <td>Sprint 3: Build Evidence</td><td>22–23 Jul 2026</td><td>Multi-session</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#ef4444">4</span></td>
        <td>Sprint 4: Review &amp; Revision</td><td>1 Aug 2026</td><td>10:00 PM – 2:10 AM</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#8b5cf6">5</span></td>
        <td>Sprint 5: Final Artifact Improvement</td><td>31 Jul 2026</td><td>10:00 AM – 3:40 PM</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#ec4899">6</span></td>
        <td>Iris Hacks IV: Applications of AI</td><td>1 Aug 2026</td><td>Form submitted 10:00 PM</td><td>2h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Drive</a></td>
      </tr>
      <tr>
        <td><span class="num" style="background:#14b8a6">7</span></td>
        <td>Sprint 6: Public Write-up / Walkthrough</td><td>31 Jul 2026</td><td>10:00 AM – 2:00 PM</td><td>4h</td>
        <td><span class="st">Delivered</span></td>
        <td><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Drive</a></td>
        <td><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Drive</a></td>
      </tr>
    </tbody>
  </table>
  </div>
</section>

<div class="divider"></div>

<!-- ══════════════════════════════════ WEEK 5 ══════════════════════════════════ -->
<section>
  <div class="wk-bar w5">
    <div class="wk-lbl">Week 5</div>
    <h2>Strict Evidence &amp; Process Logs</h2>
    <div class="wk-sub">20 Jul – 26 Jul 2026 &nbsp;·&nbsp; Verified Make-up Hours</div>
  </div>

  <!-- Sprint 1 -->
  <div class="card c-indigo">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(99,102,241,.14);color:#a5b4fc;border-color:rgba(99,102,241,.4)">W5D1</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 25 Jul 2026, 09:51 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 1 — Extension Sprint 1: Verified Work Plan</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>      <span class="ival">Monday, 20 July 2026</span>
      <span class="ilbl">Start</span>     <span class="ival">10:00 AM PKT</span>
      <span class="ilbl">End</span>       <span class="ival">3:40 PM PKT</span>
      <span class="ilbl">Artifact</span>  <span class="ival"><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Google Drive — Kaggle Pandas Certificate</a></span>
      <span class="ilbl">Proof</span>    <span class="ival"><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Google Drive — Certificate File</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Completed the Pandas course on Kaggle. Pandas accounted for 70–80% of all code written during YouthxAI sessions for training AI models. Completing this course solidified understanding of data management and its role in ML pipelines. The Kaggle course certificate is the proof artifact.</p>
      <div class="ai-note">Used AI to understand concepts not well covered by the course.</div>
    </div>
  </div>

  <!-- Sprint 2 -->
  <div class="card c-sky">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(14,165,233,.14);color:#7dd3fc;border-color:rgba(14,165,233,.4)">W5D2</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 25 Jul 2026, 11:04 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 2 — Extension Sprint 2: Research &amp; Source Log</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>       <span class="ival">Thursday, 23 July 2026</span>
      <span class="ilbl">Start</span>      <span class="ival">4:00 AM PKT</span>
      <span class="ilbl">End</span>        <span class="ival">8:15 AM PKT</span>
      <span class="ilbl">Artifact</span>   <span class="ival"><a href="https://github.com/marqamghayour-lang/Research-Source-Log">GitHub — Research-Source-Log Repository</a></span>
      <span class="ilbl">Proof</span>     <span class="ival"><a href="https://drive.google.com/drive/folders/1QXIJXaLfByRDvDSf21UUr5Y2JjWZ1LzO?usp=sharing">Google Drive — Evidence Folder</a></span>
      <span class="ilbl">Process Log</span><span class="ival"><a href="https://github.com/marqamghayour-lang/Research-Source-Log/commits/main/">GitHub — Commit History</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Conducted research on NeRF (Neural Radiance Fields) 3D Reconstruction. Sources gathered from Google Scholar, filtered for credibility, read at surface level, and rewritten in own words. AI corrected grammar and formatting. Final research was reviewed, all errors fixed, and published to the GitHub repository. This directly supports ongoing NeRF-based heritage documentation work at PMW.</p>
      <div class="ai-note">Identified the most authentic sources and rectified the writing of the research report.</div>
    </div>
  </div>

  <!-- Sprint 3 -->
  <div class="card c-amber">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(245,158,11,.14);color:#fcd34d;border-color:rgba(245,158,11,.4)">W5D3</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 25 Jul 2026, 11:23 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 3 — Extension Sprint 3: Build Evidence</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>     <span class="ival">Wednesday – Thursday, 22–23 July 2026</span>
      <span class="ilbl">Session</span>  <span class="ival">Multi-session across both days (~6–7 hrs total)</span>
      <span class="ilbl">Artifact</span> <span class="ival"><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Google Drive — MLP from Scratch Evidence Folder</a></span>
      <span class="ilbl">Proof</span>   <span class="ival"><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Google Drive — Same Evidence Folder</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Trained an MLP (Neural Network) on the MNIST dataset (60,000 handwritten digit images) from scratch — zero ML libraries. Every component manually implemented: forward propagation, cross-entropy loss calculations, backpropagation, gradient descent optimization, and epoch management. The model correctly classifies handwritten digits. This extends the YouthxAI Neural Network task — that version used libraries; this one exposes all the internals those libraries abstract away.</p>
      <div class="ai-note">Used to revise the theoretical backend of model training.</div>
    </div>
  </div>

  <!-- Sprint 4 -->
  <div class="card c-red">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(239,68,68,.14);color:#fca5a5;border-color:rgba(239,68,68,.4)">W5D4</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 1 Aug 2026, 18:30 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 4 — Extension Sprint 4: Review &amp; Revision</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>     <span class="ival">Saturday, 1 August 2026 (overnight session)</span>
      <span class="ilbl">Start</span>    <span class="ival">10:00 PM PKT</span>
      <span class="ilbl">End</span>      <span class="ival">2:10 AM PKT (next day)</span>
      <span class="ilbl">Artifact</span> <span class="ival"><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Google Drive — Revised Research Folder</a></span>
      <span class="ilbl">Proof</span>   <span class="ival"><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Google Drive — Same Folder</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Full review and correction pass on the NeRF research paper. Specific fixes: verified all sources for accuracy and corrected affiliation errors; pinned an actual commit hash for the GitHub source (previously only flagged, not resolved); added a scope caveat to the main benchmark finding to prevent overgeneralization; added a missing revision date on the survey source; rewrote sections of the research paper to reflect the corrected source data.</p>
      <div class="ai-note">Used for editing the LaTeX code for the PDF.</div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══════════════════════════════════ WEEK 6 ══════════════════════════════════ -->
<section>
  <div class="wk-bar w6">
    <div class="wk-lbl">Week 6</div>
    <h2>Final Evidence Closure</h2>
    <div class="wk-sub">27 Jul – 1 Aug 2026 &nbsp;·&nbsp; Final proof packs &nbsp;·&nbsp; 3/4 blocks complete</div>
  </div>

  <!-- Sprint 5 -->
  <div class="card c-violet">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(139,92,246,.14);color:#c4b5fd;border-color:rgba(139,92,246,.4)">W6D1</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 1 Aug 2026, 17:30 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 5 — Extension Sprint 5: Final Artifact Improvement</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>       <span class="ival">Thursday, 31 July 2026</span>
      <span class="ilbl">Start</span>      <span class="ival">10:00 AM PKT</span>
      <span class="ilbl">End</span>        <span class="ival">3:40 PM PKT</span>
      <span class="ilbl">Artifact</span>   <span class="ival"><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Google Drive — TASKY Web App Evidence</a></span>
      <span class="ilbl">Proof</span>     <span class="ival"><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Google Drive — Same Folder</a></span>
      <span class="ilbl">Process Log</span><span class="ival"><a href="https://github.com/marqamghayour-lang/TASKY/commits/main/">GitHub — TASKY Commit History</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Improved the TASKY web application with two major additions: (1) CLERK Authentication System — integrated a complete login/signup flow using Clerk, handling session management and user identity. (2) Dark and Light Theme — built and integrated theme switching with proper CSS variable scoping, allowing full UI palette switching at runtime. Evidence links are in the Drive folder.</p>
      <div class="ai-note">Used for building the CSS for the web app.</div>
    </div>
  </div>

  <!-- Iris Hacks -->
  <div class="card c-pink">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(236,72,153,.14);color:#f9a8d4;border-color:rgba(236,72,153,.4)">W6D2 — Hackathon</span>
      <span class="hrs-tag">2 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 1 Aug 2026, 17:17 UTC</span>
    </div>
    <h3 class="ctitle">Iris Hacks IV — Applications of AI Hackathon</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>        <span class="ival">Saturday, 1 August 2026</span>
      <span class="ilbl">Submitted</span>   <span class="ival">10:00 PM PKT</span>
      <span class="ilbl">Participation</span><span class="ival">Form submitted — Interest status: Not Interested</span>
      <span class="ilbl">Artifact</span>    <span class="ival"><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Google Drive — Form Submission Proof</a></span>
      <span class="ilbl">Proof</span>      <span class="ival"><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Google Drive — Same Folder</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Completed and submitted the Iris Hacks IV: Applications of AI Hackathon registration form before the deadline. Screenshot proof of the submitted form is attached in the Drive folder.</p>
    </div>
  </div>

  <!-- Sprint 6 -->
  <div class="card c-teal">
    <div class="ctop">
      <span class="mod-tag" style="background:rgba(20,184,166,.14);color:#5eead4;border-color:rgba(20,184,166,.4)">W6D2</span>
      <span class="hrs-tag">4 hrs</span>
      <span class="del-tag">Delivered</span>
      <span class="sub-tag">Submitted 1 Aug 2026, 18:44 UTC</span>
    </div>
    <h3 class="ctitle">Sprint 6 — Extension Sprint 6: Public Write-up / Walkthrough</h3>
    <div class="igrid">
      <span class="ilbl">Date</span>       <span class="ival">Thursday, 31 July 2026</span>
      <span class="ilbl">Start</span>      <span class="ival">10:00 AM PKT</span>
      <span class="ilbl">End</span>        <span class="ival">2:00 PM PKT</span>
      <span class="ilbl">Artifact</span>   <span class="ival"><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Google Drive — Walkthrough Evidence Folder</a></span>
      <span class="ilbl">Proof</span>     <span class="ival"><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Google Drive — Same Folder</a></span>
      <span class="ilbl">Process Log</span><span class="ival"><a href="https://github.com/marqamghayour-lang/NERF-Research_WalkThrough">GitHub — NeRF Walkthrough README</a></span>
    </div>
    <div class="cdiv"></div>
    <div class="cbox">
      <div class="clbl">What Was Completed</div>
      <p class="ctxt">Wrote the complete public walkthrough of the NeRF Research Task as a README.md file, covering: how the research was started and what motivated it; how sources were gathered, filtered, and evaluated; how the report was structured and formatted; and how the research connects to real-world work at PreserveMy.World (PMW) for heritage documentation via 3D reconstruction. Working proofs are in the Drive folder.</p>
      <div class="ai-note">Used for README.md formatting and structure correction.</div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ══════════════════════════════════ SUMMARY ══════════════════════════════════ -->
<section>
  <h2 class="sec-title">Hours Summary</h2>

  <div class="stat-row">
    <div class="stat" style="--acc:var(--indigo)"><div class="stat-n" style="color:#a5b4fc" id="c1">0</div><div class="stat-l">Total Sprints</div></div>
    <div class="stat" style="--acc:var(--sky)">   <div class="stat-n" style="color:#7dd3fc" id="c2">0</div><div class="stat-l">Hours Claimed</div></div>
    <div class="stat" style="--acc:var(--green)"> <div class="stat-n" style="color:#86efac" id="c3">0</div><div class="stat-l">Delivered</div></div>
    <div class="stat" style="--acc:var(--amber)"> <div class="stat-n" style="color:#fcd34d">2</div>   <div class="stat-l">Weeks Covered</div></div>
  </div>

  <table class="sum">
    <thead><tr><th>Week</th><th>Sprints</th><th>Hours Claimed</th><th>Status</th></tr></thead>
    <tbody>
      <tr><td>Week 5</td><td>Sprints 1 – 4</td><td>16 h</td><td><span class="st">All Delivered</span></td></tr>
      <tr><td>Week 6</td><td>Sprints 5, 6 + Iris Hacks</td><td>10 h</td><td><span class="st">All Delivered</span></td></tr>
    </tbody>
    <tfoot>
      <tr><td>Total</td><td>7 blocks</td><td>26 h</td><td><span class="st">Complete</span></td></tr>
    </tfoot>
  </table>

  <div class="integrity">
    All submitted hours confirmed as own work and accurate &nbsp;&nbsp;|&nbsp;&nbsp;
    Muhammad Arqam Ghayour &nbsp;·&nbsp; 25I-0006 &nbsp;·&nbsp; AI-C &nbsp;·&nbsp; FAST-NUCES Islamabad
  </div>
</section>

</div>

<footer>
  <div class="fbar"></div>
  <p>Generated from submissions.csv &nbsp;·&nbsp; Muhammad Arqam Ghayour &nbsp;·&nbsp; Platform &amp; Web Engineering &nbsp;·&nbsp; YouthxAI 2026</p>
</footer>

<script>
/* ── Typing animation ── */
const phrases=['Platform & Web Engineering','YouthxAI Verified Make-Up Hours','7 Sprints — All Delivered','FAST-NUCES Islamabad · AI-C','25I-0006 · Muhammad Arqam Ghayour'];
let pi=0,ci=0,del=false;
const typer=document.getElementById('typer');
function tick(){
  const p=phrases[pi];
  typer.textContent=del?p.slice(0,ci--):p.slice(0,ci++);
  if(!del&&ci>p.length){del=true;setTimeout(tick,1800);return;}
  if(del&&ci<0){del=false;pi=(pi+1)%phrases.length;ci=0;setTimeout(tick,400);return;}
  setTimeout(tick,del?38:68);
}
tick();

/* ── Particle canvas ── */
const canvas=document.getElementById('bg-canvas');
const ctx=canvas.getContext('2d');
let pts=[];
const COLS=['#6366f1','#0ea5e9','#14b8a6','#8b5cf6','#ec4899','#f59e0b'];
function resize(){canvas.width=innerWidth;canvas.height=innerHeight;}
resize();
addEventListener('resize',()=>{resize();init();});
function init(){
  pts=[];
  const n=Math.floor(canvas.width*canvas.height/13000);
  for(let i=0;i<n;i++)pts.push({x:Math.random()*canvas.width,y:Math.random()*canvas.height,r:Math.random()*1.3+0.3,vx:(Math.random()-.5)*.28,vy:(Math.random()-.5)*.28,col:COLS[Math.floor(Math.random()*COLS.length)],a:Math.random()*.45+.15});
}
init();
function draw(){
  ctx.clearRect(0,0,canvas.width,canvas.height);
  for(const p of pts){p.x+=p.vx;p.y+=p.vy;if(p.x<0)p.x=canvas.width;if(p.x>canvas.width)p.x=0;if(p.y<0)p.y=canvas.height;if(p.y>canvas.height)p.y=0;ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fillStyle=p.col;ctx.globalAlpha=p.a;ctx.fill();}
  for(let i=0;i<pts.length;i++){for(let j=i+1;j<pts.length;j++){const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.sqrt(dx*dx+dy*dy);if(d<90){ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);ctx.strokeStyle=pts[i].col;ctx.globalAlpha=(1-d/90)*.1;ctx.lineWidth=.5;ctx.stroke();}}}
  ctx.globalAlpha=1;
  requestAnimationFrame(draw);
}
draw();

/* ── Scroll reveal ── */
const obs=new IntersectionObserver(es=>{es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('vis');obs.unobserve(e.target);}});},{threshold:.08});
document.querySelectorAll('.card').forEach(c=>obs.observe(c));

/* ── Counter animation ── */
function animCount(el,target,dur=1100){let s=null;(function step(ts){if(!s)s=ts;const p=Math.min((ts-s)/dur,1);el.textContent=Math.round(p*target);if(p<1)requestAnimationFrame(step);})(performance.now());}
const cobs=new IntersectionObserver(es=>{es.forEach(e=>{if(e.isIntersecting){const m={c1:7,c2:26,c3:7}[e.target.id];if(m)animCount(e.target,m);cobs.unobserve(e.target);}});},{threshold:.5});
['c1','c2','c3'].forEach(id=>{const el=document.getElementById(id);if(el)cobs.observe(el);});
</script>
</body>
</html>
ENDOFFILE
