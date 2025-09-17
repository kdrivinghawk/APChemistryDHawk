<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Virtual Lab — Drag & Drop Volatile Liquid Experiment</title>
  <style>
    :root{font-family:system-ui,-apple-system,Segoe UI,Roboto,'Helvetica Neue',Arial;line-height:1.4}
    body{padding:18px;max-width:1000px;margin:0 auto;color:#111;background:#f9fafb}
    h1{font-size:1.4rem;margin-bottom:6px}
    .bench{position:relative;width:100%;height:400px;border:2px solid #ccc;border-radius:12px;background:#eef2ff;overflow:hidden;margin-bottom:14px}
    .item{position:absolute;cursor:grab;user-select:none}
    .dropzone{position:absolute;border:2px dashed #888;border-radius:10px;text-align:center;line-height:1.2;font-size:0.9rem;color:#444}
    #beakerZone{left:50px;top:180px;width:180px;height:180px}
    #thermoZone{left:300px;top:160px;width:60px;height:200px}
    #messages{background:#fff;border:1px solid #ddd;padding:8px;border-radius:6px;height:120px;overflow:auto;font-family:monospace;white-space:pre-wrap}
    button{padding:8px 14px;border:none;border-radius:6px;background:#0b66ff;color:white;margin:4px;cursor:pointer}
    button:disabled{background:#93c5fd;cursor:not-allowed}
    .results{margin-top:14px;font-size:1rem;font-weight:500}
  </style>
</head>
<body>
  <h1>Virtual Lab — Heating a Volatile Liquid (Drag & Drop)</h1>
  <p>Drag the equipment onto the bench to set up the experiment. Once the setup is correct, you can start heating and collect your data.</p>

  <div class="bench" id="bench">
    <!-- Drop zones -->
    <div class="dropzone" id="beakerZone">Drop Flask Here</div>
    <div class="dropzone" id="thermoZone">Drop Thermometer Here</div>

    <!-- Draggable items -->
    <img src="https://i.ibb.co/D9p1sPp/flask.png" id="flask" class="item" style="left:600px;top:60px;width:80px" draggable="true" alt="Flask">
    <img src="https://i.ibb.co/7jC2vcj/thermometer.png" id="thermo" class="item" style="left:700px;top:80px;width:40px" draggable="true" alt="Thermometer">
  </div>

  <button id="startHeat" disabled>Start Heating</button>

  <div id="messages">Ready.</div>

  <div class="results" id="results">Molar mass: —</div>

  <script>
    const log = msg => {
      const m = document.getElementById('messages');
      m.textContent += "\n" + msg;
      m.scrollTop = m.scrollHeight;
    };

    const flask = document.getElementById('flask');
    const thermo = document.getElementById('thermo');
    const beakerZone = document.getElementById('beakerZone');
    const thermoZone = document.getElementById('thermoZone');
    let flaskPlaced = false;
    let thermoPlaced = false;

    function allowDrop(ev){ev.preventDefault();}
    function drag(ev){ev.dataTransfer.setData("id", ev.target.id);}
    function drop(ev){
      ev.preventDefault();
      const id = ev.dataTransfer.getData("id");
      const el = document.getElementById(id);
      if(ev.target.id==="beakerZone" && id==="flask"){
        el.style.left = "90px";
        el.style.top = "200px";
        flaskPlaced = true;
        log("Flask placed into water bath.");
      }
      if(ev.target.id==="thermoZone" && id==="thermo"){
        el.style.left = "310px";
        el.style.top = "180px";
        thermoPlaced = true;
        log("Thermometer placed in bath.");
      }
      if(flaskPlaced && thermoPlaced){
        document.getElementById('startHeat').disabled = false;
        log("Setup complete. You may now start heating.");
      }
    }

    [beakerZone, thermoZone].forEach(zone=>{
      zone.addEventListener('dragover', allowDrop);
      zone.addEventListener('drop', drop);
    });
    flask.addEventListener('dragstart', drag);
    thermo.addEventListener('dragstart', drag);

    document.getElementById('startHeat').addEventListener('click', ()=>{
      log("Heating started...");
      document.getElementById('startHeat').disabled = true;
      let temp = 25;
      const interval = setInterval(()=>{
        temp += 5 + Math.random()*2;
        log("Temp: "+temp.toFixed(1)+" °C");
        if(temp>=98){
          clearInterval(interval);
          log("Boiling reached. Vapor collected. Data ready.");
          generateData();
        }
      },800);
    });

    function generateData(){
      const massBefore = (50 + Math.random()*10).toFixed(2);
      const massAfter = (massBefore - (0.8+Math.random()*1.5)).toFixed(2);
      const vaporVolume = (110 + Math.random()*60).toFixed(1);
      const tempC = (95+Math.random()*4).toFixed(1);
      const pressure = 101.3;

      const R=8.3145;
      const massVapor = massBefore - massAfter;
      const V = vaporVolume/1000;
      const T = parseFloat(tempC)+273.15;
      const n = (pressure*V)/(R*T);
      const M = massVapor/n;

      document.getElementById('results').textContent = `Mass loss: ${massVapor.toFixed(2)} g | Volume: ${V.toFixed(3)} L | Temp: ${T.toFixed(1)} K | Molar mass ≈ ${M.toFixed(2)} g/mol`;
    }
  </script>
</body>
</html>
