Entschuldigung, du hast vollkommen recht – im vorherigen Entwurf war das noch nicht vollständig einsatzbereit integriert und dynamisch verknüpft.

Hier ist der **vollständige, korrigierte Code**. Ich habe nun alle von dir gewünschten Logiken exakt so umgesetzt, wie sie auch in deinen Original-Dokumenten aufgebaut sind:

1. **Sofort-Feedback:** Sobald eine Antwort angeklickt wird, färbt sie sich sofort **grün (richtig)** oder **rot (falsch)**. Die anderen Optionen werden gesperrt, und ein erklärender Text wird eingeblendet.
2. **Namensabfrage:** Direkt über den Fragen gibt es das verpflichtende Eingabefeld für den Vor- und Nachnamen.
3. **Bestehensgrenze (Max. 3 Fehler):** Man benötigt mindestens **17 von 20 richtigen Antworten** (85%), um zu bestehen. Bei 4 oder mehr Fehlern gilt der Test als nicht bestanden.
4. **Detail-Auswertung:** Am Ende wird die genaue Anzahl der richtigen und falschen Antworten angezeigt, zusammen mit dem Status („Bestanden“ oder „Nicht bestanden“).
5. **E-Mail-Übermittlung:** Der Button öffnet das Mail-Programm mit einem formatierten Bericht (inkl. Name, Score und Einzelergebnissen) adressiert an **m.christel@realm-europe.de**.

