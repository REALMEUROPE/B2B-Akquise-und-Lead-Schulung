<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Realm Germany – Die Elite-Vertriebsschulung</title>
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
.hero{background:linear-gradient(135deg,#071f38 0%,var(--blue-deep) 45%,var(--green-dark) 100%);color:#fff;padding:5rem 1.5rem 4rem;text-align:center;position:relative;overflow:hidden}
.hero::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")}
.hero-badge{display:inline-block;background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.25);border-radius:20px;padding:6px 18px;font-size:12px;letter-spacing:2px;text-transform:uppercase;margin-bottom:1.5rem;backdrop-filter:blur(4px);font-weight:700}
.hero h1{font-size:clamp(28px,6vw,46px);font-weight:900;margin-bottom:1rem;line-height:1.15;letter-spacing:-0.5px}
.hero h1 span{color:#6EE7B7}
.hero p{font-size:16px;opacity:.85;max-width:700px;margin:0 auto 2rem;line-height:1.8}

/* ── NAV ── */
.nav-wrap{background:#fff;border-bottom:1px solid var(--border);position:sticky;top:0;z-index:100;box-shadow:0 2px 10px rgba(0,0,0,.05)}
.nav-inner{max-width:1200px;margin:0 auto;padding:0 1rem;display:flex;gap:0;overflow-x:auto;scrollbar-width:none}
.nav-inner::-webkit-scrollbar{display:none}
.nav-item{flex-shrink:0;padding:1.1rem 1.3rem;font-size:14px;font-weight:700;color:var(--muted);cursor:pointer;border-bottom:4px solid transparent;transition:all .2s;white-space:nowrap}
.nav-item:hover{color:var(--text);background:var(--subtle)}
.nav-item.active{color:var(--green-dark);border-bottom-color:var(--green-dark)}

/* ── LAYOUT ── */
.page{max-width:1200px;margin:0 auto;padding:2.5rem 1rem}
.section{display:none;animation:fadeIn .3.5s ease}
.section.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(12px)}to{opacity:1;transform:translateY(0)}}

/* ── CARDS ── */
.card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:2.5rem;margin-bottom:1.75rem;box-shadow:0 4px 6px -1px rgba(0,0,0,0.02)}
.card-title{font-size:24px;font-weight:800;margin-bottom:1.5rem;color:var(--blue-deep);display:flex;align-items:center;gap:12px;border-bottom:2px solid var(--subtle);padding-bottom:0.75rem}
.card-title .ico{font-size:28px}
h3{font-size:18px;font-weight:800;margin:2rem 0 .75rem;color:var(--blue-deep);display:flex;align-items:center;gap:6px}
h4{font-size:15px;font-weight:700;margin:1.25rem 0 .5rem;color:var(--green-dark);text-transform:uppercase;letter-spacing:0.5px}
p{font-size:15px;line-height:1.8;color:#374151;margin-bottom:1.25rem}
ul,ol{padding-left:1.5rem;margin-bottom:1.25rem}
li{font-size:15px;line-height:1.8;color:#374151;margin-bottom:0.5rem}

/* ── HIGHLIGHT BOXES ── */
.hl{background:var(--green-light);border-left:5px solid var(--green-mid);border-radius:0 12px 12px 0;padding:1.25rem 1.5rem;margin:1.5rem 0;font-size:14.5px;line-height:1.8}
.hl strong{display:block;margin-bottom:5px;color:var(--green-dark);font-size:16px}

.mentor-box{background:#FFFBEB;border-left:5px solid var(--amber);border-radius:0 12px 12px 0;padding:1.25rem 1.5rem;margin:1.5rem 0;font-size:14.5px;line-height:1.8;color:#78350F}
.mentor-box strong{display:block;margin-bottom:5px;color:#92400E;font-size:16px}

/* ── SCRIPT BOX ── */
.script-box {background:#1E293B;color:#E2E8F0;border-radius:12px;padding:1.5rem;font-family:'SF Mono',Consolas,monospace;font-size:13.5px;margin:1.25rem 0;line-height:1.8;border-left:5px solid #38BDF8;box-shadow:inset 0 2px 4px rgba(0,0,0,0.2)}
.script-box strong {color:#38BDF8;font-size:14px;display:block;margin-bottom:0.5rem;text-transform:uppercase;letter-spacing:0.5px}
.script-box .bad {color:#F87171}
.script-box .good {color:#34D399}

/* ── TABLE ── */
.tbl-wrap{overflow-x:auto;margin:1.5rem 0;border-radius:12px;border:1px solid var(--border);box-shadow:0 4px 6px -1px rgba(0,0,0,0.01)}
table{width:100%;border-collapse:collapse;font-size:14px}
thead tr{background:var(--subtle)}
th{padding:12px 16px;text-align:left;font-weight:800;color:var(--blue-deep);border-bottom:2px solid var(--border)}
td{padding:14px 16px;border-bottom:1px solid #F3F4F6;color:#4B5563;vertical-align:top;line-height:1.6}

/* ── QUIZ ── */
.quiz-box{background:var(--card);border:2px solid var(--blue-deep);border-radius:16px;padding:2.5rem;margin-top:2rem;box-shadow:0 10px 15px -3px rgba(0,0,0,0.05)}
.quiz-box h3{font-size:22px;font-weight:900;margin-bottom:.5rem;color:var(--blue-deep)}
.quiz-box .qsub{font-size:14px;color:var(--muted);margin-bottom:2rem;border-bottom:2px solid var(--border);padding-bottom:1rem}
.qitem{margin-bottom:2.5rem;border-bottom:1px dashed var(--border);padding-bottom:2rem}
.qitem:last-of-type{border-bottom:none}
.qitem .qt{font-size:16px;font-weight:800;margin-bottom:1rem;line-height:1.6;color:var(--text)}

.qopt{display:flex;align-items:flex-start;gap:12px;background:#fff;border:2px solid var(--border);border-radius:10px;padding:.875rem 1.25rem;cursor:pointer;margin-bottom:10px;font-size:14px;color:#374151;width:100%;text-align:left;line-height:1.6;transition:all .2s;font-weight:500}
.qopt:hover{border-color:#6B7280;background:var(--subtle);transform:translateX(4px)}
.qopt .qdot{width:18px;height:18px;border:2px solid #D1D5DB;border-radius:50%;flex-shrink:0;margin-top:2px;transition:all .2s;position:relative}

/* Sofort-Feedback */
.qopt.correct{background:var(--green-light) !important;border-color:var(--green-mid) !important;color:#065F46 !important;font-weight:700;box-shadow:0 4px 6px -1px rgba(5,150,105,0.1)}
.qopt.correct .qdot{background:var(--green-mid) !important;border-color:var(--green-mid) !important}
.qopt.wrong{background:#FEF2F2 !important;border-color:var(--red) !important;color:#7F1D1D !important;font-weight:700}
.qopt.wrong .qdot{background:var(--red) !important;border-color:var(--red) !important}
.qopt.locked{pointer-events:none;opacity:0.6;transform:none !important}
.qopt.locked.correct, .qopt.locked.wrong{opacity:1}

.qfb{display:none;font-size:13.5px;line-height:1.7;padding:1rem 1.25rem;border-radius:10px;margin-top:.75rem;font-weight:500}
.qfb.show{display:block;animation:slideIn .2s ease}
@keyframes slideIn{from{opacity:0;transform:translateY(-5px)}to{opacity:1;transform:translateY(0)}}
.qfb.ok{background:var(--green-light);color:#065F46;border:1px solid #A7F3D0}
.qfb.err{background:#FEF2F2;color:#7F1D1D;border:1px solid #FECACA}

/* Ergebnis-Auswertung */
.quiz-score{display:none;background:#fff;border-radius:14px;padding:2.5rem;text-align:center;margin-top:2rem;border:3px solid var(--border)}
.quiz-score.show{display:block}
.quiz-score .qs-val{font-size:56px;font-weight:900;color:var(--blue-deep);margin-bottom:0.5rem}
.quiz-score .qs-details{font-size:16px;color:var(--muted);margin-bottom:1rem;font-weight:600}
.quiz-score .qs-lbl{font-size:22px;color:var(--text);margin-bottom:1.5rem;font-weight:900;text-transform:uppercase;letter-spacing:1px}

.name-row{display:flex;align-items:center;gap:16px;background:#fff;border:2px solid var(--blue-deep);border-radius:12px;padding:1rem 1.25rem;margin-bottom:2rem;box-shadow:0 4px 6px -1px rgba(0,0,0,0.05)}
.name-row label{font-size:15px;font-weight:800;white-space:nowrap;color:var(--blue-deep)}
.name-row input{flex:1;border:none;background:transparent;font-size:16px;color:var(--text);outline:none;font-weight:700}
.name-row input::placeholder{color:var(--muted);font-weight:400}

.mail-note{font-size:14.5px;color:#374151;margin-top:1.5rem;padding:1.25rem;background:#F3F4F6;border-radius:10px;border:1px solid var(--border);line-height:1.7}
.mail-note strong{color:var(--blue-deep)}

.nav-btns{display:flex;justify-content:space-between;margin-top:2.5rem;gap:12px}
.btn{padding:.8rem 1.75rem;border-radius:12px;border:2px solid var(--border);background:#fff;cursor:pointer;font-size:15px;font-weight:800;color:var(--text);transition:all .2s;display:inline-flex;align-items:center;gap:8px}
.btn:hover{background:var(--subtle);border-color:#4B5563;transform:translateY(-2px)}
.btn-primary{background:linear-gradient(135deg,var(--blue-deep),var(--green-dark));color:#fff;border-color:transparent;box-shadow:0 4px 10px rgba(11,61,107,0.2)}
.btn-primary:hover{box-shadow:0 6px 14px rgba(11,61,107,0.3);color:#fff}
.sect-progress{background:var(--border);border-radius:8px;height:6px;margin-bottom:2.5rem}
.sect-progress-fill{background:linear-gradient(90deg,var(--blue-deep),var(--green-dark));border-radius:8px;height:6px;transition:width .5s}
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="hero-badge">Realm Elite Training · Mentorat 2026</div>
  <h1>Modul 2: Die Kunst der B2B-Akquise &amp;<br><span>skalierbaren Lead-Generierung</span></h1>
  <p>Hör zu, mein Sohn: Ein durchschnittlicher Verkäufer bettelt um Termine. Ein wahrer Profi steuert die Realität seines Gegenübers. Hier lernst du, wie du das Vorzimmer dominierst, LinkedIn in eine Gelddruckmaschine verwandelst und eiskalt filterst, wo die Millionen-Projekte liegen.</p>
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

<!-- ══════════════════════════════ SECTION 0 ══ -->
<div class="section active" id="sec0">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:25%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">📞</span>Kaltakquise (Cold Calling) &amp; die totale Vorzimmer-Dominanz</div>
    
    <div class="mentor-box">
      <strong>Väterlicher Rat vom besten Vertriebler der Welt:</strong>
      „Mein Junge, merk dir eins: Das Sekretariat – der sogenannte Gatekeeper – ist keine Mauer. Es ist ein Filter für die Schwachen. Wenn du klingst wie ein Bittsteller, wirst du wie ein Bittsteller behandelt und weggeschickt. Wenn du aber mit der Tonalität und der absoluten Selbstverständlichkeit eines CEOs anrufst, öffnet sich jedes Tor. Du verkaufst dort niemals dein Produkt. Du verkaufst ausschließlich den nächsten logischen Prozessschritt.“
    </div>

    <h3>Die Psychologie des Gatekeeper-Rapports</h3>
    <p>Assistenzen der Geschäftsführung sind darauf konditioniert, Werbeanrufe innerhalb der ersten 3 Sekunden zu erkennen und zu blockieren. Sie achten auf typische Trigger: Übertriebene Freundlichkeit, Unsicherheit in der Stimme, das Verwenden von Rechtfertigungen („Ich wollte mal fragen...“) oder das sofortige Pitchen von Produkteigenschaften.</p>
    
    <p>Um das Vorzimmer zu passieren, nutzen wir den **Status-Rapport**. Du passt deine Tonalität nicht der Assistenz an, sondern der des Geschäftsführers: Ruhig, bestimmt, geschäftsmäßig, leicht gehetzt, aber absolut höflich und direkt.</p>

    <h3>Die linguistischen Werkzeuge in der Praxis</h3>
    
    <h4>1. Die "Status- und Annahme-Methode"</h4>
    <p>Du bittest nicht um Erlaubnis. Du setzt voraus, dass dein Anruf eine geschäftliche Notwendigkeit für das Unternehmen ist. Du nennst deinen Nachnamen und das Unternehmen flüssig, gefolgt von einer klaren Handlungsanweisung.</p>
    
    <div class="script-box">
      <strong>❌ Der Verlierer-Ansatz:</strong><br>
      <span class="bad">„Ja hallo, mein Name ist Jan Müller von der Realm Germany. Ich hoffe, ich störe nicht? Ich wollte mal fragen, ob eventuell der Herr Geschäftsführer Schneider heute ganz kurz Zeit für mich hätte? Es geht um unsere neuen, hocheffizienten R290-Wärmepumpen...“</span><br>
      <em>Ergebnis:</em> „Schicken Sie uns mal eine E-Mail an info@...“ *Klick. Aufgelegt.*<br><br>
      <strong>🎯 Der Elite-Ansatz (Wie wir es machen):</strong><br>
      <span class="good">„Guten Tag, Müller mein Name, Realm Germany. Frau [Name der Assistenz – falls bekannt, sonst weglassen], bringen Sie mich bitte kurz zu Herrn Schneider durch. Danke Ihnen.“</span><br>
      <em>Warum es funktioniert:</em> Keine Fragen, kein Zögern. Die Formulierung „bringen Sie mich bitte durch“ impliziert, dass es bereits einen Kontext oder eine akute geschäftliche Relevanz gibt.
    </div>

    <h4>2. Der „Prozess-Grund“ schlägt den „Produkt-Grund“</h4>
    <p>Wenn die Assistenz nachfragt: *„Worum geht es denn genau?“*, darfst du niemals dein Produkt nennen. Sobald du „Wärmepumpe“ oder „Heizung“ sagst, bist du in der Schublade „Austauschbarer Verkäufer“.</p>
    
    <div class="script-box">
      <strong>❌ Der Fehler:</strong> <span class="bad">„Es geht um unsere neuen R290 Großwärmepumpen, die super Lieferzeiten haben...“</span><br><br>
      <strong>🎯 Die Lösung:</strong> <span class="good">„Es geht um die strategische Absicherung Ihrer anstehenden Großprojekte gegen die neuen F-Gase-Regulierungen und die Vermeidung von Planungsstopps im kommenden Quartal. Herr Schneider steuert diese Kapazitäten – stellen Sie mich bitte direkt durch?“</span>
    </div>

    <h4>3. Die info@-Blackbox elegant aushebeln</h4>
    <p>Wenn der Vorwand kommt: *„Schicken Sie uns Unterlagen an info@...“*, stimmst du zu, nutzt es aber sofort als Hebel, um den Kanal zu personalisieren.</p>
    <div class="script-box">
      <strong>Dein Konter:</strong> <span class="good">„Das mache ich gern. Da es sich hierbei um die exklusiven Gebietsschutz-Dokumente und vertrauliche Projekt-Kennzahlen für die Region handelt, schicke ich das direkt auf den persönlichen Tisch von Herrn Schneider. Geben Sie mir kurz seine direkte Durchwahl oder seine persönliche E-Mail-Adresse durch?“</span>
    </div>
  </div>

  <div class="nav-btns">
    <div></div>
    <button class="btn btn-primary" onclick="goSec(1)">Weiter: Social Selling-Imperium →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 1 ══ -->
<div class="section" id="sec1">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:50%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🤝</span>Social Selling: Digitale Lead-Generierung auf allerhöchstem Niveau</div>
    
    <div class="mentor-box">
      <strong>Väterlicher Rat vom besten Vertriebler der Welt:</strong>
      „Mein Sohn, das Internet ist voll von Amateuren, die via LinkedIn hunderte Copy-Paste-Nachrichten an Geschäftsführer ballern. Das ist digitaler Spam und verbrennt den Markt. Ein wahrer Meister nutzt Social Media wie ein Präzisionsgewehr. Du baust Relevanz und Status auf, lange bevor du die erste Nachricht schreibst. Lass die Kunden das Gefühl haben, sie hätten DICH entdeckt – nicht umgekehrt.“
    </div>

    <h3>Die 3 Säulen der digitalen Anziehungskraft</h3>
    <p>Wenn ein Geschäftsführer oder Projektentwickler auf dein Profil klickt, hat er eine Aufmerksamkeitsspanne von exakt 4 Sekunden. In dieser Zeit entscheidet er, ob du ein kompetenter Branchen-Experte oder ein nerviger Verkäufer bist.</p>

    <h4>Säule 1: Das Landingpage-Profil (Die Nutzen-Formel)</h4>
    <p>Dein Profil-Slogan (Headline) darf niemals deine Position („Sales Manager bei Realm“) beinhalten. Niemand interessiert sich für deinen Jobtitel. Die Menschen interessieren sich nur für die Lösung ihrer Probleme.</p>
    <div class="hl">
      <strong>Die perfekte Profil-Formel:</strong><br>
      <em>Ich helfe [Zielgruppe] dabei, [großes Problem zu lösen] / [großes Ziel zu erreichen], ohne [größte Angst/Sorge der Zielgruppe].</em>
    </div>
    <div class="script-box">
      <strong>Beispiel für dein Profil:</strong><br>
      <span class="good">„Ich helfe TGA-Fachplanern und gewerblichen Bauträgern dabei, R290-Wärmepumpen-Großprojekte absolut lieferfähig und rechtssicher zu realisieren – ohne unvorhergesehene Kostenexplosionen und langwierige Genehmigungsprozesse.“</span>
    </div>

    <h4>Säule 2: Das "Digitale Einschleichen" (Die 3-Touchpoint-Regel)</h4>
    <p>Bevor du eine Vernetzungsanfrage schickst, machst du dich im Geiste des Entscheiders unbewusst vertraut (Nutzung des *Mere-Exposure-Effekts*):</p>
    <ul>
      <li><strong>Touchpoint 1: Der stille Besuch.</strong> Du besuchst sein Profil. Er sieht in seinen Benachrichtigungen: „Jan Müller hat Ihr Profil besucht.“</li>
      <li><strong>Touchpoint 2: Die Validierung.</strong> 24 Stunden später likest du einen seiner jüngsten geschäftlichen Beiträge oder Interaktionen.</li>
      <li><strong>Touchpoint 3: Der Experten-Kommentar.</strong> Du hinterlässt unter seinem Beitrag einen fachlich fundierten, wertschätzenden Kommentar, der deine Expertise zeigt – ohne jeglichen Pitch!</li>
    </ul>

    <h4>Säule 3: Die unaufhaltsame Vernetzungsanfrage</h4>
    <p>Erst nach diesen 3 Touchpoints vernetzt du dich. Deine Nachricht ist kurz, frei von Verkaufsabsichten und knüpft an sein Thema an.</p>
    <div class="script-box">
      <strong>Muster-Anfrage:</strong><br>
      <span class="good">„Hallo Herr Dr. Schneider, Ihr jüngster Beitrag zum Thema Effizienz im Gewerbebau hat mich inspiriert – insbesondere der Punkt bezüglich der Kältemittel-Umstellung. Ich begleite genau diesen Bereich bei der Realm Germany hier in Bayern und freue mich auf den fachlichen Austausch in meinem Netzwerk. Beste Grüße, Jan Müller“</span>
    </div>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(0)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(2)">Weiter: BANT Elite-Filter →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 2 ══ -->
<div class="section" id="sec2">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:75%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🎯</span>Rigorose Lead-Qualifizierung &amp; das BANT-Framework</div>
    
    <div class="mentor-box">
      <strong>Väterlicher Rat vom besten Vertriebler der Welt:</strong>
      „Mein Junge, merke dir diesen Satz für den Rest deines Lebens: Ein schlechter Verkäufer rennt jedem hinterher, der nicht bei drei auf den Bäumen ist, und verschwendet Monate mit unentschlossenen Kunden. Ein Top-Performer schützt seine Arbeitszeit wie seine eigene Familie. Du musst lernen, Leads so schnell wie möglich zu disqualifizieren, wenn sie deine Kriterien nicht erfüllen. Wer kein Geld hat oder keine Entscheidung treffen kann, verdient nicht deine Zeit.“
    </div>

    <h3>Das BANT-Framework als Schutzschild</h3>
    <p>Das BANT-Framework ist kein theoretischer Fragebogen, den du von oben nach unten abliest. Es ist eine strategische Leitlinie, um im lockeren Gespräch herauszufinden, ob ein Projekt echtes Potenzial hat oder nur eine Luftnummer ist.</p>

    <div class="tbl-wrap">
      <table>
        <thead>
          <tr>
            <th>Kriterium</th>
            <th>Tiefe vertriebliche Bedeutung</th>
            <th>Meisterhafte psychologische Abfrage-Technik</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>B - Budget</strong></td>
            <td>Hat das Unternehmen die finanzielle Kraft für unsere Premium-Lösung oder redest du mit einer insolventen Firma?</td>
            <td><em>Frage niemals stumpf nach dem Budget!</em> Frage stattdessen: „Herr Schneider, für Projekte dieser Größenordnung: Welcher finanzielle Rahmen wurde denn für diese Projektphase bereits vom Vorstand freigegeben?“</td>
          </tr>
          <tr>
            <td><strong>A - Authority</strong></td>
            <td>Sprecht ihr mit dem echten Entscheider (der die Unterschrift leistet) oder nur mit einem "Ja-Sager" ohne Budgetgewalt?</td>
            <td>„Angenommen, unser Konzept überzeugt Sie auf ganzer Linie: Wie sieht Ihr interner Freigabeprozess aus und wer sitzt außer Ihnen noch mit am Tisch, wenn die finale Entscheidung getroffen wird?“</td>
          </tr>
          <tr>
            <td><strong>N - Need</strong></td>
            <td>Gibt es einen echten, brennenden Schmerz (Lieferverzug, drohende Strafen), oder will sich der Kunde nur unverbindlich informieren?</td>
            <td>„Was passiert eigentlich mit Ihren Fertigstellungsterminen und Ihren Marge-Zielen, wenn Ihr aktueller Lieferant die R290-Großgeräte in 6 Monaten nicht pünktlich auf die Baustelle bringt?“</td>
          </tr>
          <tr>
            <td><strong>T - Timeline</strong></td>
            <td>Wann fließt das Geld? Ist die Umsetzung in den nächsten 3 Monaten oder redet ihr über ungelegte Eier im Jahr 2030?</td>
            <td>„Damit wir die Produktion und den exklusiven Gebietsschutz für Sie rechtzeitig blockieren können: Bis zu welchem Stichtag muss die Anlage zwingend betriebsbereit am Netz sein?“</td>
          </tr>
        </tbody>
      </table>
    </div>

    <h3>Lead-Klassifizierung: A-, B- und C-Leads</h3>
    <p>Teile deine Leads sofort nach dem Erstgespräch kompromisslos in drei Kategorien ein:</p>
    <ul>
      <li><strong>A-Leads (Sofortiger Fokus):</strong> Alle 4 BANT-Kriterien sind positiv erfüllt. Der Kunde hat Schmerzen, Geld, die Entscheidungsmacht und will sofort handeln. Hier investierst du 80% deiner Energie.</li>
      <li><strong>B-Leads (Nurturing-Pipeline):</strong> Bedarf und Geld sind da, aber die Timeline liegt in der Zukunft oder der Entscheider muss noch überzeugt werden. Diese pflegst du mit automatisierten Mehrwert-Mails.</li>
      <li><strong>C-Leads (Eiskalt aussortieren):</strong> Kein Budget, kein akuter Schmerz, kein Entscheidungsspielraum. Diese Leads werden höflich vertagt und blockieren niemals deinen Terminkalender.</li>
    </ul>
  </div>

  <div class="nav-btns">
    <button class="btn" onclick="goSec(1)">← Zurück</button>
    <button class="btn btn-primary" onclick="goSec(3)">Weiter zum Elite-Zertifikats-Test →</button>
  </div>
</div>

<!-- ══════════════════════════════ SECTION 3 ══ -->
<div class="section" id="sec3">
  <div class="sect-progress"><div class="sect-progress-fill" style="width:100%"></div></div>

  <div class="card">
    <div class="card-title"><span class="ico">🏆</span>Zertifizierungs-Prüfung – Level: Realm B2B-Closer</div>
    <p>Hör zu, mein Sohn. Jetzt trennt sich die Spreu vom Weizen. Es folgen **20 knallharte Praxisszenarien**. Um diese Prüfung zu bestehen und das offizielle Realm-Zertifikat zu erhalten, darfst du dir **maximal 3 Fehler** erlauben (Mindestens 17 von 20 richtig). Jede Antwort wird sofort ausgewertet.</p>
  </div>

  <div class="quiz-box">
    <h3>🎯 Modul 2 Abschlussprüfung – Akquise-Kompetenz</h3>
    <div class="qsub">Realm Zertifikat · Modul 2 · 20 Praxisfragen</div>

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
      <div class="qfb err">✗ Falsch! Option A und C beschreiben dich. Option B beschreibt die *Lösung für den Kunden*. Nur das zählt!</div>
    </div>

    <!-- QUESTION 8 -->
    <div class="qitem" data-correct="1">
      <div class="qt">8. Wie wendest du die „3-Touchpoint-Regel“ bei einem extrem wichtigen Wunschkunden auf LinkedIn an?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Profil besuchen, 24h später einen Beitrag von ihm liken, am Folgetag einen qualifizierten Fachkommentar hinterlassen.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ihn an drei verschiedenen Tagen exakt um die gleiche Uhrzeit per Nachricht anschreiben.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Drei verschiedene Mitarbeiter des Einkaufs gleichzeitig im Chat kontaktieren.</button>
      <div class="qfb ok">✓ Korrekt! Dadurch erzeugst du subtile psychologische Vertrautheit (*Mere-Exposure-Effekt*), bevor du überhaupt anklopfst.</div>
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
      <div class="qfb err">✗ Falsch! Oberflächliche Fragen (Option B und C) erzeugen keine Dringlichkeit. Du musst den Schmerz der Lieferverzögerung triggern.</div>
    </div>

    <!-- QUESTION 12 -->
    <div class="qitem" data-correct="3">
      <div class="qt">12. Was zeichnet ein gefährliches „C-Lead“ aus, das deine wertvolle Vertriebszeit stiehlt?</div>
      <button class="qopt" onclick="handleAnswer(this, 1)"><span class="qdot"></span>Ein Lead, das sofort ein Angebot per Mail fordert und den Vertrag morgen unterschreiben will.</button>
      <button class="qopt" onclick="handleAnswer(this, 2)"><span class="qdot"></span>Ein Mitbewerber, der vorgibt, ein Kunde zu sein, um unsere Preise zu spionieren.</button>
      <button class="qopt" onclick="handleAnswer(this, 3)"><span class="qdot"></span>Ein Kontakt ohne Budget und ohne akuten Schmerz, der nur kostenlose Beratung und Preise abgreifen will.</button>
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
      <div class="qfb ok">✓ Korrekt! Ein Frontalangriff erzeugt sofortige Abwehr (*Reaktanz*). Die Positionierung als Sicherheitsnetz/Backup öffnet die Tür spielend.</div>
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
      <div class="qfb err">✗ Falsch! Option A verbrennt deinen Kontakt. Option B führt zu monatelangem Stillstand. Mache den Kontakt zu deinem internen Verbündeten!</div>
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
    alert("Bitte trage zuerst deinen Vor- und Nachnamen oben im Prüfungsfeld ein, mein Sohn!");
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
    scoreLbl.style.color = "var(--green-dark)";
    resultText.innerHTML = `<strong>Großartige Leistung, ${globalName}!</strong> Du hast maximal 3 Fehler gemacht und bewiesen, dass du die Mechanismen des B2B-Vertriebs verstanden hast. Du bist bereit für den Markt!`;
  } else {
    scoreLbl.textContent = "❌ Zertifizierung NICHT BESTANDEN";
    scoreLbl.style.color = "var(--red)";
    resultText.innerHTML = `<strong>Das reicht noch nicht, ${globalName}.</strong> Du hast mehr als 3 Fehler gemacht. Im echten Markt verbrennst du mit diesen Fehlern Millionen-Umsätze. Gehe die Skripte noch einmal durch und versuche es erneut!`;
  }

  emailReportText = `Realm Germany Vertriebsschulung - Modul 2 (B2B-Akquise)\n`;
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

  mailNote.innerHTML = `Die detaillierte Auswertung wurde generiert. Klicke jetzt auf den Button unten, um deine Ergebnisse offiziell an <strong>m.christel@realm-europe.de</strong> zu übermitteln.`;
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
