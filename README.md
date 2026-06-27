<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
  <meta name="theme-color" content="#15061f" />
  <meta name="description" content="Dressed & Dared - a neon outfit, location, and dare randomizer." />
  <title>Dressed & Dared</title>
  <!-- v13 single-file build: includes embedded currency logo icons -->
  <style>
:root {
  --bg-0: #050309;
  --bg-1: #13051d;
  --bg-2: #220833;
  --panel: rgba(24, 12, 35, 0.82);
  --panel-strong: rgba(36, 13, 52, 0.94);
  --text: #fff7ff;
  --muted: #cdb8da;
  --accent: #ff2dbd;
  --accent-2: #9d4dff;
  --accent-3: #36f5ff;
  --accent-rgb: 255, 45, 189;
  --accent-2-rgb: 157, 77, 255;
  --accent-3-rgb: 54, 245, 255;
  --good: #79ffcd;
  --warn: #ffd36e;
  --danger: #ff5a86;
  --border: rgba(255, 45, 189, 0.38);
  --shadow: 0 0 28px rgba(255, 45, 189, 0.18), 0 0 60px rgba(157, 77, 255, 0.1);
  --radius: 22px;
  --font: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}

body.theme-purple {
  --bg-0: #05020c;
  --bg-1: #17052c;
  --bg-2: #2a0757;
  --panel: rgba(32, 12, 55, 0.84);
  --panel-strong: rgba(43, 12, 77, 0.94);
  --accent: #c85cff;
  --accent-2: #7e6cff;
  --accent-3: #ff77d9;
  --accent-rgb: 200, 92, 255;
  --accent-2-rgb: 126, 108, 255;
  --accent-3-rgb: 255, 119, 217;
  --border: rgba(200, 92, 255, 0.42);
  --shadow: 0 0 28px rgba(200, 92, 255, 0.2), 0 0 60px rgba(126, 108, 255, 0.1);
}

body.theme-electric {
  --bg-0: #01070c;
  --bg-1: #031825;
  --bg-2: #062d44;
  --panel: rgba(5, 24, 36, 0.86);
  --panel-strong: rgba(8, 39, 58, 0.95);
  --accent: #24e7ff;
  --accent-2: #ff2dbd;
  --accent-3: #78ffdb;
  --accent-rgb: 36, 231, 255;
  --accent-2-rgb: 255, 45, 189;
  --accent-3-rgb: 120, 255, 219;
  --border: rgba(36, 231, 255, 0.42);
  --shadow: 0 0 28px rgba(36, 231, 255, 0.17), 0 0 60px rgba(255, 45, 189, 0.08);
}

body.theme-blackout {
  --bg-0: #060105;
  --bg-1: #16040c;
  --bg-2: #300613;
  --panel: rgba(35, 6, 18, 0.86);
  --panel-strong: rgba(48, 9, 25, 0.95);
  --accent: #ff1f74;
  --accent-2: #ff6fc6;
  --accent-3: #fff1f8;
  --accent-rgb: 255, 31, 116;
  --accent-2-rgb: 255, 111, 198;
  --accent-3-rgb: 255, 241, 248;
  --border: rgba(255, 31, 116, 0.42);
  --shadow: 0 0 28px rgba(255, 31, 116, 0.2), 0 0 60px rgba(255, 111, 198, 0.08);
}

body.theme-vip {
  --bg-0: #060402;
  --bg-1: #1c1203;
  --bg-2: #3a2505;
  --panel: rgba(41, 25, 5, 0.86);
  --panel-strong: rgba(59, 36, 6, 0.95);
  --accent: #ffd86b;
  --accent-2: #ff3fb7;
  --accent-3: #fff3c1;
  --accent-rgb: 255, 216, 107;
  --accent-2-rgb: 255, 63, 183;
  --accent-3-rgb: 255, 243, 193;
  --border: rgba(255, 216, 107, 0.45);
  --shadow: 0 0 28px rgba(255, 216, 107, 0.17), 0 0 60px rgba(255, 63, 183, 0.08);
}

* { box-sizing: border-box; }
html { min-height: 100%; background: var(--bg-0); }
body {
  min-height: 100vh;
  margin: 0;
  color: var(--text);
  font-family: var(--font);
  background:
    radial-gradient(circle at 15% 8%, rgba(var(--accent-rgb), 0.18), transparent 34%),
    radial-gradient(circle at 87% 12%, rgba(var(--accent-2-rgb), 0.18), transparent 33%),
    linear-gradient(150deg, var(--bg-0), var(--bg-1) 48%, var(--bg-2));
  background-attachment: fixed;
}

button, input, textarea, select { font: inherit; }
button { cursor: pointer; }
button:disabled { cursor: not-allowed; opacity: 0.46; }

.app-shell {
  width: min(1120px, 100%);
  margin: 0 auto;
  min-height: 100vh;
  padding: 22px 16px 96px;
}

.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 18px;
}

.eyebrow {
  margin: 0 0 2px;
  color: var(--accent-3);
  letter-spacing: 0.18em;
  text-transform: uppercase;
  font-size: 0.72rem;
  font-weight: 800;
}

h1, h2, h3, p { margin-top: 0; }
h1 {
  margin: 0;
  font-size: clamp(2rem, 7vw, 4.5rem);
  line-height: 0.92;
  letter-spacing: -0.07em;
  text-transform: uppercase;
  text-shadow: 0 0 18px rgba(var(--accent-rgb), 0.55);
}
h1 span { color: var(--accent); }
h2 { font-size: clamp(1.35rem, 3vw, 2rem); margin-bottom: 10px; }
h3 { margin-bottom: 8px; }

.wallet {
  min-width: 112px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  border: 1px solid var(--border);
  background: linear-gradient(145deg, var(--panel-strong), rgba(255,255,255,0.04));
  border-radius: 999px;
  padding: 10px 14px;
  box-shadow: var(--shadow);
}
.wallet-icon {
  display: grid;
  place-items: center;
  width: 34px;
  height: 34px;
  border-radius: 50%;
  color: var(--bg-0);
  background: linear-gradient(135deg, var(--accent), var(--accent-3));
  font-weight: 900;
}
.wallet strong { display: block; line-height: 1; }
.wallet small { display: block; color: var(--muted); font-size: 0.72rem; margin-top: 2px; }

.view { display: none; animation: rise 260ms ease both; }
.view.active { display: block; }
@keyframes rise { from { opacity: 0; transform: translateY(12px); } to { opacity: 1; transform: translateY(0); } }

.grid { display: grid; gap: 14px; }
.grid.two { grid-template-columns: repeat(2, minmax(0, 1fr)); }
.grid.three { grid-template-columns: repeat(3, minmax(0, 1fr)); }
@media (max-width: 820px) { .grid.two, .grid.three { grid-template-columns: 1fr; } }

.card {
  position: relative;
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 18px;
  background: linear-gradient(145deg, var(--panel), rgba(255,255,255,0.035));
  box-shadow: var(--shadow);
  overflow: hidden;
}
.card::before {
  content: "";
  position: absolute;
  inset: 0;
  pointer-events: none;
  background: linear-gradient(135deg, rgba(var(--accent-rgb), 0.10), transparent 40%, rgba(var(--accent-2-rgb), 0.08));
  opacity: 0.9;
}
.card > * { position: relative; z-index: 1; }
.card.compact { padding: 14px; }
.card-title-row { display: flex; justify-content: space-between; gap: 12px; align-items: start; }
.muted { color: var(--muted); }
.small { font-size: 0.84rem; }

.hero {
  min-height: 280px;
  display: grid;
  gap: 16px;
  align-content: start;
}

