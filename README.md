<style>
  @keyframes gradientShift {
    0%   { background-position: 0% 50%; }
    50%  { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  @keyframes glowPulse {
    0%, 100% { box-shadow: 0 0 6px #6366f1, 0 0 12px #6366f1; }
    50%       { box-shadow: 0 0 18px #a78bfa, 0 0 36px #a78bfa, 0 0 60px #6366f1; }
  }
  @keyframes glowBlue {
    0%, 100% { box-shadow: 0 0 6px #0ea5e9; }
    50%       { box-shadow: 0 0 20px #38bdf8, 0 0 40px #0ea5e9; }
  }
  @keyframes glowAmber {
    0%, 100% { box-shadow: 0 0 6px #f59e0b; }
    50%       { box-shadow: 0 0 20px #fbbf24, 0 0 40px #f59e0b; }
  }
  @keyframes glowRed {
    0%, 100% { box-shadow: 0 0 6px #ef4444; }
    50%       { box-shadow: 0 0 20px #f87171, 0 0 40px #ef4444; }
  }
  @keyframes glowViolet {
    0%, 100% { box-shadow: 0 0 6px #8b5cf6; }
    50%       { box-shadow: 0 0 20px #a78bfa, 0 0 40px #8b5cf6; }
  }
  @keyframes glowPink {
    0%, 100% { box-shadow: 0 0 6px #ec4899; }
    50%       { box-shadow: 0 0 20px #f472b6, 0 0 40px #ec4899; }
  }
  @keyframes glowTeal {
    0%, 100% { box-shadow: 0 0 6px #14b8a6; }
    50%       { box-shadow: 0 0 20px #2dd4bf, 0 0 40px #14b8a6; }
  }
  @keyframes shimmer {
    0%   { background-position: -200% center; }
    100% { background-position: 200% center; }
  }
  @keyframes borderRotate {
    0%   { border-color: #6366f1; }
    16%  { border-color: #0ea5e9; }
    33%  { border-color: #14b8a6; }
    50%  { border-color: #f59e0b; }
    66%  { border-color: #ef4444; }
    83%  { border-color: #ec4899; }
    100% { border-color: #6366f1; }
  }
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes pulseBadge {
    0%, 100% { transform: scale(1); }
    50%       { transform: scale(1.06); }
  }
  @keyframes scanline {
    0%   { top: -10%; }
    100% { top: 110%; }
  }
  @keyframes textGlow {
    0%, 100% { text-shadow: 0 0 8px #6366f1, 0 0 16px #6366f1; }
    50%       { text-shadow: 0 0 16px #a78bfa, 0 0 32px #a78bfa, 0 0 48px #6366f1; }
  }

  .header-gradient {
    background: linear-gradient(270deg, #6366f1, #0ea5e9, #14b8a6, #8b5cf6, #ec4899);
    background-size: 400% 400%;
    animation: gradientShift 8s ease infinite;
    border-radius: 12px;
    padding: 28px 20px;
    margin-bottom: 20px;
  }
  .header-title {
    font-size: 2em;
    font-weight: 900;
    color: #fff;
    letter-spacing: 1px;
    animation: textGlow 3s ease-in-out infinite;
  }
  .header-sub {
    color: rgba(255,255,255,0.85);
    font-size: 0.95em;
    margin-top: 6px;
  }

  .week-divider {
    background: linear-gradient(90deg, #6366f1, #0ea5e9, #14b8a6, #8b5cf6);
    background-size: 300% 100%;
    animation: gradientShift 5s ease infinite;
    height: 3px;
    border: none;
    border-radius: 2px;
    margin: 24px 0;
  }
  .week-header {
    background: linear-gradient(135deg, rgba(99,102,241,0.15), rgba(14,165,233,0.10));
    border-left: 4px solid #6366f1;
    animation: borderRotate 8s linear infinite;
    border-radius: 0 8px 8px 0;
    padding: 12px 20px;
    margin: 20px 0;
  }
  .week-header h2 {
    margin: 0;
    font-size: 1.3em;
    color: #e2e8f0;
  }

  .sprint-card {
    border-radius: 10px;
    padding: 20px 24px;
    margin: 18px 0;
    position: relative;
    overflow: hidden;
    animation: fadeInUp 0.6s ease both;
    border: 1.5px solid transparent;
    background: rgba(15,15,30,0.85);
  }
  .sprint-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: inherit;
    filter: brightness(1.8);
  }

  .card-indigo  { border-color: #6366f1; animation: glowPulse  3s ease-in-out infinite; }
  .card-sky     { border-color: #0ea5e9; animation: glowBlue   3s ease-in-out infinite; }
  .card-amber   { border-color: #f59e0b; animation: glowAmber  3s ease-in-out infinite; }
  .card-red     { border-color: #ef4444; animation: glowRed    3s ease-in-out infinite; }
  .card-violet  { border-color: #8b5cf6; animation: glowViolet 3s ease-in-out infinite; }
  .card-pink    { border-color: #ec4899; animation: glowPink   3s ease-in-out infinite; }
  .card-teal    { border-color: #14b8a6; animation: glowTeal   3s ease-in-out infinite; }

  .badge-delivered {
    display: inline-block;
    background: linear-gradient(90deg, #166534, #15803d);
    color: #bbf7d0;
    font-weight: 700;
    font-size: 0.75em;
    padding: 3px 10px;
    border-radius: 999px;
    letter-spacing: 0.5px;
    animation: pulseBadge 2s ease-in-out infinite;
  }
  .badge-module {
    display: inline-block;
    font-weight: 700;
    font-size: 0.72em;
    padding: 2px 9px;
    border-radius: 999px;
    letter-spacing: 0.5px;
    margin-right: 6px;
  }
  .badge-hours {
    display: inline-block;
    background: #1e3a5f;
    color: #93c5fd;
    font-weight: 700;
    font-size: 0.72em;
    padding: 2px 9px;
    border-radius: 999px;
    letter-spacing: 0.5px;
  }

  .sprint-title {
    font-size: 1.15em;
    font-weight: 800;
    margin: 10px 0 14px;
    color: #f1f5f9;
  }
  .info-grid {
    display: grid;
    grid-template-columns: 130px 1fr;
    gap: 6px 14px;
    margin: 12px 0;
    font-size: 0.88em;
  }
  .info-label {
    font-weight: 700;
    color: #94a3b8;
    text-transform: uppercase;
    font-size: 0.78em;
    letter-spacing: 0.5px;
    align-self: center;
  }
  .info-value { color: #e2e8f0; }
  .info-value a { color: #60a5fa; }

  .completed-section {
    margin-top: 14px;
    padding: 12px 16px;
    border-radius: 8px;
    background: rgba(255,255,255,0.04);
    border-left: 3px solid #334155;
    font-size: 0.88em;
    color: #cbd5e1;
    line-height: 1.7;
  }
  .completed-label {
    font-weight: 800;
    color: #94a3b8;
    font-size: 0.75em;
    text-transform: uppercase;
    letter-spacing: 0.6px;
    margin-bottom: 5px;
  }
  .ai-note {
    margin-top: 10px;
    font-size: 0.78em;
    color: #64748b;
    font-style: italic;
  }

  .summary-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
    font-size: 0.9em;
  }
  .summary-table th {
    background: linear-gradient(90deg, #1e1b4b, #0c1a2e);
    color: #a5b4fc;
    padding: 10px 14px;
    text-align: left;
    font-size: 0.8em;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    border-bottom: 2px solid #334155;
  }
  .summary-table td {
    padding: 9px 14px;
    border-bottom: 1px solid #1e293b;
    color: #e2e8f0;
  }
  .summary-table tr:hover td {
    background: rgba(99,102,241,0.08);
  }

  .footer-bar {
    background: linear-gradient(270deg, #6366f1, #14b8a6, #0ea5e9, #8b5cf6);
    background-size: 300% 300%;
    animation: gradientShift 6s ease infinite;
    height: 4px;
    border-radius: 2px;
    margin: 32px 0 16px;
  }
  .integrity-banner {
    background: linear-gradient(90deg, rgba(34,197,94,0.1), rgba(21,128,61,0.1));
    border: 1px solid #166534;
    border-radius: 8px;
    padding: 12px 20px;
    text-align: center;
    color: #86efac;
    font-size: 0.88em;
    font-weight: 600;
    letter-spacing: 0.3px;
    animation: glowTeal 4s ease-in-out infinite;
  }
</style>

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                        HEADER                              -->
<!-- ═══════════════════════════════════════════════════════════ -->

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:6366f1,30:0ea5e9,60:14b8a6,100:8b5cf6&height=200&section=header&text=Muhammad%20Arqam%20Ghayour&fontSize=32&fontColor=ffffff&fontAlignY=38&desc=Make-Up%20Hour%20Submission%20Log&descAlignY=58&descSize=16&animation=fadeIn" width="100%"/>

<br/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=20&pause=1000&color=6366F1&center=true&vCenter=true&width=600&lines=Platform+%26+Web+Engineering;YouthxAI+Verified+Make-Up+Hours;7+Sprints+Delivered+%E2%80%94+All+Confirmed;25I-0006+%C2%B7+AI-C+%C2%B7+FAST-NUCES+Islamabad" alt="Typing SVG"/>

<br/><br/>

<img alt="Student ID"   src="https://img.shields.io/badge/Student%20ID-25I--0006-6366f1?style=for-the-badge&logoColor=white"/>
&nbsp;
<img alt="Section"     src="https://img.shields.io/badge/Section-AI--C-0ea5e9?style=for-the-badge&logoColor=white"/>
&nbsp;
<img alt="Hours"       src="https://img.shields.io/badge/Total%20Hours-26h-22c55e?style=for-the-badge&logoColor=white"/>
&nbsp;
<img alt="Delivered"   src="https://img.shields.io/badge/Sprints%20Delivered-7%20%2F%207-f59e0b?style=for-the-badge&logoColor=white"/>

</div>

---

## Quick Reference

| # | Sprint | Date | Time | Hours | Status | Artifact | Proof |
|---|--------|------|------|-------|--------|----------|-------|
| 1 | Extension Sprint 1: Verified Work Plan | 20 Jul 2026 | 10:00 AM – 3:40 PM PKT | 4h | Delivered | [Drive](https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing) | [Drive](https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing) |
| 2 | Extension Sprint 2: Research & Source Log | 23 Jul 2026 | 4:00 AM – 8:15 AM PKT | 4h | Delivered | [GitHub](https://github.com/marqamghayour-lang/Research-Source-Log) | [Drive](https://drive.google.com/drive/folders/1QXIJXaLfByRDvDSf21UUr5Y2JjWZ1LzO?usp=sharing) |
| 3 | Extension Sprint 3: Build Evidence | 22–23 Jul 2026 | Multi-session (6–7 hrs) | 4h | Delivered | [Drive](https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing) | [Drive](https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing) |
| 4 | Extension Sprint 4: Review & Revision | 1 Aug 2026 | 10:00 PM – 2:10 AM PKT | 4h | Delivered | [Drive](https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing) | [Drive](https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing) |
| 5 | Extension Sprint 5: Final Artifact Improvement | 31 Jul 2026 | 10:00 AM – 3:40 PM PKT | 4h | Delivered | [Drive](https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing) | [Drive](https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing) |
| 6 | Iris Hacks IV: Applications of AI Hackathon | 1 Aug 2026 | Form submitted 10:00 PM PKT | 2h | Delivered | [Drive](https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing) | [Drive](https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing) |
| 7 | Extension Sprint 6: Public Write-up / Walkthrough | 31 Jul 2026 | 10:00 AM – 2:00 PM PKT | 4h | Delivered | [Drive](https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing) | [Drive](https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing) |

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                       WEEK 5                               -->
<!-- ═══════════════════════════════════════════════════════════ -->

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1e1b4b,100:0c1a2e&height=60&text=WEEK%205%20%E2%80%94%20Strict%20Evidence%20%26%20Process%20Logs&fontSize=18&fontColor=a5b4fc&animation=blinking" width="100%"/>
<sub>20 Jul – 26 Jul 2026 &nbsp;·&nbsp; Verified Make-up Hours</sub>
</div>

<br/>

<!-- ───────── SPRINT 1 ───────── -->

<div class="sprint-card card-indigo">

<span class="badge-module" style="background:#312e81;color:#a5b4fc;">W5D1</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 25 Jul 2026, 09:51 UTC</span>

<div class="sprint-title">Sprint 1 — Extension Sprint 1: Verified Work Plan</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Monday, 20 July 2026</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">10:00 AM PKT</span>

  <span class="info-label">End Time</span>
  <span class="info-value">3:40 PM PKT</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Google Drive — Kaggle Pandas Certificate</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/file/d/1vFGXRlBmELX9QOYmnLvSTHsXjS2BCeDP/view?usp=sharing">Google Drive — Same Certificate File</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Completed the Pandas course on Kaggle. Pandas accounted for 70–80% of all code written during YouthxAI sessions for training AI models. Completing this course solidified understanding of data management and its role in ML pipelines. The Kaggle course certificate is the proof artifact.
  <div class="ai-note">AI Use: Used to understand concepts not well covered by the course.</div>
</div>

</div>

<!-- ───────── SPRINT 2 ───────── -->

<div class="sprint-card card-sky">

<span class="badge-module" style="background:#0c2a3f;color:#7dd3fc;">W5D2</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 25 Jul 2026, 11:04 UTC</span>

<div class="sprint-title">Sprint 2 — Extension Sprint 2: Research & Source Log</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Thursday, 23 July 2026</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">4:00 AM PKT</span>

  <span class="info-label">End Time</span>
  <span class="info-value">8:15 AM PKT</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://github.com/marqamghayour-lang/Research-Source-Log">GitHub — Research-Source-Log Repository</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1QXIJXaLfByRDvDSf21UUr5Y2JjWZ1LzO?usp=sharing">Google Drive — Evidence Folder</a></span>

  <span class="info-label">Process Log</span>
  <span class="info-value"><a href="https://github.com/marqamghayour-lang/Research-Source-Log/commits/main/">GitHub — Commit History</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Conducted research on the 3D Reconstruction method NeRF (Neural Radiance Fields). Sources were gathered from Google Scholar, filtered for credibility, read at surface level, and then rewritten in own words. AI was used to correct grammar and formatting. The final research was reviewed, all errors fixed, and published to the GitHub repository. This research directly supports ongoing NeRF-based heritage documentation work at PMW.
  <div class="ai-note">AI Use: Identified the most authentic sources and rectified the writing of the research report.</div>
</div>

</div>

<!-- ───────── SPRINT 3 ───────── -->

<div class="sprint-card card-amber">

<span class="badge-module" style="background:#3d2700;color:#fcd34d;">W5D3</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 25 Jul 2026, 11:23 UTC</span>

<div class="sprint-title">Sprint 3 — Extension Sprint 3: Build Evidence</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Wednesday–Thursday, 22–23 July 2026</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">Multi-session across both days</span>

  <span class="info-label">End Time</span>
  <span class="info-value">~6–7 hrs total</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Google Drive — MLP from Scratch Evidence Folder</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/17YuSfCG-AfUHNVrXMPWrYWeWiF1C90cS?usp=sharing">Google Drive — Same Evidence Folder</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Trained an MLP (Neural Network) on the MNIST dataset (60,000 handwritten digit images) from scratch — zero ML libraries. Every component manually implemented: forward propagation, cross-entropy loss calculations, backpropagation, gradient descent optimization, and epoch management. The model correctly classifies handwritten digits. This extends the YouthxAI Neural Network task — that version used libraries; this one exposes all the internals those libraries abstract away.
  <div class="ai-note">AI Use: Used to revise the theoretical backend of model training.</div>
</div>

</div>

<!-- ───────── SPRINT 4 ───────── -->

<div class="sprint-card card-red">

<span class="badge-module" style="background:#3d0a0a;color:#fca5a5;">W5D4</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 1 Aug 2026, 18:30 UTC</span>

<div class="sprint-title">Sprint 4 — Extension Sprint 4: Review & Revision</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Saturday, 1 August 2026 (overnight session)</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">10:00 PM PKT</span>

  <span class="info-label">End Time</span>
  <span class="info-value">2:10 AM PKT (next day)</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Google Drive — Revised Research Folder</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1js3T7Q-eTkJdZPLE5j0iaVUYNy7GJNxe?usp=sharing">Google Drive — Same Revised Research Folder</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Full review and correction pass on the NeRF research paper. Specific fixes: verified all sources for accuracy and corrected affiliation errors; pinned an actual commit hash for the GitHub source (previously only flagged, not resolved); added a scope caveat to the main benchmark finding to prevent overgeneralization; added a missing revision date on the survey source; rewrote sections of the research paper to reflect the corrected source data.
  <div class="ai-note">AI Use: Used for editing the LaTeX code for the PDF.</div>
</div>

</div>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                       WEEK 6                               -->
<!-- ═══════════════════════════════════════════════════════════ -->

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0d1f0d,100:0c1a2e&height=60&text=WEEK%206%20%E2%80%94%20Final%20Evidence%20Closure&fontSize=18&fontColor=86efac&animation=blinking" width="100%"/>
<sub>27 Jul – 1 Aug 2026 &nbsp;·&nbsp; Final proof packs &nbsp;·&nbsp; 3/4 blocks complete</sub>
</div>

<br/>

<!-- ───────── SPRINT 5 ───────── -->

<div class="sprint-card card-violet">

<span class="badge-module" style="background:#2e1b63;color:#c4b5fd;">W6D1</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 1 Aug 2026, 17:30 UTC</span>

<div class="sprint-title">Sprint 5 — Extension Sprint 5: Final Artifact Improvement</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Thursday, 31 July 2026</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">10:00 AM PKT</span>

  <span class="info-label">End Time</span>
  <span class="info-value">3:40 PM PKT</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Google Drive — TASKY Web App Evidence</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1oN5bTqI03OR6lcOPwu4FsChUCAGHBgqy?usp=sharing">Google Drive — Same Folder</a></span>

  <span class="info-label">Process Log</span>
  <span class="info-value"><a href="https://github.com/marqamghayour-lang/TASKY/commits/main/">GitHub — TASKY Commit History</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Improved the TASKY web application with two major additions: (1) CLERK Authentication System — integrated a complete login/signup flow using Clerk, handling session management and user identity; (2) Dark and Light Theme — built and integrated theme switching with proper CSS variable scoping, allowing full UI palette switching at runtime. Evidence links are in the Drive folder.
  <div class="ai-note">AI Use: Used for building the CSS for the web app.</div>
</div>

</div>

<!-- ───────── IRIS HACKS ───────── -->

<div class="sprint-card card-pink">

<span class="badge-module" style="background:#4a0a2e;color:#f9a8d4;">W6D2 — Hackathon</span>
<span class="badge-hours">2 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 1 Aug 2026, 17:17 UTC</span>

<div class="sprint-title">Iris Hacks IV — Applications of AI Hackathon</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Saturday, 1 August 2026</span>

  <span class="info-label">Form Submitted</span>
  <span class="info-value">10:00 PM PKT</span>

  <span class="info-label">Participation</span>
  <span class="info-value">Form submitted — Interest status: Not Interested</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Google Drive — Form Submission Proof</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1wPMz2BcEA1g5ycbd8xk5lMcsbdRl792m?usp=sharing">Google Drive — Same Folder</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Completed and submitted the Iris Hacks IV: Applications of AI Hackathon registration form before the deadline. Screenshot proof of the submitted form is attached in the Drive folder.
</div>

</div>

<!-- ───────── SPRINT 6 ───────── -->

<div class="sprint-card card-teal">

<span class="badge-module" style="background:#0a2e2a;color:#5eead4;">W6D2</span>
<span class="badge-hours">4 hrs</span>
&nbsp;
<span class="badge-delivered">DELIVERED</span>
&nbsp;
<span style="font-size:0.75em;color:#64748b;">Submitted: 1 Aug 2026, 18:44 UTC</span>

<div class="sprint-title">Sprint 6 — Extension Sprint 6: Public Write-up / Walkthrough</div>

<div class="info-grid">
  <span class="info-label">Date</span>
  <span class="info-value">Thursday, 31 July 2026</span>

  <span class="info-label">Start Time</span>
  <span class="info-value">10:00 AM PKT</span>

  <span class="info-label">End Time</span>
  <span class="info-value">2:00 PM PKT</span>

  <span class="info-label">Artifact</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Google Drive — Walkthrough Evidence Folder</a></span>

  <span class="info-label">Proof</span>
  <span class="info-value"><a href="https://drive.google.com/drive/folders/1gr-FgEF5vzwzeEPpkIempJYINBy7Tipi?usp=sharing">Google Drive — Same Folder</a></span>

  <span class="info-label">Process Log</span>
  <span class="info-value"><a href="https://github.com/marqamghayour-lang/NERF-Research_WalkThrough">GitHub — NeRF Walkthrough README</a></span>
</div>

<div class="completed-section">
  <div class="completed-label">What Was Completed</div>
  Wrote the complete public walkthrough of the NeRF Research Task as a README.md file, covering: how the research was started and what motivated it; how sources were gathered, filtered, and evaluated; how the report was structured and formatted; and how the research connects to real-world work at PreserveMy.World (PMW) for heritage documentation via 3D reconstruction. Working proofs are attached in the Drive folder.
  <div class="ai-note">AI Use: Used for README.md formatting and structure correction.</div>
</div>

</div>

---

<!-- ═══════════════════════════════════════════════════════════ -->
<!--                    HOURS SUMMARY                           -->
<!-- ═══════════════════════════════════════════════════════════ -->

<div align="center"><strong>Hours Summary</strong></div>

<table class="summary-table">
<thead>
<tr>
  <th>Week</th>
  <th>Sprints</th>
  <th>Hours Claimed</th>
  <th>Status</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Week 5</td>
  <td>Sprints 1 – 4</td>
  <td>16 h</td>
  <td><span class="badge-delivered">ALL DELIVERED</span></td>
</tr>
<tr>
  <td>Week 6</td>
  <td>Sprints 5, 6 + Iris Hacks</td>
  <td>10 h</td>
  <td><span class="badge-delivered">ALL DELIVERED</span></td>
</tr>
<tr>
  <td><strong>Total</strong></td>
  <td><strong>7 blocks</strong></td>
  <td><strong>26 h</strong></td>
  <td><span class="badge-delivered">COMPLETE</span></td>
</tr>
</tbody>
</table>

<br/>

<div class="integrity-banner">
All submitted hours confirmed as own work and accurate &nbsp;|&nbsp; Muhammad Arqam Ghayour &nbsp;·&nbsp; 25I-0006 &nbsp;·&nbsp; AI-C &nbsp;·&nbsp; FAST-NUCES Islamabad
</div>

<div class="footer-bar"></div>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:8b5cf6,50:0ea5e9,100:14b8a6&height=120&section=footer&animation=fadeIn" width="100%"/>
</div>
