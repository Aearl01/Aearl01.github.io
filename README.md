# Aearl01.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TBH + Rate</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      background: #f5f4f0;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 2rem 1rem;
    }

    .card {
      background: #ffffff;
      border-radius: 16px;
      border: 0.5px solid rgba(0,0,0,0.12);
      padding: 2rem;
      width: 100%;
      max-width: 460px;
      box-shadow: 0 2px 16px rgba(0,0,0,0.06);
    }

    .title {
      font-size: 24px;
      font-weight: 600;
      color: #111;
      margin-bottom: 4px;
    }

    .sub {
      font-size: 14px;
      color: #888;
      margin-bottom: 1.75rem;
    }

    .field {
      margin-bottom: 1rem;
    }

    .field label {
      display: block;
      font-size: 13px;
      color: #666;
      margin-bottom: 6px;
      font-weight: 500;
    }

    .field input {
      width: 100%;
      padding: 10px 14px;
      font-size: 15px;
      border: 0.5px solid rgba(0,0,0,0.2);
      border-radius: 10px;
      outline: none;
      color: #111;
      background: #fff;
      transition: border-color 0.15s;
      font-family: inherit;
    }

    .field input:focus {
      border-color: rgba(0,0,0,0.45);
      box-shadow: 0 0 0 3px rgba(0,0,0,0.06);
    }

    .btn {
      width: 100%;
      margin-top: 0.75rem;
      padding: 12px;
      font-size: 15px;
      cursor: pointer;
      border-radius: 10px;
      background: #111;
      border: none;
      color: #fff;
      font-weight: 500;
      font-family: inherit;
      transition: background 0.15s, transform 0.1s;
    }

    .btn:hover { background: #333; }
    .btn:active { transform: scale(0.98); }

    .result {
      display: none;
      margin-top: 1.75rem;
      border-top: 0.5px solid rgba(0,0,0,0.1);
      padding-top: 1.75rem;
      animation: fadeIn 0.3s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(6px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .section-label {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #aaa;
      margin-bottom: 8px;
    }

    .tbh-text {
      font-size: 17px;
      color: #111;
      line-height: 1.6;
      margin-bottom: 1.5rem;
      background: #f5f4f0;
      border-radius: 10px;
      padding: 14px 16px;
    }

    .rate-row {
      display: flex;
      align-items: baseline;
      gap: 8px;
      margin-bottom: 8px;
    }

    .rate-num {
      font-size: 56px;
      font-weight: 700;
      color: #111;
      line-height: 1;
    }

    .rate-denom {
      font-size: 22px;
      color: #aaa;
      font-weight: 400;
    }

    .hearts {
      font-size: 22px;
      margin-top: 4px;
    }

    .reset-btn {
      margin-top: 1.25rem;
      width: 100%;
      padding: 10px;
      font-size: 14px;
      cursor: pointer;
      border-radius: 10px;
      background: transparent;
      border: 0.5px solid rgba(0,0,0,0.2);
      color: #666;
      font-family: inherit;
      transition: background 0.15s;
    }

    .reset-btn:hover { background: #f5f4f0; }
  </style>
</head>
<body>

<div class="card">
  <p class="title">TBH + Rate </p>
  <p class="sub">Enter your info to get your honest rating</p>

  <div id="formSection">
    <div class="field">
      <label for="nameInput">Your name</label>
      <input type="text" id="nameInput" placeholder="e.g. Emilee" />
    </div>
    <div class="field">
      <label for="bdayInput">Your birthday</label>
      <input type="date" id="bdayInput" placeholder="e.g. 08/13/2004"/>
    </div>
    <button class="btn" onclick="generate()">Get my TBH + rate →</button>
  </div>

  <div class="result" id="result">
    <p class="section-label">TBH</p>
    <p class="tbh-text" id="tbhText"></p>
    <p class="section-label">Rating</p>
    <div class="rate-row">
      <span class="rate-num">67</span>
      <span class="rate-denom">/ 10</span>
    </div>
    <div class="hearts">💨💨💨😭😭😭😂</div>
    <button class="reset-btn" onclick="reset()">← Try another name</button>
  </div>
</div>

<script>
  function generate() {
    const name = document.getElementById('nameInput').value.trim();
    const bday = document.getElementById('bdayInput').value;
    if (!name || !bday) {
      alert('Please enter both your name and birthday!');
      return;
    }
    document.getElementById('tbhText').textContent =
      'TBH ' + name + 'You lowk be rippin ahh like fuh twin but I fw you and I hope you dont block my bitch ahh';
    document.getElementById('result').style.display = 'block';
    document.getElementById('result').scrollIntoView({ behavior: 'smooth', block: 'nearest' });
  }

  function reset() {
    document.getElementById('nameInput').value = '';
    document.getElementById('bdayInput').value = '';
    document.getElementById('result').style.display = 'none';
    document.getElementById('nameInput').focus();
  }

  document.addEventListener('keydown', function(e) {
    if (e.key === 'Enter') generate();
  });
</script>

</body>
</html>
