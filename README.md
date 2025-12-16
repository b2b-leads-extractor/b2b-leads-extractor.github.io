<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>B2B Leads Extractor — Desktop Lead Collection Software</title>
  <meta name="description" content="B2B Leads Extractor is a desktop software to collect publicly available business information from online map listings and directories, organized in a fast, export-ready table." />
  <style>
    :root{
      --bg:#0f1420;
      --bg2:#121a2a;
      --card: rgba(255,255,255,.05);
      --card2: rgba(255,255,255,.035);
      --text:#eaf0ff;
      --muted:#a8b3cc;
      --line: rgba(255,255,255,.10);
      --accent:#63b3ff;
      --accent2:#7cffd1;
      --shadow: 0 10px 40px rgba(0,0,0,.40);
      --radius: 18px;
      --radius2: 22px;
      --max: 1120px;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:var(--sans);
      color:var(--text);
      background:
        radial-gradient(1100px 650px at 8% 0%, rgba(99,179,255,.16), transparent 60%),
        radial-gradient(1000px 650px at 90% 10%, rgba(124,255,209,.12), transparent 55%),
        linear-gradient(180deg, var(--bg), var(--bg2));
      letter-spacing:.2px;
    }
    a{color:inherit}
    img{max-width:100%; display:block}
    .wrap{max-width:var(--max); margin:0 auto; padding:24px;}
    .topbar{
      display:flex; align-items:center; justify-content:space-between;
      gap:16px; padding:14px 18px; border:1px solid var(--line);
      background:rgba(18,26,42,.55); backdrop-filter: blur(10px);
      border-radius:var(--radius2); box-shadow: var(--shadow);
      position:sticky; top:16px; z-index:20;
    }
    .brand{display:flex; align-items:center; gap:12px; min-width: 240px;}
    .brand img{width:40px; height:40px; border-radius:12px; border:1px solid rgba(255,255,255,.12); background:rgba(255,255,255,.04)}
    .brand h1{font-size:14px; margin:0; font-weight:900; letter-spacing:.6px}
    .brand p{margin:2px 0 0; font-size:12px; color:var(--muted)}
    .nav{display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end}
    .nav a{
      text-decoration:none; font-size:12px; color:var(--muted);
      padding:8px 10px; border-radius:12px; border:1px solid transparent;
    }
    .nav a:hover{border-color:var(--line); color:var(--text); background: rgba(255,255,255,.03);}
    .btn{
      display:inline-flex; align-items:center; justify-content:center; gap:10px;
      padding:12px 14px; border-radius:14px; border:1px solid rgba(255,255,255,.12);
      background:rgba(255,255,255,.04);
      color:var(--text); text-decoration:none; font-weight:800; font-size:13px;
      transition: transform .08s ease, border-color .12s ease, background .12s ease;
      user-select:none;
      white-space:nowrap;
    }
    .btn:hover{transform: translateY(-1px); border-color: rgba(99,179,255,.35); background: rgba(99,179,255,.10);}
    .btn.primary{
      background: linear-gradient(135deg, rgba(99,179,255,.95), rgba(124,255,209,.75));
      color:#06101b; border:0;
      box-shadow: 0 18px 30px rgba(99,179,255,.18);
    }
    .btn.primary:hover{transform: translateY(-1px); filter:brightness(1.02)}
    .hero{
      padding:42px 0 18px;
      display:grid; grid-template-columns: 1.15fr .85fr; gap:18px; align-items:stretch;
    }
    .card{
      border:1px solid var(--line);
      background: rgba(18,26,42,.50);
      border-radius:var(--radius2);
      box-shadow: var(--shadow);
      padding:22px;
      backdrop-filter: blur(12px);
    }
    .hero h2{
      font-size:38px; line-height:1.1; margin:0 0 12px; letter-spacing:.4px;
    }
    .hero .sub{
      color:var(--muted); font-size:15px; line-height:1.7; margin:0 0 18px;
    }
    .chips{display:flex; flex-wrap:wrap; gap:10px; margin: 16px 0 18px;}
    .chip{
      font-size:12px; color: rgba(231,238,252,.92);
      padding:8px 10px; border-radius:999px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.03);
    }
    .ctaRow{display:flex; gap:12px; flex-wrap:wrap; align-items:center; margin-top: 18px;}
    .note{font-size:12px; color:var(--muted); margin-top:10px; line-height:1.55;}
    .side{display:flex; flex-direction:column; gap:14px;}
    .boxshot{
      display:grid; grid-template-columns: 1fr; gap:12px;
      align-items:stretch;
    }
    .boxshot img{
      border-radius:18px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.03);
      box-shadow: 0 18px 45px rgba(0,0,0,.35);
    }
    .statGrid{display:grid; grid-template-columns: 1fr 1fr; gap:12px; margin-top:10px;}
    .stat{
      padding:14px; border-radius:16px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.03);
    }
    .stat b{display:block; font-size:14px;}
    .stat span{display:block; margin-top:6px; font-size:12px; color:var(--muted); line-height:1.45;}
    section{padding: 22px 0;}
    .sectionTitle{
      display:flex; align-items:flex-end; justify-content:space-between; gap:16px;
      margin: 0 0 14px;
    }
    .sectionTitle h3{margin:0; font-size:18px; letter-spacing:.3px}
    .sectionTitle p{margin:0; color:var(--muted); font-size:13px;}
    .grid3{display:grid; grid-template-columns: repeat(3, 1fr); gap:14px;}
    .grid2{display:grid; grid-template-columns: repeat(2, 1fr); gap:14px;}
    .tile{
      border:1px solid var(--line);
      background: rgba(18,26,42,.40);
      border-radius:var(--radius);
      padding:16px;
    }
    .tile h4{margin:0 0 8px; font-size:14px}
    .tile p{margin:0; color:var(--muted); font-size:13px; line-height:1.65}
    .steps{
      display:grid; grid-template-columns: repeat(3, 1fr); gap:14px;
    }
    .shot{
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.03);
      border-radius: 18px;
      overflow:hidden;
      box-shadow: 0 14px 34px rgba(0,0,0,.28);
    }
    .shot .cap{
      padding:10px 12px;
      border-top:1px solid rgba(255,255,255,.10);
      font-size:12px;
      color:var(--muted);
    }
    .callout{
      border:1px solid rgba(99,179,255,.22);
      background: rgba(99,179,255,.08);
      border-radius: var(--radius2);
      padding: 16px;
      color: rgba(231,238,252,.95);
    }
    .callout small{display:block; color: rgba(231,238,252,.82); margin-top:8px; line-height:1.6}
    .pricing{
      display:grid; grid-template-columns: 1fr 1fr; gap:14px;
    }
    .plan{
      border:1px solid var(--line);
      background: rgba(18,26,42,.45);
      border-radius: var(--radius2);
      padding:18px;
    }
    .plan h4{margin:0 0 6px; font-size:14px}
    .plan .tag{display:inline-block; margin:10px 0 0; font-size:12px; color:rgba(231,238,252,.95);
      border:1px solid rgba(255,255,255,.12); background:rgba(255,255,255,.03);
      padding:6px 10px; border-radius:999px;
    }
    .plan ul{margin:12px 0 0; padding:0 0 0 16px; color:var(--muted); font-size:13px; line-height:1.65}
    .plan li{margin:6px 0}
    .faq details{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.03);
      border-radius: 14px;
      padding: 12px 14px;
    }
    .faq details + details{margin-top:10px;}
    summary{cursor:pointer; font-weight:800; font-size:13px}
    .faq p{margin: 10px 0 0; color: var(--muted); font-size:13px; line-height:1.65;}
    footer{
      margin: 22px 0 28px;
      padding: 18px 0 0;
      border-top: 1px solid var(--line);
      color: var(--muted);
      font-size: 12px;
      line-height:1.6;
    }
    @media (max-width: 980px){
      .hero{grid-template-columns: 1fr; padding-top: 22px;}
      .grid3{grid-template-columns: 1fr;}
      .grid2{grid-template-columns: 1fr;}
      .steps{grid-template-columns: 1fr;}
      .pricing{grid-template-columns: 1fr;}
      .topbar{position:relative; top:auto;}
      .brand{min-width: unset;}
      .nav{display:none;}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header class="topbar">
      <div class="brand">
        <img src="https://b2b-leads-extractor.github.io/logo1.png" alt="B2B Leads Extractor Logo" />
        <div>
          <h1>B2B Leads Extractor</h1>
          <p>Desktop lead collection • fast, structured, export-ready</p>
        </div>
      </div>

      <nav class="nav" aria-label="Page navigation">
        <a href="#features">Features</a>
        <a href="#screenshots">Screenshots</a>
        <a href="#pricing">Free Trial / Pro</a>
        <a href="#faq">FAQ</a>
      </nav>

      <div style="display:flex; gap:10px; flex-wrap:wrap;">
        <a class="btn" href="#screenshots">Screenshots</a>
        <a class="btn primary" href="#pricing">Get Free Trial</a>
      </div>
    </header>

    <main>
      <div class="hero">
        <div class="card">
          <h2>Collect business leads<br/>in a structured table — fast.</h2>
          <p class="sub">
            <b>B2B Leads Extractor</b> is a desktop software designed to collect <b>publicly available</b> business information
            from online map listings and directories. Results are displayed in a clean table in real time, ready for review and export.
          </p>

          <div class="chips" aria-label="Highlights">
            <div class="chip">Business name • Address • Phone</div>
            <div class="chip">Website • Rating (when available)</div>
            <div class="chip">Latitude • Longitude</div>
            <div class="chip">Real-time results</div>
            <div class="chip">Optimized for large datasets</div>
          </div>

          <div class="ctaRow">
            <a class="btn primary" href="#"
               onclick="alert('Add your FREE TRIAL download link here.'); return false;">Download FREE TRIAL</a>
            <a class="btn" href="https://store.payproglobal.com/checkout?products[1][id]=123452" target="_blank" rel="noopener">
              Buy PRO License (1 Year)
            </a>
          </div>

          <p class="note">
            PRO license is valid for <b>1 year</b> and removes limits on the amount of data you can extract.
            (You can edit this text anytime.)
          </p>
        </div>

        <div class="side">
          <div class="card boxshot" aria-label="Boxshot">
            <div class="sectionTitle" style="margin-bottom:10px;">
              <h3>Product Boxshot</h3>
              <p>Professional desktop tool</p>
            </div>
            <img src="https://store.payproglobal.com/Content/files/152994/fastb2b.jpg" alt="B2B Leads Extractor Boxshot" />
            <div class="statGrid">
              <div class="stat">
                <b>Desktop-first</b>
                <span>Work locally and keep your output under your control.</span>
              </div>
              <div class="stat">
                <b>Fast workflow</b>
                <span>Search → extract → export. Minimal setup.</span>
              </div>
              <div class="stat">
                <b>Large lists</b>
                <span>Designed to stay responsive even with thousands of leads.</span>
              </div>
              <div class="stat">
                <b>Optional enrichment</b>
                <span>Email discovery from websites & contact pages (when available).</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <section id="features">
        <div class="sectionTitle">
          <h3>Key Features</h3>
          <p>Everything you need to build an export-ready B2B lead list.</p>
        </div>

        <div class="grid3">
          <div class="tile">
            <h4>Search by category & location</h4>
            <p>Run targeted searches and collect business listings into a structured table.</p>
          </div>
          <div class="tile">
            <h4>Real-time results table</h4>
            <p>Watch leads appear while extraction runs, then review, filter, and export.</p>
          </div>
          <div class="tile">
            <h4>Core business fields</h4>
            <p>Business name, address, phone, website, coordinates, and rating (when available).</p>
          </div>
          <div class="tile">
            <h4>Optional email discovery</h4>
            <p>Scans websites and contact pages to locate publicly listed email addresses.</p>
          </div>
          <div class="tile">
            <h4>Export-ready output</h4>
            <p>Save results to common formats for spreadsheets, CRMs, and analysis workflows.</p>
          </div>
          <div class="tile">
            <h4>Designed for large datasets</h4>
            <p>Optimized to remain usable and stable while collecting thousands of records.</p>
          </div>
        </div>

        <div style="margin-top:14px;" class="callout">
          <b>Responsible use</b>
          <small>
            This software is intended to collect <b>publicly available</b> business information. Users are responsible for complying
            with applicable laws, website terms, and privacy requirements.
          </small>
        </div>
      </section>

      <section id="screenshots">
        <div class="sectionTitle">
          <h3>Screenshots</h3>
          <p>Step-by-step usage examples (you can add more images later).</p>
        </div>

        <div class="steps">
          <div class="shot">
            <img src="https://b2b-leads-extractor.github.io/b1.png" alt="Step 1 — Add location" />
            <div class="cap">Step 1 — Add location</div>
          </div>
          <div class="shot">
            <img src="https://b2b-leads-extractor.github.io/b2.png" alt="Step 2 — Real-time results table" />
            <div class="cap">Step 2 — Results are displayed in real time</div>
          </div>
          <div class="shot">
            <img src="https://b2b-leads-extractor.github.io/b3.png" alt="Step 3 — Four steps overview" />
            <div class="cap">Step 3 — Follow the 4 steps to use the program</div>
          </div>
        </div>
      </section>

      <section id="pricing">
        <div class="sectionTitle">
          <h3>FREE TRIAL & PRO License</h3>
          <p>Choose the option that fits your workflow.</p>
        </div>

        <div class="pricing">
          <div class="plan">
            <h4>FREE TRIAL (Download)</h4>
            <div class="tag">Try before you buy</div>
            <ul>
              <li>Install and test the software on your PC</li>
              <li>See real-time extraction and exported data format</li>
              <li>Some limitations may apply (you can edit this text)</li>
            </ul>
            <div style="margin-top:14px;">
              <a class="btn primary" href="#"
                 onclick="alert('Add your FREE TRIAL download link here.'); return false;">Download FREE TRIAL</a>
            </div>
          </div>

          <div class="plan">
            <h4>PRO License (1 Year)</h4>
            <div class="tag">Unlimited data extraction</div>
            <ul>
              <li>Valid for <b>1 year</b></li>
              <li><b>No limits</b> on the amount of data you can extract</li>
              <li>Ideal for heavy usage and large lead lists</li>
            </ul>
            <div style="margin-top:14px;">
              <a class="btn primary" href="https://store.payproglobal.com/checkout?products[1][id]=123452" target="_blank" rel="noopener">
                Buy PRO License
              </a>
            </div>
          </div>
        </div>
      </section>

      <section id="faq" class="faq">
        <div class="sectionTitle">
          <h3>FAQ</h3>
          <p>Quick answers to common questions.</p>
        </div>

        <details>
          <summary>What data can B2B Leads Extractor collect?</summary>
          <p>
            It can collect business name, address, phone number, website, latitude/longitude, and rating when available.
            Available fields depend on what is publicly displayed by the source.
          </p>
        </details>

        <details>
          <summary>Does the PRO license remove extraction limits?</summary>
          <p>
            Yes. The PRO license (valid for 1 year) removes limits on the amount of data you can extract.
          </p>
        </details>

        <details>
          <summary>Can it find email addresses?</summary>
          <p>
            If enabled, the software can scan business websites and typical contact pages to locate publicly listed email addresses.
            Some websites do not publish emails or hide them behind forms.
          </p>
        </details>

        <details>
          <summary>Can I extract thousands of leads?</summary>
          <p>
            Yes. The software is optimized to remain responsive while processing large lists and displaying results in the table.
          </p>
        </details>
      </section>

      <section id="contact">
        <div class="sectionTitle">
          <h3>Support</h3>
          <p>Replace this section with your real support details.</p>
        </div>

        <div class="grid2">
          <div class="tile">
            <h4>Contact</h4>
            <p>
              <span style="color:var(--muted);">Email:</span> <a href="mailto:support@example.com">support@example.com</a><br/>
              <span style="color:var(--muted);">Website:</span> <a href="#" onclick="alert('Replace with your website URL.'); return false;">your-website.com</a>
            </p>
          </div>
          <div class="tile">
            <h4>Notes</h4>
            <p>
              You can add screenshots, feature highlights, and a short tutorial video in this page later.
            </p>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div><b>B2B Leads Extractor</b> — Desktop lead collection software.</div>
      <div>© <span id="year"></span> Your Company. All rights reserved.</div>
      <script>document.getElementById('year').textContent = new Date().getFullYear();</script>
    </footer>
  </div>
</body>
</html>
