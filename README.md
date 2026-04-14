<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<title>TapCash Pro™ — Gana Dinero Real</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Outfit:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
* { margin:0; padding:0; box-sizing:border-box; }
:root {
  --gold: #FFD700;
  --gold-dark: #B8960C;
  --green: #00E676;
  --bg: #0a0a12;
  --card: #12121f;
  --accent: #7B61FF;
}
body {
  font-family: 'Outfit', sans-serif;
  background: var(--bg);
  color: #fff;
  min-height: 100dvh;
  overflow-x: hidden;
  position: relative;
}
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background:
    radial-gradient(circle at 20% 20%, rgba(123,97,255,.08) 0%, transparent 50%),
    radial-gradient(circle at 80% 80%, rgba(255,215,0,.06) 0%, transparent 50%);
  pointer-events: none;
  z-index: 0;
}

.app { position: relative; z-index: 1; max-width: 420px; margin: 0 auto; padding: 16px; }

/* Header */
.header {
text-align: center;
padding: 20px 0 10px;
}
.logo {
font-family: ‘Orbitron’, sans-serif;
font-size: 1.6rem;
font-weight: 900;
background: linear-gradient(135deg, var(–gold), #fff, var(–gold));
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
letter-spacing: 2px;
text-shadow: 0 0 30px rgba(255,215,0,.3);
}
.logo span { font-size: .7rem; vertical-align: super; }
.subtitle {
font-size: .75rem;
color: rgba(255,255,255,.4);
margin-top: 4px;
letter-spacing: 3px;
text-transform: uppercase;
}

/* Balance */
.balance-card {
background: linear-gradient(135deg, #1a1a2e, #16213e);
border: 1px solid rgba(255,215,0,.15);
border-radius: 20px;
padding: 24px;
margin: 16px 0;
text-align: center;
position: relative;
overflow: hidden;
}
.balance-card::after {
content: ‘’;
position: absolute;
top: -50%; right: -50%;
width: 100%; height: 100%;
background: radial-gradient(circle, rgba(255,215,0,.05) 0%, transparent 70%);
pointer-events: none;
}
.balance-label {
font-size: .7rem;
text-transform: uppercase;
letter-spacing: 3px;
color: rgba(255,255,255,.5);
margin-bottom: 8px;
}
.balance-amount {
font-family: ‘Orbitron’, sans-serif;
font-size: 2.4rem;
font-weight: 900;
color: var(–gold);
text-shadow: 0 0 20px rgba(255,215,0,.3);
}
.balance-amount .currency { font-size: 1.4rem; }
.balance-amount .cents { font-size: 1.2rem; color: var(–gold-dark); }

/* Stats row */
.stats {
display: flex;
gap: 8px;
margin: 12px 0;
}
.stat-box {
flex: 1;
background: var(–card);
border: 1px solid rgba(255,255,255,.06);
border-radius: 14px;
padding: 12px 8px;
text-align: center;
}
.stat-value {
font-family: ‘Orbitron’, sans-serif;
font-size: .95rem;
font-weight: 700;
color: var(–green);
}
.stat-label {
font-size: .6rem;
color: rgba(255,255,255,.35);
text-transform: uppercase;
letter-spacing: 1px;
margin-top: 4px;
}

/* TAP BUTTON */
.tap-zone {
display: flex;
justify-content: center;
align-items: center;
padding: 24px 0;
position: relative;
}
.tap-btn {
width: 180px;
height: 180px;
border-radius: 50%;
border: none;
cursor: pointer;
position: relative;
background: linear-gradient(145deg, #FFD700, #FFA000);
box-shadow:
0 0 40px rgba(255,215,0,.3),
0 8px 30px rgba(0,0,0,.4),
inset 0 -4px 12px rgba(0,0,0,.2),
inset 0 4px 12px rgba(255,255,255,.3);
transition: transform .08s, box-shadow .08s;
-webkit-tap-highlight-color: transparent;
user-select: none;
z-index: 2;
}
.tap-btn:active {
transform: scale(.93);
box-shadow:
0 0 20px rgba(255,215,0,.2),
0 4px 15px rgba(0,0,0,.4),
inset 0 4px 12px rgba(0,0,0,.3),
inset 0 -2px 8px rgba(255,255,255,.2);
}
.tap-btn .icon {
font-size: 3rem;
display: block;
pointer-events: none;
}
.tap-btn .label {
font-family: ‘Orbitron’, sans-serif;
font-size: .8rem;
font-weight: 700;
color: #1a1a2e;
letter-spacing: 2px;
pointer-events: none;
}
.tap-ring {
position: absolute;
width: 210px; height: 210px;
border-radius: 50%;
border: 2px solid rgba(255,215,0,.15);
animation: pulse-ring 2s ease-out infinite;
pointer-events: none;
}
@keyframes pulse-ring {
0% { transform: scale(1); opacity: .6; }
100% { transform: scale(1.4); opacity: 0; }
}

/* Floating +€ */
.float-coin {
position: absolute;
font-family: ‘Orbitron’, sans-serif;
font-size: .9rem;
font-weight: 700;
color: var(–gold);
pointer-events: none;
animation: float-up .8s ease-out forwards;
z-index: 10;
text-shadow: 0 0 8px rgba(255,215,0,.5);
}
@keyframes float-up {
0% { opacity: 1; transform: translateY(0) scale(1); }
100% { opacity: 0; transform: translateY(-80px) scale(1.3); }
}

/* Missions / Packages */
.section-title {
font-family: ‘Orbitron’, sans-serif;
font-size: .7rem;
letter-spacing: 3px;
text-transform: uppercase;
color: rgba(255,255,255,.4);
margin: 20px 0 10px;
}

.mission-card {
background: var(–card);
border: 1px solid rgba(255,255,255,.06);
border-radius: 16px;
padding: 16px;
margin-bottom: 10px;
position: relative;
overflow: hidden;
}
.mission-card.active { border-color: rgba(255,215,0,.25); }
.mission-card.completed {
border-color: rgba(0,230,118,.3);
background: linear-gradient(135deg, var(–card), rgba(0,230,118,.05));
}
.mission-header {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 8px;
}
.mission-name {
font-weight: 600;
font-size: .9rem;
}
.mission-reward {
font-family: ‘Orbitron’, sans-serif;
font-size: .8rem;
color: var(–gold);
font-weight: 700;
}
.progress-bar {
height: 6px;
background: rgba(255,255,255,.08);
border-radius: 3px;
overflow: hidden;
margin-top: 8px;
}
.progress-fill {
height: 100%;
background: linear-gradient(90deg, var(–gold-dark), var(–gold));
border-radius: 3px;
transition: width .3s;
}
.mission-progress-text {
font-size: .65rem;
color: rgba(255,255,255,.4);
margin-top: 4px;
text-align: right;
font-family: ‘Orbitron’, sans-serif;
}
.mission-card.completed .progress-fill {
background: linear-gradient(90deg, #00C853, var(–green));
}

/* Withdraw button */
.withdraw-btn {
display: none;
width: 100%;
padding: 16px;
margin: 16px 0;
border: none;
border-radius: 14px;
font-family: ‘Orbitron’, sans-serif;
font-size: .9rem;
font-weight: 700;
letter-spacing: 2px;
cursor: pointer;
background: linear-gradient(135deg, var(–green), #00C853);
color: #0a0a12;
box-shadow: 0 0 30px rgba(0,230,118,.25);
animation: glow-green 2s ease-in-out infinite alternate;
transition: transform .1s;
}
.withdraw-btn:active { transform: scale(.97); }
.withdraw-btn.show { display: block; }
@keyframes glow-green {
from { box-shadow: 0 0 20px rgba(0,230,118,.2); }
to { box-shadow: 0 0 40px rgba(0,230,118,.4); }
}

/* Modal overlay */
.modal-overlay {
display: none;
position: fixed;
inset: 0;
background: rgba(0,0,0,.85);
z-index: 100;
justify-content: center;
align-items: center;
padding: 20px;
backdrop-filter: blur(8px);
}
.modal-overlay.show { display: flex; }
.modal {
background: var(–card);
border: 1px solid rgba(255,255,255,.1);
border-radius: 24px;
padding: 32px 24px;
width: 100%;
max-width: 360px;
text-align: center;
animation: modal-in .3s ease-out;
}
@keyframes modal-in {
from { transform: scale(.85) translateY(20px); opacity: 0; }
to { transform: scale(1) translateY(0); opacity: 1; }
}
.modal h2 {
font-family: ‘Orbitron’, sans-serif;
font-size: 1rem;
margin-bottom: 6px;
color: var(–gold);
}
.modal p {
font-size: .8rem;
color: rgba(255,255,255,.5);
margin-bottom: 20px;
}
.modal input {
width: 100%;
padding: 14px;
border-radius: 12px;
border: 1px solid rgba(255,255,255,.1);
background: rgba(255,255,255,.05);
color: #fff;
font-family: ‘Orbitron’, sans-serif;
font-size: 1.1rem;
text-align: center;
outline: none;
margin-bottom: 16px;
transition: border-color .2s;
}
.modal input:focus { border-color: var(–gold); }
.modal-actions {
display: flex;
gap: 10px;
}
.modal-actions button {
flex: 1;
padding: 12px;
border-radius: 12px;
border: none;
font-family: ‘Outfit’, sans-serif;
font-weight: 600;
font-size: .85rem;
cursor: pointer;
transition: transform .1s;
}
.modal-actions button:active { transform: scale(.95); }
.btn-cancel {
background: rgba(255,255,255,.08);
color: rgba(255,255,255,.6);
}
.btn-confirm {
background: linear-gradient(135deg, var(–green), #00C853);
color: #0a0a12;
}

/* PRANK REVEAL */
.prank-overlay {
display: none;
position: fixed;
inset: 0;
z-index: 200;
justify-content: center;
align-items: center;
padding: 20px;
flex-direction: column;
}
.prank-overlay.show {
display: flex;
animation: prank-bg 1s ease forwards;
}
@keyframes prank-bg {
from { background: rgba(0,0,0,0); }
to { background: #b71c1c; }
}
.prank-content {
text-align: center;
animation: prank-in .6s .3s ease-out both;
}
@keyframes prank-in {
from { transform: scale(.3) rotate(-10deg); opacity: 0; }
to { transform: scale(1) rotate(0); opacity: 1; }
}
.prank-star {
font-size: 5rem;
display: block;
margin-bottom: 16px;
animation: spin-star 3s linear infinite;
filter: drop-shadow(0 0 30px rgba(255,215,0,.6));
}
@keyframes spin-star {
from { transform: rotate(0); }
to { transform: rotate(360deg); }
}
.prank-title {
font-family: ‘Orbitron’, sans-serif;
font-size: 1.8rem;
font-weight: 900;
color: var(–gold);
text-shadow: 0 0 30px rgba(255,215,0,.5);
line-height: 1.3;
margin-bottom: 20px;
letter-spacing: 2px;
}
.prank-sub {
font-family: ‘Outfit’, sans-serif;
font-size: 1.2rem;
color: rgba(255,255,255,.9);
font-weight: 300;
font-style: italic;
letter-spacing: 1px;
animation: fade-sub 1s 1s ease both;
}
@keyframes fade-sub {
from { opacity: 0; transform: translateY(10px); }
to { opacity: 1; transform: translateY(0); }
}
.prank-flag {
margin-top: 24px;
font-size: 4rem;
animation: flag-wave 1s 1.2s ease both;
}
@keyframes flag-wave {
from { opacity: 0; transform: scale(0); }
50% { transform: scale(1.3); }
to { opacity: 1; transform: scale(1); }
}
.confetti {
position: fixed;
width: 10px; height: 10px;
z-index: 201;
pointer-events: none;
animation: confetti-fall 3s ease-in forwards;
}
@keyframes confetti-fall {
0% { opacity: 1; transform: translateY(-20px) rotate(0); }
100% { opacity: 0; transform: translateY(100vh) rotate(720deg); }
}

/* Verified badge */
.verified {
display: inline-flex;
align-items: center;
gap: 4px;
background: rgba(0,230,118,.1);
border: 1px solid rgba(0,230,118,.2);
border-radius: 20px;
padding: 4px 10px;
font-size: .6rem;
color: var(–green);
letter-spacing: 1px;
text-transform: uppercase;
margin-top: 8px;
}
.verified::before { content: ‘✓’; font-weight: 700; }

/* Fake users counter */
.users-online {
text-align: center;
font-size: .65rem;
color: rgba(255,255,255,.3);
margin-top: 12px;
}
.users-online .dot {
display: inline-block;
width: 6px; height: 6px;
background: var(–green);
border-radius: 50%;
margin-right: 4px;
animation: blink 1.5s infinite;
}
@keyframes blink {
0%,100% { opacity: 1; }
50% { opacity: .3; }
}
</style>

</head>
<body>

<div class="app">
  <!-- Header -->
  <div class="header">
    <div class="logo">TAPCASH<span>™</span></div>
    <div class="subtitle">Gana dinero con cada tap</div>
    <div class="verified">Plataforma Verificada 2026</div>
  </div>

  <!-- Balance -->

  <div class="balance-card">
    <div class="balance-label">Tu Balance Disponible</div>
    <div class="balance-amount">
      <span class="currency">€</span><span id="euros">0</span>.<span class="cents" id="cents">00</span>
    </div>
  </div>

  <!-- Stats -->

  <div class="stats">
    <div class="stat-box">
      <div class="stat-value" id="totalTaps">0</div>
      <div class="stat-label">Taps Totales</div>
    </div>
    <div class="stat-box">
      <div class="stat-value" id="tapsPerSec">0</div>
      <div class="stat-label">Taps/Seg</div>
    </div>
    <div class="stat-box">
      <div class="stat-value" id="level">1</div>
      <div class="stat-label">Nivel</div>
    </div>
  </div>

  <!-- TAP BUTTON -->

  <div class="tap-zone" id="tapZone">
    <div class="tap-ring"></div>
    <button class="tap-btn" id="tapBtn">
      <span class="icon">💰</span>
      <span class="label">TAP TAP</span>
    </button>
  </div>

  <!-- Missions -->

  <div class="section-title">📋 Misiones / Paquetes</div>

  <div class="mission-card active" id="mission1">
    <div class="mission-header">
      <span class="mission-name">🥉 Paquete Starter</span>
      <span class="mission-reward">€10.00</span>
    </div>
    <div style="font-size:.7rem;color:rgba(255,255,255,.4)">Completa 1,000 taps</div>
    <div class="progress-bar"><div class="progress-fill" id="prog1" style="width:0%"></div></div>
    <div class="mission-progress-text"><span id="progText1">0</span> / 1,000</div>
  </div>

  <div class="mission-card" id="mission2">
    <div class="mission-header">
      <span class="mission-name">🥈 Paquete Pro</span>
      <span class="mission-reward">€100.00</span>
    </div>
    <div style="font-size:.7rem;color:rgba(255,255,255,.4)">Completa 10,000 taps</div>
    <div class="progress-bar"><div class="progress-fill" id="prog2" style="width:0%"></div></div>
    <div class="mission-progress-text"><span id="progText2">0</span> / 10,000</div>
  </div>

  <div class="mission-card" id="mission3">
    <div class="mission-header">
      <span class="mission-name">🥇 Paquete VIP</span>
      <span class="mission-reward">€1,000.00</span>
    </div>
    <div style="font-size:.7rem;color:rgba(255,255,255,.4)">Completa 100,000 taps</div>
    <div class="progress-bar"><div class="progress-fill" id="prog3" style="width:0%"></div></div>
    <div class="mission-progress-text"><span id="progText3">0</span> / 100,000</div>
  </div>

  <!-- Withdraw -->

<button class="withdraw-btn" id="withdrawBtn">💸 RETIRAR FONDOS</button>

  <!-- Fake users -->

  <div class="users-online"><span class="dot"></span><span id="onlineCount">12,847</span> usuarios activos ahora</div>
</div>

<!-- WITHDRAW MODAL -->

<div class="modal-overlay" id="withdrawModal">
  <div class="modal">
    <h2>💸 Retirar Fondos</h2>
    <p>Introduce la cantidad que deseas retirar a tu cuenta bancaria</p>
    <input type="number" id="withdrawAmount" placeholder="0.00" step="0.01" min="0">
    <div style="font-size:.65rem;color:rgba(255,255,255,.3);margin:-10px 0 16px;">Balance disponible: €<span id="modalBalance">0.00</span></div>
    <div class="modal-actions">
      <button class="btn-cancel" id="cancelBtn">Cancelar</button>
      <button class="btn-confirm" id="confirmBtn">Confirmar Retiro</button>
    </div>
  </div>
</div>

<!-- PRANK REVEAL -->

<div class="prank-overlay" id="prankOverlay">
  <div class="prank-content">
    <span class="prank-star">⭐</span>
    <div class="prank-title">¡VIVA LA<br>REVOLUCIÓN<br>CUBANA!</div>
    <div class="prank-sub">Hasta la victoria siempre 🤝</div>
    <div class="prank-flag">🇨🇺</div>
  </div>
</div>

<script>
let taps = 0;
let balance = 0; // in cents
let tapsHistory = [];
const missions = [
  { target: 1000, reward: 1000, el: 'mission1', prog: 'prog1', text: 'progText1', done: false },
  { target: 10000, reward: 10000, el: 'mission2', prog: 'prog2', text: 'progText2', done: false },
  { target: 100000, reward: 100000, el: 'mission3', prog: 'prog3', text: 'progText3', done: false },
];

const tapBtn = document.getElementById('tapBtn');
const tapZone = document.getElementById('tapZone');

function updateDisplay() {
  const euros = Math.floor(balance / 100);
  const cents = balance % 100;
  document.getElementById('euros').textContent = euros.toLocaleString();
  document.getElementById('cents').textContent = String(cents).padStart(2, '0');
  document.getElementById('totalTaps').textContent = taps.toLocaleString();

  // Level
  let lvl = 1;
  if (taps >= 100000) lvl = 10;
  else if (taps >= 50000) lvl = 8;
  else if (taps >= 10000) lvl = 6;
  else if (taps >= 5000) lvl = 4;
  else if (taps >= 1000) lvl = 3;
  else if (taps >= 100) lvl = 2;
  document.getElementById('level').textContent = lvl;

  // Missions
  let anyCompleted = false;
  missions.forEach(m => {
    const pct = Math.min(100, (taps / m.target) * 100);
    document.getElementById(m.prog).style.width = pct + '%';
    document.getElementById(m.text).textContent = Math.min(taps, m.target).toLocaleString();

    const card = document.getElementById(m.el);
    if (taps >= m.target && !m.done) {
      m.done = true;
      card.classList.remove('active');
      card.classList.add('completed');
    }
    if (m.done) anyCompleted = true;
    if (!m.done && taps > 0) card.classList.add('active');
  });

  // Show withdraw
  const wb = document.getElementById('withdrawBtn');
  if (anyCompleted) wb.classList.add('show');
}

function spawnFloater(x, y) {
  const el = document.createElement('div');
  el.className = 'float-coin';
  el.textContent = '+€0.01';
  el.style.left = x + 'px';
  el.style.top = y + 'px';
  tapZone.appendChild(el);
  setTimeout(() => el.remove(), 800);
}

// Taps per second
setInterval(() => {
  const now = Date.now();
  tapsHistory = tapsHistory.filter(t => now - t < 1000);
  document.getElementById('tapsPerSec').textContent = tapsHistory.length;
}, 200);

// Fake online users
setInterval(() => {
  const base = 12847;
  const delta = Math.floor(Math.random() * 200) - 100;
  document.getElementById('onlineCount').textContent = (base + delta).toLocaleString();
}, 3000);

tapBtn.addEventListener('pointerdown', (e) => {
  e.preventDefault();
  taps++;
  balance++;
  tapsHistory.push(Date.now());

  const rect = tapZone.getBoundingClientRect();
  const x = e.clientX - rect.left - 20 + (Math.random() * 40 - 20);
  const y = e.clientY - rect.top - 10;
  spawnFloater(x, y);

  updateDisplay();
});

// Withdraw flow
document.getElementById('withdrawBtn').addEventListener('click', () => {
  document.getElementById('modalBalance').textContent = (balance / 100).toFixed(2);
  document.getElementById('withdrawAmount').value = '';
  document.getElementById('withdrawModal').classList.add('show');
});

document.getElementById('cancelBtn').addEventListener('click', () => {
  document.getElementById('withdrawModal').classList.remove('show');
});

document.getElementById('confirmBtn').addEventListener('click', () => {
  const amt = parseFloat(document.getElementById('withdrawAmount').value);
  if (!amt || amt <= 0) {
    document.getElementById('withdrawAmount').style.borderColor = '#ff1744';
    setTimeout(() => document.getElementById('withdrawAmount').style.borderColor = 'rgba(255,255,255,.1)', 600);
    return;
  }

  document.getElementById('withdrawModal').classList.remove('show');

  // Show prank
  setTimeout(() => {
    document.getElementById('prankOverlay').classList.add('show');
    launchConfetti();
  }, 500);
});

function launchConfetti() {
  const colors = ['#FFD700', '#ff1744', '#00E676', '#2979FF', '#FF9100', '#fff'];
  for (let i = 0; i < 60; i++) {
    setTimeout(() => {
      const c = document.createElement('div');
      c.className = 'confetti';
      c.style.left = Math.random() * 100 + 'vw';
      c.style.top = '-10px';
      c.style.background = colors[Math.floor(Math.random() * colors.length)];
      c.style.borderRadius = Math.random() > .5 ? '50%' : '2px';
      c.style.width = (6 + Math.random() * 8) + 'px';
      c.style.height = (6 + Math.random() * 8) + 'px';
      c.style.animationDuration = (2 + Math.random() * 2) + 's';
      document.body.appendChild(c);
      setTimeout(() => c.remove(), 4000);
    }, i * 50);
  }
}

updateDisplay();
</script>

</body>
</html>