```html
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Realm Germany – Vertriebsschulung: Modul 2</title>
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

/* Sofort-Feedback Klassen */
.qopt.correct{background:var(--green-light) !important;border-color:var(--green-mid) !important;color:#065F46 !important;font-weight:600}
.qopt.correct .qdot{background:var(--green-mid) !important;border-color:var(--green-mid) !important}
.qopt.wrong{background:#FEF2F2 !important;border-color:var(--red) !important;color:#7F1D1D !important}
.qopt.wrong .qdot{background:var(--red) !important;border-color:var(--red) !important}
.qopt.locked{pointer-events:none;opacity:0.7}
.qopt.locked.correct, .qopt.locked.wrong{opacity:1}

.qfb{display:none;font-size:12px;line-height:1.6;padding:.55rem .875rem;border-radius:8px;margin-top:.4rem}
.qfb.show{display:block}
.qfb.ok{background:var(--green-light);color:#065F46;border:1px solid #A7F3D0}
.qfb.err{background:#FEF2F2;color:#7F1D1D;border:1px solid #FECACA}

/* Ergebnis-Auswertung */
.quiz-score{display:none;background:#fff;border-radius:10px;padding:2rem;text-align:center;margin-top:1.5rem;border:2px solid var(--border)}
.quiz-score.show{display:block}
.quiz-score .qs-val{font-size:44px;font-weight:800;color:var(--blue-deep);margin-bottom:0.25rem}
.quiz-score .qs-details{font-size:15px;color:var(--muted);margin-bottom:0.75rem}
.quiz-score .qs-lbl{font-size:18px;color:var(--text);margin-bottom:1.5rem;font-weight:800;text-transform:uppercase}

.name-row{display:flex;align-items:center;gap:12px;background:#fff;border:1.5px solid var(--border);border-radius:10px;padding:.75rem 1rem;margin-bottom:1.5rem}
.name-row label{font-size:14px;font-weight:700;white-space:nowrap;color:var(--blue-deep)}
.name-row input{flex:1;border:none;background:transparent;font-size:14px;color:var(--text);outline:none;font-weight:600}
.name-row input::placeholder{color:var(--muted);font-weight:400}

.mail-note{font-size:13.5px;color:var(--muted);margin-top:1.25rem;padding:0.75rem;background:var(--subtle);border-radius:8px;border:1px solid var(--border)}
.mail-note strong{color:var(--blue-deep)}

.nav-btns{display:flex;justify-content:space-between;margin-top:2rem;gap:10px}
.btn{padding:.65rem 1.4rem;border-radius:10px;border:1.5px solid var(--border);background:#fff;cursor:pointer;font-size:14px;font-weight:700;color:var(--text);transition:all .2s;display:inline-flex;align-items:center;gap:6px}
.btn:hover{background:var(--subtle);border-color:#9CA3AF}
.btn-primary{background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;border-color:transparent}
.sect-progress{background:var(--border);border-radius:8px;height:5px;margin-bottom:2rem}
.sect-progress-fill{background:linear-gradient(90deg,var(--blue-deep),var(--green-dark));border-radius:8px;height:5px;transition:width .5s}
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
    <p>Die größte Hürde in der B2B-Telefonakquise ist das Vorzimmer (Sekretariat, Assistenz oder Zentrale), auch bekannt als der „Gatekeeper“. Wer hier versucht, sein Produkt oder seine Dienstleistung zu verkaufen, scheitert in 98% der Fälle.</p>

    <div class="hl"><strong>Das strategische Mindset:</strong><br>Der Gatekeeper ist kein Feind, sondern ein potenzieller Verbündeter und Navigator. Ihr Ziel am Telefon ist niemals der Abschluss, sondern ausschließlich die Weiterleitung zum Entscheider oder die Vereinbarung eines qualifizierten Erstgesprächs.</div>

    <h3>Die psychologischen Hebel zum Überwinden des Vorzimmers</h3>
    <p>Um die Assistenz zu passieren, nutzen Top-Vertriebler linguistische Muster, die Augenhöhe, Dringlichkeit und bestehende Relevanz signalisieren.</p>

    <h4>1. Die „Status- und Annahme-Methode“ (Verbindlichkeit statt Betteln)</h4>
    <div class="script-box">
      <strong>Falsch:</strong> „Guten Tag, mein Name ist Müller von der Realm Germany. Ich wollte fragen, ob eventuell der Herr Geschäftsführer Schneider zu sprechen ist? Wir vertreiben hocheffiziente R290-Wärmepumpen...“<br>
      <span style="color:#F87171">→ Ergebnis: „Bitte schicken Sie uns eine Info-Mail...“ (Aufgelegt).</span><br><br>
      <strong>Richtig:</strong> „Guten Tag, Müller mein Name, Realm Germany. Frau [Name der Assistenz], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“
    </div>

    <h4>2. Der „Prozess-Grund“ statt „Produkt-Grund“</h4>
    <div class="script-box">
      <strong>Assistenz:</strong> „Worum geht es denn bei dem Anruf? Er ist gerade sehr beschäftigt.“<br>
      <strong>Vertriebs-Profi:</strong> „Es geht um die strategische Neuausrichtung Ihrer Projektkapazitäten und die Absicherung gegen die neuen Lieferengpässe im Bereich der R290-Großprojekte für das kommende Quartal. Herr Schneider erwartet hierzu Informationen bezüglich unseres Gebietsschutzes im Raum Bayern. Stellen Sie mich bitte durch?“
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
    <p>Im modernen B2B-Vertrieb ist Hardselling per Direktnachricht tot. Beim Social Selling geht es primär um den digitalen Beziehungsaufbau (Nutzenstiftung vor Umsatzforderung).</p>

    <div class="hl"><strong>Die goldene Regel des Social Selling:</strong><br>„Give before you take.“ Erst Mehrwert liefern, Sichtbarkeit erzeugen und Vertrauen aufbauen – erst danach folgt das unverbindliche Gesprächsangebot.</div>

    <h3>Der 4-Schritte-Fahrplan zur Lead-Generierung via Social Media</h3>
    <h4>Schritt 1: Profil-Optimierung</h4>
    <div class="script-box">
      <strong>Muster-Slogan für dein Profil:</strong><br>
      „Ich helfe SHK-Fachbetrieben und Projektentwicklern dabei, R290-Wärmepumpen-Großprojekte ohne lange Lieferzeiten umzusetzen und sich exklusiven Gebietsschutz zu sichern.“
    </div>

    <h4>Schritt 2: Das „Digitale Einschleichen“ (Die 3-Touchpoint-Regel)</h4>
    <p>Vor der Vernetzungsanfrage: Profil besuchen (Touchpoint 1), Beitrag liken (Touchpoint 2), einen qualifizierten Fachkommentar hinterlassen (Touchpoint 3).</p>
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
    <p>Die wertvollste Ressource eines B2B-Vertrieblers ist seine Arbeitszeit. Das BANT-Framework schützt dich vor Zeitdieben und trennt die Spreu vom Weizen.</p>

    <div class="tbl-wrap">
      <table>
        <thead><tr><th>BANT-Kriterium</th><th>Bedeutung im B2B-Kontext</th><th>Strategische Qualifizierungs-Fragen</th></tr></thead>
        <tbody>
          <tr><td><strong>B</strong>udget</td><td>Verfügt das Unternehmen über die finanziellen Mittel für unsere Premium-Lösung?</td><td>„Welcher finanzielle Rahmen ist für diese Projektphase freigegeben?“</td></tr>
          <tr><td><strong>A</strong>uthority</td><td>Spreche ich mit dem echten Entscheider mit Unterschriftenvollmacht?</td><td>„Wer ist außer Ihnen noch an der finalen Freigabe beteiligt?“</td></tr>
          <tr><td><strong>N</strong>eed</td><td>Hat das Unternehmen ein ungelöstes, akutes Problem (Lieferzeiten, F-Gase)?</td><td>„Was passiert, wenn Sie das Lieferzeitproblem in 3 Monaten nicht gelöst haben?“</td></tr>
          <tr><td><strong>T</strong>imeline</td><td>Wann genau soll die Umsetzung oder der Kauf erfolgen?</td><td>„Bis wann muss die Anlage spätestens im Gebäude betriebsbereit sein?“</td></tr>
        </tbody>
      </table>
    </div>
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
    <p>20 hochspezifische Fachfragen zur Neukundenakquise. Zum Bestehen der Zertifizierung sind mindestens <strong>17 von 20 Fragen (85%)</strong> korrekt zu beantworten (maximal 3 Fehler erlaubt).</p>
  </div>

  <div class="quiz-box">
    <h3>🎯 Modul 2 Abschlussprüfung – Akquise-Kompetenz</h3>
    <div class="qsub">Realm Zertifikat · Modul 2 · 20 Praxisfragen</div>

    <div class="name-row">
      <label for="qename">👤 Absolvent Name:</label>
      <input type="text" id="qename" placeholder="Vor- und Nachname eingeben (Pflichtfeld) …" />
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">1. Was ist das primäre, strategische Ziel eines Kaltanrufs (Cold Call) im B2B-Bereich?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Der direkte Verkauf unseres Produkts oder der Abschluss eines Rahmenvertrags am Telefon.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Die Vereinbarung eines qualifizierten Erstgesprächs oder die Weiterleitung zum tatsächlichen Entscheider.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Das bloße Sammeln von allgemeinen E-Mail-Adressen für den Marketing-Newsletter.</button>
      <div class="qfb ok">✓ Korrekt! Ein B2B-Investitionsprodukt lässt sich nicht blind im ersten Telefonat verkaufen. Ziel ist ausschließlich der nächste Prozessschritt (Termin).</div>
      <div class="qfb err">✗ Falsch! Ein Direktverkauf per Kaltanruf ist im B2B-Umfeld unrealistisch. Das Ziel ist die Terminvereinbarung.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">2. Warum scheitern die meisten Vertriebler beim Versuch, den Gatekeeper (Assistenz) zu passieren?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil sie versuchen, der Assistenz das Produkt zu verkaufen, anstatt einen geschäftswichtigen Prozess-Grund zu nennen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil die Assistenz generell keine Anrufe durchstellt, unabhängig von der Wichtigkeit.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil sie den Firmennamen am Telefon zu laut aussprechen.</button>
      <div class="qfb ok">✓ Korrekt! Wer im Vorzimmer pitcht, fliegt raus. Die Assistenz ist darauf geschult, Werbe-Pitches sofort zu blockieren.</div>
      <div class="qfb err">✗ Falsch! Die Assistenz blockiert gezielt Verkaufsgespräche. Wer ein Prozess-Thema auf Augenhöhe nennt, wird durchgestellt.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">3. Welche Formulierung strahlt im Vorzimmer die meiste „Augenhöhe und Verbindlichkeit“ aus?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Guten Tag, dürfte ich vielleicht ganz kurz mit Herrn Schneider sprechen, falls er gerade Zeit hat?“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Hallo, ich wollte mal nachhören, wer bei Ihnen für das Thema Heizung zuständig ist.“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Guten Tag, Müller mein Name, Realm Germany. Frau [Name], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“</button>
      <div class="qfb ok">✓ Korrekt! Diese Formulierung verzichtet auf Bittsteller-Floskeln und signalisiert eine geschäftliche Selbstverständlichkeit.</div>
      <div class="qfb err">✗ Falsch! Die Optionen A und B positionieren dich sofort als unbedeutenden Bittsteller.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">4. Was versteht man im Telefonmarketing unter einem „Prozess-Grund“?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Die ausführliche Erklärung der technischen Funktionsweise einer R290-Wärmepumpe.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ein geschäftliches Thema auf Management-Ebene (z.B. Planungskonflikte, Marktveränderungen), das die Relevanz des Anrufs begründet.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Den rechtlichen Grund für ein laufendes Gerichtsverfahren gegen einen Wettbewerber.</button>
      <div class="qfb ok">✓ Korrekt! Ein Prozess-Grund knüpft an die aktuellen strategischen Herausforderungen des Entscheiders an, nicht an die Merkmale deines Produkts.</div>
      <div class="qfb err">✗ Falsch! Ein Prozess-Grund ist kein Produktfeature, sondern ein strategisches Management-Thema.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">5. Wie reagiert ein Profi auf den Assistenz-Vorwand: „Schicken Sie uns einfach eine Info-Mail an info@...“?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Er stimmt zu, fordert aber die persönliche Mailadresse oder Durchwahl des Entscheiders ein, da das Dokument vertrauliche Konditionen enthält.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Er legt sofort frustriert auf, da info@-Mails niemals gelesen werden.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Er fängt an, der Assistenz am Telefon wütend zu widersprechen.</button>
      <div class="qfb ok">✓ Korrekt! Damit nutzt du den Vorwand als Hebel, um an qualifizierte Kontaktdaten des Entscheiders zu gelangen.</div>
      <div class="qfb err">✗ Falsch! Einfaches Nachgeben führt in die info@-Blackbox. Nutze das Argument der Personalisierung/Vertraulichkeit.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">6. Was ist das goldene Gesetz beim Social Selling über LinkedIn und Xing?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Möglichst viele Kontakte pro Tag per automatisiertem Bot anschreiben und sofort das Angebot mitsenden.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Sein Profil rein privat nutzen und geschäftliche Themen komplett heraushalten.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Erst vertrauensvollen Beziehungsaufbau betreiben und Mehrwert stiften, bevor man ein Angebot platziert.</button>
      <div class="qfb ok">✓ Korrekt! „Hardselling“ in der ersten Nachricht verbrennt im modernen B2B-Vertrieb wertvolle Leads.</div>
      <div class="qfb err">✗ Falsch! Spamming führt zu Blockaden. Social Selling basiert auf digitalem Vertrauensaufbau.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">7. Wie sollte der Profil-Slogan (Headline) eines B2B-Vertrieblers im Idealfall aufgebaut sein?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Als tabellarischer Lebenslauf mit allen bisherigen Arbeitgebern und Notendurchschnitten.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Als Nutzen-Formel, die der Zielgruppe sofort zeigt, welches konkrete Problem du für sie löst.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Möglichst kryptisch und geheimnisvoll, damit der Kunde nachfragen muss.</button>
      <div class="qfb ok">✓ Korrekt! Dein Slogan muss wie die Überschrift einer Landingpage wirken: Problem benennen, Lösung aufzeigen.</div>
      <div class="qfb err">✗ Falsch! Dein Profil ist kein Lebenslauf für Personalvermittler, sondern ein Werkzeug zur Lead-Gewinnung.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">8. Was besagt die „3-Touchpoint-Regel“ vor dem Absenden einer Vernetzungsanfrage?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Dass man vor der Kontaktaufnahme das Profil des Leads besucht, einen Beitrag von ihm liket und einen qualifizierten Fachkommentar hinterlässt.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Dass man den Lead an drei aufeinanderfolgenden Tagen exakt um 12:00 Uhr anrufen muss.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Dass man drei unterschiedliche E-Mail-Adressen des Zielunternehmens anschreibt.</button>
      <div class="qfb ok">✓ Korrekt! Dadurch erzeugst du psychologische Vertrautheit. Dein Name ist dem Entscheider bereits positiv aufgefallen.</div>
      <div class="qfb err">✗ Falsch! Touchpoints im Social Selling sind digitale Interaktionen wie Profilbesuche, Likes und Kommentare.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">9. Wofür steht das Akronym „BANT“ im Qualifizierungsprozess von B2B-Leads?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Business, Action, Negotiation, Trust</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Budget, Authority, Need, Timeline</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Buying-Power, Agreement, Network, Target</button>
      <div class="qfb ok">✓ Korrekt! Das BANT-Framework prüft Finanzen, Entscheidungsbefugnis, realen Bedarf und den zeitlichen Rahmen.</div>
      <div class="qfb err">✗ Falsch! BANT ist der weltweite Standard für Budget, Authority, Need und Timeline.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">10. Du sprichst mit einem Projektleiter, der von einer Lösung begeistert ist, aber keine finanzielle Unterschriftenberechtigung besitzt. Welches BANT-Kriterium ist gefährdet?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Need (Bedarf)</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Timeline (Zeithorizont)</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Authority (Entcheidungskompetenz)</button>
      <div class="qfb ok">✓ Korrekt! Ohne die Einbindung des echten Budget-Entscheiders (Authority) bleibt das Projekt in der Schwebe.</div>
      <div class="qfb err">✗ Falsch! Begeisterung zeigt zwar den „Need“, aber ohne Unterschriftenberechtigung fehlt die „Authority“.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">11. Mit welcher Frage qualifizierst du das Kriterium „Need“ (Bedarf/Schmerz) am effektivsten?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Welche konkreten wirtschaftlichen Folgen hat es für Ihr Unternehmen, wenn sich Ihre aktuellen Bauprojekte durch Lieferengpässe verzögern?“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Gefällt Ihnen die Farbe unseres Außengehäuses auf einer Skala von 1 bis 10?“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Wie viele Mitarbeiter beschäftigt Ihre Buchhaltungsabteilung aktuell?“</button>
      <div class="qfb ok">✓ Korrekt! Diese Frage deckt den realen, finanziellen Schmerzpunkt auf und verwandelt das Produkt in ein „Must-have“.</div>
      <div class="qfb err">✗ Falsch! Nur Fragen nach Schmerzen, Engpässen und den Folgen von Untätigkeit qualifizieren den echten Bedarf.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">12. Was charakterisiert ein sogenanntes „C-Lead“ im Vertriebsalltag?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ein Lead mit unbegrenztem Budget und sofortigem Kaufinteresse beim Geschäftsführer.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ein Mitbewerber, der versucht, unsere Vertriebsmitarbeiter abzuwerben.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Ein anfragendes Unternehmen ohne echtes Budget, ohne akuten Leidensdruck, das lediglich Preise abgreifen will.</button>
      <div class="qfb ok">✓ Korrekt! C-Leads kosten enorm viel Zeit und bringen keinen Umsatz. Sie müssen konsequent disqualifiziert werden.</div>
      <div class="qfb err">✗ Falsch! C-Leads sind reine Zeitdiebe ohne Kaufabsicht oder Budget. Sie sollten aussortiert werden.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">13. Was versteht man im B2B-Vertrieb unter dem Begriff „Lead Nurturing“?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Das aggressive Drängen eines Kunden zum schnellen Vertragsabschluss am Telefon.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Das strategische Begleiten und Informieren eines Leads (z.B. B-Leads) mit relevantem Mehrwert, bis dieser kaufbereit ist.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Die automatische Löschung von ungenutzten Kontaktdaten aus dem CRM-System.</button>
      <div class="qfb ok">✓ Korrekt! Nurturing bedeutet „Pflege“. Du fütterst den Interessenten so lange mit Content, bis seine „Timeline“ reif ist.</div>
      <div class="qfb err">✗ Falsch! Lead Nurturing bezeichnet die gezielte Weiterentwicklung von Leads durch kontinuierliche Nutzenstiftung.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">14. Warum ist das Erfragen der „Timeline“ (Zeithorizont) so kritisch für deine Provisionsplanung?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil ein Lead mit akutem Bedarf, das aber erst in 24 Monaten kaufen will, dir im aktuellen Quartal keinen Umsatz bringt.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil die Timeline festlegt, wie lange das Telefonat maximal dauern darf.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil die Timeline gesetzlich im Bundesdatenschutzgesetz verankert ist.</button>
      <div class="qfb ok">✓ Korrekt! Nur Leads mit einer nahen Timeline sichern dir kurzfristige Vertriebserfolge und Abschlüsse.</div>
      <div class="qfb err">✗ Falsch! Ohne zeitliche Komponente investierst du eventuell zu viel Energie in Projekte, die erst in Jahren realisiert werden.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">15. Ein potenzieller Kunde sagt: „Wir arbeiten bereits seit 15 Jahren glücklich mit unserem Lieferanten zusammen.“ Wie reagiert der Profi?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Er erklärt dem Kunden, warum sein bisheriger Lieferant technisch minderwertig ist.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Er lobt die Treue und positioniert Realm rein als strategische Zweitlieferanten-Option zur Absicherung gegen Marktengpässe.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Er entschuldigt sich höflich für die Störung und löscht den Kontakt sofort.</button>
      <div class="qfb ok">✓ Korrekt! Ein Frontalangriff auf bestehende Partner erzeugt Reaktanz. Die Positionierung als Sicherheitsnetz öffnet Türen.</div>
      <div class="qfb err">✗ Falsch! Schlechtreden erzeugt Abwehr. Biete dich stattdessen ohne Wechseldruck als Risikoabsicherung (Backup) an.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">16. Welches Verhalten signalisiert in den ersten Sekunden eines Telefonats psychologisch „Mangel an Augenhöhe“?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ein ruhiges Sprechtempo und eine feste, tiefe Stimmlage.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Das direkte Nennen des eigenen Namens und des Unternehmens ohne Umschweife.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Die Verwendung von Rechtfertigungen wie: „Ich störe Sie nur ganz ungern, aber ich hätte eine kurze Frage...“</button>
      <div class="qfb ok">✓ Korrekt! Entschuldigungen im Opener deuten darauf hin, dass deine Zeit weniger wert ist als die des Gegenübers.</div>
      <div class="qfb err">✗ Falsch! Wer sich für seinen Anruf entschuldigt, wertet seinen eigenen geschäftlichen Status sofort ab.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">17. Was versteht man unter dem Begriff „Social Selling Index (SSI)“ bei LinkedIn?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Eine Metrik von LinkedIn, die misst, wie effektiv du deine professionelle Marke aufbaust, die richtigen Personen findest und Beziehungen pflegst.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Die Anzahl der Werbebanner, die ein Nutzer pro Monat auf der Plattform schaltet.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Das Verhältnis zwischen gelikten Beiträgen und geschriebenen Direktnachrichten.</button>
      <div class="qfb ok">✓ Korrekt! Ein hoher SSI korreliert statistisch nachweisbar mit einem höheren Erfolg bei der digitalen Neukundenakquise.</div>
      <div class="qfb err">✗ Falsch! Der SSI ist LinkedIns Gradmesser für die Qualität deines Netzwerk- und Markenaufbaus.</div>
    </div>

    <div class="qitem" data-correct="2">
      <div class="qt">18. Warum ist die Frage „Haben Sie dafür ein Budget?“ im frühen B2B-Erstgespräch oft unstrategisch?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil sie laut Datenschutzgrundverordnung (DSGVO) in Deutschland verboten ist.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil Kunden bei direkter Abfrage reflexartig blocken oder behaupten, kein Geld zu haben, um Verhandlungsspielraum zu wahren.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil das Budget im B2B-Bereich grundsätzlich erst nach der Lieferung verhandelt wird.</button>
      <div class="qfb ok">✓ Korrekt! Frage stattdessen nach Rahmenbedingungen oder bereits bewilligten Fördermitteln, um den finanziellen Rahmen weicher abzufragen.</div>
      <div class="qfb err">✗ Falsch! Direktes Fragen nach Geld erzeugt Abwehr. Besser ist das indirekte Abklopfen von genehmigten Projektkorridoren.</div>
    </div>

    <div class="qitem" data-correct="3">
      <div class="qt">19. Ein Lead erfüllt Budget, Bedarf und Timeline perfekt, aber du verhandelst ausschließlich mit dem stellvertretenden Einkäufer ohne finale Freigabemacht. Was ist dein nächster Schritt?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Das Angebot sofort schreiben und hoffen, dass es irgendwie durchgewinkt wird.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Den Kontakt sofort abbrechen, da der Einkäufer nicht der Hauptentscheider ist.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Den Einkäufer zum internen Verbündeten machen und vorschlagen, den Hauptentscheider (z.B. Geschäftsführer) im nächsten Call hinzuzuziehen.</button>
      <div class="qfb ok">✓ Korrekt! So umgehst du die Blockade charmant, ohne den Einkäufer zu übergehen oder zu brüskieren.</div>
      <div class="qfb err">✗ Falsch! Den Einkäufer zu übergehen beschädigt den Deal. Nutze ihn als Brücke, um die echte „Authority“ an den Tisch zu holen.</div>
    </div>

    <div class="qitem" data-correct="1">
      <div class="qt">20. Welcher Hebel erhöht die Erfolgsquote (Conversion Rate) bei der Kaltakquise am Telefon nachhaltig?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Die präzise Vorqualifizierung der Ziel-Firmenliste vor dem ersten Anruf, statt wahllos Nummern aus dem Telefonbuch zu wählen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Das Sprechen in extrem hoher Lautstärke, um Dominanz zu beweisen.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Möglichst ohne Punkt und Komma zu reden, damit der Angerufene nicht dazwischensprechen kann.</button>
      <div class="qfb ok">✓ Korrekt! Je besser die Zielliste (z.B. Fokus auf Fachbetriebe im passenden PLZ-Gebiet mit Großprojekt-Historie), desto höher die Trefferquote im Gespräch.</div>
      <div class="qfb err">✗ Falsch! Monologe oder Gebrüll zerstören das Telefonat. Erfolg basiert auf Zielgruppenrelevanz und Vorbereitung.</div>
    </div>

    <button class="btn btn-primary" style="width:100%; justify-content:center; margin-top:1.5rem; padding: 1rem;" onclick="finishAndEvaluate()">
      🎓 Prüfung abschließen &amp; Auswertung generieren
    </button>

    <div id="resultBox" class="quiz-score">
      <div class="qs-val" id="scoreVal">0 / 20</div>
      <div class="qs-details" id="scoreDetails">Richtig: 0 | Falsch: 0</div>
      <div class="qs-lbl" id="scoreLbl">Prüfung nicht bestanden.</div>
      <p id="resultText"></p>
      
      <div id="mailNote" class="mail-note"></div>
      
      <button id="sendMailBtn" class="btn btn-primary" style="margin-top: 1.25rem; display:none; width: 100%; justify-content: center;" onclick="sendResultEmail()">
        ✉️ Ergebnisse jetzt an m.christel@realm-europe.de senden
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

// Globale Antworten-Verwaltung
let userAnswers = {}; 
const TOTAL_QUESTIONS = 20;

// Sofort-Feedback-Logik beim Klicken einer Option
function handleAnswer(optButton, chosenIdx) {
  const qitem = optButton.closest('.qitem');
  
  // Wenn diese Frage bereits beantwortet wurde, Klicks ignorieren
  if(qitem.classList.contains('answered')) return;
  
  const correctIdx = parseInt(qitem.getAttribute('data-correct'));
  const options = qitem.querySelectorAll('.qopt');
  const fbOk = qitem.querySelector('.qfb.ok');
  const fbErr = qitem.querySelector('.qfb.err');
  
  qitem.classList.add('answered');
  userAnswers[qitem.querySelector('.qt').textContent.substring(0,10)] = {
    chosen: chosenIdx,
    correct: correctIdx,
    text: optButton.textContent.trim()
  };

  // Optionen sperren und einfärben
  options.forEach((opt, idx) => {
    opt.classList.add('locked');
    const currentIdx = idx + 1;
    
    if(currentIdx === correctIdx) {
      opt.classList.add('correct'); // Richtige Antwort immer grün einfärben
    }
  });

  if (chosenIdx === correctIdx) {
    optButton.classList.add('correct');
    fbOk.classList.add('show');
  } else {
    optButton.classList.add('wrong'); // Falsch gewählte Antwort rot einfärben
    fbErr.classList.add('show');
  }
}

// Variablen für E-Mail-Inhalt
let finalCorrect = 0;
let finalWrong = 0;
let globalName = "";
let emailReportText = "";

function finishAndEvaluate() {
  globalName = document.getElementById('qename').value.trim();
  if(!globalName) {
    alert("Bitte tragen Sie zuerst Ihren Vor- und Nachnamen oben im Prüfungsfeld ein.");
    document.getElementById('qename').focus();
    return;
  }

  const qItems = document.querySelectorAll('.qitem');
  let unansweredCount = 0;
  finalCorrect = 0;
  finalWrong = 0;
  let reportLines = "";

  qItems.forEach((item, idx) => {
    const correctIdx = parseInt(item.getAttribute('data-correct'));
    const options = item.querySelectorAll('.qopt');
    let selectedIdx = 0;
    let chosenText = "Keine Antwort";

    options.forEach((opt, oIdx) => {
      if(opt.classList.contains('wrong') || (opt.classList.contains('correct') && item.classList.contains('answered') && (oIdx+1) === correctIdx)) {
        if(opt.classList.contains('wrong') || opt.classList.contains('correct')) {
          // Finden heraus was angeklickt wurde
          // Falls korrekt, war das zeitgleich das richtige Element
        }
      }
    });

    // Strukturierter Durchlauf zur sicheren Ermittlung
    let answeredThis = false;
    options.forEach((opt, oIdx) => {
      if(opt.classList.contains('wrong')) {
        selectedIdx = oIdx + 1;
        chosenText = opt.textContent.trim();
        answeredThis = true;
      } else if(opt.classList.contains('correct') && !opt.classList.contains('locked')) {
        // Falls geklickt bevor Auswertung lief
      }
    });
    
    // Fallback falls korrekt geklickt wurde
    options.forEach((opt, oIdx) => {
      if(opt.classList.contains('correct') && opt.style.borderColor !== "") {
        // Hilfsmarker
      }
    });

    // Direkte Prüfung über den Status des Elements
    const fbOkVisible = item.querySelector('.qfb.ok.show');
    const fbErrVisible = item.querySelector('.qfb.err.show');

    if(fbOkVisible) {
      finalCorrect++;
      reportLines += `Frage ${idx+1}: RICHTIG\n`;
    } else if(fbErrVisible) {
      finalWrong++;
      reportLines += `Frage ${idx+1}: FALSCH\n`;
    } else {
      unansweredCount++;
      finalWrong++; // Unbeantwortet gilt als Fehler
      reportLines += `Frage ${idx+1}: NICHT BEANTWORTET\n`;
      
      // Falls noch nicht beantwortet, jetzt die richtige Lösung anzeigen
      item.classList.add('answered');
      options.forEach((opt, oIdx) => {
        opt.classList.add('locked');
        if((oIdx + 1) === correctIdx) opt.classList.add('correct');
      });
      item.querySelector('.qfb.err').classList.add('show');
    }
  });

  // Ergebnisbox befüllen und anzeigen
  const resultBox = document.getElementById('resultBox');
  const scoreVal = document.getElementById('scoreVal');
  const scoreDetails = document.getElementById('scoreDetails');
  const scoreLbl = document.getElementById('scoreLbl');
  const resultText = document.getElementById('resultText');
  const sendMailBtn = document.getElementById('sendMailBtn');
  const mailNote = document.getElementById('mailNote');

  resultBox.classList.add('show');
  scoreVal.textContent = `${finalCorrect} / 20`;
  scoreDetails.textContent = `Richtige Antworten: ${finalCorrect} | Falsche Antworten: ${finalWrong}`;

  // Maximal 3 Fehler erlaubt -> Mindestens 17 Richtig
  const passed = finalCorrect >= 17;
  
  if(passed) {
    scoreLbl.textContent = "🎉 Prüfung BESTANDEN!";
    scoreLbl.style.color = "var(--green-dark)";
    resultText.textContent = `Hervorragende Leistung, ${globalName}! Sie haben maximal 3 Fehler gemacht und sich erfolgreich als Realm B2B-Akquise-Profi zertifiziert.`;
  } else {
    scoreLbl.textContent = "❌ Prüfung NICHT BESTANDEN";
    scoreLbl.style.color = "var(--red)";
    resultText.textContent = `Schade, ${globalName}. Sie haben mehr als 3 Fehler gemacht. Für ein Bestehen der Schulung müssen mindestens 17 von 20 Fragen korrekt sein. Bitte gehen Sie die Skripte noch einmal durch.`;
  }

  // Generierung des exakten E-Mail-Bodys
  emailReportText = `Realm Germany Vertriebsschulung - Modul 2 (B2B-Akquise)\n`;
  emailReportText += `==================================================\n`;
  emailReportText += `Teilnehmer: ${globalName}\n`;
  emailReportText += `Ergebnis: ${finalCorrect} von 20 Punkten\n`;
  emailReportText += `Fehlerquote: ${finalWrong} von maximal 3 erlaubten Fehlern\n`;
  emailReportText += `Status: ${passed ? 'BESTANDEN' : 'NICHT BESTANDEN'}\n`;
  emailReportText += `Datum/Uhrzeit: ${new Date().toLocaleString('de-DE')}\n\n`;
  emailReportText += `Detaillierte Fragen-Übersicht:\n`;
  emailReportText += reportLines;
  emailReportText += `\n──────────────────────────────────────────────────\n`;
  emailReportText += `Automatisch generiert durch das Realm Zertifizierungssystem.`;

  // Aktivierung Mail-Button
  mailNote.innerHTML = `Die Auswertung wurde generiert. Bitte klicken Sie jetzt auf den Button unten, um Ihre Ergebnisse offiziell an <strong>m.christel@realm-europe.de</strong> zu übermitteln.`;
  sendMailBtn.style.display = "inline-flex";
  
  resultBox.scrollIntoView({behavior: 'smooth'});
}

function sendResultEmail() {
  const subject = encodeURIComponent(`Schulungsergebnis Modul 2: ${globalName} (${finalCorrect}/20 - ${finalCorrect >= 17 ? 'Bestanden' : 'Nicht bestanden'})`);
  const body = encodeURIComponent(emailReportText);
  window.location.href = `mailto:m.christel@realm-europe.de?subject=${subject}&body=${body}`;
}
</script>

</body>
</html>

```