.roll-controls { display: flex; gap: 10px; align-items: center; flex-wrap: wrap; }
.control-pill {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  border: 1px solid var(--border);
  border-radius: 999px;
  padding: 8px 12px;
  background: rgba(0,0,0,0.18);
}
.control-pill select {
  color: var(--text);
  background: transparent;
  border: 0;
  outline: 0;
}
.control-pill option { color: #1d0d26; }

.btn {
  border: 0;
  border-radius: 999px;
  padding: 12px 16px;
  color: var(--text);
  background: rgba(255,255,255,0.08);
  border: 1px solid rgba(255,255,255,0.13);
  transition: transform 140ms ease, border-color 140ms ease, background 140ms ease, box-shadow 140ms ease;
}
.btn:hover:not(:disabled) { transform: translateY(-1px); border-color: var(--accent); }
.btn.primary {
  color: white;
  font-weight: 900;
  letter-spacing: 0.02em;
  background: linear-gradient(135deg, var(--accent), var(--accent-2));
  box-shadow: 0 0 22px rgba(var(--accent-rgb), 0.38);
}
.btn.danger { border-color: rgba(255,90,134,0.4); color: #ffd6e0; }
.btn.ghost { background: transparent; }
.btn.small { padding: 8px 11px; font-size: 0.85rem; }

.result-grid { display: grid; gap: 12px; }
.result-section {
  border: 1px solid var(--border);
  border-radius: 18px;
  background: rgba(0,0,0,0.18);
  padding: 14px;
}
.result-section h3 {
  margin: 0 0 8px;
  color: var(--accent-3);
  text-transform: uppercase;
  font-size: 0.78rem;
  letter-spacing: 0.16em;
}
.result-list { list-style: none; padding: 0; margin: 0; display: grid; gap: 7px; }
.result-list li {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  border-bottom: 1px dashed rgba(255,255,255,0.1);
  padding-bottom: 7px;
}
.result-list li:last-child { border-bottom: 0; padding-bottom: 0; }
.reward { color: var(--good); font-weight: 800; white-space: nowrap; }
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  border: 1px solid var(--border);
  border-radius: 999px;
  padding: 5px 9px;
  color: var(--accent-3);
  background: rgba(0,0,0,0.24);
  font-size: 0.78rem;
  font-weight: 800;
}
.badge.common { color: #ffffff; border-color: rgba(255,255,255,0.72); box-shadow: 0 0 12px rgba(255,255,255,0.08); }
.badge.rare { color: #72d8ff; border-color: rgba(80,180,255,0.72); box-shadow: 0 0 12px rgba(80,180,255,0.14); }
.badge.epic { color: #ff8bd7; border-color: rgba(255,80,190,0.78); box-shadow: 0 0 13px rgba(255,80,190,0.18); }
.badge.legendary { color: #ffd85a; border-color: rgba(255,215,70,0.86); box-shadow: 0 0 16px rgba(255,215,70,0.22); }
.badge.discount-badge { color: #fff; border-color: rgba(255,80,190,0.78); background: linear-gradient(135deg, rgba(255,20,157,0.32), rgba(255,216,90,0.14)); box-shadow: 0 0 18px rgba(255,20,157,0.22); }
.badge.freeze-badge { color: #fff3ba; border-color: rgba(255,215,90,0.70); background: rgba(255,215,90,0.10); }

.empty {
  border: 1px dashed var(--border);
  border-radius: 18px;
  padding: 16px;
  color: var(--muted);
  background: rgba(0,0,0,0.16);
}

.color-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(105px, 1fr));
  gap: 8px;
}
.color-chip, .check-row {
  display: flex;
  align-items: center;
  gap: 8px;
  border: 1px solid rgba(255,255,255,0.11);
  border-radius: 999px;
  padding: 8px 10px;
  background: rgba(0,0,0,0.18);
  user-select: none;
}
.color-chip input, .check-row input { accent-color: var(--accent); }
.color-dot {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  box-shadow: inset 0 0 0 1px rgba(255,255,255,0.36), 0 0 10px rgba(255,255,255,0.08);
}

.form-row { display: flex; gap: 10px; align-items: stretch; }
.form-row input, .form-row textarea {
  flex: 1;
  min-width: 0;
  border: 1px solid rgba(255,255,255,0.12);
  border-radius: 16px;
  padding: 12px 13px;
  color: var(--text);
  background: rgba(0,0,0,0.24);
  outline: none;
}
.form-row textarea { min-height: 78px; resize: vertical; }
.form-row input:focus, .form-row textarea:focus { border-color: var(--accent); box-shadow: 0 0 0 3px rgba(var(--accent-rgb), 0.16); }
@media (max-width: 620px) { .form-row { flex-direction: column; } }

.item-list { display: grid; gap: 8px; margin-top: 12px; }
.list-item {
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  gap: 10px;
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 16px;
  padding: 10px;
  background: rgba(0,0,0,0.18);
}
.list-item .text { overflow-wrap: anywhere; }

.shop-tabs { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 14px; }
.shop-tab {
  border: 1px solid var(--border);
  color: var(--text);
  background: rgba(0,0,0,0.16);
  border-radius: 999px;
  padding: 9px 13px;
}
.shop-tab.active { background: linear-gradient(135deg, var(--accent), var(--accent-2)); font-weight: 900; }
.shop-item {
  display: grid;
  gap: 10px;
  min-height: 170px;
  transition: transform 160ms ease, box-shadow 160ms ease, border-color 160ms ease;
}
.shop-item footer { display: flex; justify-content: space-between; align-items: center; gap: 10px; flex-wrap: wrap; margin-top: auto; }
.shop-item:hover { transform: translateY(-1px); }
.shop-item.rarity-common { border-color: rgba(255,255,255,0.62); box-shadow: var(--shadow), inset 0 0 0 1px rgba(255,255,255,0.10); }
.shop-item.rarity-rare { border-color: rgba(80,180,255,0.72); box-shadow: var(--shadow), 0 0 22px rgba(80,180,255,0.13); }
.shop-item.rarity-epic { border-color: rgba(255,80,190,0.76); box-shadow: var(--shadow), 0 0 24px rgba(255,80,190,0.18); }
.shop-item.rarity-legendary { border-color: rgba(255,215,70,0.90); box-shadow: var(--shadow), 0 0 28px rgba(255,215,70,0.22); }
.shop-item.rarity-legendary::before { background: linear-gradient(135deg, rgba(255,215,70,0.14), transparent 42%, rgba(255,20,157,0.08)); }
.shop-item.discounted { border-style: solid; }
.price { color: var(--good); font-weight: 900; }
.owned { color: var(--accent-3); font-weight: 900; }
.purchase-flash { animation: purchaseFlash 900ms ease both; }
@keyframes purchaseFlash { 0% { transform: scale(0.985); } 45% { transform: scale(1.018); box-shadow: 0 0 45px rgba(var(--accent-rgb),0.44), 0 0 70px rgba(var(--accent-2-rgb),0.25); } 100% { transform: scale(1); } }

.bottom-nav {
  position: fixed;
  z-index: 50;
  left: 50%;
  bottom: 14px;
  transform: translateX(-50%);
  width: min(760px, calc(100% - 24px));
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 6px;
  border: 1px solid var(--border);
  border-radius: 24px;
  padding: 8px;
  background: rgba(16, 5, 24, 0.96);
  box-shadow: var(--shadow);
  backdrop-filter: blur(20px);
}
.nav-btn {
  border: 0;
  border-radius: 18px;
  background: transparent;
  color: var(--muted);
  padding: 9px 6px;
  font-size: 0.78rem;
  font-weight: 800;
}
.nav-btn span { display: block; font-size: 1rem; margin-bottom: 2px; }
.nav-btn.active {
  color: white;
  background: linear-gradient(135deg, rgba(var(--accent-rgb), 0.55), rgba(var(--accent-2-rgb), 0.35));
}

.toast {
  position: fixed;
  left: 50%;
  bottom: 96px;
  transform: translateX(-50%) translateY(20px);
  opacity: 0;
  pointer-events: none;
  z-index: 100;
  border: 1px solid var(--border);
  border-radius: 999px;
  padding: 11px 15px;
  color: var(--text);
  background: var(--panel-strong);
  box-shadow: var(--shadow);
  transition: opacity 180ms ease, transform 180ms ease;
  max-width: min(560px, calc(100% - 24px));
  text-align: center;
}
.toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

.pulse-roll { animation: pulseRoll 520ms ease both; }
@keyframes pulseRoll { 0% { transform: scale(0.99); } 45% { transform: scale(1.014); box-shadow: 0 0 40px rgba(var(--accent-rgb), 0.35); } 100% { transform: scale(1); } }
.effect-neon { animation: neonFlash 920ms ease both; }
@keyframes neonFlash { 0%,100% { filter: none; } 25% { filter: brightness(1.25) drop-shadow(0 0 18px var(--accent)); } 55% { filter: brightness(1.4) drop-shadow(0 0 34px var(--accent-3)); } }
.effect-heart { animation: heartBurst 900ms ease both; }
@keyframes heartBurst { 0% { transform: scale(0.98); } 40% { transform: scale(1.022) rotate(-0.5deg); box-shadow: 0 0 36px rgba(255,133,213,0.24); } 100% { transform: scale(1) rotate(0); } }
.effect-glitch { animation: glitchRoll 760ms steps(2, end) both; }
@keyframes glitchRoll { 0%, 100% { transform: translate(0,0); filter: none; } 16% { transform: translate(3px,-1px); filter: hue-rotate(30deg); } 32% { transform: translate(-3px,1px); filter: hue-rotate(-35deg); } 48% { transform: translate(2px,2px); } 64% { transform: translate(-2px,-2px); } 80% { transform: translate(1px,-1px); } }
.effect-sparkle { animation: sparkleRoll 1000ms ease both; }
@keyframes sparkleRoll { 0% { box-shadow: var(--shadow); } 50% { box-shadow: 0 0 20px var(--accent), 0 0 65px var(--accent-3); } 100% { box-shadow: var(--shadow); } }
.effect-vip { animation: vipFlash 1050ms ease both; }
@keyframes vipFlash { 0%,100% { outline: 0 solid transparent; } 45% { outline: 3px solid #ffd85a; box-shadow: 0 0 38px #ffd85a, 0 0 72px rgba(255,20,157,0.26); } }
.roll-fx-stage {
  position: absolute;
  inset: 0;
  overflow: hidden;
  pointer-events: none;
  z-index: 2;
  opacity: 0;
}
.roll-fx-stage.show { opacity: 1; }
.roll-fx-stage span {
  position: absolute;
  left: var(--x);
  top: var(--y);
  font-size: var(--size, 1.2rem);
  font-weight: 1000;
  color: var(--fx-color, var(--accent-3));
  text-shadow: 0 0 12px currentColor, 0 0 28px currentColor;
  animation: fxFloat 1050ms ease-out both;
}
@keyframes fxFloat { 0% { opacity: 0; transform: translateY(10px) scale(0.7) rotate(-8deg); } 18% { opacity: 1; } 100% { opacity: 0; transform: translateY(-56px) scale(1.26) rotate(12deg); } }
.roll-fx-stage.fx-basic { --fx-color: var(--accent-3); }
.roll-fx-stage.fx-neon { --fx-color: #61f7ff; }
.roll-fx-stage.fx-heart { --fx-color: #ff85d5; }
.roll-fx-stage.fx-glitch { --fx-color: #76f7ff; }
.roll-fx-stage.fx-sparkle { --fx-color: #ffffff; }
.roll-fx-stage.fx-vip { --fx-color: #ffd85a; }
.wallet.bump { animation: walletBump 850ms ease both; }
@keyframes walletBump { 0% { transform: translateY(0) scale(1); } 35% { transform: translateY(-2px) scale(1.04); box-shadow: 0 0 28px rgba(var(--accent-rgb),0.35); } 100% { transform: translateY(0) scale(1); } }
.milestone-entry.major, .milestone-entry.legendary-entry { border-color: rgba(255,215,70,0.55); box-shadow: 0 0 22px rgba(255,215,70,0.13); }
.milestone-entry.new-pop { animation: newMilestonePop 900ms ease both; }
@keyframes newMilestonePop { 0% { transform: scale(0.97); opacity: 0.4; } 45% { transform: scale(1.015); opacity: 1; box-shadow: 0 0 32px rgba(var(--accent-rgb),0.35); } 100% { transform: scale(1); } }

@media (display-mode: standalone) {
  .app-shell { padding-top: max(22px, env(safe-area-inset-top)); }
}


@media (max-width: 520px) {
  .app-shell { padding: 16px 12px 94px; }
  .topbar { align-items: flex-start; gap: 10px; }
  h1 { font-size: clamp(1.85rem, 13vw, 3.15rem); letter-spacing: -0.055em; }
  .wallet { min-width: 92px; padding: 8px 10px; }
  .wallet-icon { width: 28px; height: 28px; }
  .card { padding: 14px; border-radius: 18px; }
  .card-title-row { flex-direction: column; align-items: stretch; }
  .roll-controls { align-items: stretch; }
  .roll-controls .btn, .roll-controls .control-pill { width: 100%; justify-content: center; }
  .bottom-nav { bottom: 8px; width: calc(100% - 16px); border-radius: 20px; padding: 6px; }
  .nav-btn { font-size: 0.69rem; border-radius: 15px; padding: 8px 3px; }
  .color-grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .list-item { grid-template-columns: auto 1fr; }
  .list-item .btn { grid-column: 1 / -1; }
}

.big-number {
  margin: 8px 0 0;
  font-size: clamp(2rem, 7vw, 3.6rem);
  font-weight: 950;
  color: var(--accent-3);
  text-shadow: 0 0 20px rgba(var(--accent-3-rgb), 0.35);
}

.error-box {
  white-space: pre-wrap;
  background: rgba(0,0,0,0.38);
  border: 1px solid rgba(var(--accent-rgb), 0.35);
  border-radius: 14px;
  padding: 12px;
  color: var(--danger);
  overflow:auto;
}


/* v10 training system */
.top-wallets { display: flex; gap: 10px; align-items: stretch; flex-wrap: wrap; justify-content: flex-end; }
.obedience-wallet { border-color: rgba(54,245,255,0.38); box-shadow: 0 0 22px rgba(54,245,255,0.10); }
.training-summary { display: grid; gap: 10px; grid-template-columns: repeat(3, minmax(0, 1fr)); margin-top: 12px; }
.training-stat { border: 1px solid var(--border); border-radius: 16px; padding: 12px; background: rgba(0,0,0,0.18); }
.training-stat strong { display:block; font-size:1.25rem; }
.training-category { position: relative; overflow: hidden; }
.training-category::before { content:''; position:absolute; inset:0; background: radial-gradient(circle at top right, rgba(var(--accent-rgb),0.12), transparent 45%); pointer-events:none; }
.training-category > * { position: relative; }
.offer-box, .active-task-box, .task-editor-box, .upgrade-box { border: 1px solid rgba(255,255,255,0.10); background: rgba(0,0,0,0.18); border-radius: 18px; padding: 12px; margin-top: 12px; }
.offer-box { border-color: rgba(54,245,255,0.30); box-shadow: 0 0 18px rgba(54,245,255,0.08); }
.active-task-box { border-color: rgba(255,216,90,0.36); box-shadow: 0 0 18px rgba(255,216,90,0.09); }
.training-task-list { display:grid; gap:8px; margin-top:10px; }
.training-add-row {
  display:flex;
  gap:8px;
  align-items:stretch;
  margin-top:10px;
  padding:10px;
  border:1px solid rgba(var(--accent-rgb),0.24);
  border-radius:18px;
  background:
    radial-gradient(circle at top left, rgba(var(--accent-rgb),0.12), transparent 46%),
    rgba(0,0,0,0.20);
  box-shadow: inset 0 0 0 1px rgba(255,255,255,0.025);
}
.training-add-row input,
.training-task-row input[type='text'] {
  flex:1;
  min-width:0;
  border:1px solid rgba(255,255,255,0.12);
  border-radius:15px;
  padding:10px 12px;
  color:var(--text);
  background:rgba(0,0,0,0.28);
  outline:none;
  box-shadow: inset 0 0 12px rgba(0,0,0,0.20);
}
.training-add-row input::placeholder,
.training-task-row input[type='text']::placeholder { color: rgba(255,255,255,0.46); }
.training-add-row input:focus,
.training-task-row input[type='text']:focus {
  border-color:var(--accent);
  box-shadow:0 0 0 3px rgba(var(--accent-rgb),0.16), inset 0 0 12px rgba(0,0,0,0.22);
}
.training-task-row {
  display:flex;
  align-items:center;
  gap:8px;
  padding:9px;
  border:1px solid rgba(255,255,255,0.10);
  border-radius:16px;
  background:linear-gradient(135deg, rgba(var(--accent-rgb),0.055), rgba(var(--accent-2-rgb),0.035)), rgba(0,0,0,0.18);
}
.training-task-row input[type='checkbox'] { accent-color: var(--accent); width:18px; height:18px; }
.training-task-display {
  margin:10px 0;
  padding:12px 13px;
  border:1px solid rgba(var(--accent-rgb),0.24);
  border-radius:16px;
  background:linear-gradient(135deg, rgba(var(--accent-rgb),0.10), rgba(var(--accent-2-rgb),0.055)), rgba(0,0,0,0.22);
  color:var(--text);
  box-shadow: inset 0 0 18px rgba(0,0,0,0.12);
}
@media (max-width: 520px) { .training-add-row, .training-task-row { flex-direction:column; align-items:stretch; } }
.timer-display { font-size: 1.8rem; font-weight: 900; letter-spacing: 0.04em; color: var(--warn); text-shadow: 0 0 18px rgba(255,211,110,0.25); margin: 8px 0; }
.category-pill-row { display:flex; gap:8px; flex-wrap:wrap; }
.conversion-row { display:flex; gap:10px; flex-wrap:wrap; align-items:center; margin-top:12px; }
.upgrade-grid { display:grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap:12px; margin-top:12px; }
.upgrade-box footer { display:flex; justify-content:space-between; gap:10px; align-items:center; margin-top:10px; }
.milestone-entry.training-milestone { border-color: rgba(54,245,255,0.28); }
.price.obedience-price, .obedience-text { color: var(--accent-3); text-shadow: 0 0 14px rgba(54,245,255,0.18); }

/* v12 outfit library + rank battle pass */
.collection-summary { display:grid; grid-template-columns: repeat(4, minmax(0, 1fr)); gap:10px; margin-top:12px; }
.collection-stat { border:1px solid var(--border); border-radius:16px; padding:12px; background:rgba(0,0,0,0.18); }
.collection-stat strong { display:block; font-size:1.2rem; }
.outfit-card.locked { opacity:0.72; filter:saturate(0.65); }
.outfit-card .pieces { margin-top:10px; display:grid; gap:4px; }
.outfit-card .pieces span { display:block; font-size:.84rem; color:var(--muted); }
.rank-hero { position:relative; overflow:hidden; }
.rank-hero::before { content:''; position:absolute; inset:-80px -80px auto auto; width:220px; height:220px; background:radial-gradient(circle, rgba(var(--accent-rgb),0.22), transparent 62%); pointer-events:none; }
.rank-hero > * { position:relative; }
.rank-progress { height:18px; background:rgba(255,255,255,0.08); border:1px solid var(--border); border-radius:999px; overflow:hidden; box-shadow: inset 0 0 16px rgba(0,0,0,0.25); }
.rank-progress > span { display:block; height:100%; width:0%; background:linear-gradient(90deg, var(--accent), var(--accent-2)); box-shadow:0 0 18px rgba(var(--accent-rgb),0.42); transition:width 350ms ease; }
.rank-track { display:grid; gap:10px; margin-top:14px; }
.rank-node { display:grid; grid-template-columns: 86px 1fr auto; gap:12px; align-items:center; border:1px solid var(--border); border-radius:18px; padding:12px; background:rgba(255,255,255,0.045); }
.rank-node.claimed { border-color:rgba(75,255,165,0.28); background:rgba(75,255,165,0.055); }
.rank-node.current { border-color:rgba(var(--accent-rgb),0.55); box-shadow:0 0 22px rgba(var(--accent-rgb),0.16); }
.rank-number { font-weight:900; font-size:1.05rem; }
.rank-reward-list { display:flex; gap:6px; flex-wrap:wrap; margin-top:4px; }
.rank-reward-list .badge { font-size:.74rem; }
.discount-line { font-size:.82rem; color:var(--muted); }
@media (max-width: 720px) { .collection-summary { grid-template-columns: 1fr 1fr; } .rank-node { grid-template-columns: 1fr; } }

/* v13 currency logo icons */
:root {
  --logo-exhys: url('data:image/webp;base64,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');
  --logo-obedience: url('data:image/webp;base64,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');
}
.wallet-icon.currency-logo {
  position: relative;
  overflow: hidden;
  color: transparent;
  background: rgba(0,0,0,0.28);
  border: 1px solid rgba(255,255,255,0.16);
  box-shadow: 0 0 18px rgba(var(--accent-rgb),0.22), inset 0 0 0 1px rgba(255,255,255,0.04);
  padding: 0;
}
.wallet-icon.currency-logo::before {
  content: '';
  position: absolute;
  inset: 0;
  background-size: cover;
  background-position: center;
  border-radius: inherit;
}
.wallet-icon.currency-logo.exhys::before { background-image: var(--logo-exhys); }
.wallet-icon.currency-logo.obedience::before { background-image: var(--logo-obedience); }
.currency-inline {
  display: inline-block;
  width: 1.18em;
  height: 1.18em;
  margin-right: 0.28em;
  vertical-align: -0.22em;
  border-radius: 999px;
  background-size: cover;
  background-position: center;
  box-shadow: 0 0 10px rgba(var(--accent-rgb),0.20);
}
.currency-inline.exhys { background-image: var(--logo-exhys); }
.currency-inline.obedience { background-image: var(--logo-obedience); box-shadow: 0 0 10px rgba(255,255,255,0.16); }
.wallet small.currency-label { display:flex; align-items:center; gap:4px; }


@media (max-width: 720px) { .training-summary, .upgrade-grid { grid-template-columns: 1fr; } .top-wallets { width:100%; justify-content:space-between; } .top-wallets .wallet { flex:1; min-width: 0; } }

  </style>
</head>
<body class="theme-neon">
  <div id="app" class="app-shell">
    <header class="topbar">
      <div>
        <p class="eyebrow">Neon Dressing Room</p>
        <h1>Dressed <span>&amp;</span> Dared</h1>
      </div>
      <div class="top-wallets">
        <div class="wallet" title="Exhys balance">
          <span class="wallet-icon currency-logo exhys" aria-hidden="true"></span>
          <div>
            <strong id="exhysBalance">0</strong>
            <small>Exhys</small>
          </div>
        </div>
        <div class="wallet obedience-wallet" title="Obedience balance">
          <span class="wallet-icon currency-logo obedience" aria-hidden="true"></span>
          <div>
            <strong id="obedienceBalance">0</strong>
            <small>Obedience</small>
          </div>
        </div>
      </div>
    </header>

    <main>
      <section id="view-home" class="view active">
        <section class="card">
          <h2>Loading Dressed &amp; Dared...</h2>
          <p class="muted">If this stays here, clear site data for this GitHub Pages site and reload.</p>
        </section>
      </section>
      <section id="view-wardrobe" class="view"></section>
      <section id="view-training" class="view"></section>
      <section id="view-rank" class="view"></section>
      <section id="view-lists" class="view"></section>
      <section id="view-shop" class="view"></section>
    </main>

    <nav class="bottom-nav" aria-label="Main navigation">
      <button class="nav-btn active" type="button" data-view="home"><span>◆</span>Home</button>
      <button class="nav-btn" type="button" data-view="wardrobe"><span>◇</span>Wardrobe</button>
      <button class="nav-btn" type="button" data-view="training"><span>◆</span>Training</button>
      <button class="nav-btn" type="button" data-view="rank"><span>★</span>Rank</button>
      <button class="nav-btn" type="button" data-view="lists"><span>✚</span>Lists</button>
      <button class="nav-btn" type="button" data-view="shop"><span>✦</span>Shop</button>
    </nav>
  </div>

  <div id="toast" class="toast" aria-live="polite"></div>

  <script>
(() => {
  'use strict';

  const STORAGE_KEY = 'dressedAndDared.v1';

  const COLORS = [
    { name: 'Black', value: '#050505' },
    { name: 'White', value: '#f6f2ff' },
    { name: 'Red', value: '#ff2f51' },
    { name: 'Pink', value: '#ff85d5' },
    { name: 'Hot Pink', value: '#ff149d' },
    { name: 'Blue', value: '#3aa8ff' },
    { name: 'Purple', value: '#9d4dff' },
    { name: 'Yellow', value: '#ffd83e' },
    { name: 'Silver', value: '#cfd5e6' },
    { name: 'Gold', value: '#ffd76b' },
    { name: 'Brown', value: '#9a5b2e' },
    { name: 'Green', value: '#46ef9c' },
    { name: 'Clear', value: 'linear-gradient(135deg, rgba(255,255,255,0.8), rgba(80,200,255,0.35))' }
  ];

  const WIG_OPTIONS = [
    { name: 'Platinum Blonde', value: 'linear-gradient(135deg, #f7f0cf, #ffffff)' },
    { name: 'Blonde', value: '#f7d66b' },
    { name: 'Purple', value: '#9d4dff' },
    { name: 'Pink', value: '#ff85d5' },
    { name: 'Black', value: '#050505' },
    { name: 'Red and Black', value: 'linear-gradient(135deg, #ff2f51 0 48%, #050505 52% 100%)' },
    { name: 'Brunette', value: '#6b3a1e' },
    { name: 'Curly Brunette', value: 'linear-gradient(135deg, #4a2614, #8a552e)' },
    { name: 'Pink and White', value: 'linear-gradient(135deg, #ff85d5 0 48%, #ffffff 52% 100%)' },
    { name: 'Silver', value: '#cfd5e6' }
  ];

  const CATEGORIES = [
    'Panties', 'Bra', 'Dress', 'Top', 'Skirt', 'Stockings', 'Socks', 'Shoes', 'Wig', 'Makeup', 'Accessory', 'Coat'
  ];

  const TEMPLATES = [
    { name: 'Dress', slots: ['Panties', 'Bra', 'Dress', 'Stockings', 'Shoes', 'Wig', 'Makeup', 'Accessory'] },
    { name: 'Skirt', slots: ['Panties', 'Bra', 'Top', 'Skirt', 'Stockings', 'Shoes', 'Wig', 'Makeup', 'Accessory'] },
    { name: 'Lingerie', slots: ['Panties', 'Bra', 'Stockings', 'Shoes', 'Makeup'] },
    { name: 'Covered', slots: ['Panties', 'Bra', 'Top', 'Skirt', 'Shoes', 'Coat', 'Makeup'] },
    { name: 'Casual', slots: ['Panties', 'Bra', 'Top', 'Skirt', 'Socks', 'Shoes', 'Makeup'] }
  ];


  const RARITY = {
    common: { label: 'Common', basePrice: 60, weight: 40 },
    rare: { label: 'Rare', basePrice: 150, weight: 20 },
    epic: { label: 'Epic', basePrice: 350, weight: 8 },
    legendary: { label: 'Legendary', basePrice: 800, weight: 2 }
  };

  const OUTFIT_LIBRARY = [
    {
        "id": "outfit-001",
        "number": 1,
        "kind": "outfit",
        "name": "Bubblegum Errand",
        "rarity": "common",
        "details": "Pink top, jeans, pink trainers, blonde wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-002",
        "number": 2,
        "kind": "outfit",
        "name": "Blue Weekend",
        "rarity": "common",
        "details": "Blue top, jeans, blue trainers, brunette wig",
        "unlock": "start"
    },
    {
        "id": "outfit-003",
        "number": 3,
        "kind": "outfit",
        "name": "Snowdrop Casual",
        "rarity": "common",
        "details": "White top, jeans, white heels, platinum blonde wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-004",
        "number": 4,
        "kind": "outfit",
        "name": "Midnight Coffee Run",
        "rarity": "common",
        "details": "Black top, jeans, black heels, black wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-005",
        "number": 5,
        "kind": "outfit",
        "name": "Lemon Daydream",
        "rarity": "common",
        "details": "Yellow top, jeans, pink trainers, blonde wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-006",
        "number": 6,
        "kind": "outfit",
        "name": "Candy Skater",
        "rarity": "common",
        "details": "Pink top, white skirt, pink heels, pink wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-007",
        "number": 7,
        "kind": "outfit",
        "name": "Cloud Nine",
        "rarity": "common",
        "details": "White top, blue skirt, blue heels, blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-008",
        "number": 8,
        "kind": "outfit",
        "name": "After-Dark Beginner",
        "rarity": "common",
        "details": "Black top, black skirt, black heels, black wig, black makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-009",
        "number": 9,
        "kind": "outfit",
        "name": "Blush Sunday",
        "rarity": "common",
        "details": "Pink top, white skirt, white heels, platinum blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-010",
        "number": 10,
        "kind": "outfit",
        "name": "Honey Skirt",
        "rarity": "common",
        "details": "Yellow top, white skirt, yellow heels, blonde wig, pink makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-011",
        "number": 11,
        "kind": "outfit",
        "name": "Blue Dash",
        "rarity": "common",
        "details": "Blue top, jeans, blue trainers, silver wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-012",
        "number": 12,
        "kind": "outfit",
        "name": "Bubblegum Dash",
        "rarity": "common",
        "details": "Pink top, jeans, pink trainers, pink and white wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-013",
        "number": 13,
        "kind": "outfit",
        "name": "Pink Daydream",
        "rarity": "common",
        "details": "Pink dress, pink heels, pink wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-014",
        "number": 14,
        "kind": "outfit",
        "name": "Bluebell",
        "rarity": "common",
        "details": "Blue dress, blue heels, blonde wig",
        "unlock": "start"
    },
    {
        "id": "outfit-015",
        "number": 15,
        "kind": "outfit",
        "name": "Snow Angel Day",
        "rarity": "common",
        "details": "White dress, white heels, platinum blonde wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-016",
        "number": 16,
        "kind": "outfit",
        "name": "Midnight Dress",
        "rarity": "common",
        "details": "Black dress, black heels, black wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-017",
        "number": 17,
        "kind": "outfit",
        "name": "Lemon Drop",
        "rarity": "common",
        "details": "Yellow dress, yellow heels, blonde wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-018",
        "number": 18,
        "kind": "outfit",
        "name": "Violet Crush",
        "rarity": "common",
        "details": "Purple dress, purple heels, purple wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-019",
        "number": 19,
        "kind": "outfit",
        "name": "Meadow Girl",
        "rarity": "common",
        "details": "Green dress, white heels, brunette wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-020",
        "number": 20,
        "kind": "outfit",
        "name": "Cocoa Softie",
        "rarity": "common",
        "details": "Brown dress, black heels, curly brunette wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-021",
        "number": 21,
        "kind": "outfit",
        "name": "Sugar Pop",
        "rarity": "common",
        "details": "Pink top, white skirt, pink heels, pink and white wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-022",
        "number": 22,
        "kind": "outfit",
        "name": "Blue Sugar",
        "rarity": "common",
        "details": "Blue top, white skirt, blue heels, silver wig, blue makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-023",
        "number": 23,
        "kind": "outfit",
        "name": "Midnight Blush",
        "rarity": "common",
        "details": "Black top, pink skirt, black heels, black wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-024",
        "number": 24,
        "kind": "outfit",
        "name": "Lemon Splash",
        "rarity": "common",
        "details": "Yellow top, blue skirt, blue heels, blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-025",
        "number": 25,
        "kind": "outfit",
        "name": "Porcelain Blue",
        "rarity": "common",
        "details": "White top, blue skirt, white heels, silver wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-026",
        "number": 26,
        "kind": "outfit",
        "name": "Violet Lounge",
        "rarity": "common",
        "details": "Pink top, purple leggings, pink trainers, purple wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-027",
        "number": 27,
        "kind": "outfit",
        "name": "Citrus Sport",
        "rarity": "common",
        "details": "Orange sports bra, jeans, blue trainers, brunette wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-028",
        "number": 28,
        "kind": "outfit",
        "name": "Purple Pulse",
        "rarity": "common",
        "details": "Purple sports bra, jeans, pink trainers, purple wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-029",
        "number": 29,
        "kind": "outfit",
        "name": "Hidden Sweetheart",
        "rarity": "common",
        "details": "White top, jeans, long overcoat, black heels, blonde wig",
        "unlock": "start"
    },
    {
        "id": "outfit-030",
        "number": 30,
        "kind": "outfit",
        "name": "Blonde Blush",
        "rarity": "common",
        "details": "Pink dress, white heels, blonde wig, pink makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-031",
        "number": 31,
        "kind": "outfit",
        "name": "Soft Storm",
        "rarity": "common",
        "details": "Blue top, jeans, black heels, curly brunette wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-032",
        "number": 32,
        "kind": "outfit",
        "name": "Silver Sunday",
        "rarity": "common",
        "details": "White dress, white heels, silver wig, blue makeup",
        "unlock": "rank",
        "rankLevel": 2
    },
    {
        "id": "outfit-033",
        "number": 33,
        "kind": "outfit",
        "name": "Pink Candy Run",
        "rarity": "common",
        "details": "Pink top, jeans, pink trainers, pink wig",
        "unlock": "rank",
        "rankLevel": 4
    },
    {
        "id": "outfit-034",
        "number": 34,
        "kind": "outfit",
        "name": "Black Coffee",
        "rarity": "common",
        "details": "Black top, jeans, black heels, black wig",
        "unlock": "rank",
        "rankLevel": 6
    },
    {
        "id": "outfit-035",
        "number": 35,
        "kind": "outfit",
        "name": "Scarlet Streak",
        "rarity": "common",
        "details": "White top, black skirt, red and black wig, red heels",
        "unlock": "rank",
        "rankLevel": 8
    },
    {
        "id": "outfit-036",
        "number": 36,
        "kind": "outfit",
        "name": "Platinum Breeze",
        "rarity": "common",
        "details": "Blue dress, white heels, platinum blonde wig",
        "unlock": "rank",
        "rankLevel": 10
    },
    {
        "id": "outfit-037",
        "number": 37,
        "kind": "outfit",
        "name": "Garden Blush",
        "rarity": "common",
        "details": "Green dress, white heels, brunette wig, pink makeup",
        "unlock": "rank",
        "rankLevel": 12
    },
    {
        "id": "outfit-038",
        "number": 38,
        "kind": "outfit",
        "name": "Hot Pink Spark",
        "rarity": "common",
        "details": "Hot pink dress, pink heels, pink wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-039",
        "number": 39,
        "kind": "outfit",
        "name": "Cherry Daylight",
        "rarity": "common",
        "details": "Red dress, red heels, red and black wig, red makeup",
        "unlock": "rank",
        "rankLevel": 14
    },
    {
        "id": "outfit-040",
        "number": 40,
        "kind": "outfit",
        "name": "Golden Hour",
        "rarity": "common",
        "details": "Gold dress, white heels, blonde wig",
        "unlock": "rank",
        "rankLevel": 16
    },
    {
        "id": "outfit-041",
        "number": 41,
        "kind": "outfit",
        "name": "Silver Glow",
        "rarity": "common",
        "details": "Silver dress, white heels, silver wig",
        "unlock": "rank",
        "rankLevel": 18
    },
    {
        "id": "outfit-042",
        "number": 42,
        "kind": "outfit",
        "name": "Blush Under Cover",
        "rarity": "common",
        "details": "Pink dress, long overcoat, pink heels, pink wig",
        "unlock": "rank",
        "rankLevel": 20
    },
    {
        "id": "outfit-043",
        "number": 43,
        "kind": "outfit",
        "name": "Blue Under Cover",
        "rarity": "common",
        "details": "Blue dress, long overcoat, blue heels, blonde wig",
        "unlock": "rank",
        "rankLevel": 24
    },
    {
        "id": "outfit-044",
        "number": 44,
        "kind": "outfit",
        "name": "Midnight Under Cover",
        "rarity": "common",
        "details": "Black dress, long overcoat, black heels, black wig",
        "unlock": "rank",
        "rankLevel": 26
    },
    {
        "id": "outfit-045",
        "number": 45,
        "kind": "outfit",
        "name": "Snow Under Cover",
        "rarity": "common",
        "details": "White dress, long overcoat, white heels, platinum blonde wig",
        "unlock": "rank",
        "rankLevel": 28
    },
    {
        "id": "outfit-046",
        "number": 46,
        "kind": "outfit",
        "name": "Blush Invitation",
        "rarity": "rare",
        "details": "Pink dress, white stockings, pink heels, pink wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-047",
        "number": 47,
        "kind": "outfit",
        "name": "Midnight Invitation",
        "rarity": "rare",
        "details": "Black dress, black stockings, black heels, black wig, red makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-048",
        "number": 48,
        "kind": "outfit",
        "name": "Scarlet Invitation",
        "rarity": "rare",
        "details": "Red dress, black stockings, red heels, red and black wig, red makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-049",
        "number": 49,
        "kind": "outfit",
        "name": "Blue Velvet",
        "rarity": "rare",
        "details": "Blue dress, white stockings, blue heels, blonde wig, blue makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-050",
        "number": 50,
        "kind": "outfit",
        "name": "Violet Velvet",
        "rarity": "rare",
        "details": "Purple dress, black stockings, purple heels, purple wig",
        "unlock": "rank",
        "rankLevel": 22
    },
    {
        "id": "outfit-051",
        "number": 51,
        "kind": "outfit",
        "name": "Hot Pink Afterparty",
        "rarity": "rare",
        "details": "Hot pink dress, pink stockings, hot pink heels, pink wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-052",
        "number": 52,
        "kind": "outfit",
        "name": "Silver Spotlight",
        "rarity": "rare",
        "details": "Silver dress, white stockings, blue heels, silver wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-053",
        "number": 53,
        "kind": "outfit",
        "name": "Golden Spotlight",
        "rarity": "rare",
        "details": "Gold dress, white stockings, yellow heels, blonde wig, gold-style makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-054",
        "number": 54,
        "kind": "outfit",
        "name": "Black Cherry",
        "rarity": "rare",
        "details": "Black dress, red stockings, red heels, red and black wig, red makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-055",
        "number": 55,
        "kind": "outfit",
        "name": "Sugar Date",
        "rarity": "rare",
        "details": "White dress, pink stockings, pink heels, platinum blonde wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-056",
        "number": 56,
        "kind": "outfit",
        "name": "Ice Blue Doll",
        "rarity": "rare",
        "details": "Blue dress, white stockings, silver wig, blue heels, blue makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-057",
        "number": 57,
        "kind": "outfit",
        "name": "Violet Doll",
        "rarity": "rare",
        "details": "Purple dress, white stockings, purple wig, pink makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-058",
        "number": 58,
        "kind": "outfit",
        "name": "Candy Doll",
        "rarity": "rare",
        "details": "Pink dress, white stockings, pink and white wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-059",
        "number": 59,
        "kind": "outfit",
        "name": "Midnight Doll",
        "rarity": "rare",
        "details": "Black dress, white stockings, black wig, black makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-060",
        "number": 60,
        "kind": "outfit",
        "name": "Scarlet Doll",
        "rarity": "rare",
        "details": "Red dress, black stockings, red and black wig, red heels",
        "unlock": "shop"
    },
    {
        "id": "outfit-061",
        "number": 61,
        "kind": "outfit",
        "name": "Garden Date",
        "rarity": "rare",
        "details": "Green dress, white stockings, brunette wig, pink makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-062",
        "number": 62,
        "kind": "outfit",
        "name": "Cocoa Date",
        "rarity": "rare",
        "details": "Brown dress, black stockings, curly brunette wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-063",
        "number": 63,
        "kind": "outfit",
        "name": "Pink Promenade",
        "rarity": "rare",
        "details": "Pink top, pink skirt, white stockings, pink heels, pink wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-064",
        "number": 64,
        "kind": "outfit",
        "name": "Blue Promenade",
        "rarity": "rare",
        "details": "Blue top, blue skirt, white stockings, blue heels, blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-065",
        "number": 65,
        "kind": "outfit",
        "name": "Midnight Promenade",
        "rarity": "rare",
        "details": "Black top, black skirt, black stockings, black heels, black wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-066",
        "number": 66,
        "kind": "outfit",
        "name": "Snow Promenade",
        "rarity": "rare",
        "details": "White top, white skirt, pink stockings, white heels, platinum blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-067",
        "number": 67,
        "kind": "outfit",
        "name": "Violet Silhouette",
        "rarity": "rare",
        "details": "Purple leggings, black top, purple heels, purple wig, black makeup",
        "unlock": "rank",
        "rankLevel": 30
    },
    {
        "id": "outfit-068",
        "number": 68,
        "kind": "outfit",
        "name": "Citrus Tease",
        "rarity": "rare",
        "details": "Orange sports bra, black skirt, black stockings, black heels, brunette wig",
        "unlock": "rank",
        "rankLevel": 32
    },
    {
        "id": "outfit-069",
        "number": 69,
        "kind": "outfit",
        "name": "Purple Tease",
        "rarity": "rare",
        "details": "Purple sports bra, black skirt, black stockings, purple heels, purple wig",
        "unlock": "rank",
        "rankLevel": 34
    },
    {
        "id": "outfit-070",
        "number": 70,
        "kind": "outfit",
        "name": "Raceway Crush",
        "rarity": "rare",
        "details": "Pink racing bodysuit, pink heels, pink wig, pink makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-071",
        "number": 71,
        "kind": "outfit",
        "name": "Midnight Cover Story",
        "rarity": "rare",
        "details": "Black dress, long overcoat, black stockings, black heels, black wig",
        "unlock": "rank",
        "rankLevel": 36
    },
    {
        "id": "outfit-072",
        "number": 72,
        "kind": "outfit",
        "name": "Snow Cover Story",
        "rarity": "rare",
        "details": "White dress, long overcoat, white stockings, white heels, platinum blonde wig",
        "unlock": "rank",
        "rankLevel": 38
    },
    {
        "id": "outfit-073",
        "number": 73,
        "kind": "outfit",
        "name": "Scarlet Cover Story",
        "rarity": "rare",
        "details": "Red dress, long overcoat, black stockings, red heels, red and black wig",
        "unlock": "rank",
        "rankLevel": 40
    },
    {
        "id": "outfit-074",
        "number": 74,
        "kind": "outfit",
        "name": "Blush Cover Story",
        "rarity": "rare",
        "details": "Pink dress, long overcoat, white stockings, pink heels, pink wig",
        "unlock": "rank",
        "rankLevel": 42
    },
    {
        "id": "outfit-075",
        "number": 75,
        "kind": "outfit",
        "name": "Blue Cover Story",
        "rarity": "rare",
        "details": "Blue dress, long overcoat, white stockings, blue heels, silver wig",
        "unlock": "rank",
        "rankLevel": 43
    },
    {
        "id": "outfit-076",
        "number": 76,
        "kind": "outfit",
        "name": "Angel Lingerie",
        "rarity": "epic",
        "details": "White panties, white bra, white stockings, white heels, platinum blonde wig, pink makeup",
        "unlock": "start"
    },
    {
        "id": "outfit-077",
        "number": 77,
        "kind": "outfit",
        "name": "Devil Lingerie",
        "rarity": "epic",
        "details": "Black panties, red bra, black stockings, red heels, red and black wig, red makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-078",
        "number": 78,
        "kind": "outfit",
        "name": "Bubblegum Lingerie",
        "rarity": "epic",
        "details": "Hot pink panties, hot pink bra, pink stockings, hot pink heels, pink wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-079",
        "number": 79,
        "kind": "outfit",
        "name": "Midnight Lingerie",
        "rarity": "epic",
        "details": "Black panties, black bra, black stockings, black heels, black wig, black makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-080",
        "number": 80,
        "kind": "outfit",
        "name": "Scarlet Lingerie",
        "rarity": "epic",
        "details": "Red panties, red bra, black stockings, red heels, red and black wig, red makeup",
        "unlock": "milestone"
    },
    {
        "id": "outfit-081",
        "number": 81,
        "kind": "outfit",
        "name": "Violet Lingerie",
        "rarity": "epic",
        "details": "Purple panties, purple bra, black stockings, purple heels, purple wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-082",
        "number": 82,
        "kind": "outfit",
        "name": "Blue Lingerie",
        "rarity": "epic",
        "details": "Blue panties, blue bra, white stockings, blue heels, silver wig, blue makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-083",
        "number": 83,
        "kind": "outfit",
        "name": "Snow Lingerie",
        "rarity": "epic",
        "details": "White panties, white bra, white stockings, white heels, blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-084",
        "number": 84,
        "kind": "outfit",
        "name": "Candy Lingerie",
        "rarity": "epic",
        "details": "Pink panties, white bra, pink stockings, white heels, pink and white wig, pink makeup",
        "unlock": "rank",
        "rankLevel": 41
    },
    {
        "id": "outfit-085",
        "number": 85,
        "kind": "outfit",
        "name": "Emerald Lingerie",
        "rarity": "epic",
        "details": "Green panties, green bra, black stockings, black heels, brunette wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-086",
        "number": 86,
        "kind": "outfit",
        "name": "Honey Lingerie",
        "rarity": "epic",
        "details": "Yellow panties, yellow bra, white stockings, yellow heels, blonde wig",
        "unlock": "milestone"
    },
    {
        "id": "outfit-087",
        "number": 87,
        "kind": "outfit",
        "name": "Silver Illusion",
        "rarity": "epic",
        "details": "White panties, white bra, silver dress, white stockings, silver wig, blue makeup",
        "unlock": "rank",
        "rankLevel": 44
    },
    {
        "id": "outfit-088",
        "number": 88,
        "kind": "outfit",
        "name": "Yes Daddy",
        "rarity": "epic",
        "details": "Yes Daddy bodysuit, black stockings, black heels, black wig, red makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-089",
        "number": 89,
        "kind": "outfit",
        "name": "Pit Girl",
        "rarity": "epic",
        "details": "Pink racing bodysuit, white stockings, hot pink heels, pink wig, pink makeup",
        "unlock": "rank",
        "rankLevel": 46
    },
    {
        "id": "outfit-090",
        "number": 90,
        "kind": "outfit",
        "name": "After-Dark Overcoat",
        "rarity": "epic",
        "details": "Black panties, red bra, black stockings, red heels, long overcoat, red and black wig",
        "unlock": "rank",
        "rankLevel": 48
    },
    {
        "id": "outfit-091",
        "number": 91,
        "kind": "outfit",
        "name": "The Pretty Pink Helper",
        "rarity": "legendary",
        "details": "Black and pink maid dress, pink stockings, pink heeled boots, pink wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-092",
        "number": 92,
        "kind": "outfit",
        "name": "The Scary Girly",
        "rarity": "legendary",
        "details": "Black dress, black stockings, black heeled boots, black makeup, black wig",
        "unlock": "shop"
    },
    {
        "id": "outfit-093",
        "number": 93,
        "kind": "outfit",
        "name": "The Rubberdoll",
        "rarity": "legendary",
        "details": "Pink latex catsuit, pink boots, pink hood",
        "unlock": "milestone"
    },
    {
        "id": "outfit-094",
        "number": 94,
        "kind": "outfit",
        "name": "The Leatherworker",
        "rarity": "legendary",
        "details": "Leather catsuit, matching heels, pink and white wig, slutty makeup",
        "unlock": "rank",
        "rankLevel": 45
    },
    {
        "id": "outfit-095",
        "number": 95,
        "kind": "outfit",
        "name": "The Bondage Slave",
        "rarity": "legendary",
        "details": "Latex maid dress, black hood, white heels, ball gag",
        "unlock": "milestone"
    },
    {
        "id": "outfit-096",
        "number": 96,
        "kind": "outfit",
        "name": "The Cheerleader",
        "rarity": "legendary",
        "details": "Cheerleader dress, pink trainers, blonde wig, pink makeup",
        "unlock": "shop"
    },
    {
        "id": "outfit-097",
        "number": 97,
        "kind": "outfit",
        "name": "The Ultimate Risk",
        "rarity": "legendary",
        "details": "Long overcoat, black boots",
        "unlock": "rank",
        "rankLevel": 50
    },
    {
        "id": "outfit-098",
        "number": 98,
        "kind": "outfit",
        "name": "Princess Belle",
        "rarity": "legendary",
        "details": "Princess Belle dress, curly brunette wig, pink makeup, yellow heels",
        "unlock": "milestone"
    },
    {
        "id": "outfit-099",
        "number": 99,
        "kind": "outfit",
        "name": "Princess Elsa",
        "rarity": "legendary",
        "details": "Princess Elsa dress, platinum blonde wig, pink makeup, blue heels",
        "unlock": "rank",
        "rankLevel": 47
    },
    {
        "id": "outfit-100",
        "number": 100,
        "kind": "outfit",
        "name": "Divine Spirit",
        "rarity": "legendary",
        "details": "White see-through dress, white heels, white stockings, silver wig",
        "unlock": "rank",
        "rankLevel": 49
    }
];
  const STARTING_OUTFIT_IDS = OUTFIT_LIBRARY.filter(item => item.unlock === 'start').map(item => item.id);
  const SHOP_OUTFIT_IDS = OUTFIT_LIBRARY.filter(item => item.unlock === 'shop').map(item => item.id);

  const SHOP_ITEMS = [
    { id: 'theme-neon', kind: 'theme', name: 'Neon Dressing Room', basePrice: 0, themeClass: 'theme-neon', description: 'Default hot pink and purple neon dressing-room UI.' },
    { id: 'theme-purple', kind: 'theme', name: 'Purple Glow', basePrice: 120, themeClass: 'theme-purple', description: 'Deep violet glow with softer pink highlights.' },
    { id: 'theme-electric', kind: 'theme', name: 'Electric Blue', basePrice: 120, themeClass: 'theme-electric', description: 'Cyan neon, sharp contrast, cool nightclub energy.' },
    { id: 'theme-blackout', kind: 'theme', name: 'Pink Blackout', basePrice: 180, themeClass: 'theme-blackout', description: 'Black and deep red-pink with a punchier glow.' },
    { id: 'theme-vip', kind: 'theme', name: 'VIP Gold', basePrice: 350, themeClass: 'theme-vip', description: 'Gold VIP lounge styling with neon highlights.' },

    { id: 'effect-basic', kind: 'effect', name: 'Basic Dice', basePrice: 0, effectClass: 'pulse-roll', description: 'Simple roll pulse.' },
    { id: 'effect-neon', kind: 'effect', name: 'Neon Dice', basePrice: 75, effectClass: 'effect-neon', description: 'Bright neon flash on every roll.' },
    { id: 'effect-heart', kind: 'effect', name: 'Heart Burst', basePrice: 100, effectClass: 'effect-heart', description: 'Soft playful pop animation.' },
    { id: 'effect-glitch', kind: 'effect', name: 'Glitch Roll', basePrice: 125, effectClass: 'effect-glitch', description: 'Fast glitchy shake before the result lands.' },
    { id: 'effect-sparkle', kind: 'effect', name: 'Sparkle Roll', basePrice: 150, effectClass: 'effect-sparkle', description: 'Extra bright sparkle glow.' },
    { id: 'effect-vip', kind: 'effect', name: 'VIP Flash', basePrice: 250, effectClass: 'effect-vip', description: 'Premium flash effect with a stronger outline.' },
    ...OUTFIT_LIBRARY.filter(item => item.unlock === 'shop')
  ];


  const DEFAULT_LOCATIONS = [
    'Apartment hallway', 'Front door', 'Mailbox', 'Trash bins', 'Car park', 'Quiet street', 'Park bench', 'Corner shop'
  ];

  const DEFAULT_DARES = [
    'Stand there for 60 seconds.',
    'Walk there and back once.',
    'Take one photo before returning.',
    'Check your phone there for 2 minutes.',
    'Touch up your makeup there.',
    'Sit there for 3 minutes.',
    'Walk past one person.',
    'Count to 100 before leaving.'
  ];

  const TRAINING_CATEGORIES = ['Chastity', 'Anal', 'Oral', 'Bondage', 'Dress Up', 'Chores', 'Exposure'];
  const USER_TASK_TRAINING_CATEGORIES = ['Anal', 'Oral', 'Bondage', 'Chores', 'Exposure'];

  const TRAINING_UPGRADES = [
    { id: 'extraRerolls', name: 'Extra Rerolls', baseCost: 2000, description: '+1 free reroll per level. Applies to each category on the next fresh offer cycle.' },
    { id: 'obedienceMultiplier', name: 'Obedience Multiplier', baseCost: 2500, description: '+10% guaranteed Obedience reward per level.' },
    { id: 'betterOffers', name: 'Better Offers', baseCost: 3000, description: 'Improves the offer curve so better Obedience offers become more likely.' },
    { id: 'trainingLuck', name: 'Training Luck', baseCost: 3500, description: '+10% chance per level for +100 Obedience on completion.' }
  ];

  const TRAINING_MILESTONE_REWARDS = { small: 250, medium: 750, big: 1500, major: 3000 };

  const MAIN_MILESTONE_OUTFIT_REWARDS = {
    m002: 'outfit-007', m006: 'outfit-008', m011: 'outfit-009', m017: 'outfit-010', m024: 'outfit-019',
    m032: 'outfit-020', m041: 'outfit-023', m050: 'outfit-024', m060: 'outfit-025', m070: 'outfit-026',
    m078: 'outfit-030', m085: 'outfit-031', m091: 'outfit-056', m096: 'outfit-057', m100: 'outfit-093'
  };

  const TRAINING_MILESTONE_OUTFIT_REWARDS = {
    tm002: 'outfit-059', tm006: 'outfit-061', tm011: 'outfit-062', tm017: 'outfit-063', tm024: 'outfit-064',
    tm032: 'outfit-065', tm041: 'outfit-066', tm050: 'outfit-070', tm060: 'outfit-080', tm070: 'outfit-081',
    tm078: 'outfit-083', tm085: 'outfit-085', tm091: 'outfit-086', tm096: 'outfit-095', tm100: 'outfit-098'
  };

  const RANK_REWARDS = [
    {
        "rank": 1,
        "label": "+50 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 50
            }
        ]
    },
    {
        "rank": 2,
        "label": "Outfit: Silver Sunday",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-032"
            }
        ]
    },
    {
        "rank": 3,
        "label": "+750 Obedience",
        "rewards": [
            {
                "type": "obedience",
                "amount": 750
            }
        ]
    },
    {
        "rank": 4,
        "label": "Outfit: Pink Candy Run",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-033"
            }
        ]
    },
    {
        "rank": 5,
        "label": "25% secret shop discount",
        "rewards": [
            {
                "type": "shopDiscount",
                "percent": 0.25
            }
        ]
    },
    {
        "rank": 6,
        "label": "Outfit: Black Coffee",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-034"
            }
        ]
    },
    {
        "rank": 7,
        "label": "+75 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 75
            }
        ]
    },
    {
        "rank": 8,
        "label": "Outfit: Scarlet Streak",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-035"
            }
        ]
    },
    {
        "rank": 9,
        "label": "+1,000 Obedience",
        "rewards": [
            {
                "type": "obedience",
                "amount": 1000
            }
        ]
    },
    {
        "rank": 10,
        "label": "Outfit: Platinum Breeze + Price Freeze",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-036"
            },
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 11,
        "label": "+100 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 100
            }
        ]
    },
    {
        "rank": 12,
        "label": "Outfit: Garden Blush",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-037"
            }
        ]
    },
    {
        "rank": 13,
        "label": "25% training upgrade discount",
        "rewards": [
            {
                "type": "trainingDiscount",
                "percent": 0.25
            }
        ]
    },
    {
        "rank": 14,
        "label": "Outfit: Cherry Daylight",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-039"
            }
        ]
    },
    {
        "rank": 15,
        "label": "+1,500 Obedience",
        "rewards": [
            {
                "type": "obedience",
                "amount": 1500
            }
        ]
    },
    {
        "rank": 16,
        "label": "Outfit: Golden Hour",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-040"
            }
        ]
    },
    {
        "rank": 17,
        "label": "+125 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 125
            }
        ]
    },
    {
        "rank": 18,
        "label": "Outfit: Silver Glow",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-041"
            }
        ]
    },
    {
        "rank": 19,
        "label": "35% secret shop discount",
        "rewards": [
            {
                "type": "shopDiscount",
                "percent": 0.35
            }
        ]
    },
    {
        "rank": 20,
        "label": "Outfit: Blush Under Cover + Price Freeze",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-042"
            },
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 21,
        "label": "+2,000 Obedience",
        "rewards": [
            {
                "type": "obedience",
                "amount": 2000
            }
        ]
    },
    {
        "rank": 22,
        "label": "Outfit: Violet Velvet",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-050"
            }
        ]
    },
    {
        "rank": 23,
        "label": "+150 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 150
            }
        ]
    },
    {
        "rank": 24,
        "label": "Outfit: Blue Under Cover",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-043"
            }
        ]
    },
    {
        "rank": 25,
        "label": "35% training upgrade discount",
        "rewards": [
            {
                "type": "trainingDiscount",
                "percent": 0.35
            }
        ]
    },
    {
        "rank": 26,
        "label": "Outfit: Midnight Under Cover",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-044"
            }
        ]
    },
    {
        "rank": 27,
        "label": "+2,500 Obedience",
        "rewards": [
            {
                "type": "obedience",
                "amount": 2500
            }
        ]
    },
    {
        "rank": 28,
        "label": "Outfit: Snow Under Cover",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-045"
            }
        ]
    },
    {
        "rank": 29,
        "label": "Price Freeze",
        "rewards": [
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 30,
        "label": "Outfit: Violet Silhouette + 50% shop discount",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-067"
            },
            {
                "type": "shopDiscount",
                "percent": 0.5
            }
        ]
    },
    {
        "rank": 31,
        "label": "+225 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 225
            }
        ]
    },
    {
        "rank": 32,
        "label": "Outfit: Citrus Tease",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-068"
            }
        ]
    },
    {
        "rank": 33,
        "label": "40% training upgrade discount",
        "rewards": [
            {
                "type": "trainingDiscount",
                "percent": 0.4
            }
        ]
    },
    {
        "rank": 34,
        "label": "Outfit: Purple Tease",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-069"
            }
        ]
    },
    {
        "rank": 35,
        "label": "+3,500 Obedience + Price Freeze",
        "rewards": [
            {
                "type": "obedience",
                "amount": 3500
            },
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 36,
        "label": "Outfit: Midnight Cover Story",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-071"
            }
        ]
    },
    {
        "rank": 37,
        "label": "+275 Exhys",
        "rewards": [
            {
                "type": "exhys",
                "amount": 275
            }
        ]
    },
    {
        "rank": 38,
        "label": "Outfit: Snow Cover Story",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-072"
            }
        ]
    },
    {
        "rank": 39,
        "label": "50% secret shop discount",
        "rewards": [
            {
                "type": "shopDiscount",
                "percent": 0.5
            }
        ]
    },
    {
        "rank": 40,
        "label": "Outfit: Scarlet Cover Story + 400 Exhys",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-073"
            },
            {
                "type": "exhys",
                "amount": 400
            }
        ]
    },
    {
        "rank": 41,
        "label": "Outfit: Candy Lingerie",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-084"
            }
        ]
    },
    {
        "rank": 42,
        "label": "Outfit: Blush Cover Story + 50% training discount",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-074"
            },
            {
                "type": "trainingDiscount",
                "percent": 0.5
            }
        ]
    },
    {
        "rank": 43,
        "label": "Outfit: Blue Cover Story",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-075"
            }
        ]
    },
    {
        "rank": 44,
        "label": "Outfit: Silver Illusion + Price Freeze",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-087"
            },
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 45,
        "label": "Outfit: The Leatherworker + 5,000 Obedience",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-094"
            },
            {
                "type": "obedience",
                "amount": 5000
            }
        ]
    },
    {
        "rank": 46,
        "label": "Outfit: Pit Girl + 50% shop discount",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-089"
            },
            {
                "type": "shopDiscount",
                "percent": 0.5
            }
        ]
    },
    {
        "rank": 47,
        "label": "Outfit: Princess Elsa + Price Freeze",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-099"
            },
            {
                "type": "priceFreeze",
                "count": 1
            }
        ]
    },
    {
        "rank": 48,
        "label": "Outfit: After-Dark Overcoat + 500 Exhys",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-090"
            },
            {
                "type": "exhys",
                "amount": 500
            }
        ]
    },
    {
        "rank": 49,
        "label": "Outfit: Divine Spirit + 50% training discount",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-100"
            },
            {
                "type": "trainingDiscount",
                "percent": 0.5
            }
        ]
    },
    {
        "rank": 50,
        "label": "Outfit: The Ultimate Risk + 1,000 Exhys",
        "rewards": [
            {
                "type": "outfit",
                "outfitId": "outfit-097"
            },
            {
                "type": "exhys",
                "amount": 1000
            }
        ]
    }
];


  let state = loadState();
  let activeView = 'home';
  let activeShopTab = 'themes';
  let lastShopFlashId = null;
  let lastMilestoneFlashId = null;

  const views = {
    home: document.getElementById('view-home'),
    wardrobe: document.getElementById('view-wardrobe'),
    training: document.getElementById('view-training'),
    rank: document.getElementById('view-rank'),
    lists: document.getElementById('view-lists'),
    shop: document.getElementById('view-shop')
  };

  function createDefaultState() {
    const wardrobe = {};
    CATEGORIES.forEach(cat => {
      wardrobe[cat] = defaultColorsFor(cat);
    });
    return {
      version: 12,
      exhys: 0,
      obedience: 0,
      totalPurchases: 0,
      shopMultiplier: 1,
      activeTheme: 'theme-neon',
      activeEffect: 'effect-basic',
      randomEffect: false,
      purchased: ['theme-neon', 'effect-basic', ...STARTING_OUTFIT_IDS],
      wardrobe,
      dareCount: 3,
      locations: DEFAULT_LOCATIONS.map(text => makeListItem(text)),
      dares: DEFAULT_DARES.map(text => makeListItem(text)),
      currentRoll: null,
      milestonesUnlocked: [],
      milestoneLog: [],
      discounts: {},
      priceFreezes: 0,
      trainingUpgradeDiscounts: {},
      sissyRank: createDefaultSissyRankState(),
      stats: createDefaultStats(),
      training: createDefaultTrainingState()
    };
  }

  function createDefaultStats() {
    return {
      totalRollsGenerated: 0,
      completedRolls: 0,
      completedDares: 0,
      totalExhysEarned: 0,
      taskExhysEarned: 0,
      highestRollReward: 0,
      highestDareReward: 0,
      shopPurchases: 0,
      freeOutfitsUnlocked: 0,
      secretDiscountsReceived: 0,
      priceFreezesReceived: 0,
      priceFreezesUsed: 0,
      discountsUsed: 0,
      shopOutfitCompletions: 0,
      randomOutfitCompletions: 0,
      matchingOutfitCompletions: 0,
      mixedOutfitCompletions: 0,
      outfitLibraryCompletions: 0
    };
  }

  function createDefaultSissyRankState() {
    return { rank: 0, xp: 0, totalXp: 0, rewardsClaimed: [] };
  }

  function createDefaultTrainingState() {
    const categories = {};
    TRAINING_CATEGORIES.forEach(category => {
      categories[category] = { tasks: [], offer: null, active: null };
    });
    return {
      categories,
      upgrades: { extraRerolls: 0, obedienceMultiplier: 0, betterOffers: 0, trainingLuck: 0 },
      milestonesUnlocked: [],
      milestoneLog: [],
      stats: createDefaultTrainingStats()
    };
  }

  function createDefaultTrainingStats() {
    return {
      offersRolled: 0,
      offersAccepted: 0,
      autoAcceptedOffers: 0,
      rerollsUsed: 0,
      tasksCompleted: 0,
      totalObedienceEarned: 0,
      taskObedienceEarned: 0,
      highestBaseReward: 0,
      highestFinalReward: 0,
      obedienceConverted: 0,
      exhysFromObedience: 0,
      upgradesBought: 0,
      luckBonusesTriggered: 0,
      luckBonusObedience: 0,
      dressUpGenerated: 0,
      chastityOffersRolled: 0,
      chastityCompleted: 0,
      chastityNoCount: 0,
      chastityTotalMinutes: 0,
      analCompleted: 0,
      oralCompleted: 0,
      bondageCompleted: 0,
      dressUpCompleted: 0,
      choresCompleted: 0,
      exposureCompleted: 0
    };
  }

  function defaultColorsFor(category) {
    const all = ['Black', 'White', 'Red', 'Pink', 'Hot Pink', 'Blue', 'Purple', 'Yellow', 'Silver', 'Gold'];
    const lingerie = ['Black', 'White', 'Red', 'Pink', 'Hot Pink'];
    const clothes = ['Black', 'White', 'Red', 'Pink', 'Blue', 'Purple', 'Yellow'];
    const shoes = ['Black', 'White', 'Red', 'Pink', 'Silver', 'Gold'];
    const wigs = WIG_OPTIONS.map(option => option.name);
    const makeup = ['Black', 'White', 'Red', 'Pink', 'Hot Pink', 'Blue', 'Purple', 'Silver', 'Gold'];
    if (['Panties', 'Bra'].includes(category)) return [...lingerie];
    if (['Dress', 'Top', 'Skirt', 'Coat', 'Accessory'].includes(category)) return [...clothes, 'Silver', 'Gold'];
    if (['Stockings', 'Socks'].includes(category)) return ['Black', 'White', 'Pink', 'Red'];
    if (category === 'Shoes') return [...shoes];
    if (category === 'Wig') return [...wigs];
    if (category === 'Makeup') return [...makeup];
    return [...all];
  }

  function makeListItem(text) {
    return { id: uid(), text, enabled: true };
  }

  function uid() {
    if (typeof crypto !== 'undefined' && crypto.randomUUID) return crypto.randomUUID();
    return 'id-' + Date.now().toString(36) + '-' + Math.random().toString(36).slice(2);
  }

  function loadState() {
    try {
      const raw = localStorage.getItem(STORAGE_KEY);
      if (!raw) return createDefaultState();
      const loaded = JSON.parse(raw);
      return migrateState(loaded);
    } catch (err) {
      console.warn('Failed to load state, creating default.', err);
      return createDefaultState();
    }
  }

  function migrateState(loaded) {
    const fresh = createDefaultState();
    const merged = { ...fresh, ...loaded };
    merged.wardrobe = { ...fresh.wardrobe, ...(loaded.wardrobe || {}) };
    CATEGORIES.forEach(cat => {
      if (!Array.isArray(merged.wardrobe[cat])) merged.wardrobe[cat] = fresh.wardrobe[cat];
    });
    merged.locations = Array.isArray(merged.locations) ? merged.locations : fresh.locations;
    merged.dares = Array.isArray(merged.dares) ? merged.dares : fresh.dares;
    merged.purchased = Array.from(new Set([...(merged.purchased || []), 'theme-neon', 'effect-basic', ...STARTING_OUTFIT_IDS]));
    merged.totalPurchases = Number(merged.totalPurchases || 0);
    merged.shopMultiplier = Number(merged.shopMultiplier || legacyShopMultiplier(merged.totalPurchases));
    merged.exhys = Number(merged.exhys || 0);
    merged.obedience = Number(merged.obedience || 0);
    merged.dareCount = Number(merged.dareCount || 1);
    merged.milestonesUnlocked = Array.isArray(merged.milestonesUnlocked) ? merged.milestonesUnlocked : [];
    merged.milestoneLog = Array.isArray(merged.milestoneLog) ? merged.milestoneLog : [];
    merged.discounts = merged.discounts && typeof merged.discounts === 'object' ? merged.discounts : {};
    merged.trainingUpgradeDiscounts = merged.trainingUpgradeDiscounts && typeof merged.trainingUpgradeDiscounts === 'object' ? merged.trainingUpgradeDiscounts : {};
    merged.priceFreezes = Number(merged.priceFreezes || 0);
    merged.sissyRank = migrateSissyRankState(merged.sissyRank);
    merged.stats = { ...createDefaultStats(), ...(merged.stats || {}) };
    if (!Object.prototype.hasOwnProperty.call(merged.stats, 'taskExhysEarned')) merged.stats.taskExhysEarned = 0;
    merged.training = migrateTrainingState(merged.training);
    // Older builds had local history/saved rolls. Keep imported data valid, but do not render or use it.
    return merged;
  }

  function migrateSissyRankState(rankState) {
    const fresh = createDefaultSissyRankState();
    const merged = { ...fresh, ...(rankState || {}) };
    merged.rank = Math.min(50, Math.max(0, Number(merged.rank || 0)));
    merged.xp = Math.max(0, Number(merged.xp || 0));
    merged.totalXp = Math.max(0, Number(merged.totalXp || 0));
    merged.rewardsClaimed = Array.isArray(merged.rewardsClaimed) ? merged.rewardsClaimed : [];
    return merged;
  }

  function migrateTrainingState(training) {
    const fresh = createDefaultTrainingState();
    const merged = { ...fresh, ...(training || {}) };
    merged.categories = { ...fresh.categories, ...(training?.categories || {}) };
    TRAINING_CATEGORIES.forEach(category => {
      const current = merged.categories[category] || {};
      merged.categories[category] = {
        tasks: Array.isArray(current.tasks) ? current.tasks : [],
        offer: current.offer || null,
        active: current.active || null
      };
    });
    merged.upgrades = { ...fresh.upgrades, ...(merged.upgrades || {}) };
    TRAINING_UPGRADES.forEach(upgrade => {
      merged.upgrades[upgrade.id] = Math.max(0, Number(merged.upgrades[upgrade.id] || 0));
    });
    merged.milestonesUnlocked = Array.isArray(merged.milestonesUnlocked) ? merged.milestonesUnlocked : [];
    merged.milestoneLog = Array.isArray(merged.milestoneLog) ? merged.milestoneLog : [];
    merged.stats = { ...createDefaultTrainingStats(), ...(merged.stats || {}) };
    if (!Object.prototype.hasOwnProperty.call(merged.stats, 'taskObedienceEarned')) merged.stats.taskObedienceEarned = 0;
    return merged;
  }

  function saveState() {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
    updateBodyTheme();
    document.getElementById('exhysBalance').textContent = formatNum(state.exhys);
    const obedienceEl = document.getElementById('obedienceBalance');
    if (obedienceEl) obedienceEl.textContent = formatNum(state.obedience);
  }

  function updateBodyTheme() {
    const theme = SHOP_ITEMS.find(item => item.id === state.activeTheme);
    document.body.className = theme?.themeClass || 'theme-neon';
  }

  function formatNum(value) {
    const num = Number(value || 0);
    if (Number.isInteger(num)) return String(num);
    return num.toFixed(1).replace(/\.0$/, '');
  }

  function currencyIcon(type) {
    return `<span class="currency-inline ${type === 'obedience' ? 'obedience' : 'exhys'}" aria-hidden="true"></span>`;
  }


  function esc(value) {
    return String(value ?? '')
      .replaceAll('&', '&amp;')
      .replaceAll('<', '&lt;')
      .replaceAll('>', '&gt;')
      .replaceAll('"', '&quot;')
      .replaceAll("'", '&#039;');
  }

  function choice(arr) {
    return arr[Math.floor(Math.random() * arr.length)];
  }

  function shuffle(arr) {
    const copy = [...arr];
    for (let i = copy.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [copy[i], copy[j]] = [copy[j], copy[i]];
    }
    return copy;
  }

  function weightedChoice(items, getWeight) {
    const total = items.reduce((sum, item) => sum + Math.max(0, Number(getWeight(item) || 0)), 0);
    if (total <= 0) return null;
    let roll = Math.random() * total;
    for (const item of items) {
      roll -= Math.max(0, Number(getWeight(item) || 0));
      if (roll <= 0) return item;
    }
    return items[items.length - 1] || null;
  }

  function weightedExhysReward() {
    const values = [];
    for (let amount = 1; amount <= 140; amount++) values.push(amount);
    return weightedChoice(values, exhysRewardWeight);
  }

  function exhysRewardWeight(amount) {
    if (amount >= 1 && amount <= 29) return 0.1 + ((amount - 1) / 28) * 0.4;
    if (amount >= 30 && amount <= 70) return 2 - ((amount - 30) / 40);
    if (amount >= 71 && amount <= 100) return 0.5 - ((amount - 71) / 29) * 0.4;
    if (amount >= 101 && amount <= 140) return 0.01;
    return 0;
  }

  function legacyShopMultiplier(purchases) {
    let multiplier = 1;
    const count = Math.max(0, Number(purchases || 0));
    for (let i = 0; i < count; i++) multiplier *= (1 + Math.max(0.03, 0.10 - (i * 0.002)));
    return multiplier;
  }

  function currentInflationRate() {
    return Math.max(0.03, 0.10 - (Number(state.totalPurchases || 0) * 0.002));
  }

  function currentPrice(item) {
    if (!item.basePrice) return 0;
    const raw = item.basePrice * Number(state.shopMultiplier || 1);
    return Math.ceil(raw * 10) / 10;
  }

  function outfitBasePrice(item) {
    return RARITY[item.rarity]?.basePrice || 150;
  }

  function itemBasePrice(item) {
    if (item.kind === 'outfit') return outfitBasePrice(item);
    return item.basePrice || 0;
  }

  function itemCurrentPrice(item) {
    let price = currentPrice({ basePrice: itemBasePrice(item) });
    const discount = state.discounts?.[item.id];
    if (discount && !isOwned(item.id)) price = Math.ceil((price * (1 - Number(discount.percent || 0))) * 10) / 10;
    return price;
  }

  function fullInflatedPrice(item) {
    return currentPrice({ basePrice: itemBasePrice(item) });
  }

  function isOwned(id) {
    return state.purchased.includes(id);
  }

  function enabled(items) {
    return items.filter(item => item.enabled && item.text.trim());
  }

  const MILESTONE_REWARDS = { small: 37.5, medium: 75, big: 131.25, major: 187.5 };
  const MILESTONES = buildHiddenMilestones();

  function buildHiddenMilestones() {
    const list = [];
    const add = (size, stat, threshold) => list.push({ id: `m${String(list.length + 1).padStart(3, '0')}`, size, stat, threshold });

    [1,2,3,4,5,6,7,8,9,10].forEach(n => add('small', 'completedRolls', n));
    [1,2,3,5,7,10,12,15,18,20].forEach(n => add('small', 'completedDares', n));
    [1,2,3,5,8].forEach(n => add('small', 'locationsCount', n));
    [1,3,5,8,10].forEach(n => add('small', 'daresCount', n));
    [1,2,3,4,5].forEach(n => add('small', 'shopPurchases', n));
    [100,250,500,750,1000].forEach(n => add('small', 'taskExhysEarned', n));
    [1,2,3,4,5].forEach(n => add('small', 'wardrobeCoverage', n));

    [15,20,30,40,50,65,80,100].forEach(n => add('medium', 'completedRolls', n));
    [25,40,60,80,100,130,160,200].forEach(n => add('medium', 'completedDares', n));
    [1500,2000,3000,4000,5000].forEach(n => add('medium', 'taskExhysEarned', n));
    [6,8,10,12].forEach(n => add('medium', 'shopPurchases', n));
    [1,2,3].forEach(n => add('medium', 'outfitsUnlocked', n));
    [70,85].forEach(n => add('medium', 'highestDareReward', n));

    [125,150,200,250].forEach(n => add('big', 'completedRolls', n));
    [250,350,500,750].forEach(n => add('big', 'completedDares', n));
    [7500,10000,15000].forEach(n => add('big', 'taskExhysEarned', n));
    [250,400].forEach(n => add('big', 'highestRollReward', n));
    [6,10].forEach(n => add('big', 'outfitsUnlocked', n));

    [300,500].forEach(n => add('major', 'completedRolls', n));
    [1000,1500].forEach(n => add('major', 'completedDares', n));
    [25000,50000].forEach(n => add('major', 'taskExhysEarned', n));
    [120,140].forEach(n => add('major', 'highestDareReward', n));
    add('major', 'allOutfitsUnlocked', 1);
    add('major', 'shopPurchases', 20);

    return list;
  }

  function milestoneCounts() {
    return MILESTONES.reduce((counts, milestone) => {
      counts[milestone.size] = (counts[milestone.size] || 0) + 1;
      return counts;
    }, {});
  }

  function statValue(stat) {
    const stats = state.stats || createDefaultStats();
    if (stat === 'locationsCount') return state.locations.length;
    if (stat === 'daresCount') return state.dares.length;
    if (stat === 'outfitsUnlocked') return OUTFIT_LIBRARY.filter(item => isOwned(item.id)).length;
    if (stat === 'themesUnlocked') return SHOP_ITEMS.filter(item => item.kind === 'theme' && isOwned(item.id)).length;
    if (stat === 'effectsUnlocked') return SHOP_ITEMS.filter(item => item.kind === 'effect' && isOwned(item.id)).length;
    if (stat === 'allOutfitsUnlocked') return OUTFIT_LIBRARY.every(item => isOwned(item.id)) ? 1 : 0;
    if (stat === 'wardrobeCoverage') return CATEGORIES.filter(cat => (state.wardrobe[cat] || []).length > 0).length;
    return Number(stats[stat] || 0);
  }

  function milestoneReveal(milestone) {
    const stat = milestone.stat;
    const n = milestone.threshold;
    const labels = {
      completedRolls: n === 1 ? 'Complete your first roll' : `Complete ${n} rolls`,
      completedDares: n === 1 ? 'Complete your first dare' : `Complete ${n} dares`,
      locationsCount: n === 1 ? 'Add your first location' : `Add ${n} locations`,
      daresCount: n === 1 ? 'Add your first dare' : `Add ${n} dares to the list`,
      shopPurchases: n === 1 ? 'Make your first shop purchase' : `Make ${n} shop purchases`,
      taskExhysEarned: `Earn ${formatNum(n)} Exhys from completed Dressed & Dared rolls`,
      wardrobeCoverage: n === 1 ? 'Enable your first wardrobe category' : `Enable colors in ${n} wardrobe categories`,
      outfitsUnlocked: n === 1 ? 'Unlock your first outfit' : `Unlock ${n} outfits`,
      highestDareReward: `Reveal a ${formatNum(n)}+ Exhys single-dare reward`,
      highestRollReward: `Reveal a ${formatNum(n)}+ Exhys roll reward`,
      allOutfitsUnlocked: 'Unlock every outfit'
    };
    const condition = labels[stat] || `Reach ${formatNum(n)} ${stat}`;
    const sizeName = milestone.size.charAt(0).toUpperCase() + milestone.size.slice(1);
    return {
      title: `${sizeName} Milestone`,
      condition
    };
  }

  function recordMilestoneUnlock(milestone, reward, legendaryBonus, rewardText = '') {
    const reveal = milestoneReveal(milestone);
    const existing = new Set((state.milestoneLog || []).map(entry => entry.id));
    if (existing.has(milestone.id)) return;
    state.milestoneLog = state.milestoneLog || [];
    state.milestoneLog.unshift({
      id: milestone.id,
      title: reveal.title,
      condition: reveal.condition,
      size: milestone.size,
      reward,
      rewardText,
      legendaryBonus: legendaryBonus || '',
      unlockedAt: new Date().toISOString()
    });
  }

  function renderUnlockedMilestones() {
    const mainLog = Array.isArray(state.milestoneLog) ? state.milestoneLog.map(entry => ({ ...entry, type: 'Main', currency: 'Exhys' })) : [];
    const legacyUnlocked = (state.milestonesUnlocked || [])
      .filter(id => !mainLog.some(entry => entry.id === id))
      .map(id => {
        const milestone = MILESTONES.find(m => m.id === id);
        if (!milestone) return null;
        const reveal = milestoneReveal(milestone);
        return {
          id,
          title: reveal.title,
          condition: reveal.condition,
          size: milestone.size,
          reward: MILESTONE_REWARDS[milestone.size] || 0,
          legendaryBonus: '',
          unlockedAt: '',
          type: 'Main',
          currency: 'Exhys'
        };
      }).filter(Boolean);
    const trainingLog = Array.isArray(state.training?.milestoneLog)
      ? state.training.milestoneLog.map(entry => ({ ...entry, type: 'Training', currency: 'Obedience' }))
      : [];
    const entries = [...mainLog, ...legacyUnlocked, ...trainingLog]
      .sort((a, b) => String(b.unlockedAt || '').localeCompare(String(a.unlockedAt || '')));
    if (!entries.length) {
      return '<div class="empty">No milestones unlocked yet. Hidden milestones appear here only after they trigger.</div>';
    }
    return `<div class="item-list milestone-list">${entries.map(entry => `
      <div class="list-item milestone-entry ${entry.type === 'Training' ? 'training-milestone' : ''} ${entry.size === 'major' ? 'major legendary-entry' : ''} ${entry.id === lastMilestoneFlashId ? 'new-pop' : ''}">
        <div class="text">
          <strong>${esc(entry.type)} · ${esc(entry.title)}</strong>
          <div class="small muted">${esc(entry.condition)}</div>
          ${entry.legendaryBonus ? `<div class="small">Legendary Bonus: ${esc(entry.legendaryBonus)}</div>` : ''}
        </div>
        <div style="text-align:right;display:grid;gap:6px;justify-items:end">
          <span class="badge ${esc(entry.size)}">${esc(entry.size)}</span>
          <span class="price ${entry.currency === 'Obedience' ? 'obedience-price' : ''}">${entry.rewardText ? esc(entry.rewardText) : `${currencyIcon(entry.currency === 'Obedience' ? 'obedience' : 'exhys')}+${formatNum(entry.reward)} ${esc(entry.currency)}`}</span>
        </div>
      </div>
    `).join('')}</div>`;
  }

  function checkHiddenMilestones() {
    const unlocked = new Set(state.milestonesUnlocked || []);
    const messages = [];
    for (const milestone of MILESTONES) {
      if (unlocked.has(milestone.id)) continue;
      if (statValue(milestone.stat) < milestone.threshold) continue;

      unlocked.add(milestone.id);
      state.milestonesUnlocked.push(milestone.id);
      const outfitRewardId = MAIN_MILESTONE_OUTFIT_REWARDS[milestone.id];
      let reward = MILESTONE_REWARDS[milestone.size] || 0;
      let legendaryText = '';
      let rewardText = '';
      const sizeLabel = milestone.size.charAt(0).toUpperCase() + milestone.size.slice(1);

      if (outfitRewardId) {
        const outfitName = unlockOutfit(outfitRewardId) || 'Outfit';
        reward = 0;
        rewardText = `Outfit: ${outfitName}`;
        messages.push(`${sizeLabel} milestone unlocked: outfit reward — ${outfitName}.`);
      } else {
        if (reward > 0) state.exhys = Math.round((state.exhys + reward) * 10) / 10;
        if (milestone.size === 'major') {
          legendaryText = applyLegendaryBonus().replace(/^Legendary Bonus:\s*/i, '');
          messages.push(`Major milestone unlocked: +${formatNum(reward)} Exhys. Legendary Bonus: ${legendaryText}`);
        } else {
          messages.push(`${sizeLabel} milestone unlocked: +${formatNum(reward)} Exhys.`);
        }
      }
      const rankMessages = addRankXp(15, 'Milestone unlocked');
      lastMilestoneFlashId = milestone.id;
      recordMilestoneUnlock(milestone, reward, legendaryText, rewardText);
      messages.push(...rankMessages);
    }
    return messages;
  }

  function applyLegendaryBonus() {
    const possible = [];
    const lockedOutfits = OUTFIT_LIBRARY.filter(item => !isOwned(item.id));
    const lockedDiscountTargets = SHOP_ITEMS.filter(item => !isOwned(item.id) && itemBasePrice(item) > 0);

    if (lockedOutfits.length) possible.push('free-outfit');
    possible.push('price-freeze');
    if (lockedDiscountTargets.length) possible.push('secret-discount');

    const picked = choice(possible);
    if (picked === 'free-outfit') {
      const outfit = choice(lockedOutfits);
      unlockOutfit(outfit.id);
      state.stats.freeOutfitsUnlocked += 1;
      return `Legendary Bonus: free outfit unlocked (${outfit.name}).`;
    }

    if (picked === 'secret-discount') {
      const candidates = lockedDiscountTargets.filter(item => !state.discounts?.[item.id]);
      const target = choice(candidates.length ? candidates : lockedDiscountTargets);
      state.discounts[target.id] = { percent: 0.5, createdAt: new Date().toISOString() };
      state.stats.secretDiscountsReceived += 1;
      return `Legendary Bonus: one locked shop item is now 50% off.`;
    }

    state.priceFreezes = Number(state.priceFreezes || 0) + 1;
    state.stats.priceFreezesReceived += 1;
    return `Legendary Bonus: your next purchase will not increase prices.`;
  }


  const TRAINING_MILESTONES = buildHiddenTrainingMilestones();

  function buildHiddenTrainingMilestones() {
    const list = [];
    const add = (size, stat, threshold) => list.push({ id: `tm${String(list.length + 1).padStart(3, '0')}`, size, stat, threshold });

    [1,2,3,4,5,6,7,8,9,10].forEach(n => add('small', 'tasksCompleted', n));
    [1,2,3,4,5].forEach(n => add('small', 'offersAccepted', n));
    [1,2,3,4,5].forEach(n => add('small', 'rerollsUsed', n));
    [50,100,200,300,500,750,1000,1500].forEach(n => add('small', 'taskObedienceEarned', n));
    [1,2,3,4].forEach(n => add('small', 'trainingTaskListsWithItems', n));
    [1,2,3,4].forEach(n => add('small', 'trainingCategoriesCompleted', n));
    [1,2,3].forEach(n => add('small', 'upgradesBought', n));
    [1,2,3].forEach(n => add('small', 'dressUpGenerated', n));
    [1,2,3].forEach(n => add('small', 'chastityOffersRolled', n));

    [15,20,25,30,40,50,65,80].forEach(n => add('medium', 'tasksCompleted', n));
    [10,15,20,30,40].forEach(n => add('medium', 'offersAccepted', n));
    [2500,4000,6000,8000,10000,15000].forEach(n => add('medium', 'taskObedienceEarned', n));
    [500,1000].forEach(n => add('medium', 'highestFinalReward', n));
    [5,8,10].forEach(n => add('medium', 'upgradesBought', n));
    [1,2].forEach(n => add('medium', 'chastityCompleted', n));
    [1,2].forEach(n => add('medium', 'luckBonusesTriggered', n));
    [1,2].forEach(n => add('medium', 'autoAcceptedOffers', n));

    [100,150,200,300].forEach(n => add('big', 'tasksCompleted', n));
    [25000,40000,60000].forEach(n => add('big', 'taskObedienceEarned', n));
    [1500,2500].forEach(n => add('big', 'highestFinalReward', n));
    [15,25].forEach(n => add('big', 'upgradesBought', n));
    [5,10].forEach(n => add('big', 'chastityCompleted', n));
    [5,10].forEach(n => add('big', 'luckBonusesTriggered', n));

    [500,1000].forEach(n => add('major', 'tasksCompleted', n));
    [100000,250000].forEach(n => add('major', 'taskObedienceEarned', n));
    [3500,5000].forEach(n => add('major', 'highestFinalReward', n));
    [50].forEach(n => add('major', 'upgradesBought', n));
    [25].forEach(n => add('major', 'chastityCompleted', n));
    [25].forEach(n => add('major', 'luckBonusesTriggered', n));
    [50].forEach(n => add('major', 'autoAcceptedOffers', n));

    return list;
  }

  function trainingStatValue(stat) {
    const training = state.training || createDefaultTrainingState();
    const stats = training.stats || createDefaultTrainingStats();
    if (stat === 'trainingTaskListsWithItems') {
      return USER_TASK_TRAINING_CATEGORIES.filter(category => (training.categories?.[category]?.tasks || []).some(task => task.enabled && task.text.trim())).length;
    }
    if (stat === 'trainingCategoriesCompleted') {
      return ['Chastity','Anal','Oral','Bondage','Dress Up','Chores','Exposure'].filter(category => Number(stats[categoryStatKey(category)] || 0) > 0).length;
    }
    return Number(stats[stat] || 0);
  }

  function trainingMilestoneReveal(milestone) {
    const stat = milestone.stat;
    const n = milestone.threshold;
    const labels = {
      tasksCompleted: n === 1 ? 'Complete your first training task' : `Complete ${n} training tasks`,
      offersAccepted: n === 1 ? 'Accept your first training offer' : `Accept ${n} training offers`,
      rerollsUsed: n === 1 ? 'Use your first training reroll' : `Use ${n} training rerolls`,
      taskObedienceEarned: `Earn ${formatNum(n)} Obedience from completed training tasks`,
      trainingTaskListsWithItems: `Add enabled tasks to ${n} training categories`,
      trainingCategoriesCompleted: `Complete tasks in ${n} different training categories`,
      upgradesBought: n === 1 ? 'Buy your first training upgrade' : `Buy ${n} training upgrades`,
      dressUpGenerated: n === 1 ? 'Roll your first Dress Up training offer' : `Roll ${n} Dress Up training offers`,
      chastityOffersRolled: n === 1 ? 'Roll your first Chastity offer' : `Roll ${n} Chastity offers`,
      highestFinalReward: `Complete a training task worth ${formatNum(n)}+ Obedience`,
      chastityCompleted: n === 1 ? 'Complete your first Chastity timer' : `Complete ${n} Chastity timers`,
      luckBonusesTriggered: n === 1 ? 'Trigger your first Training Luck bonus' : `Trigger ${n} Training Luck bonuses`,
      autoAcceptedOffers: n === 1 ? 'Auto-accept your first final reroll offer' : `Auto-accept ${n} final reroll offers`,
      exhysFromObedience: `Convert ${formatNum(n)} Exhys from Obedience`
    };
    const sizeName = milestone.size.charAt(0).toUpperCase() + milestone.size.slice(1);
    return { title: `${sizeName} Training Milestone`, condition: labels[stat] || `Reach ${formatNum(n)} ${stat}` };
  }

  function checkTrainingMilestones() {
    const training = state.training || createDefaultTrainingState();
    const unlocked = new Set(training.milestonesUnlocked || []);
    const messages = [];
    for (const milestone of TRAINING_MILESTONES) {
      if (unlocked.has(milestone.id)) continue;
      if (trainingStatValue(milestone.stat) < milestone.threshold) continue;
      unlocked.add(milestone.id);
      training.milestonesUnlocked.push(milestone.id);
      const outfitRewardId = TRAINING_MILESTONE_OUTFIT_REWARDS[milestone.id];
      let reward = TRAINING_MILESTONE_REWARDS[milestone.size] || 0;
      let rewardText = '';
      const reveal = trainingMilestoneReveal(milestone);
      const sizeLabel = milestone.size.charAt(0).toUpperCase() + milestone.size.slice(1);
      if (outfitRewardId) {
        const outfitName = unlockOutfit(outfitRewardId) || 'Outfit';
        reward = 0;
        rewardText = `Outfit: ${outfitName}`;
        messages.push(`${sizeLabel} training milestone unlocked: outfit reward — ${outfitName}.`);
      } else {
        state.obedience = Math.round((Number(state.obedience || 0) + reward) * 10) / 10;
        messages.push(`${sizeLabel} training milestone unlocked: +${formatNum(reward)} Obedience.`);
      }
      const rankMessages = addRankXp(15, 'Milestone unlocked');
      training.milestoneLog.unshift({
        id: milestone.id,
        title: reveal.title,
        condition: reveal.condition,
        size: milestone.size,
        reward,
        rewardText,
        unlockedAt: new Date().toISOString()
      });
      lastMilestoneFlashId = milestone.id;
      messages.push(...rankMessages);
    }
    return messages;
  }

  function categoryStatKey(category) {
    return {
      Chastity: 'chastityCompleted',
      Anal: 'analCompleted',
      Oral: 'oralCompleted',
      Bondage: 'bondageCompleted',
      'Dress Up': 'dressUpCompleted',
      Chores: 'choresCompleted',
      Exposure: 'exposureCompleted'
    }[category] || 'tasksCompleted';
  }

  function queueToasts(messages) {
    messages.filter(Boolean).forEach((message, index) => setTimeout(() => toast(message), index * 1700));
  }

  function animateExhysBalance(from, to) {
    const balance = document.getElementById('exhysBalance');
    const wallet = document.querySelector('.wallet');
    if (!balance || from === to) return;
    const start = Number(from || 0);
    const end = Number(to || 0);
    const duration = 850;
    const started = performance.now();
    wallet?.classList.remove('bump');
    void wallet?.offsetWidth;
    wallet?.classList.add('bump');
    function tick(now) {
      const t = Math.min(1, (now - started) / duration);
      const eased = 1 - Math.pow(1 - t, 3);
      balance.textContent = formatNum(start + ((end - start) * eased));
      if (t < 1) requestAnimationFrame(tick);
      else balance.textContent = formatNum(end);
    }
    requestAnimationFrame(tick);
  }

  function render() {
    saveState();
    renderNav();
    renderHome();
    renderWardrobe();
    renderTraining();
    renderRank();
    renderLists();
    renderShop();
  }

  function renderNav() {
    document.querySelectorAll('.nav-btn').forEach(btn => {
      btn.classList.toggle('active', btn.dataset.view === activeView);
    });
    Object.entries(views).forEach(([name, el]) => {
      el.classList.toggle('active', name === activeView);
    });
  }

  function renderHome() {
    const enabledDares = enabled(state.dares);
    const maxDares = Math.max(1, enabledDares.length);
    const selectedCount = Math.min(Math.max(1, state.dareCount || 1), maxDares);
    state.dareCount = selectedCount;

    views.home.innerHTML = `
      <div class="grid two">
        <section class="card hero" id="rollCard">
          <div id="rollFxStage" class="roll-fx-stage" aria-hidden="true"></div>
          <div class="card-title-row">
            <div>
              <h2>Roll Full Dare</h2>
              <p class="muted">Roll one outfit, one location, and your chosen number of dares.</p>
            </div>
            <span class="badge">Weighted outfit library</span>
          </div>

          <div class="roll-controls">
            <label class="control-pill">
              Dares
              <select id="dareCountSelect" ${enabledDares.length ? '' : 'disabled'}>
                ${Array.from({ length: Math.min(10, maxDares) }, (_, i) => i + 1).map(n => `<option value="${n}" ${n === selectedCount ? 'selected' : ''}>${n}</option>`).join('')}
              </select>
            </label>
            <span class="badge">Outfit weights: 40 / 20 / 8 / 2</span>
            <span class="badge">Rewards hidden until done</span>
          </div>

          <button id="rollBtn" class="btn primary">◆ Roll Full Dare</button>
          <div id="rollMessage" class="small muted"></div>
        </section>

        <section class="card">
          <div class="card-title-row">
            <div>
              <h2>Current Result</h2>
              <p class="muted">Mark the roll as done to reveal and claim Exhys.</p>
            </div>
            ${state.currentRoll?.done ? `<span class="badge">${formatNum(state.currentRoll.totalReward)} Exhys earned</span>` : ''}
          </div>
          <div id="currentResult">${renderCurrentRoll()}</div>
        </section>
      </div>

      <section class="card" style="margin-top:14px">
        <div class="card-title-row">
          <div>
            <h2>Milestones</h2>
            <p class="muted">Locked milestones stay hidden. Completed milestones appear here with what unlocked and what bonus they gave.</p>
          </div>
          <span class="badge">Main ${state.milestonesUnlocked.length}/${MILESTONES.length}</span>
          <span class="badge">Training ${state.training.milestonesUnlocked.length}/${TRAINING_MILESTONES.length}</span>
        </div>
        ${renderUnlockedMilestones()}
      </section>
    `;

    document.getElementById('dareCountSelect')?.addEventListener('change', e => {
      state.dareCount = Number(e.target.value);
      render();
    });
    document.getElementById('rollBtn')?.addEventListener('click', rollFullDare);
    document.getElementById('markDoneBtn')?.addEventListener('click', markDone);
    document.getElementById('clearRollBtn')?.addEventListener('click', () => {
      state.currentRoll = null;
      toast('Current roll cleared.');
      render();
    });
  }

  function renderCurrentRoll() {
    const roll = state.currentRoll;
    if (!roll) return `<div class="empty">No roll yet. Choose the number of dares and press Roll Full Dare.</div>`;

    let outfitHtml = '';
    if (roll.outfit?.source === 'random') {
      outfitHtml = roll.outfit.items.map(item => `<li><span>${esc(item)}</span></li>`).join('') || `<li><span>No outfit categories had selected colors.</span></li>`;
    } else {
      const pieces = roll.outfit?.pieces || String(roll.outfit?.details || '').split(',').map(x => x.trim()).filter(Boolean);
      outfitHtml = `<li><span>${esc(roll.outfit?.name || 'Outfit')}</span><span class="badge ${esc(roll.outfit?.rarity || '')}">${esc(roll.outfit?.rarityLabel || 'Outfit')}</span></li>` +
        pieces.map(piece => `<li><span>${esc(piece)}</span></li>`).join('');
    }

    const outfitTitle = roll.outfit?.source === 'random'
      ? `Outfit · ${esc(roll.outfit.template || 'Legacy')} · ${roll.outfit.matching ? 'Matching' : 'Mixed'}`
      : 'Outfit · Library';

    return `
      <div class="result-grid">
        <div class="result-section">
          <h3>${outfitTitle}</h3>
          <ul class="result-list">${outfitHtml}</ul>
        </div>
        <div class="result-section">
          <h3>Location</h3>
          <p>${esc(roll.location)}</p>
        </div>
        <div class="result-section wide">
          <h3>Dares</h3>
          <ol class="dare-result-list">
            ${roll.dares.map(dare => `<li>${esc(dare.text)} ${roll.done ? `<span class="price">${currencyIcon('exhys')}+${formatNum(dare.reward)} Exhys</span>` : '<span class="badge">Hidden reward</span>'}</li>`).join('')}
          </ol>
        </div>
      </div>
      <div class="roll-controls" style="margin-top:14px">
        ${roll.done ? `<span class="price">${currencyIcon('exhys')}Total earned: ${formatNum(roll.totalReward)} Exhys</span>` : `<button id="markDoneBtn" class="btn primary">Mark as Done & Reveal Exhys</button>`}
        <button id="clearRollBtn" class="btn ghost">Clear</button>
      </div>
    `;
  }

  function rollFullDare() {
    const locations = enabled(state.locations);
    const dares = enabled(state.dares);
    if (!locations.length) {
      toast('Add at least one enabled location before rolling.');
      switchView('lists');
      return;
    }
    if (!dares.length) {
      toast('Add at least one enabled dare before rolling.');
      switchView('lists');
      return;
    }

    const count = Math.min(Math.max(1, state.dareCount || 1), dares.length);
    const chosenDares = shuffle(dares).slice(0, count).map(d => ({ text: d.text, reward: weightedExhysReward() }));
    const totalReward = chosenDares.reduce((sum, d) => sum + d.reward, 0);

    state.currentRoll = {
      id: uid(),
      createdAt: new Date().toISOString(),
      outfit: rollOutfit(),
      location: choice(locations).text,
      dares: chosenDares,
      totalReward,
      done: false
    };
    state.stats.totalRollsGenerated += 1;

    render();
    animateRoll();
    toast(`Rolled ${count} dare${count === 1 ? '' : 's'}. Exhys hidden until done.`);
  }

  function unlockedOutfits() {
    return OUTFIT_LIBRARY.filter(item => isOwned(item.id));
  }

  function lockedOutfits() {
    return OUTFIT_LIBRARY.filter(item => !isOwned(item.id));
  }

  function findOutfit(id) {
    return OUTFIT_LIBRARY.find(item => item.id === id);
  }

  function unlockOutfit(id) {
    const outfit = findOutfit(id);
    if (!outfit) return '';
    if (!isOwned(id)) state.purchased.push(id);
    if (state.discounts?.[id]) delete state.discounts[id];
    return outfit.name;
  }

  function rollOutfit() {
    const ownedOutfits = unlockedOutfits();
    const outfit = weightedChoice(ownedOutfits, item => RARITY[item.rarity]?.weight || 1) || ownedOutfits[0] || OUTFIT_LIBRARY[0];
    return {
      source: 'library',
      id: outfit.id,
      number: outfit.number,
      name: outfit.name,
      details: outfit.details || '',
      pieces: String(outfit.details || '').split(',').map(x => x.trim()).filter(Boolean),
      rarity: outfit.rarity,
      rarityLabel: RARITY[outfit.rarity]?.label || 'Outfit'
    };
  }


  function activeRollEffect() {
    const ownedEffects = SHOP_ITEMS.filter(item => item.kind === 'effect' && isOwned(item.id));
    let effect = SHOP_ITEMS.find(item => item.id === state.activeEffect) || SHOP_ITEMS.find(item => item.id === 'effect-basic');
    if (state.randomEffect && ownedEffects.length) effect = choice(ownedEffects);
    return effect || SHOP_ITEMS.find(item => item.id === 'effect-basic');
  }

  function effectVisual(effect) {
    const id = effect?.id || 'effect-basic';
    if (id === 'effect-neon') return { fx: 'fx-neon', symbols: ['◆','◇','✦','NEON','◆','✦'] };
    if (id === 'effect-heart') return { fx: 'fx-heart', symbols: ['♥','♡','♥','♡','♥','♡'] };
    if (id === 'effect-glitch') return { fx: 'fx-glitch', symbols: ['#','X','//','404','◆','!!'] };
    if (id === 'effect-sparkle') return { fx: 'fx-sparkle', symbols: ['✦','✧','✶','✦','✧','✶'] };
    if (id === 'effect-vip') return { fx: 'fx-vip', symbols: ['★','VIP','✦','♛','★','✦'] };
    return { fx: 'fx-basic', symbols: ['◆','◇','◆','◇','✦'] };
  }

  function animateRoll() {
    const card = document.getElementById('rollCard');
    const result = document.querySelector('#currentResult .result-grid');
    const stage = document.getElementById('rollFxStage');
    const effect = activeRollEffect();
    const cls = effect?.effectClass || 'pulse-roll';
    [card, result].forEach(el => {
      if (!el) return;
      el.classList.remove('pulse-roll', 'effect-neon', 'effect-heart', 'effect-glitch', 'effect-sparkle', 'effect-vip');
      void el.offsetWidth;
      el.classList.add(cls);
      setTimeout(() => el.classList.remove(cls), 1150);
    });
    if (stage) {
      const visual = effectVisual(effect);
      stage.className = `roll-fx-stage show ${visual.fx}`;
      stage.innerHTML = visual.symbols.map((symbol, index) => {
        const x = 10 + ((index * 17) % 78);
        const y = 22 + ((index * 23) % 54);
        const size = 1 + ((index % 3) * 0.28);
        return `<span style="--x:${x}%;--y:${y}%;--size:${size}rem">${esc(symbol)}</span>`;
      }).join('');
      setTimeout(() => { stage.className = 'roll-fx-stage'; stage.innerHTML = ''; }, 1150);
    }
    const rollMessage = document.getElementById('rollMessage');
    if (rollMessage) rollMessage.textContent = `${effect?.name || 'Basic Dice'} effect triggered.`;
  }

  function markDone() {
    const roll = state.currentRoll;
    if (!roll || roll.done) return;
    roll.done = true;
    const oldExhys = Number(state.exhys || 0);
    const newExhys = Math.round((oldExhys + roll.totalReward) * 10) / 10;
    state.exhys = newExhys;

    state.stats.completedRolls += 1;
    state.stats.completedDares += roll.dares.length;
    state.stats.totalExhysEarned = Math.round((Number(state.stats.totalExhysEarned || 0) + roll.totalReward) * 10) / 10;
    state.stats.taskExhysEarned = Math.round((Number(state.stats.taskExhysEarned || 0) + roll.totalReward) * 10) / 10;
    state.stats.highestRollReward = Math.max(Number(state.stats.highestRollReward || 0), roll.totalReward);
    state.stats.highestDareReward = Math.max(Number(state.stats.highestDareReward || 0), ...roll.dares.map(d => Number(d.reward || 0)));
    if (roll.outfit.source === 'library') state.stats.outfitLibraryCompletions += 1;
    if (roll.outfit.source === 'shop') state.stats.shopOutfitCompletions += 1;
    if (roll.outfit.source === 'random') state.stats.randomOutfitCompletions += 1;
    if (roll.outfit.source === 'random' && roll.outfit.matching) state.stats.matchingOutfitCompletions += 1;
    if (roll.outfit.source === 'random' && !roll.outfit.matching) state.stats.mixedOutfitCompletions += 1;

    const rankMessages = addRankXp(15 * roll.dares.length, 'Main roll completed');
    const milestoneMessages = checkHiddenMilestones();
    render();
    animateExhysBalance(oldExhys, newExhys);
    queueToasts([`Claimed ${formatNum(roll.totalReward)} Exhys.`, ...rankMessages, ...milestoneMessages]);
  }

  function renderWardrobe() {
    const counts = ['common','rare','epic','legendary'].map(rarity => ({
      rarity,
      owned: OUTFIT_LIBRARY.filter(item => item.rarity === rarity && isOwned(item.id)).length,
      total: OUTFIT_LIBRARY.filter(item => item.rarity === rarity).length
    }));
    views.wardrobe.innerHTML = `
      <section class="card">
        <div class="card-title-row">
          <div>
            <h2>Wardrobe Collection</h2>
            <p class="muted">Your unlocked outfit library. Main rolls and Dress Up training roll from unlocked outfits using rarity weights.</p>
          </div>
          <span class="badge">${unlockedOutfits().length}/${OUTFIT_LIBRARY.length} unlocked</span>
        </div>
        <div class="collection-summary">
          ${counts.map(row => `<div class="collection-stat"><strong>${row.owned}/${row.total}</strong><span class="muted small">${esc(RARITY[row.rarity].label)}</span></div>`).join('')}
        </div>
      </section>
      <div class="grid three" style="margin-top:14px">
        ${OUTFIT_LIBRARY.map(renderOutfitCollectionCard).join('')}
      </div>
    `;
  }

  function outfitUnlockLabel(outfit) {
    if (outfit.unlock === 'start') return 'Starting outfit';
    if (outfit.unlock === 'shop') return 'Shop';
    if (outfit.unlock === 'milestone') return 'Hidden milestone';
    if (outfit.unlock === 'rank') return `Sissy Rank ${outfit.rankLevel}`;
    return 'Locked';
  }

  function renderOutfitCollectionCard(outfit) {
    const owned = isOwned(outfit.id);
    const rarity = RARITY[outfit.rarity] || RARITY.common;
    const hiddenMilestone = outfit.unlock === 'milestone' && !owned;
    const title = hiddenMilestone ? 'Hidden Milestone Outfit' : outfit.name;
    const details = hiddenMilestone ? 'Complete hidden milestones to reveal this outfit.' : outfit.details;
    const pieces = String(details || '').split(',').map(x => x.trim()).filter(Boolean);
    return `
      <section class="card compact shop-item outfit-card rarity-${esc(outfit.rarity)} ${owned ? '' : 'locked'}">
        <div class="card-title-row">
          <div>
            <h3>${esc(outfit.number)}. ${esc(title)}</h3>
            <span class="badge ${esc(outfit.rarity)}">${esc(rarity.label)} · weight ${rarity.weight}</span>
          </div>
          <span class="badge">${owned ? 'Unlocked' : 'Locked'}</span>
        </div>
        <p class="muted small">Unlock source: ${esc(outfitUnlockLabel(outfit))}</p>
        <div class="pieces">${pieces.map(piece => `<span>• ${esc(piece)}</span>`).join('')}</div>
      </section>
    `;
  }


  function wardrobeOptionsFor(category) {
    return category === 'Wig' ? WIG_OPTIONS : COLORS;
  }

  function renderCategoryCard(category) {
    const selected = new Set(state.wardrobe[category] || []);
    return `
      <section class="card compact">
        <div class="card-title-row">
          <div>
            <h3>${esc(category)}</h3>
            <p class="small muted">${selected.size} color${selected.size === 1 ? '' : 's'} selected</p>
          </div>
          <div class="roll-controls">
            <button class="btn ghost small" data-select-all="${esc(category)}">All</button>
            <button class="btn ghost small" data-clear-all="${esc(category)}">Clear</button>
          </div>
        </div>
        <div class="color-grid">
          ${wardrobeOptionsFor(category).map(color => `
            <label class="color-chip">
              <input type="checkbox" data-color-toggle data-category="${esc(category)}" data-color="${esc(color.name)}" ${selected.has(color.name) ? 'checked' : ''}>
              <span class="color-dot" style="background:${esc(color.value)}"></span>
              ${esc(color.name)}
            </label>
          `).join('')}
        </div>
      </section>
    `;
  }

  function renderTraining() {
    syncTrainingTimers();
    const training = state.training || createDefaultTrainingState();
    const fullConvert = Math.floor(Number(state.obedience || 0) / 100);
    views.training.innerHTML = `
      <section class="card">
        <div class="card-title-row">
          <div>
            <h2>Sissy Training</h2>
            <p class="muted">Side tasks earn Obedience. Main Dressed & Dared rolls remain the best way to earn Exhys.</p>
          </div>
          <span class="badge">100 Obedience = 1 Exhys</span>
        </div>
        <div class="training-summary">
          <div class="training-stat"><strong>${formatNum(state.obedience)}</strong><span class="muted small">Obedience</span></div>
          <div class="training-stat"><strong>${formatNum(training.stats.tasksCompleted || 0)}</strong><span class="muted small">Training tasks completed</span></div>
          <div class="training-stat"><strong>${formatNum(training.stats.taskObedienceEarned || 0)}</strong><span class="muted small">Task-earned Obedience</span></div>
        </div>
        <div class="conversion-row">
          <button id="convertObedienceBtn" class="btn primary small" ${fullConvert > 0 ? '' : 'disabled'}>Convert ${formatNum(fullConvert * 100)} Obedience → ${formatNum(fullConvert)} Exhys</button>
          <span class="small muted">Leftover Obedience stays after conversion.</span>
        </div>
      </section>

      <section class="card" style="margin-top:14px">
        <div class="card-title-row">
          <div>
            <h2>Training Upgrades</h2>
            <p class="muted">Bought with Obedience. These do not increase normal shop prices.</p>
          </div>
          <span class="badge">Cost scaling ×1.3</span>
        </div>
        <div class="upgrade-grid">${TRAINING_UPGRADES.map(upgrade => renderTrainingUpgrade(upgrade)).join('')}</div>
      </section>

      <div class="grid two" style="margin-top:14px">
        ${TRAINING_CATEGORIES.map(category => renderTrainingCategory(category)).join('')}
      </div>
    `;

    document.getElementById('convertObedienceBtn')?.addEventListener('click', convertObedience);
    document.querySelectorAll('[data-training-upgrade]').forEach(btn => btn.addEventListener('click', () => buyTrainingUpgrade(btn.dataset.trainingUpgrade)));
    document.querySelectorAll('[data-roll-training]').forEach(btn => btn.addEventListener('click', () => rollTrainingOffer(btn.dataset.rollTraining)));
    document.querySelectorAll('[data-reroll-training]').forEach(btn => btn.addEventListener('click', () => rerollTrainingOffer(btn.dataset.rerollTraining)));
    document.querySelectorAll('[data-accept-training]').forEach(btn => btn.addEventListener('click', () => acceptTrainingOffer(btn.dataset.acceptTraining)));
    document.querySelectorAll('[data-complete-training]').forEach(btn => btn.addEventListener('click', () => completeTrainingTask(btn.dataset.completeTraining)));
    document.querySelectorAll('[data-cancel-training]').forEach(btn => btn.addEventListener('click', () => cancelTrainingTask(btn.dataset.cancelTraining)));
    document.querySelectorAll('[data-chastity-locked]').forEach(btn => btn.addEventListener('click', () => startChastityTimer()));
    document.querySelectorAll('[data-chastity-unlock]').forEach(btn => btn.addEventListener('click', () => askChastityUnlock()));
    document.querySelectorAll('[data-add-training-task]').forEach(btn => btn.addEventListener('click', () => addTrainingTask(btn.dataset.addTrainingTask)));
    document.querySelectorAll('[data-new-training-task]').forEach(input => input.addEventListener('keydown', event => {
      if (event.key === 'Enter') {
        event.preventDefault();
        addTrainingTask(input.dataset.newTrainingTask);
      }
    }));
    document.querySelectorAll('[data-training-task-enabled]').forEach(input => input.addEventListener('change', () => updateTrainingTask(input.dataset.trainingTaskEnabled, input.dataset.taskId, { enabled: input.checked })));
    document.querySelectorAll('[data-training-task-text]').forEach(input => input.addEventListener('input', () => updateTrainingTask(input.dataset.trainingTaskText, input.dataset.taskId, { text: input.value })));
    document.querySelectorAll('[data-delete-training-task]').forEach(btn => btn.addEventListener('click', () => deleteTrainingTask(btn.dataset.deleteTrainingTask, btn.dataset.taskId)));
  }

  function renderTrainingUpgrade(upgrade) {
    const level = Number(state.training.upgrades[upgrade.id] || 0);
    const cost = trainingUpgradeCost(upgrade.id);
    const fullCost = trainingUpgradeFullCost(upgrade.id);
    const discount = state.trainingUpgradeDiscounts?.[upgrade.id];
    return `
      <div class="upgrade-box">
        <div class="card-title-row">
          <div>
            <h3>${esc(upgrade.name)}</h3>
            <p class="muted small">${esc(upgrade.description)}</p>
          </div>
          <span class="badge">Lv ${level}</span>${discount ? `<span class="badge discount-badge">${Math.round(Number(discount.percent || 0) * 100)}% off</span>` : ''}
        </div>
        <footer>
          <span class="price obedience-price">${currencyIcon('obedience')}${formatNum(cost)} Obedience${discount ? ` <small class="muted"><s>${formatNum(fullCost)}</s></small>` : ''}</span>
          <button class="btn primary small" data-training-upgrade="${esc(upgrade.id)}" ${state.obedience >= cost ? '' : 'disabled'}>Upgrade</button>
        </footer>
      </div>
    `;
  }

  function renderTrainingCategory(category) {
    const data = state.training.categories[category];
    const offer = data.offer;
    const active = data.active;
    const normalTaskEditor = USER_TASK_TRAINING_CATEGORIES.includes(category) ? renderTrainingTaskEditor(category) : '';
    const specialNote = category === 'Chastity'
      ? '<p class="muted small">Unique timer system. Rolls a duration from 1h to 12h and pays only after “May I unlock now?” says yes.</p>'
      : category === 'Dress Up'
        ? '<p class="muted small">Rolls from your unlocked Wardrobe outfit collection instead of a separate task list.</p>'
        : '<p class="muted small">Add equal tasks below. The offer gamble rolls the reward, not task difficulty.</p>';
    return `
      <section class="card compact training-category">
        <div class="card-title-row">
          <div>
            <h2>${esc(category)}</h2>
            ${specialNote}
          </div>
          <span class="badge">${trainingRerollLimitForNewOffer()} rerolls</span>
        </div>
        ${renderTrainingStatus(category, offer, active)}
        ${normalTaskEditor}
      </section>
    `;
  }

  function renderTrainingStatus(category, offer, active) {
    if (active) return renderActiveTrainingTask(category, active);
    if (offer) return renderTrainingOffer(category, offer);
    return `
      <div class="offer-box">
        <p class="muted small">No active offer. Roll a task offer for this category.</p>
        <button class="btn primary small" data-roll-training="${esc(category)}">Gamble for Offer</button>
      </div>
    `;
  }

  function renderTrainingOffer(category, offer) {
    const remainingRerolls = Math.max(0, Number(offer.maxRerolls || 0) - Number(offer.rerollsUsed || 0));
    return `
      <div class="offer-box">
        <h3>Current Offer</h3>
        <p class="training-task-display">${esc(offer.taskText)}</p>
        ${offer.durationMinutes ? `<p class="small muted">Duration: ${formatDuration(offer.durationMinutes * 60)}</p>` : ''}
        <p class="price obedience-price">${currencyIcon('obedience')}Reward: ${formatNum(offer.reward)} Obedience</p>
        <p class="small muted">Rerolls used: ${offer.rerollsUsed || 0}/${offer.maxRerolls || 0}. ${remainingRerolls === 1 ? 'Next reroll auto-accepts.' : remainingRerolls > 1 ? `${remainingRerolls} rerolls remaining.` : 'No rerolls remaining.'}</p>
        <div class="roll-controls">
          <button class="btn small" data-reroll-training="${esc(category)}" ${remainingRerolls > 0 ? '' : 'disabled'}>Reroll Offer</button>
          <button class="btn primary small" data-accept-training="${esc(category)}">Accept</button>
        </div>
      </div>
    `;
  }

  function renderActiveTrainingTask(category, active) {
    if (category === 'Chastity') return renderActiveChastity(active);
    return `
      <div class="active-task-box">
        <h3>Active Task</h3>
        <p class="training-task-display">${esc(active.taskText)}</p>
        <p class="price obedience-price">${currencyIcon('obedience')}Reward on completion: ${formatNum(active.reward)} Obedience</p>
        <p class="small muted">Rewards are only paid after completion. Rerolls reset for this category after completion.</p>
        <div class="roll-controls">
          <button class="btn primary small" data-complete-training="${esc(category)}">Complete Task</button>
          <button class="btn ghost small" data-cancel-training="${esc(category)}">Cancel</button>
        </div>
      </div>
    `;
  }

  function renderActiveChastity(active) {
    const status = active.status || 'accepted';
    const remaining = chastityRemainingSeconds(active);
    let body = '';
    if (status === 'accepted') {
      body = `<p class="muted small">Accepted. Press Locked when the timer has actually started.</p><button class="btn primary small" data-chastity-locked="1">Locked</button>`;
    } else if (status === 'locked') {
      body = `<div class="timer-display">${formatDuration(remaining)}</div><p class="muted small">Timer is running. It keeps counting down based on real time.</p>`;
    } else {
      body = `<p class="muted small">Timer finished.</p><button class="btn primary small" data-chastity-unlock="1">May I unlock now?</button>`;
    }
    return `
      <div class="active-task-box">
        <h3>Active Chastity Timer</h3>
        <p class="training-task-display">${esc(active.taskText)}</p>
        <p class="price obedience-price">${currencyIcon('obedience')}Reward after yes: ${formatNum(active.reward)} Obedience</p>
        <p class="small muted">No count: ${Number(active.noCount || 0)}. Minimum no-extension timer is 5 minutes.</p>
        ${body}
        <div class="roll-controls"><button class="btn ghost small" data-cancel-training="Chastity">Cancel</button></div>
      </div>
    `;
  }

  function renderTrainingTaskEditor(category) {
    const tasks = state.training.categories[category]?.tasks || [];
    return `
      <div class="task-editor-box">
        <h3>Task List</h3>
        <p class="muted small">Each task is treated as equal. No difficulty or intensity.</p>
        <div class="training-add-row">
          <input type="text" data-new-training-task="${esc(category)}" placeholder="Add a ${esc(category)} training task..." maxlength="220">
          <button class="btn primary small" data-add-training-task="${esc(category)}">Add Task</button>
        </div>
        <div class="training-task-list">
          ${tasks.map(task => `
            <div class="training-task-row">
              <input type="checkbox" data-training-task-enabled="${esc(category)}" data-task-id="${esc(task.id)}" ${task.enabled ? 'checked' : ''}>
              <input type="text" data-training-task-text="${esc(category)}" data-task-id="${esc(task.id)}" value="${esc(task.text)}" placeholder="Training task">
              <button class="btn ghost small" data-delete-training-task="${esc(category)}" data-task-id="${esc(task.id)}">×</button>
            </div>
          `).join('') || '<div class="empty">No tasks yet.</div>'}
        </div>
      </div>
    `;
  }

  function trainingUpgradeCost(id) {
    const upgrade = TRAINING_UPGRADES.find(item => item.id === id);
    const level = Number(state.training.upgrades[id] || 0);
    const base = Math.ceil((upgrade?.baseCost || 1000) * Math.pow(1.3, level));
    const discount = state.trainingUpgradeDiscounts?.[id];
    if (discount) return Math.ceil(base * (1 - Number(discount.percent || 0)));
    return base;
  }

  function trainingUpgradeFullCost(id) {
    const upgrade = TRAINING_UPGRADES.find(item => item.id === id);
    const level = Number(state.training.upgrades[id] || 0);
    return Math.ceil((upgrade?.baseCost || 1000) * Math.pow(1.3, level));
  }

  function trainingRerollLimitForNewOffer() {
    return 2 + Number(state.training.upgrades.extraRerolls || 0);
  }

  function obedienceMultiplier() {
    return 1 + (Number(state.training.upgrades.obedienceMultiplier || 0) * 0.10);
  }

  function trainingOfferScale() {
    return 300 + (Number(state.training.upgrades.betterOffers || 0) * 50);
  }

  function rollTrainingBaseReward() {
    const scale = trainingOfferScale();
    return Math.max(1, Math.min(5000, Math.ceil(-Math.log(1 - Math.random()) * scale)));
  }

  function applyTrainingMultiplier(baseReward) {
    return Math.max(1, Math.floor(baseReward * obedienceMultiplier()));
  }

  function rollTrainingOffer(category) {
    const data = state.training.categories[category];
    if (data.active) { toast('Complete or cancel the active task first.'); return; }
    const offer = createTrainingOffer(category);
    if (!offer) return;
    data.offer = offer;
    state.training.stats.offersRolled += 1;
    if (category === 'Chastity') state.training.stats.chastityOffersRolled += 1;
    if (category === 'Dress Up') state.training.stats.dressUpGenerated += 1;
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`Offer rolled for ${category}.`, ...milestoneMessages]);
  }

  function rerollTrainingOffer(category) {
    const data = state.training.categories[category];
    const oldOffer = data.offer;
    if (!oldOffer || data.active) return;
    const maxRerolls = Number(oldOffer.maxRerolls || 0);
    const nextUsed = Number(oldOffer.rerollsUsed || 0) + 1;
    if (nextUsed > maxRerolls) return;
    const newOffer = createTrainingOffer(category);
    if (!newOffer) return;
    newOffer.maxRerolls = maxRerolls;
    newOffer.rerollsUsed = nextUsed;
    state.training.stats.rerollsUsed += 1;
    if (nextUsed >= maxRerolls) {
      data.offer = newOffer;
      acceptTrainingOffer(category, true);
      return;
    }
    data.offer = newOffer;
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`Offer rerolled.`, ...milestoneMessages]);
  }

  function createTrainingOffer(category) {
    const base = { id: uid(), category, rerollsUsed: 0, maxRerolls: trainingRerollLimitForNewOffer(), createdAt: new Date().toISOString() };
    if (category === 'Chastity') return { ...base, ...createChastityOffer() };
    if (category === 'Dress Up') return { ...base, ...createDressUpTrainingOffer() };
    const tasks = enabled(state.training.categories[category]?.tasks || []);
    if (!tasks.length) { toast(`Add at least one enabled ${category} task first.`); return null; }
    const task = choice(tasks);
    const baseReward = rollTrainingBaseReward();
    return { ...base, taskText: task.text, baseReward, reward: applyTrainingMultiplier(baseReward) };
  }

  function createDressUpTrainingOffer() {
    const outfit = rollOutfit();
    const outfitText = `${outfit.name}${outfit.details ? ` — ${outfit.details}` : ''}`;
    const minutes = 10 + Math.floor(Math.random() * 81);
    const baseReward = rollTrainingBaseReward();
    return {
      taskText: `Wear this outfit for ${minutes} minutes: ${outfitText}.`,
      baseReward,
      reward: applyTrainingMultiplier(baseReward),
      outfit
    };
  }

  function createChastityOffer() {
    const durationMinutes = 60 + Math.floor(Math.random() * (720 - 60 + 1));
    const cap = chastityRewardCap(durationMinutes);
    const baseReward = Math.max(1, Math.ceil(Math.pow(Math.random(), 1.8) * cap));
    return {
      taskText: `Stay locked for ${formatDuration(durationMinutes * 60)}.`,
      durationMinutes,
      currentTimerSeconds: durationMinutes * 60,
      baseReward,
      reward: applyTrainingMultiplier(baseReward)
    };
  }

  function chastityRewardCap(durationMinutes) {
    const hours = durationMinutes / 60;
    if (hours < 6) return 400;
    const progress = (hours - 6) / 6;
    return 400 + Math.floor(Math.pow(progress, 1.7) * 1600);
  }

  function acceptTrainingOffer(category, autoAccepted = false) {
    const data = state.training.categories[category];
    const offer = data.offer;
    if (!offer) return;
    data.offer = null;
    data.active = { ...offer, acceptedAt: new Date().toISOString(), status: category === 'Chastity' ? 'accepted' : 'active' };
    state.training.stats.offersAccepted += 1;
    if (autoAccepted) state.training.stats.autoAcceptedOffers += 1;
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([autoAccepted ? `Final reroll auto-accepted for ${category}.` : `${category} task accepted.`, ...milestoneMessages]);
  }

  function completeTrainingTask(category) {
    const data = state.training.categories[category];
    const active = data.active;
    if (!active || category === 'Chastity') return;
    payTrainingReward(category, active);
  }

  function payTrainingReward(category, active) {
    const luck = trainingLuckBonus();
    const finalReward = Math.round((Number(active.reward || 0) + luck.bonus) * 10) / 10;
    state.obedience = Math.round((Number(state.obedience || 0) + finalReward) * 10) / 10;
    state.training.categories[category].active = null;
    state.training.categories[category].offer = null;
    const stats = state.training.stats;
    stats.tasksCompleted += 1;
    stats.totalObedienceEarned = Math.round((Number(stats.totalObedienceEarned || 0) + finalReward) * 10) / 10;
    stats.taskObedienceEarned = Math.round((Number(stats.taskObedienceEarned || 0) + finalReward) * 10) / 10;
    stats.highestBaseReward = Math.max(Number(stats.highestBaseReward || 0), Number(active.baseReward || 0));
    stats.highestFinalReward = Math.max(Number(stats.highestFinalReward || 0), finalReward);
    const key = categoryStatKey(category);
    stats[key] = Number(stats[key] || 0) + 1;
    if (category === 'Chastity') {
      stats.chastityTotalMinutes = Number(stats.chastityTotalMinutes || 0) + Number(active.durationMinutes || 0);
    }
    if (luck.bonus > 0) {
      stats.luckBonusesTriggered += luck.chunks;
      stats.luckBonusObedience += luck.bonus;
    }
    const xpAmount = category === 'Chastity' ? Math.max(1, Math.floor(Number(active.durationMinutes || 0) / 60)) : 5;
    const rankMessages = addRankXp(xpAmount, `${category} training completed`);
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`Training complete: +${formatNum(finalReward)} Obedience${luck.bonus ? ` (${formatNum(luck.bonus)} from luck)` : ''}.`, ...rankMessages, ...milestoneMessages]);
  }

  function trainingLuckBonus() {
    const level = Number(state.training.upgrades.trainingLuck || 0);
    const chance = level * 10;
    const guaranteed = Math.floor(chance / 100);
    const leftover = chance % 100;
    let chunks = guaranteed;
    if (leftover > 0 && Math.random() * 100 < leftover) chunks += 1;
    return { chunks, bonus: chunks * 100 };
  }

  function cancelTrainingTask(category) {
    if (!confirm(`Cancel the active ${category} task? No Obedience will be paid.`)) return;
    state.training.categories[category].active = null;
    state.training.categories[category].offer = null;
    toast(`${category} task cancelled.`);
    render();
  }

  function startChastityTimer() {
    const active = state.training.categories.Chastity.active;
    if (!active || active.status !== 'accepted') return;
    active.status = 'locked';
    active.endTime = Date.now() + (Number(active.currentTimerSeconds || 0) * 1000);
    render();
    toast('Chastity timer started.');
  }

  function syncTrainingTimers() {
    const active = state.training?.categories?.Chastity?.active;
    if (!active || active.status !== 'locked') return;
    if (chastityRemainingSeconds(active) <= 0) {
      active.status = 'awaitingUnlock';
      active.endTime = null;
    }
  }

  function chastityRemainingSeconds(active) {
    if (!active || active.status !== 'locked' || !active.endTime) return Math.max(0, Number(active.currentTimerSeconds || 0));
    return Math.max(0, Math.ceil((Number(active.endTime) - Date.now()) / 1000));
  }

  function askChastityUnlock() {
    const active = state.training.categories.Chastity.active;
    if (!active || active.status !== 'awaitingUnlock') return;
    if (Math.random() < 0.95) {
      payTrainingReward('Chastity', active);
      queueToasts(['Yes. You may unlock now.']);
      return;
    }
    const nextSeconds = Math.max(300, Math.ceil(Number(active.currentTimerSeconds || 300) / 2));
    active.currentTimerSeconds = nextSeconds;
    active.status = 'locked';
    active.endTime = Date.now() + nextSeconds * 1000;
    active.noCount = Number(active.noCount || 0) + 1;
    state.training.stats.chastityNoCount += 1;
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`No. Timer restarted for ${formatDuration(nextSeconds)}.`, ...milestoneMessages]);
  }

  function formatDuration(seconds) {
    seconds = Math.max(0, Math.ceil(Number(seconds || 0)));
    const h = Math.floor(seconds / 3600);
    const m = Math.floor((seconds % 3600) / 60);
    const s = seconds % 60;
    if (h > 0) return `${h}h ${String(m).padStart(2, '0')}m`;
    if (m > 0) return `${m}m ${String(s).padStart(2, '0')}s`;
    return `${s}s`;
  }

  function addTrainingTask(category) {
    const input = Array.from(document.querySelectorAll('[data-new-training-task]')).find(item => item.dataset.newTrainingTask === category);
    const text = input ? input.value.trim() : '';
    if (!text) {
      toast('Type a training task first.');
      if (input) input.focus();
      return;
    }
    state.training.categories[category].tasks.push(makeListItem(text));
    if (input) input.value = '';
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`${category} task added.`, ...milestoneMessages]);
  }

  function updateTrainingTask(category, id, patch) {
    const tasks = state.training.categories[category]?.tasks || [];
    const task = tasks.find(item => item.id === id);
    if (!task) return;
    Object.assign(task, patch);
    saveState();
  }

  function deleteTrainingTask(category, id) {
    state.training.categories[category].tasks = (state.training.categories[category]?.tasks || []).filter(item => item.id !== id);
    render();
  }

  function convertObedience() {
    const exhys = Math.floor(Number(state.obedience || 0) / 100);
    if (exhys <= 0) return;
    state.obedience = Math.round((Number(state.obedience || 0) - (exhys * 100)) * 10) / 10;
    state.exhys = Math.round((Number(state.exhys || 0) + exhys) * 10) / 10;
    state.training.stats.obedienceConverted += exhys * 100;
    state.training.stats.exhysFromObedience += exhys;
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`Converted ${formatNum(exhys * 100)} Obedience into ${formatNum(exhys)} Exhys.`, ...milestoneMessages]);
  }

  function buyTrainingUpgrade(id) {
    const cost = trainingUpgradeCost(id);
    const upgrade = TRAINING_UPGRADES.find(item => item.id === id);
    if (!upgrade) return;
    if (state.obedience < cost) { toast(`Not enough Obedience. Need ${formatNum(cost)}.`); return; }
    state.obedience = Math.round((Number(state.obedience || 0) - cost) * 10) / 10;
    if (state.trainingUpgradeDiscounts?.[id]) delete state.trainingUpgradeDiscounts[id];
    state.training.upgrades[id] = Number(state.training.upgrades[id] || 0) + 1;
    state.training.stats.upgradesBought += 1;
    const rankMessages = addRankXp(10, 'Training upgrade bought');
    const milestoneMessages = checkTrainingMilestones();
    render();
    queueToasts([`${upgrade.name} upgraded.`, ...rankMessages, ...milestoneMessages]);
  }


  function xpToNextRank(rank = state.sissyRank?.rank || 0) {
    if (Number(rank) >= 50) return 0;
    return Math.ceil(100 * Math.pow(1.0675, Number(rank || 0)));
  }

  function rankTitle(rank = state.sissyRank?.rank || 0) {
    rank = Number(rank || 0);
    if (rank >= 50) return 'Publicly Exposed Sissy Showtoy';
    if (rank >= 45) return 'Exposed Sissy Slut';
    if (rank >= 40) return 'Public Showpiece';
    if (rank >= 35) return 'Displayed Whore';
    if (rank >= 30) return 'Shameless Toy';
    if (rank >= 25) return 'Slutty Plaything';
    if (rank >= 20) return 'Trained Pet';
    if (rank >= 15) return 'Obedient Sissy';
    if (rank >= 10) return 'Shy Doll';
    if (rank >= 5) return 'Panty Trainee';
    return 'Blushing Beginner';
  }

  function addRankXp(amount, reason = '') {
    amount = Math.max(0, Number(amount || 0));
    if (!amount || state.sissyRank.rank >= 50) return [];
    const messages = [`+${formatNum(amount)} Sissy XP${reason ? ` — ${reason}` : ''}.`];
    state.sissyRank.xp += amount;
    state.sissyRank.totalXp += amount;
    while (state.sissyRank.rank < 50) {
      const needed = xpToNextRank(state.sissyRank.rank);
      if (state.sissyRank.xp < needed) break;
      state.sissyRank.xp -= needed;
      state.sissyRank.rank += 1;
      messages.push(`Sissy Rank Up: Rank ${state.sissyRank.rank} — ${rankTitle(state.sissyRank.rank)}.`);
      messages.push(...applyRankReward(state.sissyRank.rank));
    }
    if (state.sissyRank.rank >= 50) state.sissyRank.xp = 0;
    return messages;
  }

  function applyRankReward(rank) {
    const reward = RANK_REWARDS.find(item => item.rank === rank);
    if (!reward) return [];
    if (!state.sissyRank.rewardsClaimed.includes(rank)) state.sissyRank.rewardsClaimed.push(rank);
    const messages = [];
    reward.rewards.forEach(action => {
      if (action.type === 'exhys') {
        state.exhys = Math.round((Number(state.exhys || 0) + Number(action.amount || 0)) * 10) / 10;
        messages.push(`Rank reward: +${formatNum(action.amount)} Exhys.`);
      }
      if (action.type === 'obedience') {
        state.obedience = Math.round((Number(state.obedience || 0) + Number(action.amount || 0)) * 10) / 10;
        messages.push(`Rank reward: +${formatNum(action.amount)} Obedience.`);
      }
      if (action.type === 'outfit') {
        const outfitName = unlockOutfit(action.outfitId);
        messages.push(`Rank reward: outfit unlocked — ${outfitName}.`);
      }
      if (action.type === 'priceFreeze') {
        state.priceFreezes = Number(state.priceFreezes || 0) + Number(action.count || 1);
        state.stats.priceFreezesReceived += Number(action.count || 1);
        messages.push('Rank reward: Price Freeze added.');
      }
      if (action.type === 'shopDiscount') {
        const text = applyRandomShopDiscount(Number(action.percent || 0.25));
        messages.push(`Rank reward: ${text}`);
      }
      if (action.type === 'trainingDiscount') {
        const text = applyRandomTrainingDiscount(Number(action.percent || 0.25));
        messages.push(`Rank reward: ${text}`);
      }
    });
    return messages;
  }

  function applyRandomShopDiscount(percent) {
    const targets = SHOP_ITEMS.filter(item => !isOwned(item.id) && itemBasePrice(item) > 0 && !state.discounts?.[item.id]);
    const fallback = SHOP_ITEMS.filter(item => !isOwned(item.id) && itemBasePrice(item) > 0);
    const target = choice(targets.length ? targets : fallback);
    if (!target) return 'no locked shop item was available for discount.';
    state.discounts[target.id] = { percent, createdAt: new Date().toISOString() };
    state.stats.secretDiscountsReceived += 1;
    return `${Math.round(percent * 100)}% discount applied to ${target.name}.`;
  }

  function applyRandomTrainingDiscount(percent) {
    state.trainingUpgradeDiscounts = state.trainingUpgradeDiscounts || {};
    const targets = TRAINING_UPGRADES.filter(upgrade => !state.trainingUpgradeDiscounts[upgrade.id]);
    const target = choice(targets.length ? targets : TRAINING_UPGRADES);
    if (!target) return 'no Training upgrade was available for discount.';
    state.trainingUpgradeDiscounts[target.id] = { percent, createdAt: new Date().toISOString() };
    return `${Math.round(percent * 100)}% discount applied to ${target.name}.`;
  }

  function renderRank() {
    const rank = state.sissyRank || createDefaultSissyRankState();
    const need = xpToNextRank(rank.rank);
    const pct = rank.rank >= 50 ? 100 : Math.min(100, (Number(rank.xp || 0) / Math.max(1, need)) * 100);
    const nextReward = RANK_REWARDS.find(item => item.rank === Math.min(50, rank.rank + 1));
    views.rank.innerHTML = `
      <section class="card rank-hero">
        <div class="card-title-row">
          <div>
            <h2>Sissy Rank</h2>
            <p class="muted">Battle-pass progression. Every rank gives a visible reward.</p>
          </div>
          <span class="badge">Rank ${rank.rank}/50</span>
        </div>
        <div class="training-summary">
          <div class="training-stat"><strong>${rank.rank}</strong><span class="muted small">Current rank</span></div>
          <div class="training-stat"><strong>${esc(rankTitle(rank.rank))}</strong><span class="muted small">Current title</span></div>
          <div class="training-stat"><strong>${formatNum(rank.totalXp || 0)}</strong><span class="muted small">Total Sissy XP</span></div>
        </div>
        <div style="margin-top:14px">
          <div class="rank-progress"><span style="width:${pct}%"></span></div>
          <p class="small muted">${rank.rank >= 50 ? 'Maximum rank reached.' : `${formatNum(rank.xp)} / ${formatNum(need)} XP to Rank ${rank.rank + 1}. Next reward: ${esc(nextReward?.label || 'Reward')}`}</p>
        </div>
      </section>
      <section class="card" style="margin-top:14px">
        <div class="card-title-row">
          <div>
            <h2>Reward Track</h2>
            <p class="muted">Claimed automatically on rank-up.</p>
          </div>
          <span class="badge">Visible rewards</span>
        </div>
        <div class="rank-track">${RANK_REWARDS.map(renderRankNode).join('')}</div>
      </section>
    `;
  }

  function renderRankNode(entry) {
    const current = state.sissyRank.rank === entry.rank;
    const claimed = state.sissyRank.rank >= entry.rank;
    return `
      <div class="rank-node ${claimed ? 'claimed' : ''} ${current ? 'current' : ''}">
        <div class="rank-number">Rank ${entry.rank}</div>
        <div>
          <strong>${esc(rankTitle(entry.rank))}</strong>
          <div class="rank-reward-list">${entry.rewards.map(renderRankRewardBadge).join('')}</div>
        </div>
        <span class="badge">${claimed ? 'Claimed' : 'Locked'}</span>
      </div>
    `;
  }

  function renderRankRewardBadge(action) {
    if (action.type === 'exhys') return `<span class="badge">${currencyIcon('exhys')}+${formatNum(action.amount)} Exhys</span>`;
    if (action.type === 'obedience') return `<span class="badge">${currencyIcon('obedience')}+${formatNum(action.amount)} Obedience</span>`;
    if (action.type === 'priceFreeze') return `<span class="badge freeze-badge">Price Freeze</span>`;
    if (action.type === 'shopDiscount') return `<span class="badge discount-badge">${Math.round(action.percent * 100)}% Shop Discount</span>`;
    if (action.type === 'trainingDiscount') return `<span class="badge discount-badge">${Math.round(action.percent * 100)}% Training Discount</span>`;
    if (action.type === 'outfit') {
      const outfit = findOutfit(action.outfitId);
      return `<span class="badge ${esc(outfit?.rarity || '')}">Outfit: ${esc(outfit?.name || 'Outfit')}</span>`;
    }
    return `<span class="badge">Reward</span>`;
  }

  function renderLists() {
    views.lists.innerHTML = `
      <div class="grid two">
        <section class="card">
          <div class="card-title-row">
            <div>
              <h2>Locations</h2>
              <p class="muted">Plain list. No categories, no intensity, full randomness.</p>
            </div>
            <span class="badge">${enabled(state.locations).length} enabled</span>
          </div>
          <div class="form-row">
            <input id="locationInput" placeholder="Add location..." maxlength="100" />
            <button id="addLocationBtn" class="btn primary">Add</button>
          </div>
          <div class="item-list">${state.locations.map(item => renderEditableItem(item, 'location')).join('') || '<div class="empty">No locations yet.</div>'}</div>
        </section>

        <section class="card">
          <div class="card-title-row">
            <div>
              <h2>Dares</h2>
              <p class="muted">Plain list. Choose how many to roll on the home screen. No duplicate dares in one roll.</p>
            </div>
            <span class="badge">${enabled(state.dares).length} enabled</span>
          </div>
          <div class="form-row">
            <textarea id="dareInput" placeholder="Add dare..."></textarea>
            <button id="addDareBtn" class="btn primary">Add</button>
          </div>
          <div class="item-list">${state.dares.map(item => renderEditableItem(item, 'dare')).join('') || '<div class="empty">No dares yet.</div>'}</div>
        </section>
      </div>

      <section class="card" style="margin-top:14px">
        <div class="card-title-row">
          <div>
            <h2>Backup &amp; Progress Reset</h2>
            <p class="muted">Export/import local data. Reset Progress clears Exhys, purchases, rank, shop inflation, discounts, milestones, and current roll, but keeps locations, dares, and training task lists.</p>
          </div>
          <div class="roll-controls">
            <button class="btn" id="exportBtn">Export JSON</button>
            <button class="btn" id="importBtn">Import JSON</button>
            <button class="btn danger" id="resetProgressBtn">Reset Progress</button>
          </div>
        </div>
      </section>
    `;

    document.getElementById('addLocationBtn')?.addEventListener('click', () => addListItem('location'));
    document.getElementById('locationInput')?.addEventListener('keydown', e => {
      if (e.key === 'Enter') addListItem('location');
    });
    document.getElementById('addDareBtn')?.addEventListener('click', () => addListItem('dare'));
    document.querySelectorAll('[data-toggle-list]').forEach(input => input.addEventListener('change', e => toggleListItem(e.target.dataset.type, e.target.dataset.id, e.target.checked)));
    document.querySelectorAll('[data-delete-list]').forEach(btn => btn.addEventListener('click', () => deleteListItem(btn.dataset.type, btn.dataset.id)));
    document.getElementById('exportBtn')?.addEventListener('click', exportJson);
    document.getElementById('importBtn')?.addEventListener('click', importJson);
    document.getElementById('resetProgressBtn')?.addEventListener('click', resetProgressKeepSettings);
  }

  function renderEditableItem(item, type) {
    return `
      <div class="list-item">
        <input type="checkbox" data-toggle-list data-type="${type}" data-id="${esc(item.id)}" ${item.enabled ? 'checked' : ''} title="Enabled">
        <div class="text">${esc(item.text)}</div>
        <button class="btn danger small" data-delete-list data-type="${type}" data-id="${esc(item.id)}">Delete</button>
      </div>
    `;
  }

  function addListItem(type) {
    const input = document.getElementById(type === 'location' ? 'locationInput' : 'dareInput');
    const text = input.value.trim();
    if (!text) return;
    if (type === 'location') state.locations.push(makeListItem(text));
    else state.dares.push(makeListItem(text));
    input.value = '';
    render();
  }

  function toggleListItem(type, id, checked) {
    const list = type === 'location' ? state.locations : state.dares;
    const item = list.find(x => x.id === id);
    if (item) item.enabled = checked;
    render();
  }

  function deleteListItem(type, id) {
    const key = type === 'location' ? 'locations' : 'dares';
    state[key] = state[key].filter(item => item.id !== id);
    render();
  }

  function renderShop() {
    views.shop.innerHTML = `
      <section class="card">
        <div class="card-title-row">
          <div>
            <h2>Shop</h2>
            <p class="muted">Buy cosmetics, roll effects, and shop outfits with Exhys. Every normal purchase raises future shop prices; the inflation rate starts at +10% and drops by 0.2 percentage points per purchase, capped at +3%.</p>
          </div>
          <div class="grid" style="gap:6px;text-align:right">
            <span class="badge">Inflation steps: ${state.totalPurchases}</span>
            <span class="badge">Multiplier: ×${Number(state.shopMultiplier || 1).toFixed(3)}</span>
            <span class="badge">Next increase: +${(currentInflationRate() * 100).toFixed(1)}%</span>
            ${state.priceFreezes ? `<span class="badge freeze-badge">Price Freeze: ${state.priceFreezes}</span>` : ''}
          </div>
        </div>
        <div class="shop-tabs">
          <button class="shop-tab ${activeShopTab === 'themes' ? 'active' : ''}" data-shop-tab="themes">Themes</button>
          <button class="shop-tab ${activeShopTab === 'effects' ? 'active' : ''}" data-shop-tab="effects">Roll Effects</button>
          <button class="shop-tab ${activeShopTab === 'outfits' ? 'active' : ''}" data-shop-tab="outfits">Outfits</button>
        </div>
        <div id="shopGrid" class="grid three">${renderShopItems()}</div>
      </section>
    `;

    document.querySelectorAll('[data-shop-tab]').forEach(btn => btn.addEventListener('click', () => {
      activeShopTab = btn.dataset.shopTab;
      renderShop();
    }));
    document.querySelectorAll('[data-buy]').forEach(btn => btn.addEventListener('click', () => buyItem(btn.dataset.buy)));
    document.querySelectorAll('[data-equip-theme]').forEach(btn => btn.addEventListener('click', () => equipTheme(btn.dataset.equipTheme)));
    document.querySelectorAll('[data-equip-effect]').forEach(btn => btn.addEventListener('click', () => equipEffect(btn.dataset.equipEffect)));
    document.getElementById('randomEffectToggle')?.addEventListener('change', e => {
      state.randomEffect = e.target.checked;
      render();
    });
  }

  function renderShopItems() {
    let items;
    if (activeShopTab === 'themes') items = SHOP_ITEMS.filter(item => item.kind === 'theme');
    else if (activeShopTab === 'effects') items = SHOP_ITEMS.filter(item => item.kind === 'effect');
    else items = SHOP_ITEMS.filter(item => item.kind === 'outfit');

    const randomEffectCard = activeShopTab === 'effects' ? `
      <section class="card compact shop-item">
        <div>
          <h3>Random Unlocked Effect</h3>
          <p class="muted small">When enabled, each roll randomly picks one of your owned roll effects.</p>
        </div>
        <footer>
          <label class="check-row"><input id="randomEffectToggle" type="checkbox" ${state.randomEffect ? 'checked' : ''}> Enabled</label>
        </footer>
      </section>
    ` : '';

    return randomEffectCard + items.map(item => renderShopItem(item)).join('');
  }

  function renderShopItem(item) {
    const owned = isOwned(item.id);
    const price = itemCurrentPrice(item);
    const fullPrice = fullInflatedPrice(item);
    const discount = state.discounts?.[item.id];
    const rarity = item.kind === 'outfit' ? RARITY[item.rarity] : null;
    const equippedTheme = item.kind === 'theme' && state.activeTheme === item.id;
    const equippedEffect = item.kind === 'effect' && state.activeEffect === item.id;
    const description = item.kind === 'outfit'
      ? (item.details || 'Full predefined outfit. The name describes the look.')
      : item.description;

    let action = '';
    if (!owned) {
      action = `<button class="btn primary small" data-buy="${esc(item.id)}" ${state.exhys >= price ? '' : 'disabled'}>Buy</button>`;
    } else if (item.kind === 'theme') {
      action = `<button class="btn small" data-equip-theme="${esc(item.id)}" ${equippedTheme ? 'disabled' : ''}>${equippedTheme ? 'Equipped' : 'Equip'}</button>`;
    } else if (item.kind === 'effect') {
      action = `<button class="btn small" data-equip-effect="${esc(item.id)}" ${equippedEffect ? 'disabled' : ''}>${equippedEffect ? 'Equipped' : 'Equip'}</button>`;
    } else {
      action = `<span class="owned">Owned</span>`;
    }

    const rarityClass = item.kind === 'outfit' ? ` rarity-${item.rarity}` : '';
    const discountClass = discount && !owned ? ' discounted' : '';
    const flashClass = item.id === lastShopFlashId ? ' purchase-flash' : '';

    return `
      <section class="card compact shop-item${rarityClass}${discountClass}${flashClass}" data-shop-card="${esc(item.id)}">
        <div class="card-title-row">
          <div>
            <h3>${esc(item.name)}</h3>
            ${rarity ? `<span class="badge ${esc(item.rarity)}">${esc(rarity.label)} · weight ${rarity.weight}</span>` : ''}
          </div>
          ${owned ? '<span class="badge">Owned</span>' : ''}
        </div>
        <p class="muted small">${esc(description || '')}</p>
        ${discount && !owned ? `<p class="small"><span class="badge discount-badge">Secret Discount · ${Math.round(Number(discount.percent || 0) * 100)}% off</span></p>` : ''}
        <footer>
          <span class="price">${owned ? 'Purchased' : `${currencyIcon('exhys')}${formatNum(price)} Exhys${discount ? ` <small class="muted"><s>${formatNum(fullPrice)}</s></small>` : ''}`}</span>
          ${action}
        </footer>
      </section>
    `;
  }

  function buyItem(id) {
    const item = SHOP_ITEMS.find(x => x.id === id);
    if (!item || isOwned(id)) return;
    const price = itemCurrentPrice(item);
    if (state.exhys < price) {
      toast(`Not enough Exhys. Need ${formatNum(price)}.`);
      return;
    }

    const usedDiscount = Boolean(state.discounts?.[id]);
    const usedPriceFreeze = Number(state.priceFreezes || 0) > 0;

    state.exhys = Math.round((state.exhys - price) * 10) / 10;
    state.purchased.push(id);
    state.stats.shopPurchases += 1;
    if (usedDiscount) {
      delete state.discounts[id];
      state.stats.discountsUsed += 1;
    }
    let inflationText = '';
    if (usedPriceFreeze) {
      state.priceFreezes -= 1;
      state.stats.priceFreezesUsed += 1;
      inflationText = 'Price Freeze used. Future prices did not increase.';
    } else {
      const rate = currentInflationRate();
      state.shopMultiplier = Math.round((Number(state.shopMultiplier || 1) * (1 + rate)) * 1000000) / 1000000;
      state.totalPurchases += 1;
      inflationText = `Future shop prices increased by ${(rate * 100).toFixed(1)}%.`;
    }

    let rankMessages = [];
    if (item.kind === 'outfit') rankMessages = addRankXp(20, 'Shop outfit bought');

    if (item.kind === 'theme') state.activeTheme = id;
    if (item.kind === 'effect') state.activeEffect = id;

    const milestoneMessages = checkHiddenMilestones();
    lastShopFlashId = id;
    render();
    setTimeout(() => { lastShopFlashId = null; }, 1100);
    queueToasts([`Purchased ${item.name}. ${inflationText}`, ...rankMessages, ...milestoneMessages]);
  }

  function equipTheme(id) {
    if (!isOwned(id)) return;
    state.activeTheme = id;
    toast('Theme equipped.');
    render();
  }

  function equipEffect(id) {
    if (!isOwned(id)) return;
    state.activeEffect = id;
    state.randomEffect = false;
    toast('Roll effect equipped.');
    render();
  }

  function exportJson() {
    const blob = new Blob([JSON.stringify(state, null, 2)], { type: 'application/json' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `dressed-and-dared-backup-${new Date().toISOString().slice(0,10)}.json`;
    document.body.appendChild(a);
    a.click();
    a.remove();
    URL.revokeObjectURL(url);
  }

  function importJson() {
    const input = document.createElement('input');
    input.type = 'file';
    input.accept = 'application/json';
    input.addEventListener('change', () => {
      const file = input.files?.[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = () => {
        try {
          const data = JSON.parse(String(reader.result));
          state = migrateState(data);
          toast('Backup imported.');
          render();
        } catch (err) {
          toast('Import failed. Invalid JSON.');
        }
      };
      reader.readAsText(file);
    });
    input.click();
  }

  function resetProgressKeepSettings() {
    if (!confirm('Reset progress? This clears Exhys, purchases, rank, shop prices, discounts, milestones, and current roll, but keeps locations, dares, and training task lists.')) return;
    const keptWardrobe = JSON.parse(JSON.stringify(state.wardrobe || {}));
    const keptLocations = JSON.parse(JSON.stringify(state.locations || []));
    const keptDares = JSON.parse(JSON.stringify(state.dares || []));
    const keptDareCount = Number(state.dareCount || 1);
    const keptTrainingTasks = {};
    TRAINING_CATEGORIES.forEach(category => {
      keptTrainingTasks[category] = { tasks: JSON.parse(JSON.stringify(state.training?.categories?.[category]?.tasks || [])), offer: null, active: null };
    });
    const fresh = createDefaultState();
    state = migrateState({
      ...fresh,
      wardrobe: keptWardrobe,
      locations: keptLocations,
      dares: keptDares,
      dareCount: keptDareCount,
      training: { ...createDefaultTrainingState(), categories: { ...createDefaultTrainingState().categories, ...keptTrainingTasks } },
      purchased: ['theme-neon', 'effect-basic', ...STARTING_OUTFIT_IDS],
      shopMultiplier: 1,
      sissyRank: createDefaultSissyRankState(),
      trainingUpgradeDiscounts: {}
    });
    activeView = 'home';
    activeShopTab = 'themes';
    toast('Progress reset. Wardrobe, locations, dares, and training task lists kept.');
    render();
  }

  function switchView(view) {
    activeView = view;
    render();
  }

  function toast(message) {
    const el = document.getElementById('toast');
    el.textContent = message;
    el.classList.add('show');
    clearTimeout(toast._timer);
    toast._timer = setTimeout(() => el.classList.remove('show'), 2400);
  }

  let booted = false;

  function showFatalError(err) {
    console.error(err);
    const home = document.getElementById('view-home');
    if (!home) return;
    home.classList.add('active');
    home.innerHTML = `
      <section class="card">
        <h2>App failed to load</h2>
        <p class="muted">A JavaScript error stopped the app. Try clearing site data for this GitHub Pages site, then reload.</p>
        <pre class="error-box">${esc(err?.message || String(err))}</pre>
      </section>
    `;
  }

  function clearOldServiceWorkerCaches() {
    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.getRegistrations()
        .then(registrations => registrations.forEach(reg => reg.unregister()))
        .catch(err => console.warn('Service worker cleanup failed:', err));
    }
    if ('caches' in window) {
      caches.keys()
        .then(keys => Promise.all(keys.filter(key => key.startsWith('dressed-and-dared')).map(key => caches.delete(key))))
        .catch(err => console.warn('Cache cleanup failed:', err));
    }
  }

  function boot() {
    if (booted) return;
    booted = true;
    try {
      clearOldServiceWorkerCaches();
      document.addEventListener('click', event => {
        const navButton = event.target.closest('.nav-btn');
        if (navButton?.dataset?.view) switchView(navButton.dataset.view);
      });
      updateBodyTheme();
      render();
    } catch (err) {
      showFatalError(err);
    }
  }

  setInterval(() => {
    if (activeView === 'training') {
      const active = state.training?.categories?.Chastity?.active;
      if (active?.status === 'locked') render();
    }
  }, 1000);

  window.addEventListener('error', event => showFatalError(event.error || event.message));
  window.addEventListener('unhandledrejection', event => showFatalError(event.reason));

  if (document.readyState === 'loading') document.addEventListener('DOMContentLoaded', boot);
  else boot();
})();

  </script>
</body>
</html>
