<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Realm Germany – Vertriebsschulung: Modul 2</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{\n  --blue-deep:#0B3D6B;\n  --green-dark:#1A6B4A;\n  --green-mid:#059669;\n  --green-light:#ECFDF5;\n  --amber:#F59E0B;\n  --red:#DC2626;\n  --bg:#F0F2F5;\n  --card:#FFFFFF;\n  --border:#E5E7EB;\n  --text:#1A1A1A;\n  --muted:#6B7280;\n  --subtle:#F9FAFB;\n}
html{scroll-behavior:smooth}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;background:var(--bg);color:var(--text);line-height:1.6}

/* ── HERO ── */
.hero{background:linear-gradient(135deg,#071f38 0%,var(--blue-deep) 45%,var(--green-dark) 100%);color:#fff;padding:4rem 1.5rem 3rem;text-align:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")}
.hero-badge{display:inline-block;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.2);border-radius:20px;padding:5px 16px;font-size:11px;letter-spacing:2px;text-transform:uppercase;margin-bottom:1.25rem;backdrop-filter:blur(4px)}
.hero h1{font-size:clamp(24px,5vw,42px);font-weight:800;margin-bottom:.75rem;line-height:1.15}
.hero h1 span{color:#6EE7B7}
.hero p{font-size:15px;opacity:.8;max-width:580px;margin:0 auto 2rem}

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

/* ── HIGHLIGHT BOX ── */
.hl{background:var(--green-light);border-left:4px solid var(--green-mid);border-radius:0 10px 10px 0;padding:.875rem 1.1rem;margin:.875rem 0;font-size:13.5px;line-height:1.7}
.hl-amber{background:#FFFBEB;border-left-color:var(--amber)}
.hl-red{background:#FEF2F2;border-left-color:var(--red)}
.hl strong{display:block;margin-bottom:3px}

/* ── SCRIPT BOX ── */
.script-box {background:#1E293B;color:#E2E8F0;border-radius:10px;padding:1rem 1.25rem;font-family:'SF Mono',Consolas,monospace;font-size:13px;margin:.875rem 0;line-height:1.8;border-left:4px solid #38BDF8;}
.script-box strong {color:#38BDF8;}

/* ── TABLE ── */
.tbl-wrap{overflow-x:auto;margin:.875rem 0;border-radius:10px;border:1px solid var(--border)}
table{width:100%;border-collapse:collapse;font-size:13px}
thead tr{background:var(--subtle)}
th{padding:9px 14px;text-align:left;font-weight:700;color:#374151;border-bottom:1px solid var(--border)}
td{padding:9px 14px;border-bottom:1px solid #F3F4F6;color:#4B5563;vertical-align:top}

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

.nav-btns{display:flex;justify-content:space-between;margin-top:2rem;gap:10px}
.btn{padding:.65rem 1.4rem;border-radius:10px;border:1.5px solid var(--border);background:#fff;cursor:pointer;font-size:14px;font-weight:700;color:var(--text);transition:all .2s;display:inline-flex;align-items:center;gap:6px}
.btn:hover{background:var(--subtle);border-color:#9CA3AF}
.btn-primary{background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;border-color:transparent}
.sect-progress{background:var(--border);border-radius:8px;height:5px;margin-bottom:2rem}
.sect-progress-fill{background:linear-gradient(90deg,var(--blue-deep),var(--green-dark));border-radius:8px;height:5px;transition:width .5s}

/* ── ACCORDION ── */
.acc-item{border:1px solid var(--border);border-radius:10px;margin-bottom:8px;overflow:hidden}
.acc-hd{display:flex;align-items:center;justify-content:space-between;padding:.875rem 1rem;cursor:pointer;font-size:14px;font-weight:700;background:#fff;transition:background .15s}
.acc-hd:hover{background:var(--subtle)}
.acc-hd .acc-ico{font-size:18px;transition:transform .3s}
.acc-hd.open .acc-ico{transform:rotate(180deg)}
.acc-body{display:none;padding:1rem;border-top:1px solid var(--border);background:var(--subtle);font-size:13.5px;line-height:1.7}
.acc-body.open{display:block}
</style>
</head>
<body>

<div class="hero">
  <div class="hero-badge">Realm Germany · Vertriebsschulung 2026</div>
  <h1>Modul 2: B2B-Akquise &amp;<br><span>Lead-Generierung</span></h1>
  <p>Strategischer Beziehungsaufbau, professionelle Telefonakquise bei Gatekeeper-Widerstand und die effiziente Selektion kaufbereiter Großprojekte.</p>
</div>

<div class="nav-wrap">
  <div class="nav-inner">
    <div class="nav-item active" onclick="goSec(0)">1 · Cold Calling &amp; Gatekeeper</div>
    <div class="nav-item" onclick="goSec(1)">2 · Social Selling (LinkedIn/Xing)</div>
    <div class="nav-item" onclick="goSec(2)">3 · Qualifizierung (BANT)</div>
    <div class="nav-item" onclick="goSec(3)">4 · Zertifizierungs-Test (20 Q)</div>
  </div>
</div>

<div class="page">

<div class="section active" id="sec0">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:25%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">📞</span>Cold Calling (Telefonakquise) &amp; Gatekeeper-Management</div>
    <p>Die größte Hürde in der B2B-Telefonakquise ist das Vorzimmer (Sekretariat, Assistenz oder Zentrale), auch bekannt als der „Gatekeeper“. Wer hier versucht, sein Produkt oder seine Dienstleistung zu verkaufen, scheitert in 98% der Fälle. Die Assistenz hat die klare Arbeitsanweisung, unaufgeforderte Werbeanrufe radikal abzublocken.</p>

    <div class="hl"><strong>Das strategische Mindset:</strong><br>Der Gatekeeper ist kein Feind, sondern ein potenzieller Verbündeter und Navigator. Ihr Ziel am Telefon ist niemals der Abschluss, sondern ausschließlich die Weiterleitung zum Entscheider (z.B. Geschäftsführer, technischer Leiter, SHK-Betriebsinhaber) oder die Vereinbarung eines qualifizierten Erstgesprächs.</div>

    <h3>Die psychologischen Hebel zum Überwinden des Vorzimmers</h3>
    <p>Um die Assistenz zu passieren, nutzen Top-Vertriebler linguistische Muster, die **Augenhöhe, Dringlichkeit und bestehende Relevanz** signalisieren. Das Vorzimmer entscheidet innerhalb der ersten 5 Sekunden anhand von Tonalität, Tempo und Wortwahl, ob ein Anruf geschäftswichtig oder reine Akquise ist.</p>

    <h4>1. Die „Status- und Annahme-Methode“ (Verbindlichkeit statt Betteln)</h4>
    <p>Vermeide devote Floskeln wie <i>„Könnte ich vielleicht...“</i> oder <i>„Ich wollte mal fragen, ob...“</i>. Wer um Erlaubnis bittet, outet sich sofort als Bittsteller.</p>
    <div class="script-box">
      <strong>Falsch:</strong> „Guten Tag, mein Name ist Müller von der Realm Germany. Ich wollte fragen, ob eventuell der Herr Geschäftsführer Schneider zu sprechen ist? Wir vertreiben hocheffiziente R290-Wärmepumpen...“<br>
      <span style="color:#F87171">→ Ergebnis: „Bitte schicken Sie uns eine Info-Mail an info@...“ (Aufgelegt).</span><br><br>
      <strong>Richtig:</strong> „Guten Tag, Müller mein Name, Realm Germany. Frau [Name der Assistenz], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“
    </div>

    <h4>2. Der „Prozess-Grund“ statt „Produkt-Grund“</h4>
    <p>Wenn die Assistenz die typische Gegenfrage stellt: <i>„Worum geht es denn genau?“</i>, darfst du niemals das Produkt (Wärmepumpen, Software, Dienstleistung) pitchen. Nenne einen strategischen Grund, der auf der organisatorischen Ebene des Entscheiders liegt.</p>
    <div class="script-box">
      <strong>Assistenz:</strong> „Worum geht es denn bei dem Anruf? Er ist gerade sehr beschäftigt.“<br>
      <strong>Vertriebs-Profi:</strong> „Es geht um die strategische Neuausrichtung Ihrer Projektkapazitäten und die Absicherung gegen die neuen Lieferengpässe im Bereich der R290-Großprojekte für das kommende Quartal. Herr Schneider erwartet hierzu Informationen bezüglich unseres Gebietsschutzes im Raum Bayern. Stellen Sie mich bitte durch?“
    </div>

    <h3>Umgang mit den 3 häufigsten Vorwänden am Telefon</h3>
    <div class="tbl-wrap">
      <table>
        <thead><tr><th>Vorwand der Assistenz</th><th>Psychologische Ursache</th><th>Konter-Skript für den Vertriebler</th></tr></thead>
        <tbody>
          <tr><td>„Schicken Sie uns einfach eine E-Mail an info@...“</td><td>Standard-Abwehrmuster, um Zeit zu sparen und den Anrufer loszuwerden.</td><td>„Das mache ich gerne. Da meine Unterlagen jedoch vertrauliche Konditionen zum Gebietsschutz enthalten, muss ich das Dokument direkt für Herrn Schneider personalisieren. Geben Sie mir kurz seine direkte Durchwahl oder seine persönliche Mailadresse?“</td></tr>
          <tr><td>„Wir haben bereits bestehende Lieferanten und kein Interesse.“</td><td>Angst vor Veränderung oder Bequemlichkeit.</td><td>„Das verstehe ich vollkommen, ein Wechsel steht auch gar nicht im Raum. Es geht rein um eine strategische Zweitlieferanten-Option zur Absicherung Ihrer Großprojekte bei akuten Marktengpässen. Bringen Sie mich bitte kurz durch.“</td></tr>
          <tr><td>„Der Geschäftsführer hat dafür aktuell überhaupt keine Zeit.“</td><td>Echte Überlastung oder Schutzbehauptung.</td><td>„Genau deswegen rufe ich an. Damit Herr Schneider keine Zeit verliert, stimmen wir in genau 45 Sekunden ab, ob unser Lösungsansatz für seine aktuellen Großprojekte relevant ist. Ist er eher morgen früh um 8 Uhr oder nachmittags um 16 Uhr erreichbar?“</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <div class="nav-btns">
    <div></div>
    <button class="btn btn-primary" onclick="goSec(1)">Weiter: Social Selling →</button>
  </div>
</div>

<div class="section" id="sec1">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:50%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🤝</span>Social Selling über LinkedIn und Xing</div>
    <p>Im modernen B2B-Vertrieb ist **Hardselling per Direktnachricht (Copy-Paste-Pitches) tot**. Entscheider werden auf LinkedIn und Xing täglich mit Dutzenden unpersönlichen Verkaufsnachrichten bombardiert. Die Folge: Sofortiges Ignorieren oder Blockieren. Beim Social Selling geht es primär um den **digitalen Beziehungsaufbau (Nutzenstiftung vor Umsatzforderung)**.</p>

    <div class="hl-amber"><strong>Die goldene Regel des Social Selling:</strong><br>„Give before you take.“ Erst Mehrwert liefern, Sichtbarkeit erzeugen und Vertrauen aufbauen – erst danach folgt das unverbindliche Gesprächsangebot. Dein Profil fungiert dabei nicht als digitaler Lebenslauf, sondern als verkaufsoptimierte Landingpage für die Probleme deiner Zielgruppe.</div>

    <h3>Der 4-Schritte-Fahrplan zur Lead-Generierung via Social Media</h3>
    
    <h4>Schritt 1: Profil-Optimierung (Vom Lebenslauf zur Landingpage)</h4>
    <p>Wenn ein Entscheider dein Profil besucht, muss er innerhalb von 3 Sekunden verstehen, welchen Nutzen du ihm stiftest. Tausche langweilige Berufsbezeichnungen (<i>„Sales Manager bei Realm“</i>) gegen eine glasklare **Nutzen-Formel** aus.</p>
    <div class="script-box">
      <strong>Muster-Slogan für dein Profil:</strong><br>
      „Ich helfe SHK-Fachbetrieben und Projektentwicklern dabei, R290-Wärmepumpen-Großprojekte ohne lange Lieferzeiten umzusetzen und sich exklusiven Gebietsschutz zu sichern.“
    </div>

    <h4>Schritt 2: Das „Digitale Einschleichen“ (Die 3-Touchpoint-Regel)</h4>
    <p>Sende niemals direkt eine Vernetzungsanfrage mit einem Verkaufs-Pitch. Baue stattdessen vorab unsichtbare Touchpoints auf:</p>
    <ul>
      <li><strong>Touchpoint 1:</strong> Besuche das Profil des Entscheiders (er erhält eine Benachrichtigung).</li>
      <li><strong>Touchpoint 2:</strong> Like einen aktuellen Beitrag oder Kommentar des Entscheiders.</li>
      <li><strong>Touchpoint 3:</strong> Hinterlasse einen *qualifizierten Fachkommentar* unter seinem Beitrag. Vermeide Floskeln wie „Toller Beitrag!“, sondern füge echten Mehrwert hinzu (z.B. „Spannender Ansatz. Gerade bei der Umsetzung nach DIN EN 378 sehen wir im Feld oft, dass...“).</li>
    </ul>

    <h4>Schritt 3: Die Pitch-freie Vernetzungsanfrage</h4>
    <p>Erst wenn der Entscheider deinen Namen bereits positiv in den Benachrichtigungen gesehen hat, schickst du eine kurze, persönliche Nachricht ohne jeglichen Verkaufsdruck.</p>
    <div class="script-box">
      „Hallo Herr [Nachname], danke für Ihren spannenden Kommentar zum Thema Energiewende im Neubau. Ich verfolge Ihre Projekte im Raum Stuttgart mit großem Interesse. Lassen Sie uns hier gerne vernetzen, um im fachlichen Austausch zu bleiben. Beste Grüße, [Dein Name]“
    </div>

    <h4>Schritt 4: Die Konversation starten (Der sanfte Übergang zum Telefonat)</h4>
    <p>Nach der Annahme der Vernetzung beginnst du einen Dialog auf Augenhöhe, indem du eine offene Fachfrage zu einem aktuellen Schmerzpunkt seiner Branche stellst.</p>
    <div class="script-box">
      „Hallo Herr [Nachname], danke für die Vernetzung. Ich sehe auf Ihrer Website, dass Sie vermehrt gewerbliche Objekte ausstatten. Spüren Sie aktuell bei Ihren Kunden auch die wachsende Verunsicherung bezüglich der neuen F-Gas-Verordnung und den Quotenverboten für synthetische Kältemittel? Wie fangen Sie das im Tagesgeschäft ab?“
    </div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(0)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(2)">Weiter: Lead-Qualifizierung →</button>
  </div>
</div>

<div class="section" id="sec2">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:75%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🎯</span>Rigorose Lead-Qualifizierung (BANT-Framework)</div>
    <p>Die wertvollste Ressource eines B2B-Vertrieblers ist seine Arbeitszeit. Viele Verkäufer begehen den Fehler, wochenlang Angebote für Firmen auszuarbeiten, die weder das Budget haben, noch akuten Bedarf aufweisen oder überhaupt entscheidungsbefugt sind. Das **BANT-Framework** schützt dich vor Zeitdieben und trennt die Spreu vom Weizen.</p>

    <div class="tbl-wrap">
      <table>
        <thead><tr><th>BANT-Kriterium</th><th>Bedeutung im B2B-Kontext</th><th>Strategische Qualifizierungs-Fragen für das Gespräch</th></tr></thead>
        <tbody>
          <tr><td><strong>B</strong>udget (Finanzen)</td><td>Verfügt das Unternehmen über die finanziellen Mittel, um unsere Premium-Lösung zu bezahlen?</td><td>„Welcher finanzielle Rahmen ist für diese Projektphase von Ihrer Geschäftsführung freigegeben?“ / „Haben Sie für die Umstellung bereits Fördermittel (z.B. BEG) einkalkuliert?“</td></tr>
          <tr><td><strong>A</strong>uthority (Entscheider)</td><td>Spreche ich mit der Person, die Verträge rechtsgültig unterschreiben darf, oder mit einem reinen Informationssammler?</td><td>„Wer ist außer Ihnen noch an der finalen Freigabe dieses Projekts beteiligt?“ / „Wie sieht Ihr interner Entscheidungsprozess für Investitionen dieser Größenordnung üblicherweise aus?“</td></tr>
          <tr><td><strong>N</strong>eed (Bedarf/Schmerz)</td><td>Hat das Unternehmen ein ungelöstes, akutes Problem, das wir exakt eliminieren können? (Nice-to-have vs. Must-have)</td><td>„Was passiert, wenn Sie das Problem der langen Lieferzeiten bei Ihren aktuellen Projekten in den nächsten 3 Monaten nicht lösen?“ / „Welche technischen Hürden bereitet Ihnen die F-Gas-Verordnung?“</td></tr>
          <tr><td><strong>T</strong>imeline (Zeithorizont)</td><td>Wann genau soll die Umsetzung oder der Kauf erfolgen? Liegt ein konkreter Starttermin vor?</td><td>„Bis wann muss die neue Wärmepumpenanlage spätestens im Gebäude betriebsbereit sein?“ / „Planen Sie die Umsetzung für das laufende Quartal oder ist das ein Thema für das übernächste Jahr?“</td></tr>
        </tbody>
      </table>
    </div>

    <h3>Die Einteilung in Lead-Klassen (A-, B-, C-Leads)</h3>
    <p>Nach dem Erstgespräch teilst du das Lead sofort in eine von drei Kategorien ein, um deine Vertriebsaktivitäten mathematisch effizient zu steuern:</p>
    <ul>
      <li><strong>A-Leads (Sofort-Fokus):</strong> Alle 4 BANT-Kriterien sind positiv erfüllt. Der Kunde hat ein akutes Problem, das Budget steht bereit, du sprichst direkt mit dem Inhaber und der Zeithorizont liegt unter 30 Tagen. **Aktion:** Sofortiges Angebot und Vor-Ort-Termin innerhalb von 48 Stunden.</li>
      <li><strong>B-Leads (Nurturing-Fokus):</strong> Bedarf und Budget sind da, aber der Zeithorizont liegt in 6 Monaten oder der finale Entscheider muss noch in einen Folgetermin geholt werden. **Aktion:** Follow-up-Prozess aufsetzen, regelmäßig Mehrwert senden.</li>
      <li><strong>C-Leads (Disqualifizieren):</strong> Kein echtes Budget vorhanden, kein akuter Schmerzpunkt, reines Aushorchen von Marktpreisen. **Aktion:** Rigoros aussortieren oder auf automatisierte Info-Materialien verweisen. Verschwende hier keine wertvolle Telefonzeit!</li>
    </ul>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(1)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(3)">Weiter: Zertifizierungs-Test →</button>
  </div>
</div>

<div class="section" id="sec3">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:100%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🏆</span>Zertifizierungs-Prüfung – Level: B2B-Vertriebsprofi</div>
    <p>20 hochspezifische Fachfragen zur Neukundenakquise und Lead-Generierung. Zum Bestehen der Zertifizierung müssen mindestens **16 von 20 Fragen (80%)** korrekt beantwortet werden.</p>
  </div>

  <div class="quiz-box">
    <h3>🎯 Modul 2 Abschlussprüfung – Akquise-Kompetenz</h3>
    <div class="qsub">Realm Zertifikat · Modul 2 · 20 Praxisfragen</div>

    <div class="name-row">
      <label for="qename">👤 Absolvent Name:</label>
      <input type="text" id="qename" placeholder="Vor- und Nachname eingeben (Pflichtfeld) …" />
    </div>

    <div class="qitem" data-qidx="1" data-correct="b">
      <div class="qt">1. Was ist das primäre, strategische Ziel eines Kaltanrufs (Cold Call) im B2B-Bereich?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Der direkte Verkauf unseres Produkts oder der Abschluss eines Rahmenvertrags am Telefon.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Vereinbarung eines qualifizierten Erstgesprächs oder die Weiterleitung zum tatsächlichen Entscheider.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das bloße Sammeln von allgemeinen E-Mail-Adressen für den Marketing-Newsletter.</button>
      <div class="qfb ok">✓ Korrekt! Ein B2B-Investitionsprodukt lässt sich nicht blind im ersten Telefonat verkaufen. Ziel ist ausschließlich der nächste Prozessschritt (Termin).</div>
      <div class="qfb err">✗ Falsch! Ein Direktverkauf per Kaltanruf ist im B2B-Umfeld unrealistisch. Das Ziel ist die Terminvereinbarung.</div>
    </div>

    <div class="qitem" data-qidx="2" data-correct="a">
      <div class="qt">2. Warum scheitern die meisten Vertriebler beim Versuch, den Gatekeeper (Assistenz) zu passieren?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil sie versuchen, der Assistenz das Produkt zu verkaufen, anstatt einen geschäftswichtigen Prozess-Grund zu nennen.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil die Assistenz generell keine Anrufe durchstellt, unabhängig von der Wichtigkeit.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil sie den Firmennamen am Telefon zu laut aussprechen.</button>
      <div class="qfb ok">✓ Korrekt! Wer im Vorzimmer pitcht, fliegt raus. Die Assistenz ist darauf geschult, Werbe-Pitches sofort zu blockieren.</div>
      <div class="qfb err">✗ Falsch! Die Assistenz blockiert gezielt Verkaufsgespräche. Wer ein Prozess-Thema auf Augenhöhe nennt, wird durchgestellt.</div>
    </div>

    <div class="qitem" data-qidx="3" data-correct="c">
      <div class="qt">3. Welche Formulierung strahlt im Vorzimmer die meiste „Augenhöhe und Verbindlichkeit“ aus?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Guten Tag, dürfte ich vielleicht ganz kurz mit Herrn Schneider sprechen, falls er gerade Zeit hat?“</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Hallo, ich wollte mal nachhören, wer bei Ihnen für das Thema Heizung zuständig ist.“</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Guten Tag, Müller mein Name, Realm Germany. Frau [Name], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“</button>
      <div class="qfb ok">✓ Korrekt! Diese Formulierung verzichtet auf Bittsteller-Floskeln und signalisiert eine geschäftliche Selbstverständlichkeit.</div>
      <div class="qfb err">✗ Falsch! Die Optionen A und B positionieren dich sofort als unbedeutenden Bittsteller.</div>
    </div>

    <div class="qitem" data-qidx="4" data-correct="b">
      <div class="qt">4. Was versteht man im Telefonmarketing unter einem „Prozess-Grund“?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die ausführliche Erklärung der technischen Funktionsweise einer R290-Wärmepumpe.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein geschäftliches Thema auf Management-Ebene (z.B. Planungskonflikte, Marktveränderungen), das die Relevanz des Anrufs begründet.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Den rechtlichen Grund für ein laufendes Gerichtsverfahren gegen einen Wettbewerber.</button>
      <div class="qfb ok">✓ Korrekt! Ein Prozess-Grund knüpft an die aktuellen strategischen Herausforderungen des Entscheiders an, nicht an die Merkmale deines Produkts.</div>
      <div class="qfb err">✗ Falsch! Ein Prozess-Grund ist kein Produktfeature, sondern ein strategisches Management-Thema.</div>
    </div>

    <div class="qitem" data-qidx="5" data-correct="a">
      <div class="qt">5. Wie reagiert ein Profi auf den Assistenz-Vorwand: „Schicken Sie uns einfach eine Info-Mail an info@...“?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er stimmt zu, fordert aber die persönliche Mailadresse oder Durchwahl des Entscheiders ein, da das Dokument vertrauliche/personalisierte Daten enthält.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er legt sofort frustriert auf, da info@-Mails niemals gelesen werden.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er fängt an, der Assistenz am Telefon wütend zu widersprechen.</button>
      <div class="qfb ok">✓ Korrekt! Damit nutzt du den Vorwand als Hebel, um an qualifizierte Kontaktdaten des Entscheiders zu gelangen.</div>
      <div class="qfb err">✗ Falsch! Einfaches Nachgeben führt in die info@-Blackbox. Nutze das Argument der Personalisierung/Vertraulichkeit.</div>
    </div>

    <div class="qitem" data-qidx="6" data-correct="c">
      <div class="qt">6. Was ist das goldene Gesetz beim Social Selling über LinkedIn und Xing?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Möglichst viele Kontakte pro Tag per automatisiertem Bot anschreiben und sofort das Angebot mitsenden.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Sein Profil rein privat nutzen und geschäftliche Themen komplett heraushalten.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Erst vertrauensvollen Beziehungsaufbau betreiben und Mehrwert stiften, bevor man ein Angebot platziert.</button>
      <div class="qfb ok">✓ Korrekt! „Hardselling“ in der ersten Nachricht verbrennt im modernen B2B-Vertrieb wertvolle Leads.</div>
      <div class="qfb err">✗ Falsch! Spamming führt zu Blockaden. Social Selling basiert auf digitalem Vertrauensaufbau.</div>
    </div>

    <div class="qitem" data-qidx="7" data-correct="b">
      <div class="qt">7. Wie sollte der Profil-Slogan (Headline) eines B2B-Vertrieblers im Idealfall aufgebaut sein?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Als tabellarischer Lebenslauf mit allen bisherigen Arbeitgebern und Notendurchschnitten.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Als Nutzen-Formel, die der Zielgruppe sofort zeigt, welches konkrete Problem du für sie löst.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Möglichst kryptisch und geheimnisvoll, damit der Kunde nachfragen muss.</button>
      <div class="qfb ok">✓ Korrekt! Dein Slogan muss wie die Überschrift einer Landingpage wirken: Problem benennen, Lösung aufzeigen.</div>
      <div class="qfb err">✗ Falsch! Dein Profil ist kein Lebenslauf für Personalvermittler, sondern ein Werkzeug zur Lead-Gewinnung.</div>
    </div>

    <div class="qitem" data-qidx="8" data-correct="a">
      <div class="qt">8. Was besagt die „3-Touchpoint-Regel“ vor dem Absenden einer Vernetzungsanfrage?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Dass man vor der Kontaktaufnahme das Profil des Leads besucht, einen Beitrag von ihm liket und einen qualifizierten Fachkommentar hinterlässt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Dass man den Lead an drei aufeinanderfolgenden Tagen exakt um 12:00 Uhr anrufen muss.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Dass man drei unterschiedliche E-Mail-Adressen des Zielunternehmens anschreibt.</button>
      <div class="qfb ok">✓ Korrekt! Dadurch erzeugst du psychologische Vertrautheit. Dein Name ist dem Entscheider bereits positiv aufgefallen.</div>
      <div class="qfb err">✗ Falsch! Touchpoints im Social Selling sind digitale Interaktionen wie Profilbesuche, Likes und Kommentare.</div>
    </div>

    <div class="qitem" data-qidx="9" data-correct="b">
      <div class="qt">9. Wofür steht das Akronym „BANT“ im Qualifizierungsprozess von B2B-Leads?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Business, Action, Negotiation, Trust</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Budget, Authority, Need, Timeline</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Buying-Power, Agreement, Network, Target</button>
      <div class="qfb ok">✓ Korrekt! Das BANT-Framework prüft Finanzen, Entscheidungsbefugnis, realen Bedarf und den zeitlichen Rahmen.</div>
      <div class="qfb err">✗ Falsch! BANT ist der weltweite Standard für Budget, Authority, Need und Timeline.</div>
    </div>

    <div class="qitem" data-qidx="10" data-correct="c">
      <div class="qt">10. Du sprichst mit einem Projektleiter, der von einer Lösung begeistert ist, aber keine finanzielle Unterschriftenberechtigung besitzt. Welches BANT-Kriterium ist hier gefährdet?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Need (Bedarf)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Timeline (Zeithorizont)</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Authority (Entscheidungskompetenz)</button>
      <div class="qfb ok">✓ Korrekt! Ohne die Einbindung des echten Budget-Entscheiders (Authority) bleibt das Projekt in der Schwebe.</div>
      <div class="qfb err">✗ Falsch! Begeisterung zeigt zwar den „Need“, aber ohne Unterschriftenberechtigung fehlt die „Authority“.</div>
    </div>

    <div class="qitem" data-qidx="11" data-correct="a">
      <div class="qt">11. Mit welcher Frage qualifizierst du das Kriterium „Need“ (Bedarf/Schmerz) am effektivsten?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Welche konkreten wirtschaftlichen Folgen hat es für Ihr Unternehmen, wenn sich Ihre aktuellen Bauprojekte durch Lieferengpässe verzögern?“</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Gefällt Ihnen die Farbe unseres Außengehäuses auf einer Skala von 1 bis 10?“</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>„Wie viele Mitarbeiter beschäftigt Ihre Buchhaltungsabteilung aktuell?“</button>
      <div class="qfb ok">✓ Korrekt! Diese Frage deckt den realen, finanziellen Schmerzpunkt auf und verwandelt das Produkt von einem „Nice-to-have“ in ein „Must-have“.</div>
      <div class="qfb err">✗ Falsch! Nur Fragen nach Schmerzen, Engpässen und den Folgen von Untätigkeit qualifizieren den echten Bedarf.</div>
    </div>

    <div class="qitem" data-qidx="12" data-correct="c">
      <div class="qt">12. Was charakterisiert ein sogenanntes „C-Lead“ im Vertriebsalltag?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein Lead mit unbegrenztem Budget und sofortigem Kaufinteresse beim Geschäftsführer.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein Mitbewerber, der versucht, unsere Vertriebsmitarbeiter abzuwerben.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein anfragendes Unternehmen ohne echtes Budget, ohne akuten Leidensdruck, das lediglich Preise abgreifen will.</button>
      <div class="qfb ok">✓ Korrekt! C-Leads kosten enorm viel Zeit und bringen keinen Umsatz. Sie müssen konsequent disqualifiziert werden.</div>
      <div class="qfb err">✗ Falsch! C-Leads sind reine Zeitdiebe ohne Kaufabsicht oder Budget. Sie sollten aussortiert werden.</div>
    </div>

    <div class="qitem" data-qidx="13" data-correct="b">
      <div class="qt">13. Was versteht man im B2B-Vertrieb unter dem Begriff „Lead Nurturing“?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das aggressive Drängen eines Kunden zum schnellen Vertragsabschluss am Telefon.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das strategische Begleiten und Informieren eines Leads (z.B. B-Leads) mit relevantem Mehrwert, bis dieser kaufbereit ist.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die automatische Löschung von ungenutzten Kontaktdaten aus dem CRM-System.</button>
      <div class="qfb ok">✓ Korrekt! Nurturing bedeutet „Pflege“. Du fütterst den Interessenten so lange mit Content, bis seine „Timeline“ reif ist.</div>
      <div class="qfb err">✗ Falsch! Lead Nurturing bezeichnet die gezielte Weiterentwicklung von Leads durch kontinuierliche Nutzenstiftung.</div>
    </div>

    <div class="qitem" data-qidx="14" data-correct="a">
      <div class="qt">14. Warum ist das Erfragen der „Timeline“ (Zeithorizont) so kritisch für deine Provisionsplanung?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil ein Lead mit akutem Bedarf, das aber erst in 24 Monaten kaufen will, dir im aktuellen Quartal keinen Umsatz bringt.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil die Timeline festlegt, wie lange das Telefonat maximal dauern darf.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil die Timeline gesetzlich im Bundesdatenschutzgesetz verankert ist.</button>
      <div class="qfb ok">✓ Korrekt! Nur Leads mit einer nahen Timeline sichern dir kurzfristige Vertriebserfolge und Abschlüsse.</div>
      <div class="qfb err">✗ Falsch! Ohne zeitliche Komponente investierst du eventuell zu viel Energie in Projekte, die erst in Jahren realisiert werden.</div>
    </div>

    <div class="qitem" data-qidx="15" data-correct="b">
      <div class="qt">15. Ein potenzieller Kunde sagt: „Wir arbeiten bereits seit 15 Jahren glücklich mit unserem aktuellen Kälte-Lieferanten zusammen.“ Wie reagiert der Profi?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er erklärt dem Kunden, warum sein bisheriger Lieferant technisch minderwertig ist.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er lobt die Treue und positioniert Realm rein als strategische Zweitlieferanten-Option zur Absicherung gegen Marktengpässe.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Er entschuldigt sich höflich für die Störung und löscht den Kontakt sofort.</button>
      <div class="qfb ok">✓ Korrekt! Ein Frontalangriff auf bestehende Partner erzeugt Reaktanz. Die Positionierung als Sicherheitsnetz/Zweitlieferant öffnet Türen.</div>
      <div class="qfb err">✗ Falsch! Schlechtreden erzeugt Abwehr. Biete dich stattdessen ohne Wechseldruck als Risikoabsicherung (Backup) an.</div>
    </div>

    <div class="qitem" data-qidx="16" data-correct="c">
      <div class="qt">16. Welches Verhalten signalisiert in den ersten Sekunden eines Telefonats psychologisch „Mangel an Augenhöhe“?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Ein ruhiges Sprechtempo und eine feste, tiefe Stimmlage.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das direkte Nennen des eigenen Namens und des Unternehmens ohne Umschweife.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Verwendung von Rechtfertigungen wie: „Ich störe Sie nur ganz ungern, aber ich hätte eine kurze Frage...“</button>
      <div class="qfb ok">✓ Korrekt! Entschuldigungen im Opener deuten darauf hin, dass deine Zeit weniger wert ist als die des Gegenübers.</div>
      <div class="qfb err">✗ Falsch! Wer sich für seinen Anruf entschuldigt, wertet seinen eigenen geschäftlichen Status sofort ab.</div>
    </div>

    <div class="qitem" data-qidx="17" data-correct="a">
      <div class="qt">17. Was versteht man unter dem Begriff „Social Selling Index (SSI)“ bei LinkedIn?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Eine Metrik von LinkedIn, die misst, wie effektiv du deine professionelle Marke aufbaust, die richtigen Personen findest und Beziehungen pflegst.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die Anzahl der Werbebanner, die ein Nutzer pro Monat auf der Plattform schaltet.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Verhältnis zwischen gelikten Beiträgen und geschriebenen Direktnachrichten.</button>
      <div class="qfb ok">✓ Korrekt! Ein hoher SSI korreliert statistisch nachweisbar mit einem höheren Erfolg bei der digitalen Neukundenakquise.</div>
      <div class="qfb err">✗ Falsch! Der SSI ist LinkedIns Gradmesser für die Qualität deines Netzwerk- und Markenaufbaus.</div>
    </div>

    <div class="qitem" data-qidx="18" data-correct="b">
      <div class="qt">18. Warum ist die Frage „Haben Sie dafür ein Budget?“ im frühen B2B-Erstgespräch oft unstrategisch?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil sie laut Datenschutzgrundverordnung (DSGVO) in Deutschland verboten ist.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil Kunden bei direkter Abfrage reflexartig blocken oder behaupten, kein Geld zu haben, um Verhandlungsspielraum zu wahren.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Weil das Budget im B2B-Bereich grundsätzlich erst nach der Lieferung verhandelt wird.</button>
      <div class="qfb ok">✓ Korrekt! Frage stattdessen nach Rahmenbedingungen, Investitionskorridoren oder bereits bewilligten Fördermitteln, um den finanziellen Rahmen weicher abzufragen.</div>
      <div class="qfb err">✗ Falsch! Direktes Fragen nach Geld erzeugt Abwehr. Besser ist das indirekte Abklopfen von genehmigten Projektkorridoren.</div>
    </div>

    <div class="qitem" data-qidx="19" data-correct="c">
      <div class="qt">19. Ein Lead erfüllt Budget, Bedarf und Timeline perfekt, aber du verhandelst ausschließlich mit dem stellvertretenden Einkäufer ohne finale Freigabemacht. Was ist dein nächster Schritt?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Angebot sofort schreiben und hoffen, dass es irgendwie durchgewinkt wird.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Den Kontakt sofort abbrechen, da der Einkäufer nicht der Hauptentscheider ist.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Den Einkäufer zum internen Verbündeten machen und vorschlagen, den Hauptentscheider (z.B. Geschäftsführer) im nächsten Zoom-Call für die strategischen Fragen hinzuzuziehen.</button>
      <div class="qfb ok">✓ Korrekt! So umgehst du die Blockade charmant, ohne den Einkäufer zu übergehen oder zu brüskieren.</div>
      <div class="qfb err">✗ Falsch! Den Einkäufer zu übergehen beschädigt den Deal. Nutze ihn als Brücke, um die echte „Authority“ an den Tisch zu holen.</div>
    </div>

    <div class="qitem" data-qidx="20" data-correct="a">
      <div class="qt">20. Welcher Hebel erhöht die Erfolgsquote (Conversion Rate) bei der Kaltakquise am Telefon nachhaltig?</div>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Die präzise Vorqualifizierung der Ziel-Firmenliste vor dem ersten Anruf, statt wahllos Nummern aus dem Telefonbuch zu wählen.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Das Sprechen in extrem hoher Lautstärke, um Dominanz zu beweisen.</button>
      <button class="qopt" onclick="selectOpt(this)"><span class="qdot"></span>Möglichst ohne Punkt und Komma zu reden, damit der Angerufene nicht dazwischensprechen kann.</button>
      <div class="qfb ok">✓ Korrekt! Je besser die Zielliste (z.B. Fokus auf Fachbetriebe im passenden PLZ-Gebiet mit Großprojekt-Historie), desto höher die Trefferquote im Gespräch.</div>
      <div class="qfb err">✗ Falsch! Monologe oder Gebrüll zerstören das Telefonat. Erfolg basiert auf Zielgruppenrelevanz und Vorbereitung.</div>
    </div>

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

</div> <script>
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
  const letterMapping = ['a', 'b', 'c'];

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
      const optIdx = Array.from(options).indexOf(selectedOpt);
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
        options[letterMapping.indexOf(correctLetter)].classList.add('correct');
      }
    } else {
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
    resultText.textContent = `Herzlichen Glückwunsch, ${userName}! Sie haben die Vertriebsschulung für Modul 2 erfolgreich gemeistert und sich als Akquise-Profi qualifiziert.`;
  } else {
    scoreLbl.textContent = "❌ Prüfung LEIDER NICHT BESTANDEN";
    scoreLbl.style.color = "var(--red)";
    resultText.textContent = `Schade, ${userName}. Für eine erfolgreiche Zertifizierung sind mindestens 16 korrekte Antworten erforderlich. Gehen Sie die Skripte noch einmal durch.`;
  }

  // E-Mail Inhalt generieren
  emailBodyText = `Vertriebsschulung Modul 2 - Lead-Generierung - Ergebnis\n`;
  emailBodyText += `======================================================\n`;
  emailBodyText += `Absolvent: ${userName}\n`;
  emailBodyText += `Ergebnis: ${finalScore} von 20 Punkten (${passed ? 'BESTANDEN' : 'NICHT BESTANDEN'})\n`;
  emailBodyText += `Datum: ${new Date().toLocaleString('de-DE')}\n\n`;
  emailBodyText += `Detaillierte Übersicht:\n`;
  emailBodyText += summaryText;

  mailNote.innerHTML = `Übermittlung vorbereitet! Klicken Sie auf den folgenden Button, um Ihr Ergebnis direkt an <strong>m.christel@realm-europe.de</strong> zu senden.`;
  mailNote.className = "mail-note mail-ok";
  sendMailBtn.style.display = "inline-flex";

  resultBox.scrollIntoView({behavior: 'smooth'});
}

function sendResultEmail() {
  const subject = encodeURIComponent(`Modul 2 Akquise Ergebnis: ${userName} (${finalScore}/20)`);
  const body = encodeURIComponent(emailBodyText);
  window.location.href = `mailto:m.christel@realm-europe.de?subject=${subject}&body=${body}`;
}
</script>

</body>
</html>
