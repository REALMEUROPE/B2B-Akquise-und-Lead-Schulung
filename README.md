<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Realm Germany – Technische Tiefenschulung R290 (Profi-Edition)</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --blue-deep:#0B3D6B;
  --green-dark:#1A6B4A;
  --green-mid:#059669;
  --green-light:#ECFDF5;
  --amber:#F59E0B;
  --red:#DC2626;
  --bg:#F0F2F5;
  --card:#FFFFFF;
  --border:#E5E7EB;
  --text:#1A1A1A;
  --muted:#6B7280;
  --subtle:#F9FAFB;
}
html{scroll-behavior:smooth}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;background:var(--bg);color:var(--text);line-height:1.6}

/* ── HERO ── */
.hero{background:linear-gradient(135deg,#071f38 0%,var(--blue-deep) 45%,var(--green-dark) 100%);color:#fff;padding:4rem 1.5rem 3rem;text-align:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")}
.hero-badge{display:inline-block;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.2);border-radius:20px;padding:5px 16px;font-size:11px;letter-spacing:2px;text-transform:uppercase;margin-bottom:1.25rem;backdrop-filter:blur(4px)}
.hero h1{font-size:clamp(24px,5vw,42px);font-weight:800;margin-bottom:.75rem;line-height:1.15}
.hero h1 span{color:#6EE7B7}
.hero p{font-size:15px;opacity:.8;max-width:580px;margin:0 auto 2rem}
.hero-stats{display:flex;gap:2rem;justify-content:center;flex-wrap:wrap;margin-top:1.5rem}
.hstat{text-align:center}
.hstat .val{font-size:28px;font-weight:800;color:#6EE7B7}
.hstat .lbl{font-size:11px;opacity:.7;text-transform:uppercase;letter-spacing:1px;margin-top:2px}

/* ── NAV ── */
.nav-wrap{background:#fff;border-bottom:1px solid var(--border);position:sticky;top:0;z-index:100;box-shadow:0 1px 8px rgba(0,0,0,.06)}
.nav-inner{max-width:1100px;margin:0 auto;padding:0 1rem;display:flex;gap:0;overflow-x:auto;scrollbar-width:none}
.nav-inner::-webkit-scrollbar{display:none}
.nav-item{flex-shrink:0;padding:.875rem 1.1rem;font-size:13px;font-weight:600;color:var(--muted);cursor:pointer;border-bottom:3px solid transparent;transition:all .2s;white-space:nowrap}
.nav-item:hover{color:var(--text);background:var(--subtle)}
.nav-item.active{color:var(--green-dark);border-bottom-color:var(--green-dark)}

/* ── LAYOUT ── */
.page{max-width:1100px;margin:0 auto;padding:2rem 1rem}
.section{display:none;animation:fadeIn .3s ease}
.section.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}

/* ── CARDS ── */
.card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:1.75rem;margin-bottom:1.25rem}
.card-title{font-size:20px;font-weight:800;margin-bottom:1rem;color:var(--blue-deep);display:flex;align-items:center;gap:10px}
.card-title .ico{font-size:24px}
h3{font-size:16px;font-weight:700;margin:1.5rem 0 .6rem;color:var(--text)}
h4{font-size:14px;font-weight:700;margin:.875rem 0 .4rem;color:var(--blue-deep)}
p{font-size:14px;line-height:1.75;color:#374151;margin-bottom:.75rem}
ul,ol{padding-left:1.4rem;margin-bottom:.875rem}
li{font-size:14px;line-height:1.7;color:#374151;margin-bottom:.2rem}
strong{color:var(--text)}

/* ── HIGHLIGHT BOX ── */
.hl{background:var(--green-light);border-left:4px solid var(--green-mid);border-radius:0 10px 10px 0;padding:.875rem 1.1rem;margin:.875rem 0;font-size:13.5px;line-height:1.7}
.hl-amber{background:#FFFBEB;border-left-color:var(--amber)}
.hl-red{background:#FEF2F2;border-left-color:var(--red)}
.hl-blue{background:#EFF6FF;border-left-color:#3B82F6}
.hl strong{display:block;margin-bottom:3px}

/* ── STAT GRID ── */
.stat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:10px;margin:1rem 0}
.stat{background:var(--subtle);border:1px solid var(--border);border-radius:12px;padding:1rem;text-align:center}
.stat .val{font-size:22px;font-weight:800;color:var(--green-dark)}
.stat .lbl{font-size:11px;color:var(--muted);margin-top:4px;line-height:1.4}

/* ── TABLE ── */
.tbl-wrap{overflow-x:auto;margin:.875rem 0;border-radius:10px;border:1px solid var(--border)}
table{width:100%;border-collapse:collapse;font-size:13px}
thead tr{background:var(--subtle)}
th{padding:9px 14px;text-align:left;font-weight:700;color:#374151;border-bottom:1px solid var(--border)}
td{padding:9px 14px;border-bottom:1px solid #F3F4F6;color:#4B5563;vertical-align:top}
tr:last-child td{border-bottom:none}
tr:hover td{background:#FAFAFA}

/* ── BADGES ── */
.badge{display:inline-block;padding:2px 9px;border-radius:12px;font-size:11px;font-weight:700}
.bg{background:#D1FAE5;color:#065F46}
.bb{background:#DBEAFE;color:#1E40AF}
.ba{background:#FEF3C7;color:#92400E}
.br{background:#FEE2E2;color:#991B1B}
.bp{background:#F3E8FF;color:#6B21A8}
.go{background:#E0F2FE;color:#0369A1}

/* ── DIAGRAM / FLOW ── */
.diagram{background:var(--subtle);border:1px solid var(--border);border-radius:14px;padding:1.5rem;margin:1rem 0;overflow-x:auto}
.cycle{display:flex;align-items:center;flex-wrap:wrap;gap:0;justify-content:center}
.cycle-step{background:#fff;border:2px solid var(--border);border-radius:12px;padding:.875rem 1rem;text-align:center;min-width:130px;position:relative;flex:1;max-width:180px}
.cycle-step .cs-num{width:26px;height:26px;border-radius:50%;background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;font-size:12px;font-weight:800;display:flex;align-items:center;justify-content:center;margin:0 auto .5rem}
.cycle-step .cs-icon{font-size:24px;margin-bottom:.25rem}
.cycle-step .cs-title{font-size:13px;font-weight:700;margin-bottom:2px}
.cycle-step .cs-temp{font-size:11px;color:var(--green-dark);font-weight:700}
.cycle-step .cs-desc{font-size:11px;color:var(--muted);margin-top:3px;line-height:1.4}
.cycle-arrow{font-size:22px;color:var(--green-dark);padding:0 6px;flex-shrink:0;font-weight:700}

/* ── COMPONENT CARD ── */
.comp-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:12px;margin:1rem 0}
.comp-card{background:#fff;border:1px solid var(--border);border-radius:12px;padding:1.1rem;transition:box-shadow .2s;cursor:default}
.comp-card:hover{box-shadow:0 4px 16px rgba(0,0,0,.08)}
.comp-card .cc-icon{font-size:28px;margin-bottom:.5rem}
.comp-card .cc-title{font-size:14px;font-weight:700;margin-bottom:4px;color:var(--blue-deep)}
.comp-card .cc-brand{font-size:11px;font-weight:700;color:var(--green-dark);margin-bottom:4px}
.comp-card .cc-desc{font-size:12px;color:var(--muted);line-height:1.5}
.comp-card .cc-badge{margin-top:.5rem}

/* ── STEPS ── */
.steps{margin:.875rem 0}
.step{display:flex;gap:14px;margin-bottom:1rem;align-items:flex-start}
.step-num{width:30px;height:30px;border-radius:50%;background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;font-size:13px;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px}
.step-body h4{font-size:14px;font-weight:700;margin-bottom:3px;color:var(--text)}
.step-body p{font-size:13px;color:var(--muted);margin:0}

/* ── COMPARE TABLE ── */
.vs-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin:1rem 0}
.vs-card{border-radius:12px;padding:1.1rem;border:2px solid transparent}
.vs-realm{background:var(--green-light);border-color:var(--green-mid)}
.vs-comp{background:#F9FAFB;border-color:var(--border)}
.vs-card h4{font-size:14px;font-weight:800;margin-bottom:.75rem}
.vs-card ul{padding-left:1.2rem;margin:0}
.vs-card li{font-size:13px;margin-bottom:3px}

/* ── QUIZ ── */
.quiz-box{background:var(--subtle);border:1px solid var(--border);border-radius:14px;padding:1.5rem;margin-top:1.5rem}
.quiz-box h3{font-size:16px;font-weight:800;margin-bottom:.25rem;color:var(--blue-deep)}
.quiz-box .qsub{font-size:13px;color:var(--muted);margin-bottom:1.25rem}
.qitem{margin-bottom:2rem;border-bottom:1px dashed var(--border);padding-bottom:1.5rem}
.qitem:last-of-type{border-bottom:none}
.qitem .qt{font-size:14px;font-weight:600;margin-bottom:.6rem;line-height:1.5;color:var(--text)}
.qopt{display:flex;align-items:flex-start;gap:9px;background:#fff;border:1.5px solid var(--border);border-radius:9px;padding:.6rem .875rem;cursor:pointer;margin-bottom:6px;font-size:13px;color:#374151;width:100%;text-align:left;line-height:1.5;transition:all .15s}
.qopt:hover{border-color:#9CA3AF;background:var(--subtle)}
.qopt .qdot{width:15px;height:15px;border:2px solid #D1D5DB;border-radius:50%;flex-shrink:0;margin-top:2px;transition:all .15s}
.qopt.selected{border-color:var(--blue-deep);background:#EFF6FF}
.qopt.selected .qdot{border-color:var(--blue-deep);background:var(--blue-deep)}
.qopt.correct{background:var(--green-light);border-color:var(--green-mid);color:#065F46}
.qopt.correct .qdot{background:var(--green-mid);border-color:var(--green-mid)}
.qopt.wrong{background:#FEF2F2;border-color:var(--red);color:#7F1D1D}
.qopt.wrong .qdot{background:var(--red);border-color:var(--red)}
.qopt.locked{pointer-events:none}
.qfb{display:none;font-size:12px;line-height:1.6;padding:.55rem .875rem;border-radius:8px;margin-top:.4rem}
.qfb.show{display:block}
.qfb.ok{background:var(--green-light);color:#065F46;border:1px solid #A7F3D0}
.qfb.err{background:#FEF2F2;color:#7F1D1D;border:1px solid #FECACA}

.quiz-score{display:none;background:#fff;border-radius:10px;padding:2rem;text-align:center;margin-top:1.5rem;border:2px solid var(--border)}
.quiz-score.show{display:block}
.quiz-score .qs-val{font-size:48px;font-weight:800;color:var(--green-dark);margin-bottom:0.5rem}
.quiz-score .qs-lbl{font-size:14px;color:var(--text);margin-bottom:1.5rem;font-weight:600}

.name-row{display:flex;align-items:center;gap:12px;background:#fff;border:1.5px solid var(--border);border-radius:10px;padding:.75rem 1rem;margin-bottom:1.5rem}
.name-row label{font-size:14px;font-weight:700;white-space:nowrap;color:var(--green-dark)}
.name-row input{flex:1;border:none;background:transparent;font-size:14px;color:var(--text);outline:none}
.name-row input::placeholder{color:var(--muted)}
.mail-note{font-size:13px;color:var(--red);margin-top:1rem;font-weight:600;text-align:center}
.mail-ok{color:var(--green-mid) !important}

/* ── PROGRESS NAV BTN ── */
.nav-btns{display:flex;justify-content:space-between;margin-top:2rem;gap:10px}
.btn{padding:.65rem 1.4rem;border-radius:10px;border:1.5px solid var(--border);background:#fff;cursor:pointer;font-size:14px;font-weight:700;color:var(--text);transition:all .2s;display:inline-flex;align-items:center;gap:6px}
.btn:hover{background:var(--subtle);border-color:#9CA3AF}
.btn-primary{background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;border-color:transparent}
.btn-primary:hover{opacity:.9;background:linear-gradient(135deg,var(--blue-deep),var(--green-dark))}

/* ── PROGRESS BAR ── */
.sect-progress{background:var(--border);border-radius:8px;height:5px;margin-bottom:2rem}
.sect-progress-fill{background:linear-gradient(90deg,var(--blue-deep),var(--green-dark));border-radius:8px;height:5px;transition:width .5s}

/* ── SCOP BAR ── */
.scoprow{display:flex;align-items:center;gap:10px;margin:6px 0;font-size:13px}
.scoprow .slabel{min-width:130px;color:var(--muted);font-size:12px}
.scoprow .sbar{height:20px;border-radius:5px;display:flex;align-items:center;padding:0 9px;color:#fff;font-size:11px;font-weight:700;transition:width 1s}
.scop-realm{background:linear-gradient(90deg,var(--blue-deep),var(--green-dark))}
.scop-comp{background:#9CA3AF}
.scop-comp2{background:#B0B8C4}

/* ── ACCORDION ── */
.acc-item{border:1px solid var(--border);border-radius:10px;margin-bottom:8px;overflow:hidden}
.acc-hd{display:flex;align-items:center;justify-content:space-between;padding:.875rem 1rem;cursor:pointer;font-size:14px;font-weight:700;background:#fff;transition:background .15s}
.acc-hd:hover{background:var(--subtle)}
.acc-hd .acc-ico{font-size:18px;transition:transform .3s}
.acc-hd.open .acc-ico{transform:rotate(180deg)}
.acc-body{display:none;padding:1rem;border-top:1px solid var(--border);background:var(--subtle);font-size:13.5px;line-height:1.7}
.acc-body.open{display:block}
.acc-body p{font-size:13.5px;margin-bottom:.5rem}
.acc-body ul{padding-left:1.2rem}
.acc-body li{font-size:13.5px;margin-bottom:3px}

/* ── FORMULA BOX ── */
.formula{background:#1E293B;color:#E2E8F0;border-radius:10px;padding:1rem 1.25rem;font-family:'SF Mono',Consolas,monospace;font-size:13px;margin:.875rem 0;line-height:1.8}
.formula .fvar{color:#6EE7B7}
.formula .fval{color:#FCD34D}
.formula .fop{color:#F472B6}

@media(max-width:600px){
  .vs-grid{grid-template-columns:1fr}
  .cycle{flex-direction:column;align-items:center}
  .cycle-arrow{transform:rotate(90deg)}
  .hero-stats{gap:1.25rem}
  .comp-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">Realm Germany · Technische Tiefenschulung 2026</div>
  <h1>Der vollständige Aufbau<br>einer <span>R290 Wärmepumpe</span></h1>
  <p>Das ultimative Kompendium für Vertrieb und Technik – Von den thermodynamischen Grundlagen über hydraulische Systemarchitekturen bis zur DIN-konformen Inbetriebnahme.</p>
  <div class="hero-stats">
    <div class="hstat"><div class="val">9</div><div class="lbl">Module</div></div>
    <div class="hstat"><div class="val">R290</div><div class="lbl">Natürliches Propan</div></div>
    <div class="hstat"><div class="val">75°C</div><div class="lbl">Max. Vorlauf</div></div>
    <div class="hstat"><div class="val">–30°C</div><div class="lbl">Min. Außentemp.</div></div>
    <div class="hstat"><div class="val">SCOP 7.0</div><div class="lbl">Weltrekord-Effizienz</div></div>
  </div>
</div>

<!-- NAV -->
<div class="nav-wrap">
  <div class="nav-inner">
    <div class="nav-item active" onclick="goSec(0)">1 · Physik &amp; Prinzip</div>
    <div class="nav-item" onclick="goSec(1)">2 · Kältekreislauf</div>
    <div class="nav-item" onclick="goSec(2)">3 · Komponenten</div>
    <div class="nav-item" onclick="goSec(3)">4 · R290 Kältemittel</div>
    <div class="nav-item" onclick="goSec(4)">5 · Leistung &amp; SCOP</div>
    <div class="nav-item" onclick="goSec(5)">6 · Hydraulik &amp; Einbau</div>
    <div class="nav-item" onclick="goSec(6)">7 · Regelung &amp; Steuerung</div>
    <div class="nav-item" onclick="goSec(7)">8 · Wettbewerb</div>
    <div class="nav-item" onclick="goSec(8)">9 · Profi-Quiz (20 Q)</div>
  </div>
</div>

<div class="page">

<!-- ══════════════════════════════ SECTION 0 ══ -->
<div class="section active" id="sec0">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:11%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">⚡</span>Die Physik dahinter – Das thermodynamische Fundament</div>
    <p>Eine Luft-Wasser-Wärmepumpe erzeugt keine Wärme durch Widerstandsheizung, sondern fungiert als thermischer Transformator. Sie entzieht der Umgebungsluft (auch bei extremen Minusgraden) thermische Energie und hebt diese auf ein nutzbares Temperaturniveau für Heiz- und Trinkwarmwassersysteme (35 °C bis 75 °C) an.</p>

    <div class="hl"><strong>Das Kernprinzip: Latente Wärme &amp; Phasenumwandlung</strong><br>
    Der Prozess basiert auf der gezielten Manipulation des Siedepunkts eines Kältemittels. Durch Druckänderung wird erzwungen, dass das Kältemittel bei extrem niedrigen Temperaturen im Außenbereich verdampft (Energieaufnahme) und unter hohem Druck im Innenbereich kondensiert (Energieabgabe).</div>

    <h3>Der 2. Hauptsatz der Thermodynamik und der Energieerhaltungssatz</h3>
    <p>Laut dem 2. Hauptsatz der Thermodynamik fließt Wärme definitionsgemäß freiwillig nur vom höheren zum niedrigeren Energieniveau. Um diesen Prozess umzukehren, muss mechanische oder elektrische Arbeit ($W_{Strom}$) investiert werden. Die dem Heizsystem zugeführte Wärmemenge ($Q_{Wärme}$) ist die Summe aus der Umweltenergie ($Q_{Umwelt}$) und der elektrischen Antriebsleistung des Kompressors.</p>

    <div class="formula">
      <span class="fvar">Q_Wärme</span> <span class="fop">=</span> <span class="fvar">Q_Umwelt</span> <span class="fop">+</span> <span class="fvar">W_Strom</span><br>
      <span class="fval">7.0 kW</span> <span class="fop">=</span> <span class="fval">6.0 kW</span> <span class="fop">+</span> <span class="fval">1.0 kW</span><br>
      <span style="color:#94A3B8;font-size:11px">→ Entspricht einer Leistungszahl (COP) von 7.0 (Januar-Launch-Niveau)</span>
    </div>

    <h3>Das Carnot-Limit – Die absolute physikalische Grenze</h3>
    <p>Der maximale theoretisch erreichbare Wirkungsgrad eines thermodynamischen Kreisprozesses wird durch den Carnot-COP beschrieben. Er berechnet sich aus den absoluten Temperaturen im Kondensator und Verdampfer in Kelvin ($K = °C + 273.15$):</p>
    <div class="formula">
      <span class="fvar">COP_Carnot</span> <span class="fop">=</span> <span class="fvar">T_Kondensation</span> <span class="fop">/</span> <span class="fop">(</span><span class="fvar">T_Kondensation</span> <span class="fop">–</span> <span class="fvar">T_Verdampfung</span><span class="fop">)</span><br>
      <span style="color:#94A3B8;font-size:11px">Beispiel: Vorlauf 35 °C (Kondensation bei ~38 °C / 311 K) und Außenluft –7 °C (Verdampfung bei ~–12 °C / 261 K):</span><br>
      <span class="fvar">COP_Carnot</span> <span class="fop">=</span> <span class="fval">311 K</span> <span class="fop">/</span> <span class="fop">(</span><span class="fval">311 K</span> <span class="fop">–</span> <span class="fval">261 K</span><span class="fop">)</span> <span class="fop">=</span> <span class="fval">6.22</span><br>
      <span style="color:#94A3B8;font-size:11px">→ Die Realm Jan-2026 Modellreihe operiert dank minimaler interner Reibungsverluste bei über 90% der Carnot-Effizienz.</span>
    </div>

    <div class="hl-amber"><strong>Argumentations-Leitfaden für den Vertrieb:</strong><br>
    Sollte ein Fachpartner die Realisierbarkeit extrem hoher SCOP-Werte anzweifeln, verweisen Sie auf das Carnot-Limit. Durch den Einsatz stufenloser DC-Inverter und optimierter Strömungskanäle minimiert Realm die Exergieverluste (Strömungswiderstände, thermische Übergangsverluste) und nähert sich der physikalischen Grenze so dicht an wie kein anderer Marktteilnehmer.</div>

    <div class="stat-grid">
      <div class="stat"><div class="val">85%</div><div class="lbl">Max. Umweltenergie-Anteil</div></div>
      <div class="stat"><div class="val">15%</div><div class="lbl">Elektrischer Netzantrieb</div></div>
      <div class="stat"><div class="val">–30°C</div><div class="lbl">Kälte-Einsatzgrenze (TRUTH-Serie)</div></div>
      <div class="stat"><div class="val">75°C</div><div class="lbl">Max. Vorlauf per Wärmepumpe</div></div>
    </div>
  </div>

  <div class="card">
    <div class="card-title"><span class="ico">🌡️</span>Nomenklatur und thermodynamische Zustandsgrößen</div>
    <p>Für eine fachlich fundierte Kommunikation mit dem Fachhandwerk müssen die folgenden Fachbegriffe präzise beherrscht werden:</p>
    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Fachbegriff</th><th>Definition</th><th>Typischer Zielbereich</th><th>Auswirkung auf Systemeffizienz</th></tr></thead>
        <tbody>
          <tr><td><strong>Vorlauftemperatur (VL)</strong></td><td>Temperatur des Heizwassers beim Verlassen der Wärmepumpe zum Heizkreis.</td><td>35 °C (FBH) – 75 °C (Radiator)</td><td>Je niedriger die VL, desto geringer das Druckverhältnis im Kompressor, desto höher der COP.</td></tr>
          <tr><td><strong>Rücklauftemperatur (RL)</strong></td><td>Temperatur des Wassers nach dem Energiedurchlauf durch das Gebäude.</td><td>25 °C – 65 °C</td><td>Bestimmt in Kombination mit dem Volumenstrom die abgegebene Wärmeleistung.</td></tr>
          <tr><td><strong>Spreizung ($\Delta T$)</strong></td><td>Die absolute Differenz zwischen Vorlauf- und Rücklauftemperatur ($VL - RL$).</td><td>5 K bis 10 K</td><td>Wichtig für die Auslegung des Wärmetauschers und zur Verhinderung von laminaren Strömungszuständen.</td></tr>
          <tr><td><strong>Überhitzung (Superheat)</strong></td><td>Temperaturerhöhung des Kältemittelgases über seinen Siedepunkt hinaus am Verdampferausgang.</td><td>5 K bis 8 K</td><td>Garantiert, dass kein flüssiges Kältemittel in den Kompressor gelangt (Ausschluss von Flüssigkeitsschlägen).</td></tr>
          <tr><td><strong>Unterkühlung (Subcooling)</strong></td><td>Absenkung der Kältemitteltemperatur unter den Kondensationspunkt im flüssigen Zustand.</td><td>3 K bis 5 K</td><td>Maximiert das Enthalpiegefälle vor dem Expansionsventil und steigert die Kälteleistung.</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <div class="nav-btns">
    <div></div>
    <button class="btn btn-primary" onclick="goSec(1)">Weiter: Kältekreislauf →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 1 ══ -->
<div class="section" id="sec1">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:22%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🔄</span>Der geschlossene Kältekreislauf im h-log p-Diagramm</div>
    <p>Der Kältekreislauf basiert auf der kontinuierlichen Zustandsänderung des Kältemittels R290. Um den Heizvorgang lückenlos aufrechtzuerhalten, laufen vier thermodynamische Prozesse zyklisch ab.</p>

    <div class="diagram">
      <div class="cycle">
        <div class="cycle-step">
          <div class="cs-num">1</div>
          <div class="cs-icon">❄️</div>
          <div class="cs-title">Verdampfung</div>
          <div class="cs-temp">Niederdruck (~3-5 bar)</div>
          <div class="cs-desc">Aggregatzustand wechselt von flüssig zu gasförmig durch Umweltwärme.</div>
        </div>
        <div class="cycle-arrow">→</div>
        <div class="cycle-step">
          <div class="cs-num">2</div>
          <div class="cs-icon">⚡</div>
          <div class="cs-title">Kompression</div>
          <div class="cs-temp">Hochdruck (~18-26 bar)</div>
          <div class="cs-desc">Elektrische Kompression hebt Druck und Temperatur (Heißgas).</div>
        </div>
        <div class="cycle-arrow">→</div>
        <div class="cycle-step">
          <div class="cs-num">3</div>
          <div class="cs-icon">🔥</div>
          <div class="cs-title">Kondensation</div>
          <div class="cs-temp">Hochdruck (~18-26 bar)</div>
          <div class="cs-desc">Kältemittel verflüssigt sich und gibt latente Kondensationswärme an das Heizwasser ab.</div>
        </div>
        <div class="cycle-arrow">→</div>
        <div class="cycle-step">
          <div class="cs-num">4</div>
          <div class="cs-icon">💨</div>
          <div class="cs-title">Expansion</div>
          <div class="cs-temp">Druckabfall</div>
          <div class="cs-desc">Isenthalpe Druckabsenkung über das EEV führt zur schlagartigen Abkühlung.</div>
        </div>
        <div class="cycle-arrow">→ 1</div>
      </div>
    </div>

    <h3>Detaillierte Analyse der vier Prozessschritte</h3>
    
    <h4>Schritt 1: Isotherme/Isobare Verdampfung</h4>
    <p>Das flüssige, kalte Kältemittel strömt mit niedrigem Druck in den Verdampfer. Da die Außenlufttemperatur über der Siedetemperatur des Kältemittels liegt, findet ein intensiver Wärmeübergang statt. Das Kältemittel beginnt zu sieden. Am Ausgang des Verdampfers ist das Kältemittel zu 100% gasförmig und wird durch das elektronische Expansionsventil (EEV) gezielt um 5 bis 8 Kelvin überhitzt, um jeglichen Flüssigkeitsanteil zu eliminieren.</p>

    <h4>Schritt 2: Polytrope Kompression</h4>
    <p>Der Inverter-Doppelrotations-Kompressor saugt das überhitzte Kältemittelgas an. Unter Zufuhr elektrischer Energie wird das Gas komprimiert. Druck und Temperatur steigen simultan an. Das Kältemittel verlässt den Kompressor als sogenanntes „Heißgas“ bei Temperaturen von bis zu 95 °C.</p>

    <h4>Schritt 3: Isobare Kondensation</h4>
    <p>Das Heißgas strömt in den Verflüssiger (Kondensator). Hier kommt es in thermischen Kontakt mit dem kühleren Heizungsrücklaufwasser. Das Gas kühlt ab, erreicht den Kondensationspunkt und verflüssigt sich. Dabei wird die Phasenwechselenergie (latente Wärme) freigesetzt. Das Kältemittel verlässt den Kondensator als unterkühlte Flüssigkeit.</p>

    <h4>Schritt 4: Isenthalpe Expansion</h4>
    <p>Die flüssige Phase strömt durch das hochempfindliche, elektronische Expansionsventil. Der Strömungsquerschnitt wird stark verengt, wodurch der Kältemitteldruck schlagartig auf das Verdampfungsniveau abfällt. Dieser Prozess verläuft extrem schnell und ohne äußeren Wärmeaustausch (isenthalp). Das Kältemittel kühlt stark ab und tritt als Nassdampfgemisch erneut in den Verdampfer ein.</p>

    <h3>Die technologische Geheimwaffe: Der Economizer-Kreislauf (Enhanced Vapor Injection)</h3>
    <p>Bei extremen Außentemperaturen (z. B. –20 °C) sinkt die Dichte des Sauggases, wodurch die Heizleistung konventioneller Wärmepumpen einbricht. Realm TRUTH-Systeme nutzen daher einen integrierten **Flash-Tank-Economizer**:</p>
    <ul>
      <li>Ein Teilstrom des flüssigen Kältemittels wird nach dem Kondensator abgezweigt und in einem separaten Plattenwärmetauscher (Economizer) expandiert.</li>
      <li>Dieser Teilstrom kühlt das Hauptkältemittel weiter ab (Erhöhung der Unterkühlung = mehr Kälteleistung im Hauptprozess).</li>
      <li>Das dabei verdampfte Kältemittelgas wird über ein separates Mitteldruckventil direkt in die Zwischenstufe des Doppelrotationskompressors injiziert (Vapor Injection).</li>
      <li><strong>Der Effekt:</strong> Der Kompressor wird thermisch entlastet, die Heißgastemperatur sinkt und der Massenstrom steigt. Dies ermöglicht die Aufrechterhaltung einer Vorlauftemperatur von 75 °C selbst bei –25 °C arktischer Außentemperatur ohne elektrischen Heizstab.</li>
    </ul>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(0)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(2)">Weiter: Komponenten →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 2 ══ -->
<div class="section" id="sec2">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:33%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🔧</span>Die Komponentenarchitektur der Realm TRUTH-Serie</div>
    <p>Wärmepumpen-Effizienz ist das Resultat perfekt aufeinander abgestimmter Premium-Komponenten. Realm setzt kompromisslos auf Weltmarktführer, um Ausfallraten gen Null zu senken.</p>
  </div>

  <div class="comp-grid">
    <div class="comp-card">
      <div class="cc-icon">⚙️</div>
      <div class="cc-title">Verdichter (Kompressor)</div>
      <div class="cc-brand">Highly (Hitachi) / Mitsubishi</div>
      <div class="cc-desc">Hermetischer DC-Inverter-Doppelrotationsverdichter mit EVI-Zwischeneinspritzung. Frequenzbereich von 10 Hz bis 120 Hz stufenlos geregelt. Ausgelegt für 80.000 Betriebsstunden durch bürstenlose Permanentmagnet-Motoren.</div>
      <div class="cc-badge"><span class="badge bg">EVI Technologie</span></div>
    </div>
    <div class="comp-card">
      <div class="cc-icon">🔩</div>
      <div class="cc-title">Wärmetauscher</div>
      <div class="cc-brand">Alfa Laval / SWEP</div>
      <div class="cc-desc">Asymmetrisch gelötete Edelstahl-Plattenwärmetauscher. Die patentierte Kanalgeometrie minimiert den kältemittelseitigen Druckverlust und maximiert den turbulenten Strömungszustand für optimalen Wärmeübergang.</div>
      <div class="cc-badge"><span class="badge bb">Edelstahl AISI 316</span></div>
    </div>
    <div class="comp-card">
      <div class="cc-icon">🎛️</div>
      <div class="cc-title">Expansionsventil (EEV)</div>
      <div class="cc-brand">Danfoss ETS-Serie</div>
      <div class="cc-desc">Elektronisches Schrittmotorventil mit 480 Schritten Auflösung. Ermöglicht die hochpräzise Ausregelung der Überhitzung innerhalb von Millisekunden bei transienten Lastwechseln des Inverters.</div>
      <div class="cc-badge"><span class="badge go">Schrittmotorregelung</span></div>
    </div>
    <div class="comp-card">
      <div class="cc-icon">💨</div>
      <div class="cc-title">Axialventilator</div>
      <div class="cc-brand">EBM-Papst / Ziehl-Abegg</div>
      <div class="cc-desc">Bionisch geformte Ventilatorflügel (Eulenflügel-Design) mit hocheffizienten, bürstenlosen EC-Motoren. Drehzahlvariabler, extrem geräuscharmer Betrieb im Nachtmodus (unter 38 dB(A) in 3m Abstand).</div>
      <div class="cc-badge"><span class="badge bg">EC-Hocheffizienz</span></div>
    </div>
    <div class="comp-card">
      <div class="cc-icon">🔄</div>
      <div class="cc-title">Umwälzpumpe (Sekundär)</div>
      <div class="cc-brand">Wilo Para / Grundfos</div>
      <div class="cc-desc">Integrierte Hocheffizienz-Heizungspumpe mit PWM-Steuerungsschnittstelle. Passt den Volumenstrom adaptiv an die aktuelle Verflüssigerleistung an, um die Ziel-Spreizung konstant zu halten.</div>
      <div class="cc-badge"><span class="badge bb">PWM-gesteuert</span></div>
    </div>
    <div class="comp-card">
      <div class="cc-icon">🛡️</div>
      <div class="cc-title">4-Wege-Umschaltventil</div>
      <div class="cc-brand">Sanhua / Errecom</div>
      <div class="cc-desc">Elektromagnetisches Reversierventil zur zyklischen Umkehr des Kältekreislaufs. Verantwortlich für den aktiven Kühlbetrieb im Sommer sowie die schnelle, prozesssichere Heißgas-Abtauung im Winter.</div>
      <div class="cc-badge"><span class="badge ba">Reversibel</span></div>
    </div>
  </div>

  <div class="card">
    <div class="card-title"><span class="ico">🏗️</span>Gehäusegeometrie &amp; Strömungsmechanik der Abtauung</div>
    <p>Der Außen-Lamellenwärmetauscher ist mit einer hydrophoben **Blue-Fin-Beschichtung** versehen. Diese Beschichtung verhindert, dass Kondensat dauerhaft auf den Lamellen haftet, was das Vereisungsrisiko im Temperaturbereich zwischen –2 °C und +5 °C drastisch reduziert.</p>

    <div class="hl-blue"><strong>Das adaptive Abtauverfahren (Smart Defrosting):</strong><br>
    Konventionelle Wärmepumpen tauen starr nach Zeitintervallen ab, was enorme Energiemengen vernichtet. Realm misst permanent die Temperaturdifferenz ($\Delta T$) zwischen den Lamellen und der Außenluft sowie den Druckverlust des Luftstroms. Erst wenn eine reale Leistungsminderung durch Eisbildung detektiert wird, schaltet das 4-Wege-Ventil für 3 bis 5 Minuten um. Heißgase strömen direkt in den Verdampfer – das Eis schmilzt energieeffizient ab.</div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(1)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(3)">Weiter: R290 Kältemittel →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 3 ══ -->
<div class="section" id="sec3">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:44%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🌿</span>R290 (Propan) – Das zukunftssichere Kältemittel</div>
    <p>Durch die verschärfte europäische F-Gas-Verordnung (Revision 2024) unterliegen synthetische Kältemittel (HFKW) einer harten Kontingentierung und schrittweisen Verboten. R32 und R410A werden durch drastische Verknappung extrem teuer und in Neuanlagen verboten. R290 (reines Propan) ist als natürlicher Kohlenwasserstoff die langfristige Lösung.</p>

    <h3>Umweltkennzahlen und thermodynamischer Direktvergleich</h3>
    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Parameter</th><th>R290 (Propan)</th><th>R32</th><th>R410A (Auslaufend)</th></tr></thead>
        <tbody>
          <tr><td><strong>GWP (Global Warming Potential)</strong></td><td><span class="badge bg">3</span></td><td><span class="badge ba">675</span></td><td><span class="badge br">2088</span></td></tr>
          <tr><td><strong>ODP (Ozonabbaupotenzial)</strong></td><td>0</td><td>0</td><td>0</td></tr>
          <tr><td><strong>Kritischer Druck</strong></td><td>42.5 bar</td><td>57.8 bar</td><td>49.0 bar</td></tr>
          <tr><td><strong>Sicherheitsklassifikation (ISO 817)</strong></td><td><span class="badge br">A3 (Hochgradig entzündlich)</span></td><td><span class="badge ba">A2L (Schwer entzündlich)</span></td><td><span class="badge bg">A1 (Nicht entzündlich)</span></td></tr>
          <tr><td><strong>Spezifische Kälteleistung</strong></td><td>Sehr hoch ($~3.4$ kJ/kg)</td><td>Mittel</td><td>Niedrig</td></tr>
        </tbody>
      </table>
    </div>

    <h3>Sicherheitskonzept und ATEX-Konformität (DIN EN 378)</h3>
    <p>Aufgrund der Einstufung in die Sicherheitsklasse A3 müssen bei der Konstruktion und Installation einer R290-Wärmepumpe strenge Explosionsschutzmaßnahmen eingehalten werden. Die untere Explosionsgrenze (UEG) von Propan liegt bei 2.1 Vol.-% in der Raumluft (ca. 39 g/$m^3$).</p>
    
    <div class="hl-red"><strong>Das 4-Stufen-Sicherheitskonzept von Realm:</strong><br>
    1. **Hermetischer Kältekreis:** Alle Lötverbindungen werden automatisiert unter Schutzgas ausgeführt. Es gibt keine mechanischen Schraubverbindungen im kältemittelführenden Außenkreis.<br>
    2. **Zündquellenfreiheit (ATEX):** Alle elektrischen Komponenten im Gehäuse (Relais, Schütze, Inverter-Platinen) sind gekapselt ausgeführt (Schutzart IP54 / Ex-d) und räumlich komplett vom Kältekreis getrennt.<br>
    3. **Schwere-Kompensation:** Da Propan schwerer als Luft ist und zu Boden sinkt, besitzt das Realm-Gehäuse eine bodenseitige Entlüftungsöffnung, die ein Ansammlungsverfahren im Gehäuse unmöglich macht.<br>
    4. **Sicherheitsbereich (Schutzzone):** Bei der Außenaufstellung ist darauf zu achten, dass sich im Umkreis von 1.0 Meter um das Gerät keine Kellerfenster, Lichtschächte, Türen oder Gullys befinden.</p></div>

    <h3>Rechtliche Rahmenbedingungen: Sachkundenachweis Pflicht</h3>
    <p>Der Gesetzgeber schreibt im Rahmen der Chemikalien-Klimaschutzverordnung (§ 5 ChemKlimaschutzV) zwingend vor, dass Arbeiten an R290-Wärmepumpen nur von Technikern mit einem gültigen **Sachkundenachweis der Kategorie I** durchgeführt werden dürfen. Zudem greift bei gewerblichen Installationen die Betriebssicherheitsverordnung (BetrSichV) bezüglich des Explosionsschutzes.</p>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(2)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(4)">Weiter: Leistung &amp; SCOP →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 4 ══ -->
<div class="section" id="sec4">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:55%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">📊</span>Leistungskennzahlen, Modulationsbreite und Heizlasten</div>
    
    <h3>Der feine Unterschied: COP vs. SCOP (DIN EN 14825)</h3>
    <p>Der **COP (Coefficient of Performance)** stellt lediglich eine Momentaufnahme unter Laborbedingungen dar (z. B. A7/W35 = Außenluft 7 °C, Vorlauf 35 °C). Aussagekräftig für die realen Jahresheizkosten ist ausschließlich der **SCOP (Seasonal COP)**. Hierzu wird das Jahr in Temperaturschritte (Bins) unterteilt und die Effizienz basierend auf dem Klimaprofil für Mitteleuropa gewichtet.</p>

    <h3>Der Quantensprung: Die SCOP 7.0 Technologie (Januar-Launch 2026)</h3>
    <p>Realm bricht im Januar 2026 die magische Grenze der Energieeffizienz. Während der aktuelle Marktdurchschnitt bei einem SCOP von 4.5 bis 5.0 stagniert, erreicht die neue Realm-Generation durch die Kombination aus EVI-Zweistufenverdichtung und subkritischer Wärmetauscher-Optimierung einen **SCOP von 7.0**.</p>

    <div style="padding:1rem 0">
      <h4>Marktübersicht SCOP-Effizienzwerte (A7/W35)</h4>
      <div class="scoprow"><span class="slabel">🏆 Realm (Jan-2026)</span><div class="sbar scop-realm" style="width:290px">SCOP 7.0</div></div>
      <div class="scoprow"><span class="slabel">Lambda EU13L</span><div class="sbar scop-comp" style="width:210px">SCOP 5.0</div></div>
      <div class="scoprow"><span class="slabel">Viessmann Vitocal 250</span><div class="sbar scop-comp" style="width:200px">SCOP 4.8</div></div>
      <div class="scoprow"><span class="slabel">Vaillant aroTHERM</span><div class="sbar scop-comp" style="width:195px">SCOP 4.7</div></div>
      <div class="scoprow"><span class="slabel">Bosch Compress 5800</span><div class="sbar scop-comp2" style="width:180px">SCOP 4.3</div></div>
    </div>

    <h3>Modulationsdynamik der Realm TRUTH-Reihe</h3>
    <p>Ein massiver Konstruktionsfehler billiger On/Off-Wärmepumpen ist das konstante Ein- und Ausschalten (Takten). Jedes Takten erzeugt extrem hohe mechanische Lasten und mindert die Effizienz durch dynamische Anlaufverluste. Realm TRUTH-Systeme besitzen eine Modulationsbreite von bis zu **15% bis 100%**.</p>

    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Modellbezeichnung</th><th>Nennleistung (A7/W35)</th><th>Maximalleistung (A–7/W55)</th><th>Modulationsbereich Hz</th></tr></thead>
        <tbody>
          <tr><td>RMAW-03ZR1-V</td><td>3.0 kW</td><td>12.0 kW</td><td>15 – 90 Hz</td></tr>
          <tr><td>RMAW-04ZR3-V</td><td>4.6 kW</td><td>20.5 kW</td><td>12 – 110 Hz</td></tr>
          <tr><td>RMAW-06ZR1-V</td><td>5.5 kW</td><td>22.5 kW</td><td>10 – 120 Hz</td></tr>
        </tbody>
      </table>
    </div>

    <h3>Heizlastberechnung nach DIN EN 12831</h3>
    <p>Die exakte Auslegung erfolgt über die raumweise Heizlastberechnung. Als Faustformel für den schnellen vertrieblichen Überschlag gilt:</p>
    <div class="formula">
      <span class="fvar">Heizlast [kW]</span> <span class="fop">=</span> <span class="fop">(</span><span class="fvar">Wohnfläche [m²]</span> <span class="fop">×</span> <span class="fvar">spez. Wärmebedarf [W/m²]</span><span class="fop">)</span> <span class="fop">/</span> <span class="fval">1000</span><br>
      <span style="color:#94A3B8">Spezifische Richtwerte: Altbau unrenoviert: 100-120 W/m² | Altbau teil-saniert: 60-80 W/m² | Neubau KFW55: 25-35 W/m²</span>
    </div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(3)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(5)">Weiter: Hydraulik &amp; Einbau →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 5 ══ -->
<div class="section" id="sec5">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:66%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">💧</span>Systemhydraulik, Wärmeabgabe und Sicherheitsorganschaften</div>
    <p>Das Kältemittel verbleibt zu 100% im hermetisch dichten Außengerät (Monoblock-Bauweise). Die Energieübertragung ins Gebäude erfolgt rein hydraulisch über frostsichere, gedämmte Fernwärmerohre.</p>

    <h3>Wärmeabgabetypen im hocheffizienten Abgleich</h3>
    <p>Für den wirtschaftlichen Betrieb einer Wärmepumpe ist das nachgeschaltete Wärmeabgabesystem kritisch. Die Faustformel lautet: **Pro Kelvin Absenkung der Vorlauftemperatur steigt die Effizienz (COP) der Wärmepumpe um ca. 2.5%**.</p>

    <div class="vs-grid">
      <div class="vs-card vs-realm">
        <h4>Flächenheizung (FBH / Wand / Decke)</h4>
        <p>Systemtemperaturen: **30 °C bis 35 °C**</p>
        <ul>
          <li>Maximaler COP durch minimalen Temperaturhub</li>
          <li>Große Strahlungsfläche ermöglicht niedrigste VL</li>
          <li>Ideal für den autarken Monovalent-Betrieb</li>
        </ul>
      </div>
      <div class="vs-card vs-comp">
        <h4>Radiatoren (Bestands-Gliederheizkörper)</h4>
        <p>Systemtemperaturen: **55 °C bis 65 °C**</p>
        <ul>
          <li>Geringere Log-Effizienz durch hohen Temperaturhub</li>
          <li>Erfordert präzisen hydraulischen Abgleich</li>
          <li>Dank Realm 75 °C Option ohne Heizkörpertausch möglich</li>
        </ul>
      </div>
    </div>

    <h3>Trinkwarmwasserhydraulik &amp; Legionellenprophylaxe nach DVGW W551</h3>
    <p>Die Speicherung von Trinkwarmwasser birgt bei falscher Temperaturführung akute mikrobiologische Risiken (Legionella pneumophila). Die Arbeitsblatt-Richtlinie DVGW W551 schreibt vor, dass das Warmwasservolumen im Großanlagenbetrieb auf mindestens 60 °C erwärmt werden muss.</p>
    
    <div class="hl-amber"><strong>Der Realm-Vorteil beim Warmwasser:</strong><br>
    Herkömmliche Wärmepumpen (R32) schaffen systembedingt oft nur 55 °C im reinen Kältekreisbetrieb und müssen für die wöchentliche thermische Desinfektion den COP-unwirtschaftlichen elektrischen Heizstab (COP 1.0) zuschalten. Die Realm TRUTH-Serie fährt die **75 °C Vorlauftemperatur rein verdichterbasiert über den R290-Kreislauf**. Das spart massiv Strom und garantiert absolute Keimfreiheit nach DIN-Standard.</div>

    <h3>Sicherheitstechnische Notwendigkeit: Frostschutz &amp; Mindestvolumenstrom</h3>
    <p>Da der Heizungskreis direkt nach draußen geführt wird, besteht bei Stromausfall im Winter akute Einfriergefahr. Dem Heizungswasser ist daher ein Glykolgemisch (z.B. **Tyfocor L**, Propylenglykol) mit einem Frostschutzanteil von mindestens 25% (Sicherheit bis –15 °C) beizumischen.</p>
    <p>Zudem erfordert die Abtaufunktion ein schlagartig verfügbares Abtauvolumen. Ist dieses durch schließende Thermostatventile im Haus blockiert, bricht das System mit der Fehlermeldung „Mindestvolumenstrom unterschritten“ ab. Die Integration eines **Reihen- oder Trennpufferspeichers (mindestens 100-200 Liter)** löst dieses Problem prozesssicher.</p>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(4)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(6)">Weiter: Regelung &amp; Steuerung →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 6 ══ -->
<div class="section" id="sec6">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:77%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🧠</span>MSR-Technik, Heizkurven-Mathematik und Smart-Grid</div>
    <p>Die Regelungsplatine der Realm TRUTH-Serie steuert sämtliche Aktoren im Kältekreis über prädiktive Algorithmen.</p>

    <h3>Die Heizkurve – Das mathematische Herzstück</h3>
    <p>Die Steuerung errechnet die Soll-Vorlauftemperatur permanent in Abhängigkeit von der gedämpften Außentemperatur. Die Heizkurve wird über zwei Parameter definiert: **Steilheit (Neigung)** und **Parallelverschiebung (Niveau)**.</p>
    <div class="formula">
      <span class="fvar">T_Vorlauf_Soll</span> <span class="fop">=</span> <span class="fvar">T_Raum_Soll</span> <span class="fop">+</span> <span class="fvar">Steilheit</span> <span class="fop">×</span> <span class="fop">(</span><span class="fvar">T_Raum_Soll</span> <span class="fop">–</span> <span class="fvar">T_Außen</span><span class="fop">)</span><br>
      <span style="color:#94A3B8">Beispiel bei Steilheit 0.6, Raum-Soll 20 °C, Außentemperatur –10 °C:</span><br>
      <span class="fvar">T_Vorlauf_Soll</span> <span class="fop">=</span> <span class="fval">20</span> <span class="fop">+</span> <span class="fval">0.6</span> <span class="fop">×</span> <span class="fop">(</span><span class="fval">20</span> <span class="fop">–</span> <span class="fop">(</span><span class="fval">–10</span><span class="fop">)</span><span class="fop">)</span> <span class="fop">=</span> <span class="fval">38 °C</span>
    </div>

    <h3>SG-Ready Schnittstelle (Smart Grid Standard)</h3>
    <p>Zur netzdienlichen Steuerung und PV-Eigenverbrauchsoptimierung verfügt Realm über eine integrierte **SG-Ready-Schnittstelle**. Über zwei potenzialfreie Kontakte schaltet der Netzbetreiber oder der PV-Wechselrichter vier definierte Betriebszustände:</p>
    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Zustand</th><th>Eingang 1 / Eingang 2</th><th>Systemverhalten der Realm TRUTH</th></tr></thead>
        <tbody>
          <tr><td><strong>Zustand 1</strong></td><td>0 / 0 (Offen / Offen)</td><td>**EVU-Sperre:** Der Netzbetreiber schaltet den Kompressor temporär ab (max. 2h in Spitzenlastzeiten).</td></tr>
          <tr><td><strong>Zustand 2</strong></td><td>1 / 0 (Geschlossen / Offen)</td><td>**Normalbetrieb:** Das System arbeitet hocheffizient exakt nach der eingestellten Heizkurve.</td></tr>
          <tr><td><strong>Zustand 3</strong></td><td>0 / 1 (Offen / Geschlossen)</td><td>**Verstärkter Betrieb (Einschaltbefehl):** Vorlauf-Soll wird um z. B. 5 K angehoben, um PV-Überschuss thermisch im Estrich zu speichern.</td></tr>
          <tr><td><strong>Zustand 4</strong></td><td>1 / 1 (Geschlossen / Geschlossen)</td><td>**Maximaler Anlaufbefehl:** Die Wärmepumpe fährt mit maximaler Frequenz, um Pufferspeicher und Warmwasser vollzuladen.</td></tr>
        </tbody>
      </table>
    </div>

    <h3>Schnittstellen und Konnektivität</h3>
    <p>Realm-Anlagen sind nativ offen für moderne Smart-Home-Protokolle. Ein **Modbus-RTU (RS485)**-Anschluss gehört zum Standard-Lieferumfang. Damit kann jeder Gebäudeautomatisierer sämtliche Register (Temperaturen, Drücke, Inverterfrequenz, Störmeldungen) auslesen und Sollwerte via Gebäudeleittechnik (GLT) überschreiben.</p>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(5)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(7)">Weiter: Wettbewerb →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 7 ══ -->
<div class="section" id="sec7">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:88%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">⚔️</span>Der wettbewerbliche Tiefenvergleich</div>
    <p>Der Wärmepumpenmarkt ist hart umkämpft. Hier erfahren Sie, wie Sie asiatische Billigimporte und überteuerte europäische Platzhirsche im technischen Verkaufsgespräch schlagen.</p>

    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Technische Metrik</th><th>Realm TRUTH (Pro)</th><th>Viessmann Vitocal 250-A</th><th>Lambda EU13L</th><th>LG Therma V R32</th></tr></thead>
        <tbody>
          <tr><td><strong>Kältemittel / GWP</strong></td><td><span class="badge bg">R290 / GWP 3</span></td><td>R290 / GWP 3</td><td>R290 / GWP 3</td><td><span class="badge br">R32 / GWP 675</span></td></tr>
          <tr><td><strong>Max. Vorlauftemperatur</strong></td><td><span class="badge bg">75 °C (reiner Kältekreis)</span></td><td>70 °C</td><td>70 °C</td><td><span class="badge br">65 °C</span></td></tr>
          <tr><td><strong>Einsatzgrenze Außen</strong></td><td><span class="badge bg">–30 °C</span></td><td>–20 °C</td><td>–22 °C</td><td>–25 °C</td></tr>
          <tr><td><strong>Kompressor-EVI</strong></td><td><span class="badge bg">Ja (Zweistufiger Flash-Tank)</span></td><td>Nein</td><td>Ja</td><td>Nein</td></tr>
          <tr><td><strong>SCOP (Jan-2026er Launch)</strong></td><td><span class="badge bg">7.0</span></td><td>5.0</td><td>5.0</td><td>4.5</td></tr>
          <tr><td><strong>Ersatzteilgarantie</strong></td><td><span class="badge bg">Iron Stock (24h Express)</span></td><td>Normaler Werksdienst</td><td>Lange Lieferzeiten</td><td>Aus Fernost (Wochen)</td></tr>
        </tbody>
      </table>
    </div>

    <h3>Umgang mit kritischen Kundeneinwänden (Objection Handling)</h3>
    
    <div class="acc-item">
      <div class="acc-hd" onclick="accToggle(this)">
        <span>Einwand: „Ein asiatischer Großkonzern wie LG ist doch sicherer als Realm.“</span>
        <span class="acc-ico">▼</span>
      </div>
      <div class="acc-body">
        <p><strong>Faktenbasierte Verkaufsantwort:</strong></p>
        <p>„LG verbaut in vielen Bestandsmodellen noch das synthetische Kältemittel R32. Dieses unterliegt den harten Quotierungsverboten der EU-F-Gas-Verordnung. Wer heute R32 kauft, investiert in eine auslaufende Technologie mit unkalkulierbaren Wartungskosten bei Kältemittelleckagen.</p>
        <p>Zudem vertreibt LG reine Hardware über den Großhandel. Realm hingegen bietet ein geschlossenes Ökosystem: Gebietsschutz für Sie als Installationsbetrieb, exklusive Endkunden-Leads und eine 24-Stunden-Ersatzteilgarantie direkt über unser Zentrallager in Nürnberg (Iron Stock).“</p>
      </div>
    </div>

    <div class="acc-item">
      <div class="acc-hd" onclick="accToggle(this)">
        <span>Einwand: „Die Lambda-Wärmepumpe hat laut Prüfberichten Spitzenwerte bei der Effizienz.“</span>
        <span class="acc-ico">▼</span>
      </div>
      <div class="acc-body">
        <p><strong>Faktenbasierte Verkaufsantwort:</strong></p>
        <p>„Lambda baut exzellente Geräte mit einem SCOP von knapp 5.0. Das erkennen wir absolut an. Allerdings betragen die Lieferzeiten bei Lambda aktuell oft 9 bis 12 Monate. Das blockiert Ihren Cashflow und verärgert Ihre Kunden.</p>
        <p>Realm ist sofort lieferbar. Und mit unserem Januar-2026-Launch brechen wir mit einem verifizierten **SCOP von 7.0** die absolute Marktführerschaft. Wir bieten Ihnen also eine bessere Effizienz bei einem Bruchteil der Anschaffungskosten und sofortiger Verfügbarkeit.“</p>
      </div>
    </div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(6)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(8)">Weiter: Profi-Quiz →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 8 ══ -->
<div class="section" id="sec8">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:100%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🏆</span>Zertifizierungs-Prüfung – Level: Kälte-Anlagenbauer</div>
    <p>20 hochkomplexe, praxisnahe Fachfragen. Um die Zertifizierung erfolgreich abzuschließen, müssen mindestens **16 von 20 Fragen (80%)** korrekt beantwortet werden.</p>
  </div>

  <div class="quiz-box">
    <h3>🔧 Technische Tiefenschulung – Abschlussprüfung</h3>
    <div class="qsub">Realm Zertifikat R290 · 20 Fachfragen</div>

    <!-- NAMENS-EINGABE -->
    <div class="name-row">
      <label for="qename">👤 Absolvent Name:</label>
      <input type="text" id="qename" placeholder="Vor- und Nachname eingeben (Pflichtfeld) …" />
    </div>

    <!-- QUESTION 1 -->
    <div class="qitem" data-qidx="1" data-correct="b">
      <div class="qt">1. Was passiert physikalisch im Kompressor, wenn die Überhitzung (Superheat) am Verdampferausgang dauerhaft unter 3 K absinkt?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der Wirkungsgrad (COP) steigt exponentiell an.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Flüssiges Kältemittel gelangt in den Verdichterraum und zerstört die mechanischen Scroll-Flanken durch einen Flüssigkeitsschlag.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der Hochdruckpressostat löst sofort aus, da die Dichte des Nassdampfs zu hoch ist.</button>
      <div class="qfb ok">✓ Korrekt! Flüssigkeit ist inkompressibel. Gelangt sie in den Verdichter, führt dies zur sofortigen Zerstörung der mechanischen Komponenten (Flüssigkeitsschlag).</div>
      <div class="qfb err">✗ Falsch! Flüssigkeitsschlag ist das Resultat. Gase müssen komplett überhitzt sein (5-8 K), um den Kompressor zu schützen.</div>
    </div>

    <!-- QUESTION 2 -->
    <div class="qitem" data-qidx="2" data-correct="a">
      <div class="qt">2. Das Carnot-Limit errechnet für die Systempunkte A–7/W35 einen theoretischen Maximal-COP von 6.22. Warum ist die Angabe des Realm-Januar-Launches mit einem SCOP von 7.0 physikalisch kein Widerspruch?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil der SCOP ein gewichteter Jahresmittelwert über verschiedene Bins (Temperaturschritte) ist und nicht starr dem Extrempunkt bei –7 °C entspricht.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil R290 durch die EVI-Einspritzung das Carnot-Limit mathematisch außer Kraft setzt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der SCOP wird ohne Einbeziehung der Kelvin-Skala berechnet, weshalb die Werte abweichen.</button>
      <div class="qfb ok">✓ Korrekt! Der SCOP gewichtet das gesamte Jahr. Wärmere Tage im Frühling/Herbst ziehen den Schnitt massiv nach oben.</div>
      <div class="qfb err">✗ Falsch! Das Carnot-Limit gilt für jeden Punkt separat. Der SCOP ist ein Jahresdurchschnittswert über alle Bins.</div>
    </div>

    <!-- QUESTION 3 -->
    <div class="qitem" data-qidx="3" data-correct="b">
      <div class="qt">3. Warum schreibt die VDE 0100-410 beim Anschluss einer Inverter-Wärmepumpe zwingend einen Fehlerstrom-Schutzschalter (FI) vom Typ B (allstromsensitiv) vor?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil der Typ B für höhere Ströme über 400V ausgelegt ist.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil der Frequenzumrichter des Inverters glatte Gleichfehlerströme erzeugen kann, die einen Standard-Typ-A-FI magnetisch sättigen und somit wirkungslos machen würden.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil Typ B den Einschaltstrom des Ventilators besser toleriert.</button>
      <div class="qfb ok">✓ Korrekt! Nur allstromsensitive FIs vom Typ B erkennen glatte Gleichfehlerströme, die durch die Frequenzumrichtung entstehen können.</div>
      <div class="qfb err">✗ Falsch! Typ-A-FIs erblinden bei Gleichfehlerströmen. Typ B ist normativ zwingend vorgeschrieben.</div>
    </div>

    <!-- QUESTION 4 -->
    <div class="qitem" data-qidx="4" data-correct="c">
      <div class="qt">4. Eine Heizlastberechnung nach DIN EN 12831 ergibt für ein Objekt eine Gesamtheizlast von 21.6 kW bei der Normaußentemperatur. Welches Realm TRUTH-Modell deckt diese Last ohne monoenergetischen Heizstabeinsatz ab?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>RMAW-03ZR1-V (Nennleistung 3.0 kW)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>RMAW-04ZR3-V (Nennleistung 4.6 kW)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>RMAW-06ZR1-V (Maximalleistung 22.5 kW)</button>
      <div class="qfb ok">✓ Korrekt! Ausgelegt wird immer auf die Maximalleistung beim Normpunkt, welche beim 06er-Modell exakt bei 22.5 kW liegt.</div>
      <div class="qfb err">✗ Falsch! Die kleineren Modelle brechen in der Maximalleistung zu früh ein und würden den Heizstab anfordern.</div>
    </div>

    <!-- QUESTION 5 -->
    <div class="qitem" data-qidx="5" data-correct="b">
      <div class="qt">5. Welcher verfahrenstechnische Regelmechanismus der Realm TRUTH-Serie verhindert effektiv das schädliche „Takten“ des Kompressors?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die automatische Heißgas-Bypass-Regelung.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die stufenlose Inverter-Modulation von 10 Hz bis 120 Hz, die die Verdichterdrehzahl exakt dem aktuellen Modulationsbedarf anpasst.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die zeitgesteuerte Sperre von 10 Minuten nach jedem Abschaltvorgang.</button>
      <div class="qfb ok">✓ Korrekt! Durch die stufenlose Frequenzmodulation läuft der Kompressor stundenlang im energetisch optimalen Teillastbereich durch.</div>
      <div class="qfb err">✗ Falsch! Modulation statt simpler Ein/Aus-Schaltung ist die technologische Lösung gegen Taktschäden.</div>
    </div>

    <!-- QUESTION 6 -->
    <div class="qitem" data-qidx="6" data-correct="a">
      <div class="qt">6. Warum erzielen R290-Systeme mühelos 75 °C Vorlauftemperatur im reinen Kältekreisbetrieb, während R32-Anlagen konstruktiv meist bei 65 °C abgeregelt werden?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil R290 eine flachere Dampfdruckkurve aufweist; bei hohen Kondensationstemperaturen bleibt der Druck bei moderaten ~25 bar, während R32 die mechanische 40-bar-Grenze sprengt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil R290 eine höhere Dichte im gasförmigen Zustand besitzt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil R32-Kompressoren thermisch durch die POE-Öl-Zersetzung limitiert sind.</button>
      <div class="qfb ok">✓ Korrekt! Die thermodynamische Dampfdruckkurve von Propan erlaubt extrem hohe Temperaturen bei beherrschbaren Gehäusedrücken.</div>
      <div class="qfb err">✗ Falsch! Der Druck ist der limitierende Faktor. R32 fordert bei 65 °C bereits extreme Drücke, die Bauteile massiv belasten.</div>
    </div>

    <!-- QUESTION 7 -->
    <div class="qitem" data-qidx="7" data-correct="c">
      <div class="qt">7. Welche Aufgabe übernimmt der Flash-Tank-Economizer bei arktischen Außentemperaturen von –20 °C?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er fängt flüssiges Kältemittel ab und schützt den Verdampfer vor dem Einfrieren.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er führt dem Heizungswasser direkt elektrische Zusatzenergie zu.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er injiziert expandiertes Mitteldruckgas direkt in den Scroll-Verdichterraum, erhöht den Massenstrom und kühlt zeitgleich den Kompressor herunter.</button>
      <div class="qfb ok">✓ Korrekt! Die Enhanced Vapor Injection (EVI) sichert die hohe Heizleistung bei tiefen Minustemperaturen.</div>
      <div class="qfb err">✗ Falsch! Der Flash-Tank dient der Zwischeneinspritzung (Vapor Injection) zur Leistungssteigerung bei Extremkälte.</div>
    </div>

    <!-- QUESTION 8 -->
    <div class="qitem" data-qidx="8" data-correct="b">
      <div class="qt">8. Ein hydraulisches Phänomen im Altbau: Einzelne Räume werden überhitzt, weit entfernte Heizkörper bleiben kalt. Welche Maßnahme ist nach VRE/BAFA-Richtlinie zwingend nachzuweisen?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Erhöhung der Heizkreispumpenleistung auf Stufe 3.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der hydraulische Abgleich aller Verbraucherkreise zur Gewährleistung des exakten Nennvolumenstroms.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Installation größerer Überströmventile am Verteilerbalken.</button>
      <div class="qfb ok">✓ Korrekt! Der hydraulische Abgleich berechnet die Widerstände, sodass jeder Heizkörper exakt die benötigte Wassermenge erhält.</div>
      <div class="qfb err">✗ Falsch! Ohne hydraulischen Abgleich kollabiert die Effizienz der Wärmepumpe durch unkontrollierte Rücklauftemperaturen.</div>
    </div>

    <!-- QUESTION 9 -->
    <div class="qitem" data-qidx="9" data-correct="a">
      <div class="qt">9. Wie vollzieht das Realm TRUTH-System den energieeffizienten Abtaubetrieb bei zyklischer Reifbildung am Außenwärmetauscher?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Durch Prozessumkehr via 4-Wege-Ventil: Heißgas strömt direkt in den Außenverdampfer und schmilzt das Eis in wenigen Minuten ab.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Durch das Einschalten einer elektrischen Begleitheizung im Kondensatwannenbereich.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Durch Abschalten des Kompressors und reines Weiterlaufen des Axialventilators.</button>
      <div class="qfb ok">✓ Korrekt! Die Heißgas-Abtauung mittels Kreislaufumkehr nutzt die thermische Energie aus dem Heiznetz zur schnellen Enteisung.</div>
      <div class="qfb err">✗ Falsch! Realm nutzt die schnelle, hocheffiziente Heißgas-Abtauung durch temporäre Kältekreis-Invertierung.</div>
    </div>

    <!-- QUESTION 10 -->
    <div class="qitem" data-qidx="10" data-correct="c">
      <div class="qt">10. Bei einer Verdampfungstemperatur von –10 °C im R290-Kreislauf: Welcher ungefähre Saugdruck (Niederdruckseite) liegt laut Dampftabelle an?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>~ 1.2 bar (Absolutdruck)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>~ 12.5 bar (Überdruck)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>~ 4.7 bar (Absolutdruck)</button>
      <div class="qfb ok">✓ Korrekt! Propan hat bei –10 °C einen materialschonenden Saugdruck von rund 4.7 bar, was Lufteinträge durch Unterdruck wirksam ausschließt.</div>
      <div class="qfb err">✗ Falsch! Schlag nach im h-log-p-Diagramm für R290. Bei –10 °C liegt der Dampfdruck nahe bei 4.7 bar.</div>
    </div>

    <!-- QUESTION 11 -->
    <div class="qitem" data-qidx="11" data-correct="b">
      <div class="qt">11. Welche normative Vorgabe nach DIN EN 378 muss bezüglich Schutzzonen bei der Aufstellung einer Propan-Monoblock-Wärmepumpe im Außenbereich zwingend berücksichtigt werden?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Gerät muss mindestens 5 Meter von der Grundstücksgrenze entfernt stehen.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Im Schutzzonenbereich (1m Radius um das Gerät) dürfen sich keine Zündquellen sowie Öffnungen zu tiefer liegenden Räumen (Kellerfenster, Gullys, Lichtschächte) befinden.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Fundament muss zwingend mit einer ex-geschützten Auffangwanne für flüssiges Propan versehen sein.</button>
      <div class="qfb ok">✓ Korrekt! Da Propan schwerer als Luft ist, könnte es sich im Leckagefall in Vertiefungen oder Kellerräumen sammeln und ein zündfähiges Gemisch bilden.</div>
      <div class="qfb err">✗ Falsch! Kellerfenster und Gullys sind im direkten Umkreis verboten, da austretendes R290 nach unten sinkt.</div>
    </div>

    <!-- QUESTION 12 -->
    <div class="qitem" data-qidx="12" data-correct="a">
      <div class="qt">12. Welche Konsequenz ergibt sich für die Systemleistung, wenn die Spreizung ($\Delta T$) im Sekundärkreis durch eine extrem überdimensionierte Heizungspumpe von 7 K auf 2 K abfällt?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der Volumenstrom wird unnötig hoch, die Strömungen werden turbulent und der Pumpenstromverbrauch explodiert, während der Wärmeübergang im Kondensator kollabiert.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der COP verbessert sich, da das Kältemittel tiefer unterkühlt wird.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Es hat keinerlei Auswirkungen, da die Leistungsabgabe rein mathematisch konstant bleibt.</button>
      <div class="qfb ok">✓ Korrekt! Eine zu geringe Spreizung deutet auf ein hydraulisches Ungleichgewicht oder Kurzschlussströmungen hin – die Energie kann nicht effizient abgegeben werden.</div>
      <div class="qfb err">✗ Falsch! Zu geringe Spreizung treibt den Pumpenstrom hoch und ruiniert die Schichtung im Pufferspeicher.</div>
    </div>

    <!-- QUESTION 13 -->
    <div class="qitem" data-qidx="13" data-correct="b">
      <div class="qt">13. Was misst die standardisierte Prüfnorm DIN EN 14825 zur Ermittlung des SCOP-Wertes?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Spitzenleistung bei einer konstanten Labor-Innentemperatur von 20 °C.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Effizienz an vier repräsentativen Stützpunkten (A–7, A2, A7, A12), gewichtet nach den statistischen Betriebsstunden der europäischen Klimazone.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Den reinen Stromverbrauch des Kompressors im Standby-Modus über 365 Tage.</button>
      <div class="qfb ok">✓ Korrekt! Der Seasonal Coefficient of Performance simuliert das reale meteorologische Profil eines Jahres für verlässliche Verbrauchsprognosen.</div>
      <div class="qfb err">✗ Falsch! Der SCOP berechnet das gewichtete Jahresprofil über standardisierte Klimabins – keine simple Einzelmessung.</div>
    </div>

    <!-- QUESTION 14 -->
    <div class="qitem" data-qidx="14" data-correct="c">
      <div class="qt">14. Unter welcher installationsseitigen Bedingung kann bei einer modernen Inverter-Wärmepumpe komplett auf einen Trennpufferspeicher verzichtet werden?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Wenn das Gebäude über alte Gussradiatoren verfügt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Wenn eine solartermische Anlage die Warmwasserbereitung komplett übernimmt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Wenn das Wärmeabgabenetz (z.B. komplett offene Fußbodenheizungskreise ohne Einzelraumregelung) das zur Abtauung und Mindestlaufzeit benötigte Anlagenvolumen jederzeit garantiert.</button>
      <div class="qfb ok">✓ Korrekt! Ist das Mindestwasser-Umlaufvolumen über offene Heizkreise permanent sichergestellt, läuft das System auch direkt maximal effizient.</div>
      <div class="qfb err">✗ Falsch! Ein Puffer kann entfallen, wenn das Rohrnetz permanent geöffnet ist und das hydraulische Mindestvolumen garantiert.</div>
    </div>

    <!-- QUESTION 15 -->
    <div class="qitem" data-qidx="15" data-correct="a">
      <div class="qt">15. Wie erfüllt die Realm TRUTH-Serie die strengen Vorgaben der DVGW W551 zur Legionellenvermeidung ohne teure elektrische Direktheizstäbe?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Indem der Kältekreis das Speichervolumen dank R290-Thermodynamik rein verdichterbasiert auf über 65 °C bis 75 °C durcherhitzt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Durch den Einsatz UV-basierter Sterilisationslampen im Sekundärwärmetauscher.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die DVGW W551 greift bei Kältemitteln mit einem GWP unter 5 gesetzlich nicht.</button>
      <div class="qfb ok">✓ Korrekt! Durch die hohe Vorlauftemperatur von bis zu 75 °C knackt Realm die Legionellen-Abtötungsschwelle im Standard-Verdichterbetrieb.</div>
      <div class="qfb err">✗ Falsch! Die 75 °C Vorlauf-Power tötet die Keime rein thermodynamisch über den Kältekreis – hocheffizient und ohne Heizstab.</div>
    </div>

    <!-- QUESTION 16 -->
    <div class="qitem" data-qidx="16" data-correct="c">
      <div class="qt">16. Ein Energiemanagementsystem (HEMS) sendet das Signal „PV-Überschuss vorhanden“. Welche Schaltung an den SG-Ready-Kontakten triggert diesen Zustand?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Kontakt 1: Offen (0) / Kontakt 2: Offen (0)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Kontakt 1: Geschlossen (1) / Kontakt 2: Offen (0)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Kontakt 1: Offen (0) / Kontakt 2: Geschlossen (1) [Zustand 3] oder beide geschlossen (1/1) [Zustand 4]</button>
      <div class="qfb ok">✓ Korrekt! Die Zustände 3 und 4 signalisieren der Wärmepumpe ein Überangebot an grünem Strom, woraufhin die Zieltemperaturen als thermischer Puffer angehoben werden.</div>
      <div class="qfb err">✗ Falsch! 0/0 ist die EVU-Sperre. PV-Überschuss erfordert das Schließen von Kontakt 2 (Zustand 3) oder beider Kontakte (Zustand 4).</div>
    </div>

    <!-- QUESTION 17 -->
    <div class="qitem" data-qidx="17" data-correct="a">
      <div class="qt">17. Was definiert den sogenannten „Bivalenzpunkt“ im Rahmen der monovalenten bzw. monoenergetischen Anlagenplanung?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Außentemperatur, ab der die Wärmepumpe die Heizlast nicht mehr alleine decken kann und ein zweiter Wärmeerzeuger (Heizstab/Kessel) zuschaltet.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Den exakten Umschaltpunkt vom reinen Heizbetrieb in den aktiven Kühlmodus.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Temperatur, bei welcher der Verdampfungsdruck den kritischen Punkt erreicht.</button>
      <div class="qfb ok">✓ Korrekt! Ein optimal gewählter Bivalenzpunkt (meist zwischen –5 °C und –7 °C) sichert die wirtschaftliche Balance aus Anlageninvestition und Betriebskosten.</div>
      <div class="qfb err">✗ Falsch! Der Bivalenzpunkt markiert die energetische Einsatzgrenze, ab welcher der Spitzenlastwärmeerzeuger die WP unterstützen muss.</div>
    </div>

    <!-- QUESTION 18 -->
    <div class="qitem" data-qidx="18" data-correct="b">
      <div class="qt">18. Über welche physikalische Schnittstelle greift ein Gebäudeleittechnik-System (GLT) standardmäßig auf die internen Register der Realm TRUTH zu, um Betriebsparameter auszulesen?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Über einen analogen 4-20 mA Stromschleifen-Eingang.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Über die serielle Modbus-RTU-Schnittstelle (RS485) oder Modbus-TCP (Ethernet).</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ausschließlich proprietär über ein optisches Infrarot-Interface.</button>
      <div class="qfb ok">✓ Korrekt! Modbus gehört in der industriellen MSR-Technik zum universellen Kommunikationsstandard für offene Busarchitekturen.</div>
      <div class="qfb err">✗ Falsch! Realm bietet standardmäßig offene Modbus-RTU/TCP-Protokolle zur nahtlosen Smart-Home- und GLT-Integration.</div>
    </div>

    <!-- QUESTION 19 -->
    <div class="qitem" data-qidx="19" data-correct="a">
      <div class="qt">19. Fehlermeldung im Display: „E1 – Hochdruckpressostat ausgelöst“. Welche mechanische Ursache liegt in 90% der Praxisfälle vor?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein kompletter Stillstand des Heizungsvolumenstroms im Kondensator (z. B. durch geschlossene Zonenventile oder eine defekte Ladepumpe), wodurch die Wärme nicht abgeführt werden kann.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein massiver Kältemittelverlust im Primärkreis.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Eine Verstopfung der Kondensat-Ablaufrinne am Gehäuseboden.</button>
      <div class="qfb ok">✓ Korrekt! Kann der Kondensator die Wärme nicht ans Heizungswasser abgeben, steigen Druck und Temperatur rasant, bis die Sicherheitskette (Pressostat) die Anlage abschaltet.</div>
      <div class="qfb err">✗ Falsch! E1 signalisiert Überdruck. Das passiert, wenn die erzeugte Verflüssigerwärme mangels Durchfluss nicht abgenommen wird.</div>
    </div>

    <!-- QUESTION 20 -->
    <div class="qitem" data-qidx="20" data-correct="c">
      <div class="qt">20. Welches rechtliche Privileg sichert das Realm-Partnerprogramm „REALM HEROES“ einem zertifizierten Fachhandwerksbetrieb exklusiv zu?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Recht, kältetechnische Eingriffe ohne Sachkundenachweis vorzunehmen.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Eine kostenlose Befreiung von der gesetzlichen Gewährleistungspflicht.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Echten, vertraglich garantierten Gebietsschutz im Einzugsgebiet sowie die kostenfreie Zuweisung vorqualifizierter Endkunden-Leads.</button>
      <div class="qfb ok">✓ Korrekt! Realm setzt auf loyale Partnerschaften auf Augenhöhe mit klarem Gebietsschutz und exklusiven Vertriebskanälen für das Fachhandwerk.</div>
      <div class="qfb err">✗ Falsch! Wir stärken Ihren Betrieb mit echtem Gebietsschutz, digitaler Lead-Zuweisung und technischem Express-Support.</div>
    </div>

    <!-- AUSWERTUNGS-BEREICH -->
    <button class="btn btn-primary" style="width:100%; justify-content:center; margin-top:1.5rem; padding: 1rem;" onclick="evaluateQuiz()">
      🎓 Prüfung auswerten &amp; Ergebnisse übermitteln
    </button>

    <div id="resultBox" class="quiz-score">
      <div class="qs-val" id="scoreVal">0 / 20</div>
      <div class="qs-lbl" id="scoreLbl">Prüfung nicht bestanden.</div>
      <p id="resultText"></p>
      
      <div id="mailNote" class="mail-note"></div>
      
      <button id="sendMailBtn" class="btn btn-primary" style="margin-top: 1rem; display:none;" onclick="sendResultEmail()">
        ✉️ Ergebnisse jetzt via E-Mail einsenden
      </button>
    </div>
  </div>
</div>

</div> <!-- /page -->

<script>
// Navigations-Logik
function goSec(secIdx) {
  const sections = document.querySelectorAll('.section');
  const navItems = document.querySelectorAll('.nav-item');
  
  sections.forEach((s, idx) => {
    if(idx === secIdx) s.classList.add('active');
    else s.classList.remove('active');
  });
  
  navItems.forEach((item, idx) => {
    if(idx === secIdx) item.classList.add('active');
    else item.classList.remove('active');
  });
  
  window.scrollTo({top: 0, behavior: 'smooth'});
}

// Accordion-Logik
function accToggle(element) {
  element.classList.toggle('open');
  const body = element.nextElementSibling;
  body.classList.toggle('open');
}

// Quiz-Auswahl-Logik
function selectOpt(optButton) {
  const parent = optButton.parentElement;
  const siblings = parent.querySelectorAll('.qopt');
  
  // Wenn bereits ausgewertet, Klicks blockieren
  if(parent.querySelector('.qfb.show')) return;
  
  siblings.forEach(sib => sib.classList.remove('selected'));
  optButton.classList.add('selected');
}

// Globale Variablen für E-Mail-Inhalt
let finalScore = 0;
let userName = "";
let emailBodyText = "";

function evaluateQuiz() {
  userName = document.getElementById('qename').value.trim();
  if(!userName) {
    alert("Bitte geben Sie zuerst Ihren Vor- und Nachnamen ein, um die Prüfung auszuwerten.");
    document.getElementById('qename').focus();
    return;
  }

  const qItems = document.querySelectorAll('.qitem');
  finalScore = 0;
  let summaryText = "";

  qItems.forEach((item) => {
    const qidx = item.getAttribute('data-qidx');
    const correctLetter = item.getAttribute('data-correct');
    const options = item.querySelectorAll('.qopt');
    const selectedOpt = item.querySelector('.qopt.selected');
    const fbOk = item.querySelector('.qfb.ok');
    const fbErr = item.querySelector('.qfb.err');

    // Optionen sperren
    options.forEach(opt => opt.classList.add('locked'));

    let chosenText = "Keine Antwort";
    let isCorrect = false;

    if(selectedOpt) {
      // Index des gewählten Buttons bestimmen (a, b, c)
      const optIdx = Array.from(options).indexOf(selectedOpt);
      const letterMapping = ['a', 'b', 'c'];
      const chosenLetter = letterMapping[optIdx];
      chosenText = selectedOpt.textContent.trim();

      if(chosenLetter === correctLetter) {
        selectedOpt.classList.add('correct');
        fbOk.classList.add('show');
        finalScore++;
        isCorrect = true;
      } else {
        selectedOpt.classList.add('wrong');
        fbErr.classList.add('show');
        // Richtige Option visuell hervorheben
        options[letterMapping.indexOf(correctLetter)].classList.add('correct');
      }
    } else {
      // Nichts ausgewählt -> Feedback Fehler anzeigen
      fbErr.classList.add('show');
      options[letterMapping.indexOf(correctLetter)].classList.add('correct');
    }

    summaryText += `Frage ${qidx}: ${isCorrect ? 'RICHTIG' : 'FALSCH'} (Gewählt: "${chosenText}")\n`;
  });

  // Ergebnisbox rendern
  const resultBox = document.getElementById('resultBox');
  const scoreVal = document.getElementById('scoreVal');
  const scoreLbl = document.getElementById('scoreLbl');
  const resultText = document.getElementById('resultText');
  const mailNote = document.getElementById('mailNote');
  const sendMailBtn = document.getElementById('sendMailBtn');

  resultBox.classList.add('show');
  scoreVal.textContent = `${finalScore} / 20`;

  const passed = finalScore >= 16;
  if(passed) {
    scoreLbl.textContent = "🎉 Prüfung BESTANDEN!";
    scoreLbl.style.color = "var(--green-dark)";
    resultText.textContent = `Herzlichen Glückwunsch, ${userName}! Sie haben die technische Tiefenschulung mit Bravour gemeistert und sich als Realm R290-Experte qualifiziert.`;
  } else {
    scoreLbl.textContent = "❌ Prüfung LEIDER NICHT BESTANDEN";
    scoreLbl.style.color = "var(--red)";
    resultText.textContent = `Schade, ${userName}. Für eine erfolgreiche Zertifizierung sind mindestens 16 korrekte Antworten erforderlich. Gehen Sie die Module noch einmal in Ruhe durch.`;
  }

  // E-Mail Inhalt generieren
  emailBodyText = `Realm R290 Tiefenschulung - Prüfungsergebnis\n`;
  emailBodyText += `===============================================\n`;
  emailBodyText += `Absolvent: ${userName}\n`;
  emailBodyText += `Ergebnis: ${finalScore} von 20 Punkten (${passed ? 'BESTANDEN' : 'NICHT BESTANDEN'})\n`;
  emailBodyText += `Datum: ${new Date().toLocaleString('de-DE')}\n\n`;
  emailBodyText += `Detaillierte Übersicht:\n`;
  emailBodyText += summaryText;

  mailNote.innerHTML = `Übermittlung vorbereitet! Klicken Sie auf den folgenden Button, um Ihr Ergebnis direkt an <strong>m.christel@realm-europe.de</strong> zu senden.`;
  mailNote.className = "mail-note mail-ok";
  sendMailBtn.style.display = "inline-flex";

  // Direktes Scrollen zum Ergebnis
  resultBox.scrollIntoView({behavior: 'smooth'});
}

function sendResultEmail() {
  const subject = encodeURIComponent(`Zertifikat R290 Prüfung: ${userName} (${finalScore}/20)`);
  const body = encodeURIComponent(emailBodyText);
  window.location.href = `mailto:m.christel@realm-europe.de?subject=${subject}&body=${body}`;
}
</script>

</body>
</html>
