<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>B2B Kaltakquise &amp; Leadschulung – Realm Elite Training</title>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --dark-primary:#111827; /* Sattschwarz für maximalen Kontrast */
  --dark-muted:#4B5563;
  --bg-pure:#FFFFFF;      /* Reinweiß für absolute Lesbarkeit */
  --bg-subtle:#F9FAFB;
  --accent-grey:#E5E7EB;
  --accent-green:#059669;
  --accent-green-light:#ECFDF5;
  --accent-amber:#D97706;
  --accent-amber-light:#FFFBEB;
  --red:#DC2626;
}
html{scroll-behavior:smooth}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,sans-serif;background:var(--bg-pure);color:var(--dark-primary);line-height:1.65;padding-bottom:5rem}

/* ── HERO ── */
.hero{background:var(--bg-subtle);color:var(--dark-primary);padding:5rem 1.5rem;text-align:center;border-bottom:1px solid var(--accent-grey)}
.hero-badge{display:inline-block;background:var(--dark-primary);color:#fff;border-radius:4px;padding:6px 14px;font-size:11px;letter-spacing:1.5px;text-transform:uppercase;margin-bottom:1.5rem;font-weight:700}
.hero h1{font-size:clamp(32px,5vw,46px);font-weight:900;margin-bottom:1.5rem;line-height:1.2;color:var(--dark-primary);letter-spacing:-0.5px}
.hero h1 span{color:var(--accent-green);border-bottom:3px solid var(--accent-green)}
.hero p{font-size:17px;color:var(--dark-muted);max-width:850px;margin:0 auto;line-height:1.8;font-weight:500}

/* ── NAV ── */
.nav-wrap{background:var(--bg-pure);border-bottom:2px solid var(--dark-primary);position:sticky;top:0;z-index:100}
.nav-inner{max-width:1100px;margin:0 auto;padding:0 1rem;display:flex;gap:0;overflow-x:auto;scrollbar-width:none}
.nav-inner::-webkit-scrollbar{display:none}
.nav-item{flex-shrink:0;padding:1.4rem 1.5rem;font-size:14px;font-weight:800;color:var(--dark-muted);cursor:pointer;border-bottom:4px solid transparent;transition:all .15s;white-space:nowrap}
.nav-item:hover{color:var(--dark-primary);background:var(--bg-subtle)}
.nav-item.active{color:var(--dark-primary);border-bottom-color:var(--dark-primary)}

/* ── LAYOUT ── */
.page{max-width:1100px;margin:0 auto;padding:3rem 1rem}
.section{display:none}
.section.active{display:block}

/* ── CARDS & SECTIONS ── */
.card{background:var(--bg-pure);border:1px solid var(--accent-grey);padding:3rem 0;margin-bottom:3rem;border-bottom:3px solid var(--dark-primary)}
.card-title{font-size:28px;font-weight:900;margin-bottom:2rem;color:var(--dark-primary);display:flex;align-items:center;gap:14px;padding-bottom:1rem;border-bottom:1px solid var(--accent-grey)}
.card-title .ico{font-size:32px}
h3{font-size:22px;font-weight:900;margin:3rem 0 1.25rem;color:var(--dark-primary);letter-spacing:-0.3px}
h4{font-size:14px;font-weight:800;margin:2rem 0 0.5rem;color:var(--dark-primary);text-transform:uppercase;letter-spacing:1px}
p{font-size:16px;line-height:1.8;color:var(--dark-primary);margin-bottom:1.5rem}
ul,ol{padding-left:1.75rem;margin-bottom:1.5rem}
li{font-size:16px;line-height:1.8;color:var(--dark-primary);margin-bottom:0.75rem}

/* ── HIGHLIGHT BOXES ── */
.hl{background:var(--accent-green-light);border-left:4px solid var(--accent-green);padding:1.5rem;margin:2.5rem 0}
.hl strong{display:block;margin-bottom:6px;color:var(--dark-primary);font-size:16px;font-weight:800}

.mentor-box{background:var(--accent-amber-light);border-left:4px solid var(--accent-amber);padding:1.5rem;margin:2.5rem 0;color:var(--dark-primary)}
.mentor-box strong{display:block;margin-bottom:6px;color:var(--dark-primary);font-size:16px;font-weight:800}

/* ── SCRIPT BOX ── */
.script-box {background:var(--bg-subtle);color:var(--dark-primary);border:1px solid var(--accent-grey);padding:1.75rem;font-size:15px;margin:2rem 0;line-height:1.8;border-left:4px solid var(--dark-primary)}
.script-box strong {color:var(--dark-primary);font-size:13px;display:block;margin-bottom:0.75rem;text-transform:uppercase;letter-spacing:1px;font-weight:800}
.script-box .bad {color:var(--red);font-weight:700;display:block;margin-bottom:0.5rem}
.script-box .good {color:var(--accent-green);font-weight:700;display:block;margin-bottom:0.5rem}

/* ── TABLE ── */
.tbl-wrap{overflow-x:auto;margin:2.5rem 0;border:1px solid var(--accent-grey)}
table{width:100%;border-collapse:collapse;font-size:15px;color:var(--dark-primary)}
thead tr{background:var(--bg-subtle);border-bottom:2px solid var(--dark-primary)}
th{padding:14px 16px;text-align:left;font-weight:900;color:var(--dark-primary)}
td{padding:16px;border-bottom:1px solid var(--accent-grey);vertical-align:top;line-height:1.7}

/* ── QUIZ ── */
.quiz-box{background:var(--bg-pure);border:3px solid var(--dark-primary);padding:3rem 2rem;margin-top:3rem}
.quiz-box h3{font-size:26px;font-weight:900;margin-top:0;margin-bottom:0.5rem;color:var(--dark-primary)}
.quiz-box .qsub{font-size:14px;color:var(--dark-muted);margin-bottom:2.5rem;border-bottom:1px solid var(--accent-grey);padding-bottom:1rem;font-weight:600}
.qitem{margin-bottom:3rem;border-bottom:1px dashed var(--accent-grey);padding-bottom:2.5rem}
.qitem:last-of-type{border-bottom:none}
.qitem .qt{font-size:17px;font-weight:800;margin-bottom:1.25rem;line-height:1.6;color:var(--dark-primary)}

.qopt{display:flex;align-items:flex-start;gap:14px;background:var(--bg-pure);border:1px solid var(--accent-grey);padding:1rem 1.5rem;cursor:pointer;margin-bottom:12px;font-size:15px;color:var(--dark-primary);width:100%;text-align:left;line-height:1.6;transition:all .15s;font-weight:600}
.qopt:hover{border-color:var(--dark-primary);background:var(--bg-subtle)}
.qopt .qdot{width:18px;height:18px;border:2px solid var(--accent-grey);border-radius:50%;flex-shrink:0;margin-top:2px;position:relative}

/* Feedback-Zustände */
.qopt.correct{background:var(--accent-green-light) !important;border-color:var(--accent-green) !important;color:var(--dark-primary) !important;font-weight:800}
.qopt.correct .qdot{background:var(--accent-green) !important;border-color:var(--accent-green) !important}
.qopt.wrong{background:#FEF2F2 !important;border-color:var(--red) !important;color:var(--dark-primary) !important;font-weight:800}
.qopt.wrong .qdot{background:var(--red) !important;border-color:var(--red) !important}
.qopt.locked{pointer-events:none;opacity:0.5}
.qopt.locked.correct, .qopt.locked.wrong{opacity:1}

.qfb{display:none;font-size:14px;line-height:1.7;padding:1rem 1.25rem;margin-top:1rem;font-weight:700}
.qfb.show{display:block}
.qfb.ok{background:var(--accent-green-light);color:var(--dark-primary);border-left:4px solid var(--accent-green)}
.qfb.err{background:#FEF2F2;color:var(--dark-primary);border-left:4px solid var(--red)}

/* Auswertung */
.quiz-score{display:none;background:var(--bg-subtle);border:3px solid var(--dark-primary);padding:3rem 2rem;text-align:center;margin-top:3rem}
.quiz-score.show{display:block}
.quiz-score .qs-val{font-size:64px;font-weight:900;color:var(--dark-primary);margin-bottom:0.5rem}
.quiz-score .qs-details{font-size:16px;color:var(--dark-muted);margin-bottom:1.5rem;font-weight:700}
.quiz-score .qs-lbl{font-size:24px;color:var(--dark-primary);margin-bottom:1.5rem;font-weight:900;letter-spacing:0.5px}

.name-row{display:flex;align-items:center;gap:16px;background:var(--bg-pure);border:1px solid var(--dark-primary);padding:1rem 1.25rem;margin-bottom:2.5rem}
.name-row label{font-size:15px;font-weight:900;white-space:nowrap;color:var(--dark-primary)}
.name-row input{flex:1;border:none;background:transparent;font-size:16px;color:var(--dark-primary);outline:none;font-weight:700}
.name-row input::placeholder{color:var(--dark-muted);font-weight:500}

.mail-note{font-size:15px;color:var(--dark-primary);margin-top:2rem;padding:1.5rem;background:var(--bg-pure);border:1px solid var(--accent-grey);line-height:1.7;text-align:left}

.nav-btns{display:flex;justify-content:space-between;margin-top:3rem;gap:16px}
.btn{padding:1rem 2rem;border:1px solid var(--accent-grey);background:var(--bg-pure);cursor:pointer;font-size:15px;font-weight:800;color:var(--dark-primary);transition:all .15s;display:inline-flex;align-items:center;gap:8px}
.btn:hover{border-color:var(--dark-primary);background:var(--bg-subtle)}
.btn-primary{background:var(--dark-primary);color:#fff;border-color:var(--dark-primary)}
.btn-primary:hover{background:var(--dark-muted);border-color:var(--dark-muted);color:#fff}

.sect-progress{background:var(--accent-grey);zoom:1;height:5px;margin-bottom:3rem}
.sect-progress-fill{background:var(--dark-primary);height:5px;transition:width .4s}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">Realm Elite Training · Vertriebs-Mentorat</div>
  <h1>B2B Kaltakquise &amp; Leadschulung<br><span>Die Totale Markt-Dominanz</span></h1>
  <p>Durchschnittliche Verkäufer bitten um Termine. Die Vertriebselite steuert die Realität des Gegenübers. Diese Masterclass vermittelt die exakten Mechanismen, um das Vorzimmer zu dominieren, LinkedIn in ein präzises Instrument zur Inbound-Generierung zu verwandeln und Großprojekte eiskalt vorzuqualifizieren.</p>
</div>

<!-- NAV -->
<div class="nav-wrap">
  <div class="nav-inner">
    <div class="nav-item active" onclick="goSec(0)">1 · Cold Calling Meisterschaft</div>
    <div class="nav-item" onclick="goSec(1)">2 · Social Selling Imperium</div>
    <div class="nav-item" onclick="goSec(2)">3 · BANT Elite-Filter</div>
    <div class="nav-item" onclick="goSec(3)">4 · Zertifizierungs-Test (20 Q)</div>
  </div>
</div>

<div class="page">

<!-- SECTION 0: COLD CALLING -->
<div class="section active" id="sec0">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:25%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">📞</span>Kaltakquise (Cold Calling) &amp; die totale Vorzimmer-Dominanz</div>
    
    <div class="mentor-box">
      <strong>Strategisches Kernprinzip:</strong>
      Das Sekretariat (der Gatekeeper) ist keine Barriere, sondern ein Filter für unqualifizierte Marktteilnehmer. Wer als Bittsteller auftritt, wird abgewiesen. Wer mit der Tonalität und der unaufgeregten Selbstverständlichkeit der Management-Ebene agiert, öffnet Türen. Im Vorzimmer wird niemals das Produkt verkauft – dort wird ausschließlich der nächste Prozessschritt fixiert.
    </div>

    <h3>Die Psychologie des Gatekeeper-Rapports</h3>
    <p>Assistenzen der Geschäftsführung sind darauf konditioniert, Werbeanrufe innerhalb der ersten 3 Sekunden zu identifizieren und zu blockieren. Typische Trigger sind: Übertriebene Freundlichkeit, Unsicherheit, Rechtfertigungen („Ich hoffe, ich störe nicht...“) oder das sofortige Pitchen von Produktmerkmalen.</p>
    
    <p>Das Durchbrechen dieser Barriere erfordert den sogenannten <strong>Status-Rapport</strong>. Die eigene Tonalität orientiert sich nicht an der Assistenz, sondern an der des Geschäftsführers: Ruhig, bestimmt, geschäftsmäßig, fokussiert und absolut direkt.</p>

    <h3>Die linguistischen Werkzeuge in der Praxis</h3>
    
    <h4>1. Die "Status- und Annahme-Methode"</h4>
    <p>Es wird nicht um Erlaubnis gebeten. Das Telefonat wird als geschäftliche Notwendigkeit für das Zielunternehmen vorausgesetzt. Der Nachname und das Unternehmen werden flüssig genannt, gefolgt von einer klaren, höflichen Handlungsanweisung.</p>
    
    <div class="script-box">
      <strong>❌ Der fehlerhafte Ansatz:</strong>
      <span class="bad">„Ja hallo, mein Name ist Jan Müller von der Realm Germany. Ich hoffe, ich störe nicht? Ich wollte mal fragen, ob eventuell der Herr Geschäftsführer Schneider heute ganz kurz Zeit für mich hätte? Es geht um unsere neuen, hocheffizienten R290-Wärmepumpen...“</span>
      <em>Konsequenz:</em> „Schicken Sie uns bitte Informationen an info@...“ *Aufgelegt.*<br><br>
      <strong>🎯 Der Elite-Ansatz (Standard):</strong>
      <span class="good">„Guten Tag, Müller mein Name, Realm Germany. Frau [Name der Assistenz – falls bekannt], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“</span>
      <em>Psychologischer Hintergrund:</em> Keine Fragen, kein Zögern. Die Formulierung „bringen Sie mich bitte durch“ impliziert einen bereits bestehenden Kontext oder eine akute geschäftliche Relevanz.
    </div>

    <h4>2. Der „Prozess-Grund“ schlägt den „Produkt-Grund“</h4>
    <p>Fragt die Assistenz nach dem Grund (<em>„Worum geht es denn genau?“</em>), darf unter keinen Umständen das Produkt genannt werden. Sobald Begriffe wie „Wärmepumpe“ oder „Heizung“ fallen, erfolgt die sofortige Kategorisierung als austauschbarer Verkäufer.</p>
    
    <div class="script-box">
      <strong>❌ Der Fehler:</strong> <span class="bad">„Es geht um unsere neuen R290 Großwärmepumpen, die super Lieferzeiten haben...“</span><br><br>
      <strong>🎯 Die Lösung:</strong> <span class="good">„Es geht um die strategische Absicherung anstehender Großprojekte gegen die neuen F-Gase-Regulierungen und die Vermeidung von Planungsstopps im kommenden Quartal. Herr Schneider steuert diese Kapazitäten – stellen Sie mich bitte direkt durch?“</span>
    </div>

    <h4>3. Die info@-Blackbox elegant aushebeln</h4>
    <p>Beim Vorwand <em>„Schicken Sie uns Unterlagen an info@...“</em> wird dem Einwand formal zugestimmt, um Reaktanz zu vermeiden. Gleichzeitig wird er als Hebel genutzt, um den Kommunikationskanal zu personalisieren.</p>
    <div class="script-box">
      <strong>Gegenstrategie:</strong> <span class="good">„Das mache ich gern. Da es sich hierbei um die exklusiven Gebietsschutz-Dokumente und vertrauliche Projekt-Kennzahlen für die Region handelt, leite ich diese direkt an den persönlichen Tisch von Herrn Schneider weiter. Geben Sie mir dafür kurz seine direkte Durchwahl oder seine persönliche E-Mail-Adresse durch?“</span>
    </div>
  </div>

  <div class="nav-btns">
    <div></div>
    <button class="btn btn-primary" onclick="goSec(1)">Weiter: Social Selling-Imperium →</button>
  </div>
</div>

<!-- SECTION 1: SOCIAL SELLING -->
<div class="section" id="sec1">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:50%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🤝</span>Social Selling: Digitale Lead-Generierung auf Top-Niveau</div>
    
    <div class="mentor-box">
      <strong>Strategisches Kernprinzip:</strong>
      Massenhafte Copy-Paste-Nachrichten an Geschäftsführer verbrennen den Markt, ruinieren deine Reputation und landen im digitalen Papierkorb. Die Vertriebselite betreibt kein digitales „Klinkenputzen“, sondern <strong>Inbound-Prospecting</strong>. Wir transformieren dein LinkedIn-Profil von einer digitalen Visitenkarte in eine hochkonvertierende Landingpage. Das Ziel: Der Entscheider muss dich als unangefochtenen Branchen-Experten wahrnehmen, noch bevor du das erste Wort tippst.
    </div>

    <h3>Die 1. Säule: Das Landingpage-Profil (Die Nutzen-Formel)</h3>
    <p>Wenn ein Geschäftsführer, TGA-Fachplaner oder gewerblicher Bauträger auf dein Profil klickt, hast du exakt 4 Sekunden Zeit, um seine volle Aufmerksamkeit zu fesseln. Standard-Phrasen wie „Sales Manager bei Realm“ signalisieren sofort ein Verkaufsinteresse.</p>
    
    <div class="hl">
      <strong>Die Realm-Nutzen-Formel:</strong><br>
      Ich helfe [Zielgruppe] dabei, [großes Problem zu lösen] / [großes Ziel zu erreichen], ohne [größte Sorge/Einwand der Zielgruppe].
    </div>

    <div class="script-box">
      <strong>Musterbeispiele auf Weltklasse-Niveau:</strong><br><br>
      <span class="good">„Ich helfe TGA-Fachplanern dabei, R290-Wärmepumpen-Großprojekte absolut lieferfähig und rechtssicher zu projektieren – ohne unvorhergesehene Kostenexplosionen und langwierige Genehmigungsprozesse.“</span><br><br>
      <span class="good">„Wir sichern die KfW-Förderfähigkeit und termingerechte Fertigstellung von gewerblichen Neubauten durch skalierbare Dekarbonisierungs-Konzepte – ohne die typischen Lieferverzögerungen der Alt-Hersteller.“</span>
    </div>

    <h3>Die 2. Säule: Das digitale Prospecting (Die 3-Touchpoint-Regel)</h3>
    <p>Bevor du eine Vernetzungsanfrage sendest, nutzen wir den <strong>Mere-Exposure-Effekt</strong>, um gezielt psychologische Vertrautheit aufzubauen:</p>
    <ul>
      <li><strong>Touchpoint 1 (Tag 1) – Der Profilbesuch:</strong> Ein bewusster Besuch des Zielprofils generiert eine Benachrichtigung beim Entscheider. Dein Slogan arbeitet bereits als Teaser.</li>
      <li><strong>Touchpoint 2 (Tag 2) – Der strategische Like:</strong> Interagiere mit einem relevanten geschäftlichen Beitrag des Kontakts. Absolut ohne Verkaufsabsicht.</li>
      <li><strong>Touchpoint 3 (Tag 3) – Der Experten-Kommentar:</strong> Hinterlasse unter seinem Beitrag einen fachlich fundierten Kommentar.</li>
    </ul>

    <div class="script-box">
      <strong>Elite-Kommentarbeispiel:</strong><br>
      <span class="good">„Ein extrem spannender Ansatz bei diesem Großprojekt, Herr Dr. Schneider. Besonders der Umgang mit den Schallschutz-Auflagen im urbanen Raum zeigt, wie entscheidend vorausschauende Planung heute ist. Die Umstellung auf natürliche Kältemittel wird diesen Hebel noch massiv verstärken.“</span>
    </div>

    <h3>Die 3. Säule: Die qualifizierte Vernetzungsanfrage</h3>
    <p>Nachgelagert erfolgt die Vernetzung. Die Nachricht ist kurz, frei von Pitch-Elementen und knüpft direkt an die Interaktion an.</p>
    
    <div class="script-box">
      <strong>Muster-Skript (Bezug auf Beitrag):</strong><br>
      <span class="good">„Hallo Herr Dr. Schneider, Ihr jüngster Beitrag zum Thema Effizienz im Gewerbebau hat mich inspiriert – insbesondere Ihr Punkt bezüglich der Kältemittel-Umstellung im urbanen Raum. Ich begleite genau diesen Bereich (R290-Großprojekte) bei der Realm Germany und freue mich auf den fachlichen Austausch in meinem Netzwerk. Beste Grüße, Jan Müller“</span>
    </div>

    <h3>Der psychologische Übergang: „Chat-to-Call“-Prozess</h3>
    <p>Die Vertriebselite wartet 24 bis 48 Stunden nach Annahme, bevor sie über eine offene, strategische Frage die Konversation in ein Telefonat lenkt.</p>
    <div class="script-box">
      <strong>Die Schmerzpunkt-Validierung im Chat:</strong><br>
      <span class="good">„Vielen Dank für die Vernetzung, Herr Schneider. Ich sehe an Ihren Projekten, dass Sie Maßstäbe setzen. Sagen Sie mal aus der Praxis gesprochen: Spüren Sie bei Ihren Planungen bereits den Druck der Marktverknappung bei zertifizierten R290-Großgeräten, oder sind Ihre Lieferketten stabil?“</span>
    </div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(0)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(2)">Weiter: BANT Elite-Filter →</button>
  </div>
</div>

<!-- SECTION 2: BANT FILTER -->
<div class="section" id="sec2">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:75%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🎯</span>Rigorose Lead-Qualifizierung &amp; das BANT-Framework</div>
    
    <div class="mentor-box">
      <strong>Strategisches Kernprinzip:</strong>
      Deine Vertriebszeit ist die wertvollste Ressource. Top-Performer zeichnen sich dadurch aus, dass sie unqualifizierte Leads so schnell wie möglich identifizieren und aussortieren. Wer weder über das Budget noch über die nötige Entscheidungsmacht verfügt, darf den operativen Prozess nicht blockieren. Wir nutzen BANT als tiefenpsychologische Projektdiagnose.
    </div>

    <h3>Das BANT-Framework als strategischer Filter</h3>
    <p>Kunden neigen im Erstgespräch oft zu Schutzbehauptungen, um ihre Verhandlungsposition zu sichern oder Gratis-Consulting abzugreifen. Verwende diese präzisen, indirekten Fragetechniken:</p>

    <div class="tbl-wrap">
      <table>
        <thead>
          <tr>
            <th>Kriterium</th>
            <th>Vertriebliche Kernbedeutung</th>
            <th>Elite-Abfrage-Technik (Indirekt)</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>B - Budget</strong></td>
            <td>Verfügt das Unternehmen über die finanziellen Mittel für eine Premium-Lösung?</td>
            <td><span class="good">„Welcher finanzielle Korridor wurde von Ihrer Geschäftsführung für diese spezifische Projektphase bereits verbindlich allokiert?“</span></td>
          </tr>
          <tr>
            <td><strong>A - Authority</strong></td>
            <td>Sitzt der tatsächliche Entscheider (mit Unterschriftenvollmacht) am Tisch?</td>
            <td><span class="good">„Angenommen, unser Konzept überzeugt Sie vollständig: Wie sieht Ihr interner Freigabeprozess aus und welche Instanzen sind für die finale Unterschrift involviert?“</span></td>
          </tr>
          <tr>
            <td><strong>N - Need</strong></td>
            <td>Existiert ein akuter, wirtschaftlicher Schmerzpunkt (z.B. F-Gase-Vorgaben)?</td>
            <td><span class="good">„Welche konkreten Auswirkungen auf Ihre Genehmigungsfähigkeit im nächsten Quartal hat es, wenn wir das Thema Kältemittel-Umstellung jetzt nicht proaktiv lösen?“</span></td>
          </tr>
          <tr>
            <td><strong>T - Timeline</strong></td>
            <td>Wann ist der geplante Projekt- und Umsatzrealisierungs-Horizont?</td>
            <td><span class="good">„Damit wir die Produktionsslots im Werk sichern können: Zu welchem konkreten Stichtag muss die Anlage zwingend betriebsbereit am Netz sein?“</span></td>
          </tr>
        </tbody>
      </table>
    </div>

    <h3>Lead-Klassifizierung: Das Ampel-System</h3>
    <ul>
      <li><strong>A-Leads (Grün - Fokus 80%):</strong> Alle vier BANT-Kriterien sind positiv erfüllt. Akuter Bedarf, Budget vorhanden, Entscheider am Tisch, zeitnahe Umsetzung. Sofortiger Vor-Ort-Termin.</li>
      <li><strong>B-Leads (Gelb - Nurturing Pipeline):</strong> Bedarf und Budget vorhanden, jedoch liegt die Umsetzung weiter in der Zukunft oder der Freigabeprozess verzögert sich. Systematischer Content-Aufbau.</li>
      <li><strong>C-Leads (Rot - Disqualifikation):</strong> Kein Budget, kein realer Schmerzpunkt, keine Entscheidungsmacht. Diese Kontakte werden konsequent, aber professionell aussortiert.</li>
    </ul>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(1)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(3)">Weiter zum Elite-Zertifikats-Test →</button>
  </div>
</div>

<!-- SECTION 3: QUIZ -->
<div class="section" id="sec3">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:100%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🏆</span>Zertifizierungs-Prüfung – Level: Realm B2B-Closer</div>
    <p>Die Abschlussprüfung umfasst <strong>20 komplexe Praxisszenarien</strong> aus der Kaltakquise, dem Social Selling und der BANT-Qualifizierung. Um die Zertifizierung erfolgreich zu bestehen, sind <strong>mindestens 17 richtige Antworten</strong> erforderlich (maximal 3 Fehler). Jede Eingabe wird in Echtzeit evaluiert.</p>
  </div>

  <div class="quiz-box">
    <h3>🎯 Gesamtprüfung – B2B-Akquise &amp; Lead-Meisterschaft</h3>
    <div class="qsub">Realm Zertifikat · Module 1-3 · 20 Praxisfragen</div>

    <!-- NAMENS-EINGABE -->
    <div class="name-row">
      <label for="qename">👤 Name des Absolventen:</label>
      <input type="text" id="qename" placeholder="Trage hier deinen Vor- und Nachnamen ein (Pflichtfeld) …" />
    </div>

    <!-- QUESTION 1 -->
    <div class="qitem" data-correct="2">
      <div class="qt">1. Du greifst zum Hörer für einen Kaltanruf. Welches Mindset steuert dein Telefonat?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ich muss dem Kunden im Telefonat sofort alle technischen Vorteile der R290-Wärmepumpe erklären, damit er direkt kauft.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ich will nicht verkaufen. Mein einziges Ziel ist es, den nächsten logischen Prozessschritt (ein qualifiziertes Erstgespräch) zu vereinbaren.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Ich rufe an, um mich nett vorzustellen, damit man sich irgendwann an Realm erinnert.</button>
      <div class="qfb ok">✓ Korrekt! Wer am Telefon direkt das Produkt pitcht, scheitert an der Komplexität des B2B-Vertriebs. Es geht nur um den Termin!</div>
      <div class="qfb err">✗ Falsch! Ein Profi pitcht niemals das Produkt in der Kaltakquise, sondern ausschließlich den Termin.</div>
    </div>

    <!-- QUESTION 2 -->
    <div class="qitem" data-correct="1">
      <div class="qt">2. Warum blockieren 95% aller Assistenzen (Gatekeeper) herkömmliche Vertriebsmitarbeiter sofort ab?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil Verkäufer wie Bittsteller auftreten und versuchen, im Vorzimmer das Produkt zu pitchen, statt ein strategisches Thema zu nennen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil Assistenzen generell eine persönliche Abneigung gegen die Heizungsbranche haben.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil man Kaltanrufe gesetzlich immer sofort blockieren muss.</button>
      <div class="qfb ok">✓ Korrekt! Sobald du wie ein typischer Verkäufer klingst, greift der automatische Filtermechanismus des Vorzimmers.</div>
      <div class="qfb err">✗ Falsch! Das Vorzimmer filtert Verkäufer aus. Wer auf Augenhöhe mit einem Prozessgrund einsteigt, wird durchgestellt.</div>
    </div>

    <!-- QUESTION 3 -->
    <div class="qitem" data-correct="3">
      <div class="qt">3. Welche Tonalität und Formulierung bricht den Filter des Vorzimmers am effektivsten auf?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Schönen guten Tag, mein Name ist Müller von Realm Germany. Ich wollte mal ganz höflich anfragen, ob Herr Schneider eventuell fünf Minuten Zeit für mich hätte?“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Hallo, ich brauche mal den Chef für das Thema Heizungs-Einkauf. Wer ist das bei Ihnen?“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>(Ruhig, bestimmt) „Guten Tag, Müller mein Name, Realm Germany. Bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“</button>
      <div class="qfb ok">✓ Korrekt! Diese Formulierung strahlt absolute Chef-Ebene und die Selbstverständlichkeit eines bestehenden Kontextes aus.</div>
      <div class="qfb err">✗ Falsch! Option A ist reines Bittstellertum. Option B ist unprofessionell. Option C nutzt den Status-Rapport.</div>
    </div>

    <!-- QUESTION 4 -->
    <div class="qitem" data-correct="2">
      <div class="qt">4. Die Assistenz hakt nach: „Worum geht es denn bei dem Gespräch mit Herrn Schneider?“ Was antwortest du?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Es geht um unsere R290 Wärmepumpen, die wir kostengünstig und mit kurzen Lieferzeiten auf den Markt gebracht haben.“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Es geht um die strategische Neuausrichtung der Projektkapazitäten zur Vermeidung von Planungsstopps durch die neuen F-Gase-Regulierungen im kommenden Quartal.“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Das darf ich Ihnen leider nicht sagen, das ist streng geheim.“</button>
      <div class="qfb ok">✓ Korrekt! Du nennst einen hochrelevanten "Prozess-Grund" auf Management-Ebene, kein Produktfeature.</div>
      <div class="qfb err">✗ Falsch! Nennst du das Produkt (Option A), wirst du sofort abgewiesen. Du musst ein strategisches Management-Thema nennen.</div>
    </div>

    <!-- QUESTION 5 -->
    <div class="qitem" data-correct="1">
      <div class="qt">5. Der Gatekeeper sagt: „Bitte schicken Sie uns einfach eine Info-Mail an info@unternehmen.de.“ Deine Reaktion?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Mache ich sofort. Da die Unterlagen sensible Zahlen zum Gebietsschutz enthalten, richte ich sie persönlich an Herrn Schneider. Wie lautet seine direkte Durchwahl für Rückfragen?“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„In Ordnung, dann diktieren Sie mir kurz die info@-Adresse und ich schicke da eine Standard-Broschüre hin.“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Nein, an info@-Adressen schicke ich nichts, das liest doch sowieso kein Mensch bei Ihnen.“</button>
      <div class="qfb ok">✓ Korrekt! Du stimmst zu (Vermeidung von Reaktanz) und nutzt die Vertraulichkeit, um die info@-Blackbox zu umgehen.</div>
      <div class="qfb err">✗ Falsch! Wer die info@-Adresse akzeptiert, stirbt den virtuellen Vertriebstod. Nutze das Argument der Vertraulichkeit!</div>
    </div>

    <!-- QUESTION 6 -->
    <div class="qitem" data-correct="3">
      <div class="qt">6. Was bedeutet der Leitsatz „Give before you take“ im modernen Social Selling auf LinkedIn?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Dass wir dem Kunden vor dem Kauf Rabatte gewähren müssen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Dass man dem Kunden kostenlose Produktproben per Post schicken sollte.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Dass man zuerst digitale Aufmerksamkeit und echten fachlichen Mehrwert stiftet, bevor man ein Angebot platziert.</button>
      <div class="qfb ok">✓ Korrekt! Digitaler Beziehungsaufbau basiert auf Vertrauen. Hardselling in der ersten Nachricht verbrennt den Lead sofort.</div>
      <div class="qfb err">✗ Falsch! Es geht um Vertrauensaufbau durch Expertise und Interaktion, nicht um Rabatte.</div>
    </div>

    <!-- QUESTION 7 -->
    <div class="qitem" data-correct="2">
      <div class="qt">7. Welcher Profil-Slogan (Headline) zieht gewerbliche Bauträger und TGA-Planer magisch an?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Erfolgreicher Sales Manager bei Realm Germany – Ihr Partner für Heizungssysteme.“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Ich helfe TGA-Planern dabei, R290-Großprojekte lieferfähig umzusetzen – ohne Planungsrisiko und ohne lange Genehmigungszeiten.“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Experte für erneuerbare Energien, Motivation und B2B-Vertrieb.“</button>
      <div class="qfb ok">✓ Korrekt! Diese Headline formuliert den exakten Kundennutzen und löst ein reales Problem der Zielgruppe auf einen Blick.</div>
      <div class="qfb err">✗ Falsch! Option A und C beschreiben dich. Option B beschreibt die Lösung für den Kunden. Nur das zählt!</div>
    </div>

    <!-- QUESTION 8 -->
    <div class="qitem" data-correct="1">
      <div class="qt">8. Wie wendest du die „3-Touchpoint-Regel“ bei einem extrem wichtigen Wunschkunden auf LinkedIn an?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Profil besuchen, 24h später einen Beitrag von ihm liken, am Folgetag einen qualifizierten Fachkommentar hinterlassen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ihn an drei verschiedenen Tagen exakt um die gleiche Uhrzeit per Nachricht anschreiben.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Drei verschiedene Mitarbeiter des Einkaufs gleichzeitig im Chat kontaktieren.</button>
      <div class="qfb ok">✓ Korrekt! Dadurch erzeugst du subtile psychologische Vertrautheit (Mere-Exposure-Effekt), bevor du überhaupt anklopfst.</div>
      <div class="qfb err">✗ Falsch! Die Touchpoints müssen subtile Interaktionen auf der Plattform sein, kein Spam im Postfach.</div>
    </div>

    <!-- QUESTION 9 -->
    <div class="qitem" data-correct="2">
      <div class="qt">9. Wofür steht das BANT-Framework bei der strategischen Qualifizierung von Großprojekten?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Business, Action, Negotiations, Team-Size</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Budget, Authority, Need, Timeline</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Buying-Power, Agreement, Network, Target-Group</button>
      <div class="qfb ok">✓ Korrekt! Budget (Finanzen), Authority (Entscheider), Need (Bedarf/Schmerz) und Timeline (Zeithorizont).</div>
      <div class="qfb err">✗ Falsch! BANT ist die weltweite Elite-Formel für Budget, Authority, Need und Timeline.</div>
    </div>

    <!-- QUESTION 10 -->
    <div class="qitem" data-correct="3">
      <div class="qt">10. Du merkst im Gespräch, dass dein Ansprechpartner absolut begeistert ist, aber keine Freigabemacht besitzt. Welches Kriterium wackelt?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Need (Der Bedarf ist nicht vorhanden)</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Budget (Es ist kein Geld da)</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Authority (Es fehlt die echte Entscheidungskompetenz)</button>
      <div class="qfb ok">✓ Korrekt! Du sprichst mit einem "Sympathisanten", nicht mit dem Entscheider. Du musst die Authority an den Tisch holen.</div>
      <div class="qfb err">✗ Falsch! Begeisterung zeigt den Need. Was fehlt, ist die Unterschriftenvollmacht (Authority).</div>
    </div>

    <!-- QUESTION 11 -->
    <div class="qitem" data-correct="1">
      <div class="qt">11. Wie fragst du das Kriterium „Need“ (Schmerzpunkt) auf psychologischer Elite-Ebene ab?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Welche wirtschaftlichen Konsequenzen hat es für Ihr Projekt, wenn Ihr aktueller Lieferant die Fristen im Winter nicht einhalten kann?“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Haben Sie einen Bedarf an modernen Wärmepumpen von Realm Germany?“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Wie wichtig ist Ihnen das Thema Umweltschutz bei Ihren Gebäuden auf einer Skala von 1 bis 10?“</button>
      <div class="qfb ok">✓ Korrekt! Diese Frage führt dem Kunden das Risiko der Untätigkeit vor Augen und weckt das dringende Bedürfnis nach einer Lösung.</div>
      <div class="qfb err">✗ Falsch! Oberflächliche Fragen erzeugen keine Dringlichkeit. Du musst den Schmerz der Lieferverzögerung triggern.</div>
    </div>

    <!-- QUESTION 12 -->
    <div class="qitem" data-correct="3">
      <div class="qt">12. Was zeichnet ein gefährliches „C-Lead“ aus, das deine wertvolle Vertriebszeit stiehlt?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ein Lead, das sofort ein Angebot per Mail fordert und den Vertrag morgen unterschreiben will.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ein Mitbewerber, der vorgibt, ein Kunde zu sein, um unsere Preise zu spionieren.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Ein kontakt ohne Budget und ohne akuten Schmerz, der nur kostenlose Beratung und Preise abgreifen will.</button>
      <div class="qfb ok">✓ Korrekt! C-Leads sind Zeitdiebe. Ein wahrer Verkaufs-Profi sortiert sie sofort und konsequent aus.</div>
      <div class="qfb err">✗ Falsch! Kontakte ohne Budget und ohne echten Leidensdruck sind C-Leads. Sofort disqualifizieren!</div>
    </div>

    <!-- QUESTION 13 -->
    <div class="qitem" data-correct="2">
      <div class="qt">13. Was versteht man unter „Lead Nurturing“ bei B-Leads im B2B-Vertrieb?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Den Kunden jeden zweiten Tag anzurufen und massiven Druck aufzubauen, damit er endlich kauft.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Das strategische Begleiten und Füttern des Leads mit relevantem Experten-Content, bis seine Timeline reif für den Abschluss ist.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Das automatische Versenden von Weihnachtsgrüßen einmal im Jahr.</button>
      <div class="qfb ok">✓ Korrekt! Nurturing bedeutet "Pflege". Du bleibst durch Content und Mehrwert der unangefochtene Experte im Kopf des Kunden.</div>
      <div class="qfb err">✗ Falsch! Druck zerstört die Beziehung. Nurturing bedeutet kontinuierliche digitale Nutzenstiftung, bis die Timeline reif ist.</div>
    </div>

    <!-- QUESTION 14 -->
    <div class="qitem" data-correct="1">
      <div class="qt">14. Warum ist die exakte Qualifizierung der „Timeline“ entscheidend für dein Überleben im B2B-Vertrieb?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil ein Lead mit riesigem Bedarf, das aber erst in 3 Jahren baut, dir im aktuellen Geschäftsjahr keine Provision einbringt.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil die Timeline festlegt, wie schnell du deine Präsentation am Laptop abspielen musst.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil die Timeline regelt, wie lange die gesetzliche Garantie der Wärmepumpe läuft.</button>
      <div class="qfb ok">✓ Korrekt! Nur Leads mit einer absehbaren, akuten Timeline sichern deine Zielerreichung im laufenden Quartal.</div>
      <div class="qfb err">✗ Falsch! Ohne zeitliche Komponente investierst du kostbare Energie in Projekte, die erst in Jahren umsatzrelevant werden.</div>
    </div>

    <!-- QUESTION 15 -->
    <div class="qitem" data-correct="2">
      <div class="qt">15. Ein starker Lead sagt: „Wir arbeiten seit 20 Jahren perfekt mit unserem aktuellen Lieferanten zusammen.“ Wie konterst du?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>„Ihr Lieferant nutzt technisch veraltete Systeme. Sie sollten sofort wechseln!“</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>„Hervorragend. Treue ist im Markt selten. Wir wollen diesen Partner nicht ersetzen, sondern uns rein als strategischer Zweitlieferant zur Risikoabsicherung bei Lieferengpässen positionieren.“</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>„Schade, da kann man wohl nichts machen. Vielen Dank für das Gespräch.“</button>
      <div class="qfb ok">✓ Korrekt! Ein Frontalangriff erzeugt sofortige Abwehr (Reaktanz). Die Positionierung als Sicherheitsnetz/Backup öffnet die Tür spielend.</div>
      <div class="qfb err">✗ Falsch! Wer den bestehenden Partner schlechtredet, beleidigt die Entscheidung des Kunden. Biete dich stattdessen als Risikoabsicherung an.</div>
    </div>

    <!-- QUESTION 16 -->
    <div class="qitem" data-correct="3">
      <div class="qt">16. Welches psychologische Signal zerstört deinen Expertenstatus in den ersten Sekunden des Telefonats komplett?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Eine ruhige, tiefe Stimmlage und ein bewusst gewähltes Sprechtempo.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Das direkte Nennen des Grundes des Anrufs ohne Smalltalk-Floskeln.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Rechtfertigungen wie: „Ich störe Sie nur ganz ungern, ich weiß Ihr Tag ist stressig, aber dürfte ich vielleicht kurz...?“</button>
      <div class="qfb ok">✓ Korrekt! Wer sich für seine eigene Existenz entschuldigt, signalisiert sofort, dass seine Zeit weniger wert ist als die des Gegenübers.</div>
      <div class="qfb err">✗ Falsch! Entschuldigungen werten deinen Status massiv ab. Du rufst an, um ein Problem zu lösen – das ist keine Störung!</div>
    </div>

    <!-- QUESTION 17 -->
    <div class="qitem" data-correct="1">
      <div class="qt">17. Was misst der LinkedIn „Social Selling Index (SSI)“ und warum ist er für dich wichtig?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Er misst, wie professionell du deine Marke aufbaust, Kontakte filterst, Einblicke teilst und Beziehungen pflegst.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Er misst die Anzahl der privaten Likes, die du auf rein privaten Urlaubsbildern erhältst.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Er gibt an, wie viele Nachrichten du pro Stunde maximal verschicken darfst, bevor du blockiert wirst.</button>
      <div class="qfb ok">✓ Korrekt! Ein hoher SSI ist der statistische Beweis für ein perfekt optimiertes, digitales Vertriebs-Werkzeug.</div>
      <div class="qfb err">✗ Falsch! Der SSI ist LinkedIns interner Gradmesser für deine digitale Vertriebs-Effektivität und Netzwerk-Qualität.</div>
    </div>

    <!-- QUESTION 18 -->
    <div class="qitem" data-correct="2">
      <div class="qt">18. Warum scheitert die direkte Frage „Haben Sie dafür überhaupt das Budget?“ im frühen Erstgespräch fast immer?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Weil Fragen nach Finanzen im gewerblichen Vertrieb laut DSGVO streng verboten sind.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Weil Kunden reflexartig Mauern aufbauen und behaupten kein Geld zu haben, um ihre spätere Verhandlungsposition nicht zu schwächen.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Weil das Budget im B2B-Umfeld immer erst nach der vollständigen Lieferung festgelegt wird.</button>
      <div class="qfb ok">✓ Korrekt! Du musst den finanziellen Korridor immer elegant, indirekt und über bereits bewilligte Rahmen oder Fördermittel abfragen.</div>
      <div class="qfb err">✗ Falsch! Direkte Fragen nach Geld erzeugen sofortige Abwehr. Qualifiziere das Budget über indirekte Fragen nach Projektrahmen.</div>
    </div>

    <!-- QUESTION 19 -->
    <div class="qitem" data-correct="3">
      <div class="qt">19. Ein Projektleiter liebt Realm, hat aber keine Unterschriftenberechtigung. Wie ziehst du die „Authority“ strategisch hinzu?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ich übergehe den Projektleiter und rufe einfach direkt die Geschäftsführung an.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ich schreibe das Angebot für den Projektleiter und hoffe, dass er es intern irgendwie alleine durchbekommt.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Ich mache den Projektleiter zu meinem internen Verbündeten („Champion“) und schlage vor, die Geschäftsführung im nächsten Schritt gemeinsam fachlich abzusichern.</button>
      <div class="qfb ok">✓ Korrekt! Du nutzt deinen Champion als Hebel, um gemeinsam vor dem echten Entscheider aufzutreten, ohne Hierarchien zu verletzen.</div>
      <div class="qfb err">✗ Falsch! Option A verbrennt deinen Champion. Option B führt zu monatelangem Stillstand. Mache den Projektleiter zum Verbündeten!</div>
    </div>

    <!-- QUESTION 20 -->
    <div class="qitem" data-correct="1">
      <div class="qt">20. Welcher Hebel katapultiert deine Abschlussquote in der Telefonakquise radikal nach oben?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Die messerscharfe Vorqualifizierung der Ziel-Firmenliste nach Region und Projekt-Historie vor dem allerersten Anruf.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Möglichst laut und aggressiv zu sprechen, um das Gegenüber psychologisch einzuschüchtern.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Das Auswendiglernen von 50 verschiedenen, manipulativen Rhetorik-Tricks.</button>
      <div class="qfb ok">✓ Korrekt! Ein überragender Vertriebserfolg basiert zu 80% auf der perfekten Zielgruppe. Wer die richtige Liste telefoniert, gewinnt automatisch!</div>
      <div class="qfb err">✗ Falsch! Einschüchterung oder billige Tricks funktionieren im Millionen-Markt des B2B nicht. Erfolg basiert auf Relevanz und Vorbereitung.</div>
    </div>

    <!-- AUSWERTUNGS-BEREICH -->
    <button class="btn btn-primary" style="width:100%; justify-content:center; margin-top:2rem; padding: 1.25rem; font-size:16px;" onclick="finishAndEvaluate()">
      🎓 Prüfung abschließen &amp; Elite-Auswertung generieren
    </button>

    <div id="resultBox" class="quiz-score">
      <div class="qs-val" id="scoreVal">0 / 20</div>
      <div class="qs-details" id="scoreDetails">Richtig: 0 | Falsch: 0</div>
      <div class="qs-lbl" id="scoreLbl">Prüfung nicht bestanden.</div>
      <p id="resultText" style="font-size: 16px; font-weight: 500; margin-bottom: 1.5rem;"></p>
      
      <div id="mailNote" class="mail-note"></div>
      
      <button id="sendMailBtn" class="btn btn-primary" style="margin-top: 1.5rem; display:none; width: 100%; justify-content: center; padding: 1.1rem; font-size: 16px;" onclick="sendResultEmail()">
        ✉️ Ergebnisse jetzt offiziell an m.christel@realm-europe.de senden
      </button>
    </div>
  </div>
</div>

</div> <!-- /page -->

<script>
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

let userAnswers = {}; 
const TOTAL_QUESTIONS = 20;

function handleAnswer(optButton, chosenIdx) {
  const qitem = optButton.closest('.qitem');
  if(qitem.classList.contains('answered')) return;
  
  const correctIdx = parseInt(qitem.getAttribute('data-correct'));
  const options = qitem.querySelectorAll('.qopt');
  const fbOk = qitem.querySelector('.qfb.ok');
  const fbErr = qitem.querySelector('.qfb.err');
  
  qitem.classList.add('answered');

  options.forEach((opt, idx) => {
    opt.classList.add('locked');
    if((idx + 1) === correctIdx) {
      opt.classList.add('correct');
    }
  });

  if (chosenIdx === correctIdx) {
    optButton.classList.add('correct');
    fbOk.classList.add('show');
  } else {
    optButton.classList.add('wrong');
    fbErr.classList.add('show');
  }
}

let finalCorrect = 0;
let finalWrong = 0;
let globalName = "";
let emailReportText = "";

function finishAndEvaluate() {
  globalName = document.getElementById('qename').value.trim();
  if(!globalName) {
    alert("Bitte tragen Sie zuerst Ihren Vor- und Nachnamen im Prüfungsfeld ein.");
    document.getElementById('qename').focus();
    return;
  }

  const qItems = document.querySelectorAll('.qitem');
  finalCorrect = 0;
  finalWrong = 0;
  let reportLines = "";

  qItems.forEach((item, idx) => {
    const correctIdx = parseInt(item.getAttribute('data-correct'));
    const options = item.querySelectorAll('.qopt');
    
    const fbOkVisible = item.querySelector('.qfb.ok.show');
    const fbErrVisible = item.querySelector('.qfb.err.show');

    if(fbOkVisible) {
      finalCorrect++;
      reportLines += `Frage ${idx+1}: RICHTIG\n`;
    } else if(fbErrVisible) {
      finalWrong++;
      reportLines += `Frage ${idx+1}: FALSCH\n`;
    } else {
      finalWrong++; 
      reportLines += `Frage ${idx+1}: NICHT BEANTWORTET (Als Fehler gewertet)\n`;
      
      item.classList.add('answered');
      options.forEach((opt, oIdx) => {
        opt.classList.add('locked');
        if((oIdx + 1) === correctIdx) opt.classList.add('correct');
      });
      item.querySelector('.qfb.err').classList.add('show');
    }
  });

  const resultBox = document.getElementById('resultBox');
  const scoreVal = document.getElementById('scoreVal');
  const scoreDetails = document.getElementById('scoreDetails');
  const scoreLbl = document.getElementById('scoreLbl');
  const resultText = document.getElementById('resultText');
  const sendMailBtn = document.getElementById('sendMailBtn');
  const mailNote = document.getElementById('mailNote');

  resultBox.classList.add('show');
  scoreVal.textContent = `${finalCorrect} / 20`;
  scoreDetails.textContent = `Richtige Antworten: ${finalCorrect} | Fehler: ${finalWrong}`;

  const passed = finalCorrect >= 17;
  
  if(passed) {
    scoreLbl.textContent = "🎉 Zertifizierung BESTANDEN!";
    resultText.innerHTML = `<strong>Hervorragende Leistung, ${globalName}!</strong> Sie haben maximal 3 Fehler gemacht und bewiesen, dass Sie die psychologischen und strategischen Mechanismen des B2B-Großkundenvertriebs auf Elite-Niveau beherrschen.`;
  } else {
    scoreLbl.textContent = "❌ Zertifizierung NICHT BESTANDEN";
    resultText.innerHTML = `<strong>Das reicht noch nicht, ${globalName}.</strong> Sie haben die kritische Fehlergrenze überschritten. Im realen Markt führen diese Fehler zum Verlust von Millionen-Umsätzen. Analysieren Sie die Skripte erneut und starten Sie einen neuen Versuch.`;
  }

  emailReportText = `Realm Germany Vertriebsschulung - Gesamtauswertung (B2B-Akquise)\n`;
  emailReportText += `==================================================\n`;
  emailReportText += `Teilnehmer: ${globalName}\n`;
  emailReportText += `Ergebnis: ${finalCorrect} von 20 Punkten\n`;
  emailReportText += `Fehlerquote: ${finalWrong} von maximal 3 erlaubten Fehlern\n`;
  emailReportText += `Status: ${passed ? 'BESTANDEN (Elite-Level)' : 'NICHT BESTANDEN'}\n`;
  emailReportText += `Datum/Uhrzeit: ${new Date().toLocaleString('de-DE')}\n\n`;
  emailReportText += `Detaillierte Fragen-Übersicht:\n`;
  emailReportText += reportLines;
  emailReportText += `\n──────────────────────────────────────────────────\n`;
  emailReportText += `Generiert durch das Realm Elite Zertifizierungssystem.`;

  mailNote.innerHTML = `Die detaillierte Auswertung wurde generiert. Klicken Sie auf den Button unten, um Ihre Ergebnisse offiziell an <strong>m.christel@realm-europe.de</strong> zu übermitteln.`;
  sendMailBtn.style.display = "inline-flex";
  
  resultBox.scrollIntoView({behavior: 'smooth'});
}

function sendResultEmail() {
  const subject = encodeURIComponent(`Schulungsergebnis Masterclass: ${globalName} (${finalCorrect}/20 - ${finalCorrect >= 17 ? 'Bestanden' : 'Nicht bestanden'})`);
  const body = encodeURIComponent(emailReportText);
  window.location.href = `mailto:m.christel@realm-europe.de?subject=${subject}&body=${body}`;
}
</script>

</body>
</html>
