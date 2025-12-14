<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ancient Greece — Summary & source</title>
  <style>
    :root{
      --bg:#f7f7fb; --card:#fff; --accent:#0b64b6;
      --muted:#666; font-family:system-ui,-apple-system,Segoe UI,Roboto,"Helvetica Neue",Arial;
    }
    body{margin:0;background:var(--bg);color:#111}
    header{background:linear-gradient(90deg,rgba(11,100,182,0.12),transparent);padding:28px 20px}
    .container{max-width:900px;margin:22px auto;padding:18px}
    .card{background:var(--card);border-radius:12px;box-shadow:0 6px 20px rgba(18,22,38,0.06);padding:20px}
    h1{margin:0 0 8px;font-size:1.4rem;color:var(--accent)}
    p.lead{margin:0 0 12px;color:var(--muted)}
    .buttons{display:flex;gap:8px;margin:14px 0}
    .btn{display:inline-block;padding:8px 12px;border-radius:8px;text-decoration:none;border:1px solid rgba(11,100,182,0.12);background:#fff;color:var(--accent);font-weight:600}
    .btn.secondary{background:transparent;border:1px solid #ddd;color:#333}
    .source{font-size:0.9rem;color:var(--muted);margin-top:12px}
    .iframe-wrap{margin-top:18px;border-radius:10px;overflow:hidden;border:1px solid #eee}
    iframe{width:100%;height:500px;border:0}
    footer{max-width:900px;margin:18px auto;text-align:center;color:var(--muted);font-size:0.85rem}
    pre{background:#111;color:#fff;padding:12px;border-radius:8px;overflow:auto}
  </style>
</head>
<body>
  <header>
    <div class="container card" style="display:flex;align-items:center;gap:14px">
      <div>
        <h1>Ancient Greece — short summary</h1>
        <p class="lead">A concise, original paraphrase of Britannica's article (linked below).</p>
      </div>
    </div>
  </header>

  <main class="container">
    <section class="card">
      <h2>What ancient Greece was (short)</h2>
      <p>
        Ancient Greece refers to the civilizations developed on the Greek mainland, islands, and coastlines
        from the Bronze Age through the classical and Hellenistic periods. It is notable for the formation
        of city-states (poleis) such as Athens and Sparta, early experiments with democracy, major advances
        in philosophy, literature, drama, history, architecture, and scientific thought, and for wide-ranging
        cultural influence throughout the Mediterranean and Near East during and after the era of Alexander
        the Great.
      </p>
      <p class="source">
        Source: Britannica — <a href="https://www.britannica.com/place/ancient-Greece" target="_blank" rel="noopener noreferrer">Ancient Greek civilization</a>. :contentReference[oaicite:1]{index=1}
      </p>

      <div class="buttons">
        <a class="btn" href="https://www.britannica.com/place/ancient-Greece" target="_blank" rel="noopener noreferrer">Open original on Britannica</a>
        <a class="btn secondary" id="tryEmbed" href="#">Try embed (may be blocked)</a>
        <a class="btn secondary" href="#citation">View citation</a>
      </div>

      <div id="embedArea" class="iframe-wrap" style="display:none">
        <iframe id="remoteFrame" src="https://www.britannica.com/place/ancient-Greece" title="Britannica: Ancient Greece"></iframe>
      </div>

      <div id="embedBlockedNote" style="display:none;margin-top:12px;color:#b00">
        Embedding the page failed — many sites (including Britannica) disallow embedding for copyright/technical reasons.
        Use the "Open original" button above to visit the source.
      </div>
    </section>

    <section class="card" style="margin-top:14px">
      <h3 id="citation">How to cite / request permission</h3>
      <ol>
        <li>Always link directly to the original article and credit the author and publisher.</li>
        <li>If you need substantial reproductions (e.g., full article or multiple images), contact Britannica for permission or look for a licensing API on the publisher site.</li>
        <li>For classroom use, check your institution's library license or use open educational resources (Khan Academy, LibreTexts, etc.).</li>
      </ol>
      <p class="source">Britannica article page used as source for topic and structure. :contentReference[oaicite:2]{index=2}</p>
    </section>

    <section class="card" style="margin-top:14px">
      <h3>Developer note (attempted embedding)</h3>
      <p style="margin:0 0 8px;color:var(--muted)">
        The "Try embed" button below will try to show the live page in an iframe. If the frame is blocked,
        the page will show a message instead. This is only an attempt to *view* the original; it does not
        copy or store the article.
      </p>

      <div style="display:flex;gap:8px">
        <button id="doEmbed" class="btn">Try embed now</button>
        <button id="removeEmbed" class="btn secondary">Remove embed</button>
      </div>

      <pre id="debug" style="display:none"></pre>
    </section>

  </main>

  <footer>
    <div>Prepared as a summary and navigator to the original Britannica page. For full article see Britannica.</div>
  </footer>

  <script>
    document.getElementById('doEmbed').addEventListener('click', function(){
      const area = document.getElementById('embedArea');
      const blockedNote = document.getElementById('embedBlockedNote');
      area.style.display = 'block';
      blockedNote.style.display = 'none';
      const iframe = document.getElementById('remoteFrame');
      setTimeout(function(){
        try {
          const win = iframe.contentWindow;
          if (win && win.location && win.location.href) {}
        } catch(e){
          blockedNote.style.display = 'block';
        }
      }, 900);
    });

    document.getElementById('removeEmbed').addEventListener('click', function(){
      document.getElementById('embedArea').style.display = 'none';
      document.getElementById('embedBlockedNote').style.display = 'none';
    });

    document.getElementById('tryEmbed').addEventListener('click', function(e){
      e.preventDefault();
      document.getElementById('doEmbed').click();
    });
  </script>
</body>
</html>
