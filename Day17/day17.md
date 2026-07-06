# Vehicle Cost Analysis Dashboard

## Screenshots

<img width="893" height="705" alt="image" src="https://github.com/user-attachments/assets/6b31de6f-a042-4813-a9c8-f79ae8ca424f" />
<img width="893" height="640" alt="image" src="https://github.com/user-attachments/assets/4f74b4b0-1026-4b42-90ec-39ed916bc9f5" />
<img width="900" height="636" alt="image" src="https://github.com/user-attachments/assets/ff48d62a-94df-4eb0-a176-4d19add541a7" />
<img width="886" height="857" alt="image" src="https://github.com/user-attachments/assets/aa0e3b47-2276-4802-935a-9e2739130073" />
<img width="897" height="635" alt="image" src="https://github.com/user-attachments/assets/1d9ed499-a585-4b2f-9624-f8a4ad85be63" />
<img width="897" height="895" alt="image" src="https://github.com/user-attachments/assets/ab2be644-8cf0-4aee-ac0b-cc43971792e7" />


## Generated HTML

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hyundai i20 · E85 Fuel Analytics</title>
<style>
  :root{
    --bg:#0a0f1e;
    --card:rgba(255,255,255,0.05);
    --card-border:rgba(255,255,255,0.10);
    --text:#e8ecf6;
    --muted:#8b93a7;
    --e85:#f5a623;
    --petrol:#3b82f6;
    --diesel:#9ca3af;
    --cng:#22c55e;
    --ev:#a855f7;
    --glow-petrol: 0 0 24px rgba(59,130,246,0.55);
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    font-family:'Segoe UI',system-ui,-apple-system,sans-serif;
    background:radial-gradient(circle at 20% -10%, #14213d 0%, var(--bg) 45%) fixed;
    color:var(--text);
    padding:20px;
  }
  .wrap{max-width:1320px;margin:0 auto;}
  header{
    text-align:center;
    padding:22px 16px;
    margin-bottom:22px;
    border-radius:18px;
    background:linear-gradient(135deg, rgba(59,130,246,0.15), rgba(245,166,35,0.08));
    border:1px solid var(--card-border);
    backdrop-filter:blur(12px);
  }
  header h1{margin:0 0 6px;font-size:clamp(1.2rem,3vw,1.7rem);font-weight:700;letter-spacing:0.3px;}
  header p{margin:0;color:var(--muted);font-size:0.95rem;}
  .grid{display:grid;gap:18px;margin-bottom:22px;}
  .kpis{grid-template-columns:repeat(5,1fr);}
  .charts2{grid-template-columns:1fr 1fr;}
  .fuel-grid{grid-template-columns:repeat(5,1fr);}
  @media(max-width:1000px){.kpis{grid-template-columns:repeat(2,1fr);} .charts2{grid-template-columns:1fr;} .fuel-grid{grid-template-columns:repeat(2,1fr);}}
  @media(max-width:480px){.kpis{grid-template-columns:1fr;} .fuel-grid{grid-template-columns:1fr;}}

  .card{
    background:var(--card);
    border:1px solid var(--card-border);
    border-radius:16px;
    padding:18px;
    backdrop-filter:blur(10px);
    box-shadow:0 4px 24px rgba(0,0,0,0.25);
  }
  .kpi .label{color:var(--muted);font-size:0.78rem;text-transform:uppercase;letter-spacing:0.5px;margin-bottom:8px;}
  .kpi .value{font-size:1.5rem;font-weight:700;}
  .kpi .sub{font-size:0.75rem;color:var(--muted);margin-top:4px;}
  .kpi.highlight{border-color:rgba(59,130,246,0.5);box-shadow:var(--glow-petrol);}

  .card h2{margin:0 0 12px;font-size:1rem;color:var(--text);font-weight:600;}
  svg{width:100%;height:auto;display:block;}

  .tooltip{
    position:absolute;
    pointer-events:none;
    background:#111830;
    border:1px solid rgba(255,255,255,0.15);
    padding:6px 10px;
    border-radius:8px;
    font-size:0.75rem;
    color:var(--text);
    opacity:0;
    transition:opacity 0.15s;
    z-index:20;
    white-space:nowrap;
  }

  .verdict{text-align:center;font-size:0.95rem;color:var(--text);margin-top:10px;}
  .verdict b{color:var(--e85);}

  .fuel-card{position:relative;overflow:hidden;}
  .fuel-card h3{margin:0 0 10px;font-size:1rem;display:flex;align-items:center;gap:8px;}
  .dot{width:10px;height:10px;border-radius:50%;display:inline-block;}
  .fuel-card ul{list-style:none;padding:0;margin:0 0 10px;font-size:0.82rem;line-height:1.6;}
  .fuel-card .best{font-size:0.8rem;color:var(--muted);border-top:1px solid var(--card-border);padding-top:8px;}
  .fuel-card.active{border-color:var(--petrol);box-shadow:var(--glow-petrol);}
  .fuel-card.active::before{
    content:'YOUR FUEL';
    position:absolute;top:10px;right:-30px;
    background:var(--petrol);
    color:#fff;
    font-size:0.6rem;
    font-weight:700;
    padding:3px 32px;
    transform:rotate(35deg);
  }

  .age-line-marker{stroke:var(--petrol);stroke-width:2;stroke-dasharray:4,3;}

  .gauge-wrap{display:flex;flex-direction:column;align-items:center;}
  #gaugeNeedle{transform-origin:150px 150px;transition:transform 1.2s cubic-bezier(.34,1.56,.64,1);}
  .gauge-score{font-size:2rem;font-weight:800;fill:var(--e85);}
</style>
</head>
<body>
<div class="wrap">

<header>
  <h1>Hyundai i20 · Petrol · Age: 4y · 1000 km/mo</h1>
  <p>E85 Flex-Fuel Feasibility &amp; Fuel Economics Dashboard — 2022 model, ₹102/L, 18 km/L rated mileage</p>
</header>

<div class="grid kpis">
  <div class="card kpi highlight">
    <div class="label">Your Cost / km (Petrol)</div>
    <div class="value">₹5.67</div>
    <div class="sub">102 ÷ 18 km/L</div>
  </div>
  <div class="card kpi">
    <div class="label">E85 Cost / km (avg)</div>
    <div class="value">₹6.37</div>
    <div class="sub">from dataset avg</div>
  </div>
  <div class="card kpi">
    <div class="label">E85 Running Premium</div>
    <div class="value" style="color:var(--e85)">+12.5%</div>
    <div class="sub">vs your Petrol cost/km</div>
  </div>
  <div class="card kpi">
    <div class="label">E85 Break-even Price</div>
    <div class="value">₹72.9<span style="font-size:0.9rem;">/L</span></div>
    <div class="sub">for equal running cost</div>
  </div>
  <div class="card kpi">
    <div class="label">Your Monthly Fuel Cost</div>
    <div class="value">₹5,667</div>
    <div class="sub">1000 km/mo × ₹5.67</div>
  </div>
</div>

<div class="grid charts2">
  <div class="card">
    <h2>Average Cost / km by Fuel Type</h2>
    <svg id="barChart" viewBox="0 0 480 300"></svg>
  </div>
  <div class="card">
    <h2>Average CO₂ / km by Fuel Type</h2>
    <svg id="donutChart" viewBox="0 0 480 300"></svg>
  </div>
</div>

<div class="grid" style="grid-template-columns:1fr;">
  <div class="card">
    <h2>Cost / km vs Vehicle Age (0–12 yrs)</h2>
    <svg id="lineChart" viewBox="0 0 900 320"></svg>
  </div>
</div>

<div class="grid charts2">
  <div class="card gauge-wrap">
    <h2 style="align-self:flex-start;">E85 Feasibility Score</h2>
    <svg id="gauge" viewBox="0 0 300 190" style="max-width:320px;">
      <path d="M30,170 A120,120 0 0 1 270,170" fill="none" stroke="#1c2540" stroke-width="22" stroke-linecap="round"/>
      <path id="gaugeArc" d="M30,170 A120,120 0 0 1 270,170" fill="none" stroke="var(--e85)" stroke-width="22" stroke-linecap="round"
        stroke-dasharray="377" stroke-dashoffset="377"/>
      <g id="gaugeNeedle" transform="rotate(-90 150 170)">
        <line x1="150" y1="170" x2="150" y2="62" stroke="#fff" stroke-width="3"/>
        <circle cx="150" cy="170" r="7" fill="#fff"/>
      </g>
      <text x="150" y="150" text-anchor="middle" class="gauge-score">6.6/10</text>
    </svg>
    <div class="verdict">For this i20, E85 is <b>not yet cost-effective</b> — it wins big on CO₂ but its 12.5% running-cost premium over Petrol outweighs the emissions benefit today.</div>
  </div>
  <div class="card">
    <h2>Cost / km by Vehicle Age Bucket</h2>
    <svg id="bucketChart" viewBox="0 0 480 300"></svg>
  </div>
</div>

<div class="grid fuel-grid">

  <div class="card fuel-card active">
    <h3><span class="dot" style="background:var(--petrol)"></span>Petrol (E20)</h3>
    <ul>
      <li>✅ Widely available, zero range anxiety</li>
      <li>✅ Cheapest maintenance among ICE options</li>
      <li>❌ Highest running cost among ICE at ₹6.15/km avg</li>
      <li>❌ Higher CO₂/km than E85 or EV</li>
    </ul>
    <div class="best">🚗 Best for: everyday mixed city/highway driving, no infra dependency</div>
  </div>

  <div class="card fuel-card">
    <h3><span class="dot" style="background:var(--e85)"></span>E85 (Flex-Fuel)</h3>
    <ul>
      <li>✅ Lowest CO₂/km of all fuels tested (0.070 kg/km)</li>
      <li>✅ Low maintenance/km (₹0.46/km)</li>
      <li>❌ 12.5% costlier per km than your Petrol</li>
      <li>❌ Needs pump price ≤ ₹72.9/L to break even</li>
    </ul>
    <div class="best">🚗 Best for: eco-conscious owners with local E85 pump access</div>
  </div>

  <div class="card fuel-card">
    <h3><span class="dot" style="background:var(--diesel)"></span>Diesel</h3>
    <ul>
      <li>✅ Best mileage among liquid fuels (~19.6 km/L)</li>
      <li>✅ Fast refuel (~5 min)</li>
      <li>❌ Highest maintenance/km (₹1.00/km)</li>
      <li>❌ Cost/km rises sharply with age (10+ yrs)</li>
    </ul>
    <div class="best">🚗 Best for: high-mileage highway/fleet use</div>
  </div>

  <div class="card fuel-card">
    <h3><span class="dot" style="background:var(--cng)"></span>CNG</h3>
    <ul>
      <li>✅ Cheapest fossil running cost (₹3.32/km)</li>
      <li>✅ Lower CO₂/km than Petrol/Diesel</li>
      <li>❌ Slower refuel (~8 min), sparse stations</li>
      <li>❌ Boot space trade-off with tank</li>
    </ul>
    <div class="best">🚗 Best for: budget-focused city commuters</div>
  </div>

  <div class="card fuel-card">
    <h3><span class="dot" style="background:var(--ev)"></span>Electric (EV)</h3>
    <ul>
      <li>✅ Lowest cost/km overall (₹1.75/km)</li>
      <li>✅ Lowest maintenance/km (₹0.23/km)</li>
      <li>❌ Longest recharge time (~45 min)</li>
      <li>❌ Charging infra dependency on long trips</li>
    </ul>
    <div class="best">🚗 Best for: short daily commutes with home charging</div>
  </div>

</div>

</div>

<div class="tooltip" id="tooltip"></div>

<script>
const tooltip = document.getElementById('tooltip');
function showTip(evt, text){
  tooltip.style.opacity=1;
  tooltip.textContent=text;
  tooltip.style.left=(evt.pageX+12)+'px';
  tooltip.style.top=(evt.pageY-28)+'px';
}
function hideTip(){ tooltip.style.opacity=0; }

const fuels = [
  {name:'CNG', color:'var(--cng)', cpkm:3.3248, co2:0.1253, mpkm:0.6616, refuel:8},
  {name:'Diesel', color:'var(--diesel)', cpkm:4.6742, co2:0.1787, mpkm:1.0046, refuel:5},
  {name:'E85', color:'var(--e85)', cpkm:6.3742, co2:0.0698, mpkm:0.4597, refuel:5},
  {name:'EV', color:'var(--ev)', cpkm:1.7520, co2:0.0912, mpkm:0.2331, refuel:45},
  {name:'Petrol', color:'var(--petrol)', cpkm:6.1543, co2:0.1706, mpkm:0.4661, refuel:5}
];

// ---------- BAR CHART: cost/km ----------
(function(){
  const svg = document.getElementById('barChart');
  const W=480,H=300,pad=40,baseY=250;
  const maxV = Math.max(...fuels.map(f=>f.cpkm))*1.15;
  const bw = 60, gap=(W-2*pad-bw*fuels.length)/(fuels.length-1);
  let s = '';
  fuels.forEach((f,i)=>{
    const x = pad + i*(bw+gap);
    const h = (f.cpkm/maxV)*(baseY-30);
    const y = baseY - h;
    const c = getComputedStyle(document.documentElement).getPropertyValue(f.color.match(/--[a-z]+/)[0]).trim() || f.color;
    s += `<rect x="${x}" y="${y}" width="${bw}" height="${h}" rx="6" fill="${f.color}" opacity="0.85"
            onmouseover="showTip(event,'${f.name}: ₹${f.cpkm.toFixed(2)}/km')" onmouseout="hideTip()" style="cursor:pointer"/>`;
    s += `<text x="${x+bw/2}" y="${y-8}" text-anchor="middle" fill="#e8ecf6" font-size="13" font-weight="600">₹${f.cpkm.toFixed(2)}</text>`;
    s += `<text x="${x+bw/2}" y="${baseY+20}" text-anchor="middle" fill="#8b93a7" font-size="12">${f.name}</text>`;
  });
  s += `<line x1="${pad-10}" y1="${baseY}" x2="${W-pad+10}" y2="${baseY}" stroke="#2a324a" stroke-width="1"/>`;
  svg.innerHTML = s;
})();

// ---------- DONUT: CO2/km ----------
(function(){
  const svg = document.getElementById('donutChart');
  const cx=170, cy=150, r=95, rInner=55;
  const total = fuels.reduce((a,f)=>a+f.co2,0);
  let angle = -90;
  let s='';
  fuels.forEach(f=>{
    const frac = f.co2/total;
    const sweep = frac*360;
    const large = sweep>180?1:0;
    const a0 = angle*Math.PI/180;
    const a1 = (angle+sweep)*Math.PI/180;
    const x0 = cx+r*Math.cos(a0), y0=cy+r*Math.sin(a0);
    const x1 = cx+r*Math.cos(a1), y1=cy+r*Math.sin(a1);
    const xi0 = cx+rInner*Math.cos(a1), yi0=cy+rInner*Math.sin(a1);
    const xi1 = cx+rInner*Math.cos(a0), yi1=cy+rInner*Math.sin(a0);
    s += `<path d="M${x0},${y0} A${r},${r} 0 ${large} 1 ${x1},${y1} L${xi0},${yi0} A${rInner},${rInner} 0 ${large} 0 ${xi1},${yi1} Z"
          fill="${f.color}" opacity="0.88" stroke="#0a0f1e" stroke-width="2"
          onmouseover="showTip(event,'${f.name}: ${f.co2.toFixed(3)} kg/km')" onmouseout="hideTip()" style="cursor:pointer"/>`;
    angle += sweep;
  });
  s += `<text x="${cx}" y="${cy-4}" text-anchor="middle" fill="#e8ecf6" font-size="14" font-weight="700">CO₂/km</text>`;
  s += `<text x="${cx}" y="${cy+16}" text-anchor="middle" fill="#8b93a7" font-size="11">by fuel type</text>`;

  let legendY = 40;
  fuels.forEach(f=>{
    s += `<rect x="330" y="${legendY-10}" width="10" height="10" fill="${f.color}" rx="2"/>`;
    s += `<text x="346" y="${legendY-1}" fill="#c7cee0" font-size="11">${f.name}</text>`;
    legendY += 20;
  });
  svg.innerHTML = s;
})();

// ---------- LINE CHART: cost/km vs age ----------
(function(){
  const svg = document.getElementById('lineChart');
  const W=900,H=320,padL=50,padR=20,padT=20,padB=40;
  const maxAge=12, maxCost=8;
  const x = a => padL + (a/maxAge)*(W-padL-padR);
  const y = c => (H-padB) - (c/maxCost)*(H-padT-padB);

  // simple linear model per fuel from slope of dataset trend (approx using two known points)
  const trend = {
    CNG:      {b:2.95, m:0.055},
    Diesel:   {b:4.05, m:0.11},
    E85:      {b:6.25, m:0.14},
    EV:       {b:1.68, m:0.035},
    Petrol:   {b:5.75, m:0.09}
  };
  let s='';
  // axes
  for(let g=0; g<=maxCost; g+=2){
    s += `<line x1="${padL}" y1="${y(g)}" x2="${W-padR}" y2="${y(g)}" stroke="#1c2540" stroke-width="1"/>`;
    s += `<text x="${padL-8}" y="${y(g)+4}" text-anchor="end" fill="#8b93a7" font-size="11">₹${g}</text>`;
  }
  for(let a=0; a<=maxAge; a+=2){
    s += `<text x="${x(a)}" y="${H-padB+18}" text-anchor="middle" fill="#8b93a7" font-size="11">${a}y</text>`;
  }
  fuels.forEach(f=>{
    const t = trend[f.name];
    let path='';
    for(let a=0;a<=maxAge;a+=1){
      const c = t.b + t.m*a;
      path += (a===0?'M':'L')+x(a)+','+y(c)+' ';
    }
    s += `<path d="${path}" fill="none" stroke="${f.color}" stroke-width="2.5" opacity="0.9"/>`;
    const cEnd = t.b+t.m*maxAge;
    s += `<text x="${x(maxAge)+4}" y="${y(cEnd)+4}" fill="${f.color}" font-size="11" font-weight="600">${f.name}</text>`;
  });
  // vehicle age marker at 4y
  s += `<line x1="${x(4)}" y1="${padT}" x2="${x(4)}" y2="${H-padB}" class="age-line-marker"/>`;
  s += `<text x="${x(4)}" y="${padT-6}" text-anchor="middle" fill="var(--petrol)" font-size="12" font-weight="700">Your car (4y)</text>`;
  svg.innerHTML = s;
})();

// ---------- BUCKET CHART ----------
(function(){
  const svg = document.getElementById('bucketChart');
  const buckets = ['New(0-2y)','Mid-life(3-5y)','Aged(6-9y)','Old(10+y)'];
  const data = {
    'New(0-2y)':      {CNG:3.08, Diesel:null, E85:6.31, EV:1.71, Petrol:null},
    'Mid-life(3-5y)':{CNG:3.24, Diesel:4.35, E85:6.67, EV:1.82, Petrol:5.85},
    'Aged(6-9y)':    {CNG:3.49, Diesel:4.69, E85:null, EV:null, Petrol:6.33},
    'Old(10+y)':     {CNG:null, Diesel:5.29, E85:null, EV:null, Petrol:null}
  };
  const W=480,H=300,padL=40,padB=45,padT=20;
  const maxV=8;
  const groupW=(W-padL-10)/buckets.length;
  const barW= groupW/6.5;
  let s='';
  s += `<line x1="${padL}" y1="${H-padB}" x2="${W-10}" y2="${H-padB}" stroke="#2a324a"/>`;
  buckets.forEach((b,bi)=>{
    const gx = padL + bi*groupW;
    let fi=0;
    fuels.forEach(f=>{
      const v = data[b][f.name];
      if(v!=null){
        const h = (v/maxV)*(H-padT-padB);
        const bx = gx + fi*(barW+2);
        s += `<rect x="${bx}" y="${H-padB-h}" width="${barW}" height="${h}" fill="${f.color}" rx="3"
              onmouseover="showTip(event,'${f.name} ${b}: ₹${v.toFixed(2)}/km')" onmouseout="hideTip()" style="cursor:pointer"/>`;
      }
      fi++;
    });
    s += `<text x="${gx+groupW/2-10}" y="${H-padB+18}" text-anchor="middle" fill="#8b93a7" font-size="10">${b}</text>`;
  });
  s += `<text x="${gx4(4)}" y="0" opacity="0"></text>`; // no-op
  svg.innerHTML = s;
  function gx4(){return 0;}
})();

// ---------- GAUGE ANIMATION ----------
(function(){
  const score = 6.6; // out of 10
  const maxOffset = 377; // full arc length approx
  const arc = document.getElementById('gaugeArc');
  const needle = document.getElementById('gaugeNeedle');
  const frac = score/10;
  const offset = maxOffset - (maxOffset*frac);
  const angle = -90 + (180*frac);
  setTimeout(()=>{
    arc.style.transition='stroke-dashoffset 1.2s ease-out';
    arc.style.strokeDashoffset = offset;
    needle.setAttribute('transform', `rotate(${angle} 150 170)`);
  }, 150);
})();
</script>
</body>
</html>

## Analysis Findings

Analysis Findings

Fuel Cost per km

Across the dataset, EV is cheapest to run (₹1.75/km), followed by CNG (₹3.32/km), Diesel (₹4.67/km), Petrol E20 (₹6.15/km), and E85 (₹6.37/km) — the most expensive per km despite its lower pump price. Your i20's actual running cost (₹5.67/km, from ₹102/L ÷ 18 km/L) sits slightly better than the dataset's average Petrol figure, likely reflecting a newer, well-maintained engine.

Maintenance Cost per km

EV again leads (₹0.23/km) due to fewer moving parts, followed by E85 (₹0.46/km) and Petrol (₹0.47/km), which are close. Diesel is the most maintenance-intensive (₹1.00/km) and its cost worsens sharply with age — rising from ₹0.70/km in the Aged bucket to ₹1.41/km in vehicles 10+ years old. CNG maintenance also climbs steadily with age (₹0.50 → ₹0.70/km).

E85 Economics (Paradox)

E85 offers an 18% cheaper pump price (₹82 vs ₹100/L baseline) but its lower energy density drags mileage down (~12.9 km/L vs ~16.3 km/L Petrol), producing a net running-cost premium of ~12.5% over your i20's Petrol economics. This is the classic E85 paradox: cheaper fuel, costlier kilometre.

Break-even Analysis

For E85 to match your Petrol running cost, its pump price would need to fall to roughly ₹72.9/L — about 29% below the current ₹102/L Petrol benchmark. At today's E85 pricing (~₹82/L), it remains uneconomical purely on a cost basis.

Environmental Impact

E85 is the clear CO₂ winner, emitting just 0.070 kg/km — the lowest of all five fuel types — well ahead of EV (0.091 kg/km), Diesel (0.179 kg/km), Petrol (0.171 kg/km), and CNG (0.125 kg/km). This makes E85 attractive on emissions grounds even though it loses on cost.

Key Recommendations

Stay on Petrol for now — your current cost/km is competitive, and E85's ~12.5% premium isn't justified without a price drop toward ₹73/L.

Consider CNG if budget is the primary driver and retrofit/availability isn't a barrier — nearly half your current cost/km.

E85 is worth revisiting only if pump prices fall or environmental priorities outweigh cost — it scores well on emissions (6.6/10 overall feasibility) but lags on running economics.

Watch maintenance trajectory — if considering Diesel or CNG for the long term, factor in the steep maintenance rise after year 6, which erodes their fuel-cost advantage over time.

## Learnings

- Learned to generate HTML dashboard using AI.
- Learned vehicle cost analysis.
- Learned fuel comparison.
- Learned environmental impact visualization.
- Learned SVG dashboard generation.
