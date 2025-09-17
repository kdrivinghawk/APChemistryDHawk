<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Virtual Lab — Molar Mass of a Volatile Liquid (Dumas-like)</title>
  <style>
    :root{font-family:system-ui,-apple-system,Segoe UI,Roboto,'Helvetica Neue',Arial;line-height:1.4}
    body{padding:18px;max-width:980px;margin:0 auto;color:#111}
    header{display:flex;gap:18px;align-items:center}
    h1{font-size:1.4rem;margin:0}
    .grid{display:grid;grid-template-columns:1fr 360px;gap:18px;margin-top:14px}
    .card{border:1px solid #ddd;padding:12px;border-radius:8px;background:#fff}
    label{display:block;font-size:0.9rem;margin-top:8px}
    input[type=number],select,input[type=text],textarea{width:100%;padding:8px;margin-top:6px;border-radius:6px;border:1px solid #ccc}
    button{padding:8px 12px;border-radius:8px;border:none;background:#0b66ff;color:white;cursor:pointer}
    button.secondary{background:#6b7280}
    .controls{display:flex;gap:8px;flex-wrap:wrap;margin-top:10px}
    .diagram{height:260px;background:linear-gradient(180deg,#f8fafc,#fff);display:flex;align-items:center;justify-content:center;border-radius:6px}
    .log{height:120px;overflow:auto;font-family:monospace;background:#0f172a;color:#c7d2fe;padding:8px;border-radius:6px}
    table{width:100%;border-collapse:collapse;margin-top:8px}
    th,td{padding:6px;border:1px solid #eee;text-align:left}
    .result{font-weight:700;font-size:1.2rem;margin-top:8px}
    .hint{font-size:0.9rem;color:#374151}
    footer{margin-top:18px;font-size:0.9rem;color:#374151}
  </style>
</head>
<body>
  <header>
    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='56' height='56' viewBox='0 0 24 24' fill='none' stroke='%230b66ff' stroke-width='1.5'><path d='M12 2v6'></path><path d='M9 8h6'></path><path d='M7 12h10'></path><path d='M5 16h14'></path><circle cx='12' cy='18' r='2'></circle></svg>" alt="lab icon" style="width:56px;height:56px">
    <div>
      <h1>Virtual Lab — Heating a Volatile Liquid (Make-up / Online Version)</h1>
      <div class="hint">Simulate the Dumas method: heat a liquid in a flask, collect vapor volume at temperature and pressure, calculate molar mass.</div>
    </div>
  </header>

  <div class="grid">
    <section class="card">
      <h2>Simulation</h2>
      <div class="diagram" id="diagram">
        <!-- Simple SVG apparatus -->
        <svg width="320" height="220" viewBox="0 0 320 220" xmlns="http://www.w3.org/2000/svg">
          <rect x="20" y="10" width="280" height="200" rx="8" fill="#eef2ff" stroke="#c7d2fe"/>
          <!-- water bath -->
          <rect x="34" y="140" width="150" height="60" rx="6" fill="#e6f7ff" stroke="#93c5fd"/>
          <text x="45" y="160" font-size="12" fill="#0f172a">Water bath</text>
          <!-- flask -->
          <g id="flask" transform="translate(210,78)">
            <path d="M-28 90 q22 -80 56 0 z" fill="#fff" stroke="#111"/>
            <rect x="-6" y="-20" width="12" height="40" fill="#fff" stroke="#111"/>
            <text x="-30" y="110" font-size="12">Evaporating flask</text>
          </g>
          <!-- thermometer -->
          <rect x="76" y="30" width="10" height="80" rx="6" fill="#fff" stroke="#111"/>
          <circle cx="81" cy="120" r="12" fill="#fff" stroke="#111"/>
          <text x="62" y="25" font-size="12">Thermometer</text>
        </svg>
      </div>

      <label for="compound">Choose sample (teacher provides unknown for make-up)</label>
      <select id="compound">
        <option value="ethanol" data-mm="46.07">Ethanol (C2H6O)</option>
        <option value="acetone" data-mm="58.08">Acetone (C3H6O)</option>
        <option value="diethyl-ether" data-mm="74.12">Diethyl ether (C4H10O)</option>
        <option value="unknown" data-mm="0">Unknown (make-up)</option>
      </select>

      <label>Initial flask + liquid mass (g)</label>
      <input type="number" id="massBefore" step="0.01" value="53.21">

      <label>Final flask mass after heating (g)</label>
      <input type="number" id="massAfter" step="0.01" value="52.15">

      <label>Volume of collected vapor (mL)</label>
      <input type="number" id="vaporVolume" step="0.1" value="135.0">

      <label>Measured temperature of vapor (°C)</label>
      <input type="number" id="tempC" step="0.1" value="98.0">

      <label>Atmospheric pressure (kPa)</label>
      <input type="number" id="pressurekPa" step="0.1" value="101.3">

      <div class="controls">
        <button id="runSim">Run simulation</button>
        <button id="autoFill" class="secondary">Generate make-up dataset</button>
        <button id="calc" class="secondary">Calculate molar mass</button>
        <button id="reset" class="secondary">Reset</button>
      </div>

      <div style="margin-top:10px">
        <div class="result" id="result">Molar mass: —</div>
        <div class="hint">Formula used: n = (P·V) / (R·T) with R = 8.3145 kPa·L·K⁻¹·mol⁻¹ (note units) </div>
      </div>

    </section>

    <aside class="card">
      <h3>Lab Log & Steps</h3>
      <div class="log" id="log">
        Ready. Use <strong>Run simulation</strong> or enter your measured values then press <strong>Calculate molar mass</strong>.
      </div>

      <h4>Guided questions (for make-up)</h4>
      <ol>
        <li>What mass of vapor was produced? (mass loss)</li>
        <li>Convert collected vapor volume to liters.</li>
        <li>Convert temperature to Kelvin.</li>
        <li>Calculate moles using PV = nRT (ensure units: pressure in kPa, volume in L, R=8.3145).</li>
        <li>Compute molar mass = mass_vapor / moles.</li>
      </ol>

      <h4>Student answers / report</h4>
      <label>Your name</label>
      <input type="text" id="studentName" placeholder="First Last">

      <label>Show student report</label>
      <textarea id="report" rows="8" readonly></textarea>

      <div style="margin-top:8px">
        <button id="fillReport">Fill report</button>
        <button id="downloadReport" class="secondary">Download report (txt)</button>
      </div>

    </aside>
  </div>

  <footer>
    <div>How to embed: Host this HTML (GitHub Pages, CodePen, or your web host) and add an &lt;iframe src="[URL]"&gt; into Google Sites: Insert → Embed → Embed code/URL.</div>
  </footer>

  <script>
    // Utility functions
    const el = id => document.getElementById(id);
    const log = msg => { const l = el('log'); l.textContent = new Date().toLocaleTimeString() + ' — ' + msg + '\n' + l.textContent; };

    function calculateMolarMass(values){
      // units: mass in g, V in mL, temp C, pressure in kPa
      const R = 8.3145; // kPa·L·K^-1·mol^-1
      const massVapor = values.massBefore - values.massAfter; // g
      const V_L = values.vaporVolume / 1000.0; // L
      const T_K = values.tempC + 273.15;
      const P_kPa = values.pressurekPa;
      if (massVapor <= 0 || V_L <= 0 || T_K <= 0 || P_kPa <= 0) return {error:'Invalid inputs (non-positive).' };
      const n = (P_kPa * V_L) / (R * T_K);
      const M = massVapor / n; // g/mol
      return {massVapor, V_L, T_K, P_kPa, n, M};
    }

    // Buttons
    el('calc').addEventListener('click', ()=>{
      const values = {
        massBefore: parseFloat(el('massBefore').value),
        massAfter: parseFloat(el('massAfter').value),
        vaporVolume: parseFloat(el('vaporVolume').value),
        tempC: parseFloat(el('tempC').value),
        pressurekPa: parseFloat(el('pressurekPa').value)
      };
      const res = calculateMolarMass(values);
      if (res.error){ el('result').textContent = 'Error: ' + res.error; log('Calculation failed: ' + res.error); return; }
      el('result').textContent = 'Molar mass ≈ ' + res.M.toFixed(2) + ' g·mol⁻¹';
      log(`Calculated molar mass: ${res.M.toFixed(2)} g/mol (mass vapor ${res.massVapor.toFixed(3)} g, n=${res.n.toExponential(3)} mol)`);
    });

    el('runSim').addEventListener('click', ()=>{
      // Simple animation-like simulation: slowly raise temp to boiling (~98-100°C)
      el('runSim').disabled = true; log('Starting heating...');
      let t = parseFloat(el('tempC').value || 20);
      const interval = setInterval(()=>{
        t += Math.random()*3 + 2; // raise by 2-5°C per tick
        el('tempC').value = t.toFixed(1);
        if (t > 97 + Math.random()*3){
          clearInterval(interval);
          // evaporate some liquid to reduce mass and set vapor volume
          const before = parseFloat(el('massBefore').value);
          const loss = (Math.random()*0.8 + 0.8); // 0.8-1.6 g
          el('massAfter').value = (before - loss).toFixed(2);
          el('vaporVolume').value = (100 + Math.random()*60).toFixed(1);
          el('runSim').disabled = false; log('Boiling reached. Vapor collected and mass changed.');
        }
      },600);
    });

    el('autoFill').addEventListener('click', ()=>{
      // Generate make-up dataset with plausible values
      const sampleChoice = el('compound').value;
      let base;
      if (sampleChoice === 'ethanol') base = {mm:46.07};
      else if (sampleChoice === 'acetone') base = {mm:58.08};
      else if (sampleChoice === 'diethyl-ether') base = {mm:74.12};
      else base = {mm: 68.50}; // unknown target

      const massBefore = (50 + Math.random()*10).toFixed(2);
      const massLoss = (0.8 + Math.random()*1.5).toFixed(2);
      const massAfter = (parseFloat(massBefore) - parseFloat(massLoss)).toFixed(2);
      const vaporVolume = (110 + Math.random()*60).toFixed(1);
      const tempC = (95 + Math.random()*4).toFixed(1);
      el('massBefore').value = massBefore;
      el('massAfter').value = massAfter;
      el('vaporVolume').value = vaporVolume;
      el('tempC').value = tempC;
      el('pressurekPa').value = '101.3';
      log('Generated make-up dataset. Instruct students to show calculations.');
    });

    el('reset').addEventListener('click', ()=>{
      el('massBefore').value = '53.21';
      el('massAfter').value = '52.15';
      el('vaporVolume').value = '135.0';
      el('tempC').value = '98.0';
      el('pressurekPa').value = '101.3';
      el('studentName').value = '';
      el('report').value = '';
      el('result').textContent = 'Molar mass: —';
      log('Reset to default values.');
    });

    el('fillReport').addEventListener('click', ()=>{
      // compute and fill report
      const name = el('studentName').value || 'Student';
      const values = {
        massBefore: parseFloat(el('massBefore').value),
        massAfter: parseFloat(el('massAfter').value),
        vaporVolume: parseFloat(el('vaporVolume').value),
        tempC: parseFloat(el('tempC').value),
        pressurekPa: parseFloat(el('pressurekPa').value)
      };
      const res = calculateMolarMass(values);
      if (res.error){ alert('Cannot fill report: ' + res.error); return; }
      const chosen = el('compound').value;
      const knownMM = el('compound').selectedOptions[0].dataset.mm;
      let lines = [];
      lines.push(`Name: ${name}`);
      lines.push(`Sample: ${chosen}`);
      lines.push('---Measurements---');
      lines.push(`Initial flask + liquid mass: ${values.massBefore.toFixed(2)} g`);
      lines.push(`Final flask mass: ${values.massAfter.toFixed(2)} g`);
      lines.push(`Mass of vapor = mass loss = ${(res.massVapor).toFixed(3)} g`);
      lines.push(`Volume of vapor (collected): ${values.vaporVolume.toFixed(2)} mL = ${res.V_L.toFixed(4)} L`);
      lines.push(`Temperature: ${values.tempC.toFixed(2)} °C = ${res.T_K.toFixed(2)} K`);
      lines.push(`Pressure: ${values.pressurekPa.toFixed(2)} kPa`);
      lines.push('---Calculations---');
      lines.push(`Moles of vapor, n = (P·V)/(R·T) = ${(res.n).toExponential(4)} mol`);
      lines.push(`Molar mass = mass_vapor / n = ${res.M.toFixed(2)} g/mol`);
      if (knownMM && knownMM !== '0') lines.push(`Known molar mass (reference): ${parseFloat(knownMM).toFixed(2)} g/mol`);
      el('report').value = lines.join('\n');
      el('result').textContent = 'Molar mass ≈ ' + res.M.toFixed(2) + ' g·mol⁻¹';
      log('Report filled for ' + name + '.');
    });

    el('downloadReport').addEventListener('click', ()=>{
      const txt = el('report').value;
      if (!txt) return alert('No report to download. Click "Fill report" first.');
      const blob = new Blob([txt], {type:'text/plain'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a'); a.href = url; a.download = 'virtual_lab_report.txt'; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
      log('Report downloaded.');
    });

    // small usability: update displayed compound
    el('compound').addEventListener('change', ()=>{
      const opt = el('compound').selectedOptions[0];
      if (opt.dataset.mm === '0') log('Unknown selected: use Generate make-up dataset for values.');
      else log('Selected sample: ' + opt.textContent);
    });

    log('Interactive virtual lab loaded.');
  </script>
</body>
</html>
