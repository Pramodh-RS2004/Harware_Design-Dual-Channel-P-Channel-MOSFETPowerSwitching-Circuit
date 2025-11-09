<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Dual-Channel P-Channel MOSFET Power Switching Circuit — Project</title>
  <style>
    :root{
      --bg:#0f1724; --card:#0b1220; --accent:#00d1b2; --muted:#9aa6b2; --glass: rgba(255,255,255,0.03);
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{
      margin:0; min-height:100vh; background:
      radial-gradient(1200px 600px at 10% 10%, rgba(0,209,178,0.06), transparent 6%),
      linear-gradient(180deg, #071025 0%, #081124 40%, #06131b 100%);
      color:#e6eef3; display:flex; align-items:center; justify-content:center; padding:32px;
    }
    .wrap{width:100%; max-width:1000px;}
    header{display:flex; gap:16px; align-items:center; margin-bottom:18px}
    .logo{
      width:72px; height:72px; border-radius:12px; background:linear-gradient(135deg,var(--accent),#6ad1ff);
      display:flex; align-items:center; justify-content:center; color:#042027; font-weight:700; font-size:20px;
      box-shadow: 0 8px 30px rgba(0,0,0,0.6);
    }
    h1{margin:0; font-size:20px; letter-spacing:0.2px}
    p.lead{margin:4px 0 0; color:var(--muted); font-size:13px}
    .card{
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius:12px; padding:20px; box-shadow: 0 8px 30px rgba(2,6,23,0.7); backdrop-filter: blur(6px);
    }
    .grid{display:grid; grid-template-columns: 1fr 360px; gap:18px; align-items:start}
    .section-title{color:var(--muted); font-size:13px; margin-bottom:8px;}
    .desc{line-height:1.45; color:#cfe6ea; font-size:14px}
    ul.features{margin:12px 0 18px; padding-left:18px; color:var(--muted)}
    .screenshot{border-radius:8px; overflow:hidden; border:1px solid rgba(255,255,255,0.03)}
    .screenshot img{width:100%; height:auto; display:block}
    .controls{display:flex; gap:8px; margin-top:12px}
    .btn{
      display:inline-flex; align-items:center; gap:8px; padding:10px 12px; border-radius:10px;
      background:var(--glass); color:var(--accent); text-decoration:none; font-weight:600; font-size:13px;
      border:1px solid rgba(255,255,255,0.04);
      transition: transform .18s ease, box-shadow .18s ease;
    }
    .btn:hover{transform:translateY(-4px); box-shadow:0 10px 30px rgba(0,0,0,0.6)}
    .btn.secondary{color:#cfe6ea; border-color:rgba(255,255,255,0.03)}
    .meta{font-size:13px; color:var(--muted); margin-top:8px}
    /* animated waveform icon */
    .wave {
      width:100%; height:48px; display:flex; align-items:center; gap:10px; padding:8px 0;
    }
    .bar {height:6px; background:linear-gradient(90deg,var(--accent),#69e6ff); border-radius:6px; width:8px; opacity:.9; transform-origin:center; animation:bar 1.2s linear infinite;}
    .bar:nth-child(2){animation-delay:.08s;height:10px}
    .bar:nth-child(3){animation-delay:.16s;height:14px}
    .bar:nth-child(4){animation-delay:.24s;height:18px}
    @keyframes bar{0%{transform:scaleY(.3)}50%{transform:scaleY(1.6)}100%{transform:scaleY(.3)}}
    footer{margin-top:14px; color:var(--muted); font-size:12px; display:flex; justify-content:space-between; align-items:center}
    /* responsive */
    @media (max-width:880px){
      .grid{grid-template-columns: 1fr; }
      .screenshot{order:-1}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="logo">MOS</div>
      <div>
        <h1>Dual-Channel P-Channel MOSFET Power Switching Circuit</h1>
        <p class="lead">Fast, MOSFET-based automatic source switching for reliable embedded power delivery.</p>
      </div>
    </header>

    <div class="card">
      <div class="grid">
        <div>
          <div class="section-title">Project Summary</div>
          <div class="desc">
            MOSFET high-side switching architecture enabling instantaneous transfer between adapter and battery without mechanical relays. Verified in LTspice and prepared for PCB layout in Altium Designer.
          </div>

          <ul class="features" aria-hidden="true">
            <li><strong>Instant switching</strong> via P-channel MOSFETs (no relay delay)</li>
            <li><strong>Reverse protection</strong> using Schottky diodes</li>
            <li><strong>Gate stability</strong> with RC damping network</li>
            <li><strong>Simulation & design</strong> — LTspice & Altium</li>
          </ul>

          <div class="section-title">Quick Links</div>
          <div class="controls">
            <!-- Replace href values with your actual files -->
            <a class="btn" href="REPORT_PDF_LINK" target="_blank" rel="noopener">➜ View Report (PDF)</a>
            <a class="btn secondary" href="Dual_Power_Switching_Circuit.asc" target="_blank" rel="noopener">➜ LTspice File</a>
            <a class="btn secondary" href="GITHUB_PROJECT_URL" target="_blank" rel="noopener">➜ Repository</a>
          </div>

          <div style="margin-top:14px;">
            <div class="section-title">Specifications</div>
            <div class="meta">
              MOSFET: DMP4025LK3 • Diode: B540C • Gate resistor: 4.7 kΩ • Decoupling: 10 µF, 1 µF • Load test: 50 Ω
            </div>
          </div>

          <div style="margin-top:18px;">
            <div class="section-title">Live indicator</div>
            <div class="wave" aria-hidden="true">
              <div class="bar" style="width:6px"></div>
              <div class="bar" style="width:8px"></div>
              <div class="bar" style="width:10px"></div>
              <div class="bar" style="width:6px"></div>
              <div class="bar" style="width:12px"></div>
            </div>
            <div class="meta">Simulation-ready • Click "View Report" to open design notes & waveforms.</div>
          </div>
        </div>

        <aside>
          <div class="section-title">Schematic</div>
          <div class="screenshot">
            <!-- replace with your schematic filename -->
            <img src="SCHEMATIC_IMAGE.png" alt="Dual-Channel MOSFET Power Switching Schematic">
          </div>

          <div style="margin-top:12px">
            <div class="section-title">Tools</div>
            <div class="meta">LTspice • Altium Designer • Multimeter • Oscilloscope</div>
          </div>
        </aside>
      </div>

      <footer>
        <div>Author: Pramodh R S — Embedded Systems Engineer</div>
        <div>GitHub: <a style="color:var(--accent)" href="GITHUB_PROJECT_URL" target="_blank">Pramodh-RS2004</a></div>
      </footer>
    </div>
  </div>

  <script>
    // small animation: pulse the logo on load
    const logo = document.querySelector('.logo');
    logo.animate([
      { transform: 'scale(1)', boxShadow: '0 8px 30px rgba(2,6,23,0.7)' },
      { transform: 'scale(1.08)', boxShadow: '0 18px 60px rgba(2,6,23,0.85)' },
      { transform: 'scale(1)', boxShadow: '0 8px 30px rgba(2,6,23,0.7)' }
    ], { duration: 1400, iterations: 2 });
  </script>
</body>
</html>
