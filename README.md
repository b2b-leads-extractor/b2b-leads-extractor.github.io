<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>B2B Leads Extractor — Desktop Lead Collection Software</title>
  <meta name="description" content="B2B Leads Extractor is a desktop software to collect publicly available business information from online map listings and directories, organized in a fast, export-ready table." />
  <style>
    :root{
      --bg: #0b1220;
      --bg2:#0f1a30;
      --card:#111c34;
      --card2:#0f1930;
      --text:#e7eefc;
      --muted:#a7b3cf;
      --line: rgba(255,255,255,.08);
      --accent:#63b3ff;
      --accent2:#7cffd1;
      --danger:#ff6b6b;
      --shadow: 0 10px 40px rgba(0,0,0,.45);
      --radius: 18px;
      --radius2: 24px;
      --max: 1100px;
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
        radial-gradient(1200px 700px at 10% 0%, rgba(99,179,255,.18), transparent 60%),
        radial-gradient(1000px 650px at 85% 10%, rgba(124,255,209,.14), transparent 55%),
        linear-gradient(180deg, var(--bg), var(--bg2));
      letter-spacing:.2px;
    }
    a{color:inherit}
    .wrap{max-width:var(--max); margin:0 auto; padding:24px;}
    .topbar{
      display:flex; align-items:center; justify-content:space-between;
      gap:16px; padding:14px 18px; border:1px solid var(--line);
      background:rgba(17,28,52,.6); backdrop-filter: blur(10px);
      border-radius:var(--radius2); box-shadow: var(--shadow);
      position:sticky; top:16px; z-index:20;
    }
    .brand{display:flex; align-items:center; gap:12px; min-width: 220px;}
    .logo{
      width:38px; height:38px; border-radius:12px;
      background:
        radial-gradient(circle at 30% 30%, rgba(99,179,255,.9), transparent 55%),
        radial-gradient(circle at 70% 70%, rgba(124,255,209,.8), transparent 55%),
        linear-gradient(135deg, rgba(255,255,255,.08), rgba(255,255,255,.02));
      border:1px solid rgba(255,255,255,.10);
      box-shadow: 0 12px 26px rgba(0,0,0,.35);
    }
    .brand h1{font-size:14px; margin:0; font-weight:800; letter-spacing:.6px}
    .brand p{margin:2px 0 0; font-size:12px; color:var(--muted)}
    .nav{display:flex; gap:10px; flex-wrap:wrap; justify-content:flex-end}
    .nav a{
      text-decoration:none; font-size:12px; color:var(--muted);
      padding:8px 10px; border-radius:12px; border:1px solid transparent;
    }
    .nav a:hover{border-color:var(--line); color:var(--text); background: rgba(255,255,255,.03);}
    .btn{
      display:inline-flex; align-items:center; justify-content:center; gap:10px;
      padding:12px 14px; border-radius:14px; border:1px solid rgba(255,255,255,.10);
      background:rgba(255,255,255,.04);
      color:var(--text); text-decoration:none; font-weight:700; font-size:13px;
      transition: transform .08s ease, border-color .12s ease, background .12s ease;
      user-select:none;
    }
    .btn:hover{transform: translateY(-1px); border-color: rgba(99,179,255,.35); background: rgba(99,179,255,.10);}
    .btn.primary{
      background: linear-gradient(135deg, rgba(99,179,255,.95), rgba(124,255,209,.75));
      color:#06101b; border:0;
      box-shadow: 0 18px 30px rgba(99,179,255,.20);
    }
    .btn.primary:hover{transform: translateY(-1px); filter:brightness(1.02)}
    .hero{
      padding:44px 0 20px;
      display:grid; grid-template-columns: 1.2fr .8fr; gap:24px; align-items:stretch;
    }
    .card{
      border:1px solid var(--line);
      background: rgba(17,28,52,.55);
      border-radius:var(--radius2);
      box-shadow: var(--shadow);
      padding:22px;
      backdrop-filter: blur(12px);
    }
    .hero h2{
      font-size:38px; line-height:1.1; margin:0 0 12px; letter-spacing:.4px;
    }
    .hero .sub{
      color:var(--muted); font-size:15px; line-height:1.6; margin:0 0 18px;
    }
    .chips{display:flex; flex-wrap:wrap; gap:10px; margin: 16px 0 18px;}
    .chip{
      font-size:12px; color: rgba(231,238,252,.92);
      padding:8px 10px; border-radius:999px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.03);
    }
    .ctaRow{display:flex; gap:12px; flex-wrap:wrap; align-items:center; margin-top: 18px;}
    .note{font-size:12px; color:var(--muted); margin-top:10px;}
    .side{
      display:flex; flex-direction:column; gap:16px;
    }
    .statGrid{display:grid; grid-template-columns: 1fr 1fr; gap:12px;}
    .stat{
      padding:14px; border-radius:16px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(15,25,48,.65);
    }
    .stat b{display:block; font-size:16px;}
    .stat span{display:block; margin-top:6px; font-size:12px; color:var(--muted); line-height:1.45;}
    .preview{
      position:relative;
      border-radius:20px;
      border:1px dashed rgba(255,255,255,.18);
      background:
        radial-gradient(500px 220px at 20% 20%, rgba(99,179,255,.18), transparent 60%),
        radial-gradient(500px 240px at 85% 20%, rgba(124,255,209,.12), transparent 60%),
        rgba(15,25,48,.55);
      min-height: 230px;
      display:flex; align-items:center; justify-content:center; text-align:center;
      padding:18px;
      overflow:hidden;
    }
    .preview .ph{
      max-width: 320px;
      font-size:12px;
      color: var(--muted);
      line-height:1.6;
    }
    .preview code{
      font-family: var(--mono);
      font-size: 11px;
      color: rgba(231,238,252,.95);
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(255,255,255,.08);
      padding: 3px 6px;
      border-radius: 8px;
    }
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
      background: rgba(17,28,52,.42);
      border-radius:var(--radius);
      padding:16px;
    }
    .tile h4{margin:0 0 8px; font-size:14px}
    .tile p{margin:0; color:var(--muted); font-size:13px; line-height:1.6}
    .list{
      margin: 10px 0 0;
      padding:0;
      list-style:none;
      display:flex; flex-direction:column; gap:10px;
    }
    .li{
      display:flex; gap:10px; align-items:flex-start;
      padding:12px 12px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(15,25,48,.55);
      border-radius: 14px;
    }
    .dot{
      width:10px; height:10px; border-radius:999px; margin-top:4px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      box-shadow: 0 0 0 4px rgba(99,179,255,.14);
      flex: 0 0 auto;
    }
    .li b{display:block; font-size:13px}
    .li span{display:block; color:var(--muted); font-size:12.5px; line-height:1.55; margin-top:4px}
    .kbd{
      font-family: var(--mono);
      font-size: 11px;
      border:1px solid rgba(255,255,255,.10);
      padding:3px 6px;
      border-radius: 8px;
      background: rgba(255,255,255,.04);
      color: rgba(231,238,252,.95);
      display:inline-block;
      margin: 0 3px;
    }
    .callout{
      border:1px solid rgba(99,179,255,.20);
      background: rgba(99,179,255,.08);
      border-radius: var(--radius2);
      padding: 16px;
      color: rgba(231,238,252,.95);
    }
    .callout small{display:block; color: rgba(231,238,252,.82); margin-top:8px; line-height:1.6}
    .faq details{
      border:1px solid rgba(255,255,255,.08);
      background: rgba(15,25,48,.55);
      border-radius: 14px;
      padding: 12px 14px;
    }
    .faq details + details{margin-top:10px;}
    summary{cursor:pointer; font-weight:700; font-size:13px}
    .faq p{margin: 10px 0 0; color: var(--muted); font-size:13px; line-height:1.6;}
    footer{
      margin: 22px 0 28px;
      padding: 18px 0 0;
      border-top: 1px solid var(--line);
      color: var(--muted);
      font-size: 12px;
      line-height:1.6;
    }
    .badgeRow{display:flex; gap:10px; flex-wrap:wrap; margin-top:12px;}
    .badge{
      font-size:12px;
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.03);
      padding:8px 10px;
      border-radius: 999px;
      color: rgba(231,238,252,.92);
    }
    .twoCol{
      display:grid; grid-template-columns: 1fr 1fr; gap: 14px;
    }
    .muted{color:var(--muted)}
    @media (max-width: 980px){
      .hero{grid-template-columns: 1fr; padding-top: 24px;}
      .grid3{grid-template-columns: 1fr;}
      .grid2{grid-template-columns: 1fr;}
      .twoCol{grid-template-columns: 1fr;}
      .topbar{position:relative; top:auto;}
      .brand{min-width: unset;}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header class="topbar">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <h1>B2B Leads Extractor</h1>
          <p>Desktop lead collection • fast, structured, export-ready</p>
        </div>
      </div>
      <nav class="nav" aria-label="Page navigation">
        <a href="#features">Features</a>
        <a href="#how">How it works</a>
        <a href="#email">Email discovery</a>
        <a href="#performance">Performance</a>
        <a href="#faq">FAQ</a>
      </nav>
      <div style="display:flex; gap:10px; flex-wrap:wrap;">
        <a class="btn" href="#screenshots">Screenshots</a>
        <a class="btn primary" href="#download">Download</a>
      </div>
    </header>

    <main>
      <div class="hero">
        <div class="card">
          <h2>Collect business leads<br/>in a structured table — fast.</h2>
          <p class="sub">
            <b>B2B Leads Extractor</b> is a desktop software designed to collect <b>publicly available</b> business information
            from online map listings and directories. Results are organized in a clean table for quick review, filtering and export.
          </p>

          <div class="chips" aria-label="Highlights">
            <div class="chip">Business name • Address • Phone</div>
            <div class="chip">Website • Rating (when available)</div>
            <div class="chip">Latitude • Longitude</div>
            <div class="chip">Fast progressive extraction</div>
            <div class="chip">Optimized for large datasets</div>
          </div>

          <div class="ctaRow" id="download">
            <a class="btn primary" href="#" onclick="alert('Replace this link with your download URL.'); return false;">Download for Windows</a>
            <a class="btn" href="#" onclick="alert('Replace this link with your purchase/upgrade URL (optional).'); return false;">Upgrade / License</a>
          </div>

          <p class="note">
            Tip: add your real links above. You can also replace the hero text with your final branding (e.g. “Fast B2B Leads Extractor”).
          </p>
        </div>

        <div class="side">
          <div class="card">
            <div class="sectionTitle" style="margin-bottom:10px;">
              <h3>Built for real-world work</h3>
              <p>Stable • responsive • export-ready</p>
            </div>

            <div class="statGrid">
              <div class="stat">
                <b>Desktop-first</b>
                <span>Your data stays local. No browser extensions required.</span>
              </div>
              <div class="stat">
                <b>Structured output</b>
                <span>Organized fields ready for CRM, Excel, or analysis.</span>
              </div>
              <div class="stat">
                <b>Large lists</b>
                <span>Designed to handle large volumes of results smoothly.</span>
              </div>
              <div class="stat">
                <b>Optional enrichment</b>
                <span>Find public emails from websites and contact pages.</span>
              </div>
            </div>

            <div class="badgeRow" aria-label="Badges">
              <div class="badge">Windows Desktop</div>
              <div class="badge">CSV / TXT export</div>
              <div class="badge">Category + Location search</div>
            </div>
          </div>

          <div class="preview" id="screenshots">
            <div class="ph">
              <b>Screenshot placeholder</b><br/>
              Drop your images here later.<br/><br/>
              Suggested sizes: <code>1200×750</code> or <code>1600×900</code><br/>
              Add multiple screenshots or a carousel.
            </div>
          </div>
        </div>
      </div>

      <section id="features">
        <div class="sectionTitle">
          <h3>Key Features</h3>
          <p>Everything you need to build a usable B2B lead list.</p>
        </div>

        <div class="grid3">
          <div class="tile">
            <h4>Smart search by category & location</h4>
            <p>Run targeted searches (e.g., “restaurants in Rome”) and collect business listings into a structured table.</p>
          </div>
          <div class="tile">
            <h4>Core business fields extracted</h4>
            <p>Business name, address, phone number, website, rating (when available), plus coordinates for mapping or geo analysis.</p>
          </div>
          <div class="tile">
            <h4>Progressive extraction</h4>
            <p>Results appear as they are collected, so you can monitor progress and review data immediately.</p>
          </div>
          <div class="tile">
            <h4>Export-ready output</h4>
            <p>Export your results to common formats for Excel, Google Sheets, CRMs and custom pipelines.</p>
          </div>
          <div class="tile">
            <h4>Optional email discovery</h4>
            <p>Scan business websites and contact pages to locate publicly listed email addresses (where available).</p>
          </div>
          <div class="tile">
            <h4>Designed for large datasets</h4>
            <p>Optimized UI behavior to keep the app responsive while collecting thousands of leads.</p>
          </div>
        </div>

        <div style="margin-top:14px;" class="callout">
          <b>What makes it different?</b>
          <small>
            B2B Leads Extractor is a desktop tool focused on speed and reliability. It gathers publicly available business data,
            shows it in a clean grid, and lets you export it immediately — without relying on heavy browser automation.
          </small>
        </div>
      </section>

      <section id="how">
        <div class="sectionTitle">
          <h3>How It Works</h3>
          <p>Simple workflow, minimal setup.</p>
        </div>

        <ul class="list">
          <li class="li">
            <span class="dot" aria-hidden="true"></span>
            <div>
              <b>1) Select a category and location</b>
              <span>Choose what you need to search (industry/category) and where (city/area/country).</span>
            </div>
          </li>
          <li class="li">
            <span class="dot" aria-hidden="true"></span>
            <div>
              <b>2) Start extraction</b>
              <span>The app collects publicly available business listings and adds them to the results table progressively.</span>
            </div>
          </li>
          <li class="li">
            <span class="dot" aria-hidden="true"></span>
            <div>
              <b>3) Review and export</b>
              <span>Scan your leads in the table and export in your preferred format for outreach, research, or analysis.</span>
            </div>
          </li>
        </ul>
      </section>

      <section id="email">
        <div class="sectionTitle">
          <h3>Optional Email Discovery</h3>
          <p>Enrich leads when websites publish contact emails.</p>
        </div>

        <div class="twoCol">
          <div class="tile">
            <h4>What it does</h4>
            <p>
              When enabled, the software can visit the business website and look for publicly listed email addresses,
              including common “contact” pages (e.g., <span class="kbd">contact</span>, <span class="kbd">contatti</span>, <span class="kbd">kontakt</span>).
            </p>
          </div>
          <div class="tile">
            <h4>Notes</h4>
            <p>
              Email discovery depends on what a website publishes. Some sites do not display emails or hide them behind forms.
              The feature focuses on fast scanning and avoiding long waits on slow websites.
            </p>
          </div>
        </div>
      </section>

      <section id="performance">
        <div class="sectionTitle">
          <h3>Performance & Stability</h3>
          <p>Responsive UI and reliable processing with large lists.</p>
        </div>

        <div class="grid2">
          <div class="tile">
            <h4>Optimized for large volumes</h4>
            <p>Designed to handle large extraction sessions and maintain stability while results grow into thousands of rows.</p>
          </div>
          <div class="tile">
            <h4>Progressive UI updates</h4>
            <p>Updates are throttled to keep the app responsive, making it easier to move the window and browse results during extraction.</p>
          </div>
        </div>

        <div class="badgeRow" aria-label="System requirements">
          <div class="badge">Windows 10/11</div>
          <div class="badge">.NET Desktop App</div>
          <div class="badge">Recommended: 8GB+ RAM for very large lists</div>
        </div>
      </section>

      <section id="usecases">
        <div class="sectionTitle">
          <h3>Who It’s For</h3>
          <p>Built for professionals who need structured data quickly.</p>
        </div>

        <div class="grid3">
          <div class="tile">
            <h4>Sales teams</h4>
            <p>Build target lists by category and region, export to your CRM, and plan outreach.</p>
          </div>
          <div class="tile">
            <h4>Agencies</h4>
            <p>Collect leads for clients, segment by location and industry, and run market research.</p>
          </div>
          <div class="tile">
            <h4>Marketers & analysts</h4>
            <p>Create datasets for analysis, competitors mapping, and business intelligence.</p>
          </div>
        </div>
      </section>

      <section id="compliance">
        <div class="sectionTitle">
          <h3>Responsible Use</h3>
          <p>Keep your workflow compliant and respectful.</p>
        </div>

        <div class="callout" style="border-color: rgba(255,255,255,.12); background: rgba(255,255,255,.04);">
          <b>Important</b>
          <small>
            B2B Leads Extractor is intended to collect <b>publicly available</b> business information. Users are responsible for complying with
            applicable laws, website terms, and privacy requirements in their country and industry. Always use collected data ethically.
          </small>
        </div>
      </section>

      <section id="faq" class="faq">
        <div class="sectionTitle">
          <h3>FAQ</h3>
          <p>Quick answers for common questions.</p>
        </div>

        <details>
          <summary>What data can the software extract?</summary>
          <p>It can extract business name, address, phone number, website, rating (when available), and geographic coordinates. Fields may vary depending on what is publicly displayed.</p>
        </details>

        <details>
          <summary>Does it work without a browser?</summary>
          <p>Yes. It’s a desktop application designed to collect data and present it in a local results table without requiring browser extensions.</p>
        </details>

        <details>
          <summary>Can it find emails automatically?</summary>
          <p>The optional email discovery feature scans business websites for publicly listed emails, including typical contact pages. It will not find emails that are not published or are hidden behind forms.</p>
        </details>

        <details>
          <summary>Can I handle thousands of leads?</summary>
          <p>Yes. The UI is designed to remain usable during extraction, and exports are optimized for structured output. For extremely large lists, using export and external tools (Excel/CRM) is recommended.</p>
        </details>
      </section>

      <section id="contact">
        <div class="sectionTitle">
          <h3>Contact & Support</h3>
          <p>Replace the details below with your own.</p>
        </div>

        <div class="twoCol">
          <div class="tile">
            <h4>Support</h4>
            <p class="muted">
              Email: <a href="mailto:support@example.com">support@example.com</a><br/>
              Website: <a href="#" onclick="alert('Replace with your website URL.'); return false;">your-website.com</a>
            </p>
          </div>
          <div class="tile">
            <h4>License</h4>
            <p class="muted">
              Add your license info here (Free / Pro, trial limitations, upgrade link, etc.).
            </p>
          </div>
        </div>
      </section>
    </main>

    <footer>
      <div><b>B2B Leads Extractor</b> — Desktop lead collection software.</div>
      <div>© <span id="year"></span> Your Company. All rights reserved.</div>
      <script>
        document.getElementById('year').textContent = new Date().getFullYear();
      </script>
    </footer>
  </div>
</body>
</html>
