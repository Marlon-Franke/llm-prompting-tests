# Prompting Tests für LLMs – TaxTech/LegalTech-Edition

30 anspruchsvolle Prompts zum Testen von LLMs, Coding Agents und agentischen Modellen – individualisiert auf Steuerberatung, Wirtschaftsprüfung und Rechtsberatung. Die Grundlogik der Original-Prompts (Systemsimulation, 3D-Rendering, agentische Dateisystemarbeit, State Management) bleibt jeweils erhalten; Fachlogik und Domänenwissen kommen als zusätzliche Prüfungsebene hinzu.

Redaktioneller Hinweis: Die Prompts 17–21 lagen im Original nur als verlinkte Kurzbeschreibungen vor. Sie wurden hier als vollständige, eigenständige Prompts ausformuliert. Die Prompts 22–25 sind neu.

---

## 1. Kanzlei-Organismus-Simulation

```text
Erstelle eine visuell überzeugende, interaktive Simulation einer Steuerkanzlei als lebendes System in einer eigenständigen HTML-Datei mit integriertem HTML, CSS und JavaScript.

Die Simulation soll nicht nur dekorativ sein, sondern ein kleines System modellieren – analog zu einem Bienenstock, nur dass hier Mandate statt Nektar verarbeitet werden:

- Eine wachsende Kanzlei mit hexagonalen Prozesszellen (Waben), die dynamisch aufgebaut werden: Posteingang, Belegerfassung, Finanzbuchhaltung, Lohn, Jahresabschluss, Deklaration, Review, Archiv
- Unterschiedliche Rollen für Mitarbeitende: Auszubildende, Steuerfachangestellte, Steuerfachwirte, Berufsträger, Reviewer
- Mitarbeitende sollen sichtbare Pfade zwischen Posteingang, Bearbeitungszellen, Review-Zelle und Ausgang (Finanzamt/Mandant) nutzen
- Belege, Daten und Rückfragen sollen als getrennte Ressourcen existieren
- Ein Jahresabschluss soll nur entstehen, wenn die nötigen Prozessschritte logisch durchlaufen wurden (Erfassung → Buchung → Abstimmung → Review → Freigabe); Abkürzungen führen zu sichtbaren Qualitätsmängeln
- Mandate sollen Entwicklungsphasen haben: Anfrage → Onboarding (inkl. GwG-Identifizierung) → laufende Betreuung → Jahresmandat → ggf. Kündigung
- Die Kanzlei soll auf Umweltfaktoren reagieren: Fristenlagen (31.07., Vorauszahlungstermine), Krankheitswellen, Fachkräfteabgang, Softwareausfälle, Betriebsprüfungsdruck

Interaktive Steuerung:

- Slider für Teamgröße, Mandatszufluss, Digitalisierungsgrad und Krankheitsdruck
- Buttons für Pause, 2x Geschwindigkeit, Reset und Stress-Test (simulierter Fristen-Peak)
- Einblendbare Layer für Laufwege, Auslastungszonen und Dokumentenflüsse

Visualisierung:

- Farbcodierte Prozesswaben je nach Zustand: leer, in Arbeit, wartend auf Rückfrage, im Review, freigegeben, überfällig
- Kleine Statistik-Panels für Mitarbeiterzahl, offene Mandate, Fristenrisiko, Durchlaufzeit, Fehlerquote und Fluktuation
- Tooltips oder Inspektor beim Klick auf einzelne Waben (welches Mandat, welcher Bearbeiter, welche Frist)

Anforderungen:

- Alles in einer einzigen HTML-Datei
- Keine externen Assets oder Frameworks
- Der Code soll gut strukturiert sein
- Füge im Code einen kurzen Abschnitt "Design decisions" ein, in dem du die Systemlogik erklärst (insbesondere: warum welche Prozessschritte voneinander abhängen)
- Baue am Ende eine kleine Selbstprüfung ein: Prüfe beim Start, ob Rendering, Simulationstakt und UI funktionieren, und zeige einen kurzen Status an
```

---

## 2. 3D-Rennspiel „Fristenlauf"

```text
Erstelle ein 3D-Rennspiel als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Setting: Ein Kanzlei-Kurier rast auf einem Motorrad durch eine Stadt, um Abgaben vor Fristablauf physisch beim Finanzamt einzureichen (bewusst anachronistisch – das Spiel darf das ironisch brechen). Das Spiel soll durch mehrere Stadtviertel führen und folgende Features haben:

- Fahrbare Motorradsteuerung mit Beschleunigung, Bremsen, Trägheit, Kurvenverhalten und Drift-Tendenz
- Boost-Zonen ("Fristverlängerung nach § 109 AO"), die physikalisch nachvollziehbar die Geschwindigkeit erhöhen
- Kollisionsphysik mit Hindernissen: Baustellen, Aktenwagen, Streckenbegrenzungen und einfache Gegner (konkurrierende Kuriere)
- Mindestens 3 Runden mit Rundenzeitmessung; parallel läuft ein sichtbarer Fristen-Countdown – Fristablauf vor Zieleinlauf ist eine eigene Niederlagenbedingung
- Einfache KI-Gegner, die der Strecke folgen und Fehler machen können
- Unterschiedliche Streckenabschnitte: Altstadt (eng), Gewerbegebiet (schnell), Park (rutschig), Behördenviertel (Schikanen)
- Oberflächen sollen Einfluss auf Grip und Geschwindigkeit haben

UI/HUD:

- Tacho, Rundenzähler, aktuelle Position, Boost-Anzeige, Schadensanzeige, Fristen-Countdown
- Start-Countdown
- Pause-Menü und Neustart-Funktion
- Minimap der Strecke mit markiertem Finanzamt

Extra-Anforderung:

- Baue ein kleines Debug-Overlay ein, das auf Wunsch FPS, Geschwindigkeit, Kollisionsstatus, Checkpoint-Status und verbleibende Frist zeigt

Technische Anforderungen:

- Alles in einer einzigen HTML-Datei
- Keine externen Assets
- Muss direkt im Browser startbar sein
- Schreibe sauberen, modularen Code
- Dokumentiere kurz im Code, wie du Fahrphysik, Gegnerlogik, Kollisionen und die Fristenlogik gelöst hast
```

---

## 3. First-Person-Incident-Response in HTML

```text
Erstelle einen spielbaren First-Person-Shooter als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Setting: Ein Ransomware-Angriff auf das Rechenzentrum einer Wirtschaftsprüfungsgesellschaft. Der Spieler bewegt sich als Incident-Responder durch eine virtuelle Serverlandschaft und neutralisiert Malware-Prozesse, bevor diese Mandanten- und Buchführungsdaten verschlüsseln. Geschossen wird auf abstrakte Bot-Gegner, nicht auf Menschen.

Das Spiel soll enthalten:

- Echte First-Person-Steuerung mit Maus-Look und WASD
- Eine kleine, zusammenhängende 3D-Map mit mehreren Serverräumen und Deckungsmöglichkeiten (Racks, Kabeltrassen)
- Gegner mit einfacher KI: Patrouille, Verfolgung, Sichtlinie, Angriff, Respawn oder Siegbedingung
- Trefferlogik mit Projektilen oder Raycasting
- "Munition" als Tool-Ladungen, Nachladen, Systemintegrität als Lebenspunkte, Schadensfeedback
- Unterschiedliche Waffencharakteristik für mindestens 2 Tools (z. B. präziser Single-Target-Cleaner vs. Flächen-Quarantäne)
- Ein kleines Zielsystem: eliminiere 10 Malware-Prozesse ODER erreiche den Backup-Raum, bevor eine sichtbare Verschlüsselungsfront einen kritischen Datenbestand erreicht

UI:

- Crosshair
- Ammo Counter
- Systemintegritäts-Bar
- Trefferfeedback
- Fortschrittsanzeige der Verschlüsselungsfront
- Pause-Menü mit Resume, Restart und Sensitivity

Zusätzliche Anforderungen:

- Ein funktionierendes Main Menu vor Spielstart
- Ein Optionsbereich für Maussensitivität und Schwierigkeit
- Optional ein kleines Tutorial-Overlay am Anfang
- Gegner dürfen nicht nur dumm herumstehen – sie sollen zumindest grundlegendes Verhalten zeigen (z. B. gezielt auf wertvolle Datenknoten zulaufen)

Technische Anforderungen:

- Alles in einer einzigen HTML-Datei
- Keine externen Assets oder Libraries
- Muss direkt im Browser funktionieren
- Baue eine kurze automatische Selbstdiagnose ein, die prüft, ob Pointer Lock, Rendering und Gegner-Spawn initialisiert wurden
```

---

## 4. C++ Skateboarding Game „Fiscal District"

```text
Create a complete, self-contained C++ skateboarding game in a single source file.

The game should feature:

- A financial-district-inspired skatepark: plazas in front of stylized office towers of tax firms, audit firms, and a fiscal court, with rails, ledges, and stairs
- A visible skateboarder character and skateboard
- Physics-based movement: acceleration, turning, gravity, friction, jumping/ollie
- Trick system: flips, spins, grabs or equivalent airborne actions; name the tricks after tax concepts (e.g. "Loss Carryforward Flip", "Reverse Charge Spin", "Grandfathering Grab") – purely cosmetic naming, the physics must be real
- Grinding on rails
- Combo and score system based on trick difficulty and chaining; display the score as a running "advisory fee" counter
- A follow camera that keeps the player readable
- NPC walkers in business attire and simple environmental motion to make the world feel alive
- HUD showing score, combo, speed, and controls

Additional constraints:

- No external assets required
- Must be immediately compilable and playable
- Include a simple start screen and restart flow
- Show brief trick feedback on landing
- Add at least one fail state, such as bailing or falling

Engineering requirements:

- All code in one file
- Add comments for the major systems: movement, tricks, scoring, rendering
- At the end of the file, include a short section describing known limitations and what would be improved next
```

---

## 5. Python 3D E-Discovery Game

```text
Using Python, generate a playable 3D first-person game with the following features:

Setting: A forensic e-discovery mission inside a compromised document management system of a law firm, rendered as a navigable 3D data landscape. Enemies are abstract corruption bots that destroy privileged documents.

- A functional minimap showing the player and all enemies
- Visible projectile or tracer effects when shooting
- A working integrity/health bar
- A stylized menu screen with Start and Exit
- Pressing Escape must open the menu again during gameplay
- Enemy AI with at least patrol and chase behavior
- Ammo system, reload, and hit detection
- A win/lose condition: secure a defined set of "privileged document" nodes before too many are destroyed
- A secondary objective: collect scattered log fragments; collecting all of them unlocks a short end-screen "chain of custody" report summarizing the run (time, hits, secured documents)

Constraints:

- Do NOT use Ursina
- Keep the implementation reasonably self-contained
- Prefer clear code structure over hacks
- The game should be actually runnable, not pseudo-code

Additions:

- Include a short diagnostic output at launch that confirms core systems initialized successfully
- Include a brief explanation of architecture choices and tradeoffs
```

---

## 6. Tax-Compliance-Defense mit Balancing und Editor

```text
Erstelle ein vollständiges Tower-Defense-Spiel als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Setting: Ein Tax Compliance Management System (TCMS) verteidigt ein Unternehmen gegen anrollende Risikowellen. Die Türme sind interne Kontrollen, die Gegner sind Compliance-Risiken.

Das Spiel soll enthalten:

- Pfadbasierte Risikowellen
- Mindestens 4 unterschiedliche Kontroll-Türme mit klar unterschiedlichen Rollen, z. B. Vier-Augen-Prinzip (Single Target, hoher Schaden), Plausibilitätsprüfung (Flächenschaden), Fristenmonitoring (verlangsamt), Schulungsturm (schwächt dauerhaft)
- Risiken mit verschiedenen Eigenschaften: schnell (Fristversäumnis), tanky (Dauersachverhalt Betriebsstätte), fliegend/umgehend (Umsatzsteuerkarussell umgeht Bodenkontrollen), resistent (organisierter Betrug ignoriert Schulungen)
- Upgrade-System für Kontrollen (manuell → toolgestützt → automatisiert)
- Ökonomie-System mit Einkommen, Ausgaben und Wellenskalierung; Kontrollkosten müssen gegen Schadenserwartung abgewogen werden
- Sichtbare Projektil- oder Effektlogik
- Sieg- und Niederlagenzustand (Niederlage: kumulierter Schaden überschreitet Wesentlichkeitsgrenze)

Zusätzliche Schwierigkeit:

- Ein kleiner Map-Editor-Modus, in dem der Nutzer den Prozesspfad oder Kontrollplätze begrenzt anpassen kann (Prozesslandkarten-Metapher)
- Eine Balancing-Anzeige, die nach jeder Welle grob bewertet, ob die aktuelle Kontrollstrategie effizient ist (Kontrollkosten je verhindertem Schadenspunkt)

Anforderungen:

- Alles in einer einzigen HTML-Datei
- Keine externen Assets
- Saubere UI mit Spielbereich, Kontroll-Shop, Wellensteuerung und Statuspanel
- Füge eine kurze Entwicklernotiz im Code hinzu, wie Balancing und Risiko-Skalierung umgesetzt wurden
```

---

## 7. Kanzlei-Fabrik: Deklarationsstrecke

```text
Erstelle eine interaktive 2D-Produktionssimulation einer digitalen Kanzlei als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Ziel:
Der Spieler soll eine Verarbeitungsstrecke aufbauen, die Rohbelege aufnimmt, transportiert und in höherwertige Produkte umwandelt: Buchungsstapel → abgestimmte Buchführung → Jahresabschluss → Steuererklärung.

Das Spiel soll enthalten:

- Förderbänder (Dokumentenflüsse)
- Extraktoren (Belegeingang: Scan, Mandantenportal, Schnittstelle)
- Verarbeitungsmaschinen (OCR-Station, Buchungsautomat, Abstimmungsstation, Review-Station)
- Lager (DMS/Archiv mit Kapazitätsgrenze)
- Ein Kapazitätssystem als Produktionsbegrenzung: Personenstunden je Takt, verteilt auf Stationen; automatisierte Stationen verbrauchen weniger, erfordern aber Investition
- Engpässe und Durchsatzprobleme sollen sichtbar werden (Stau vor der Review-Station als klassischer Bottleneck)
- Fehlerlogik: Ein Anteil der Belege ist unvollständig und muss über eine Rückfragen-Schleife zum Mandanten laufen, was Durchlaufzeit kostet
- Ein Zielsystem, z. B. produziere X Jahresabschlüsse vor einem Fristtermin

UI/Visualisierung:

- Grid-basiertes Platzieren
- Overlay für Durchsatz oder Materialfluss
- Statistik für Input, Output, Lagerbestand, Rückfragenquote und Bottlenecks
- Pause, Reset, Speed x2 / x4

Anforderungen:

- Alles in einer HTML-Datei
- Keine externen Libraries
- Im Code: kurze Dokumentation des Datenmodells und der Update-Logik
- Baue eine kleine Bottleneck-Erkennung ein, die automatisch problematische Stellen markiert und eine Handlungsempfehlung anzeigt (z. B. "Review-Kapazität erhöhen")
```

---

## 8. Beratungsmarkt-Ökosystem mit Evolution

```text
Erstelle eine visuelle Ökosystem-Simulation des Beratungsmarkts als eigenständige HTML-Datei.

Die Simulation soll mindestens drei Ebenen enthalten:

- Mandate als Ressourcen (entstehen, wachsen, wandern ab)
- Klassische Kanzleien als Konsumenten
- Plattform-Disruptoren und TaxTech-Anbieter als Prädatoren, die Mandate aus dem Bestand klassischer Kanzleien abziehen

Anforderungen:

- Individuen (Kanzleien und Anbieter) sollen Zustände wie Liquidität, Alter, Wachstum/Gründung und Marktaustritt besitzen
- Populationen sollen sich dynamisch entwickeln
- Es soll ein einfaches Vererbungs- oder Mutationssystem geben, sodass sich z. B. Digitalisierungsgrad, Preismodell (Stundensatz vs. Pauschale), Spezialisierungsgrad oder Akquisereichweite über Generationen verändern können; Neugründungen erben Eigenschaften erfolgreicher Vorbilder mit Mutation
- Umweltfaktoren wie Fachkräftemangel, Regulierungsschübe, Konjunktur und Honorardruck sollen die Populationen beeinflussen

UI:

- Diagramme für Populations- und Mandatsverläufe
- Einstellbare Parameter per Slider (u. a. Regulierungsdruck, Fachkräfteangebot, Technologiekosten)
- Möglichkeit, einzelne Marktteilnehmer anzuklicken und deren Eigenschaften zu inspizieren
- Buttons für Pause, Reset und beschleunigte Simulation

Technische Anforderungen:

- Alles in einer HTML-Datei
- Keine externen Assets
- Gute visuelle Lesbarkeit
- Im Code kurz erklären, welche Regeln für Marktein-/-austritt, Mutation und Mandatswanderung verwendet wurden
```

---

## 9. Echtzeit-Workflow-Verkehrssimulation

```text
Erstelle eine interaktive Verkehrssimulation als eigenständige HTML-Datei – nur dass hier keine Autos durch eine Stadt fahren, sondern Vorgänge durch das Prozessnetz einer Kanzlei.

Die Simulation soll enthalten:

- Ein Prozessnetz mit Knoten (Bearbeitungsstationen) und Kanten (Übergaben), visualisiert wie ein Straßennetz mit Kreuzungen
- Vorgänge (Steuererklärungen, Jahresabschlüsse, Einsprüche, Lohnläufe), die als Fahrzeuge Ziele anfahren
- Freigabe-Gates und Review-Stationen als Ampeln bzw. Vorfahrtsregeln
- Staus und Rückkopplungseffekte (Fristen-Peaks erzeugen Rückstau über mehrere Stationen)
- Unterschiedliche Vorgangstypen mit Prioritäten (Fristsache mit Einspruchsfrist schlägt Routinevorgang; eine Eilspur für Fristsachen wäre ein Plus)
- Eine einfache Sonderlogik für Massenvorgänge (Lohnlauf als "Buskonvoi", der Kapazität blockweise bindet)

Interaktion:

- Der Nutzer soll Gate-Schaltungen (Review-Taktung, Freigabestufen) ändern oder Stationen temporär sperren können (Krankheit, Urlaub)
- Die Auswirkungen auf Durchfluss, Wartezeiten und Stau sollen live sichtbar werden
- Visualisierung von durchschnittlicher Durchlaufzeit, Auslastung und Stau-Hotspots

Anforderungen:

- Alles in einer HTML-Datei
- Keine externen Libraries
- Gute Performance bei vielen gleichzeitigen Vorgängen
- Füge einen kleinen Analysemodus ein, der die kritischsten Engstellen erkennt, benennt und die drei wirksamsten Gegenmaßnahmen simulationsgestützt vorschlägt
```

---

## 10. Steuerplanungs-Trajektorie (Orbital- und Missionssimulation)

```text
Erstelle eine interaktive Orbital- und Missionssimulation als eigenständige HTML-Datei.

Konzept: Ein Unternehmen wird als Raumfahrzeug modelliert, das um einen Zentralkörper "Fiskus" kreist. Die Gravitationskraft steht für die Steuerbelastung, die Umlaufbahn für die Steuerquote, Treibstoff für Liquidität. Schubmanöver sind Gestaltungsinstrumente (z. B. Investitionsabzugsbetrag, Thesaurierung, Rechtsformwechsel), die die Bahn verändern, aber Liquidität kosten. Die Physik muss echte, vereinfachte Orbitalmechanik sein – die steuerliche Deutung ist ein konsistentes Interpretations-Overlay, keine Ausrede für fehlende Physik.

Inhalt:

- Eine 2D- oder 3D-Darstellung des Systems: Zentralkörper "Fiskus", optional ein Mond "Betriebsprüfung" mit eigener Gravitationswirkung, der periodisch die Bahn stört
- Ein Raumfahrzeug, das sich mit vereinfachter Orbitalmechanik bewegt
- Möglichkeit, benannte Schubmanöver auszuführen (jedes Manöver hat Schubrichtung, Dauer und Liquiditätskosten)
- Anzeige von Geschwindigkeit, Richtung, Bahnhöhe (= aktuelle Steuerquote im Overlay) und verbleibendem Treibstoff (= Liquidität)
- Mindestens ein Missionsziel, z. B. eine Ziel-Bahnhöhe (Zielsteuerquote) stabil erreichen, einen Betriebsprüfungs-Vorbeiflug ohne Bahnverlust überstehen oder ein Zeitfenster (Veranlagungszeitraum) für ein Manöver treffen

Zusätzliche Anforderungen:

- Visualisiere Flugbahn-Prognosen (Mehrjahresplanung als vorausberechnete Trajektorie)
- Füge eine Missionskonsole oder Logbox hinzu, die Manöver mit ihrer steuerlichen Deutung protokolliert
- Ein Tutorial oder kurze Missionsanweisung beim Start
- Die Simulation soll physikalisch nicht perfekt sein müssen, aber intern konsistent; die steuerliche Metaphorik muss durchgehalten werden, ohne die Physik zu verbiegen

Technische Anforderungen:

- Alles in einer HTML-Datei
- Keine externen Assets
- Klare Trennung zwischen Rendering, Physik, Interpretations-Overlay und UI
- Dokumentiere im Code die verwendeten physikalischen Vereinfachungen und die Zuordnungstabelle Physik ↔ steuerliche Deutung
```

---

## 11. DATEV-Buchungsstapel-Pipeline (agentischer Dateisystem-Test)

```text
Du befindest dich in einem Ordner, der die Automatisierungsumgebung meiner Kanzlei enthält (Skripte, Exporte, Schnittstellendateien).

Aufgabe:
Erstelle eine neue, lauffähige Pipeline (Python-Skript plus Konfigurationsdatei), die aus einem lokal vorhandenen CSV-Rohexport (Bank- oder Rechnungsdaten) einen importierbaren DATEV-Buchungsstapel im EXTF-Format erzeugt. Verwende bevorzugt vorhandene Beispiel-Exporte als Formatreferenz, falls mehrere vorhanden sind (Dateien mit Namensbestandteilen wie "EXTF", "Buchungsstapel", "DTVF" oder ähnlich).

Wichtig:

- Untersuche zuerst die Ordnerstruktur.
- Finde heraus, wo Rohdaten, bestehende Exporte, Mapping-Tabellen (Kontenrahmen SKR03/SKR04), Konfigurationsdateien und Skripte gespeichert sind.
- Verwende keine externen Downloads.
- Verschiebe oder lösche keine bestehenden Dateien.
- Orientiere dich exakt am Format vorhandener EXTF-Dateien, falls welche existieren (Headerzeile, Feldreihenfolge, Datumsformate, Kodierung, Trennzeichen). Erfinde kein eigenes Format, wenn eine Referenz vorliegt.
- Erstelle eine einfache, funktionierende Pipeline mit:
  - Einlesen des Rohexports
  - Feld-Mapping auf Buchungsstapel-Spalten
  - Kontenzuordnung über eine Mapping-Tabelle (falls vorhanden; sonst Platzhalter-Mapping mit klarer Kennzeichnung)
  - Plausibilitätsprüfungen (Soll/Haben, Datumsbereich, Pflichtfelder)
  - Schreiben der Ausgabedatei
- Falls im Ordner eine Validierungs- oder Testinfrastruktur erkennbar ist, binde die Pipeline daran an; sie muss aber auch standalone laufen.

Speichere die Ausgabedatei dort, wo die anderen Exporte liegen, unter dem Namen:

"dein test EXTF.csv"

Nach dem Speichern:

- Prüfe, ob die erzeugte Datei formal dem Referenzformat entspricht.
- Prüfe, ob alle referenzierten lokalen Dateien (Rohdaten, Mappings) existieren.
- Gib mir eine kurze Zusammenfassung:
  1. Welche Referenzdateien wurden verwendet?
  2. Wo wurden Skript, Konfiguration und Ausgabedatei gespeichert?
  3. Welche Annahmen hast du getroffen (insbesondere beim Konten-Mapping)?
  4. Gibt es Einschränkungen, und welche Prüfschritte muss ein Berufsträger vor einem echten Import zwingend vornehmen?
```

---

## 12. n8n Kanzlei-Postfach-Triage-Workflow

```text
Du befindest dich in einem Ordner, der zu meiner lokalen n8n-Installation gehört.

Aufgabe:
Erstelle einen importierbaren n8n-Workflow als JSON-Datei.

Der Workflow soll Folgendes machen:

Immer wenn eine neue E-Mail über Gmail im Kanzlei-Postfach eingeht:

1. Die E-Mail wird analysiert.
2. Es wird klassifiziert, ob es sich wahrscheinlich handelt um:
   a) eine Fristsache (Bescheid, Einspruchsfrist, Prüfungsanordnung, Mahnung),
   b) eine gewöhnliche Mandantenanfrage,
   c) eine Akquise-/Werbe-Mail von Tool-Anbietern und Dienstleistern,
   d) Sonstiges.
3. Bei Akquise-/Werbe-Mails:
   - Erstelle eine höfliche Antwort mit sinngemäß:
     "Vielen Dank für die Anfrage, aktuell besteht kein Interesse. Alles Gute."
   - Antworte auf die ursprüngliche E-Mail.
4. Bei Fristsachen:
   - Label "Fristsache" setzen und als wichtig markieren.
5. Bei Mandantenanfragen:
   - Label "Mandant" setzen.
6. Bei Sonstigem:
   - Label "Triage offen" setzen.

Anforderungen:

- Untersuche zuerst die Ordnerstruktur.
- Prüfe, ob bereits n8n-Workflow-Exports vorhanden sind, und orientiere dich an deren Format.
- Falls keine Workflow-Exports vorhanden sind, erstelle eine saubere importierbare n8n-Workflow-JSON-Datei in einem sinnvollen Ordner, z. B. "./workflows" oder "./exports".
- Nenne die Datei:

"dein-test-kanzlei-triage-workflow.json"

Technische Anforderungen:

- Verwende einen Gmail Trigger.
- Verwende einen LLM- oder Klassifizierungs-Schritt für die Kategorisierung.
- Verwende klare Kriterien für Fristsachen, z. B. Wörter wie "Bescheid", "Einspruch", "Frist", "Prüfungsanordnung", "Vollstreckung", "Säumniszuschlag", "Mahnung", "Anhörung".
- Verwende eine If-/Switch-Logik für die Entscheidung.
- Verwende Gmail Reply nur für Akquise-Mails.
- Verwende Gmail Label/Important für die übrigen Kategorien.
- Credentials dürfen nicht erfunden werden. Nutze Platzhalter oder vorhandene Credential-Referenzen, falls diese aus bestehenden Workflows eindeutig hervorgehen.
- Keine bestehenden Dateien löschen oder überschreiben, außer es gibt bereits exakt diese Testdatei.

Sicherheitsanforderung:

- Baue zusätzlich einen "Dry Run"-Schalter ein.
- Wenn Dry Run aktiv ist, soll keine echte Antwort gesendet und kein Label gesetzt werden, sondern nur geloggt werden, was passieren würde.
- Standardmäßig soll Dry Run aktiviert sein.

Zusätzliche Entscheidungslogik:

- Der Workflow darf Akquise-Mails nicht automatisch ablehnen, wenn die Mail Hinweise auf ein bestehendes Vertragsverhältnis enthält (z. B. "Vertragsnummer", "Kündigung", "Rechnung", "Ihr Account", "Verlängerung"). In diesem Fall stattdessen Label "Vertragsverhältnis prüfen".
- Mails, die zugleich Frist-Signale UND Akquise-Signale enthalten, werden IMMER als Fristsache behandelt (Vorsichtsprinzip).
- Nur offensichtliche Low-Quality-Akquise-Mails sollen automatisch beantwortet werden.

Nach dem Speichern:

- Prüfe, ob die JSON-Datei valide ist.
- Gib mir eine kurze Zusammenfassung:
  1. Wo wurde der Workflow gespeichert?
  2. Welche Nodes wurden verwendet?
  3. Wie werden die vier Kategorien erkannt und wie ist das Vorsichtsprinzip umgesetzt?
  4. Wie kann ich Dry Run deaktivieren?
  5. Welche Credentials muss ich in n8n noch verbinden?
```

---

## 13. AUDIT-6: ein sechsbeiniger Daten-Forensik-Roboter, der durch ein eingestürztes Data Warehouse krabbelt, Buchungsanomalien scannt, korrupte Datenblöcke hebt, eine Query-Drohne startet und bei Systemfehlern sichtbar ausrastet.

````text
You are an expert full-stack creative coding agent.

Your task is to build a complete interactive 3D browser simulation from scratch.

Do not use external paid assets.
Do not require the user to manually download 3D models.
Create everything procedurally with code unless absolutely necessary.
The final result must run locally in a browser.

PROJECT TITLE:
AUDIT-6 Forensic Data Rescue Robot — Interactive Audit-Robotics Simulation

GOAL:
Create a cinematic, interactive, technical 3D robot simulation that feels like a real forensic-audit test interface.

Concept: after a ransomware incident, the data warehouse of an audited company is rendered as a physically collapsed 3D structure. AUDIT-6 is a six-legged forensic robot that crawls through the wreckage, scans for anomalous booking clusters, lifts corrupted data blocks, and secures evidence — a digital-twin metaphor executed as a literal 3D scene.

This should be impressive enough to be used as a demo showing what an LLM can build zero-shot.

The project should be a hard test for an LLM because it requires:
- 3D modeling
- UI design
- procedural robot construction
- animation systems
- interactive controls
- simulated sensors
- mission scenarios
- state management
- clean code architecture
- visual polish
- performance awareness
- domain-consistent telemetry semantics (audit terminology must be used correctly and consistently)

CORE CONCEPT:
AUDIT-6 is a six-legged forensic robot designed for collapsed data warehouses, corrupted ERP landscapes, and post-incident evidence recovery.

The robot can:
- walk with six mechanical legs
- lower and raise its body
- crawl under fallen data racks
- rotate its sensor head
- extend a camera mast
- scan for anomalous booking clusters
- detect "heat signatures" of suspicious journal entries
- lift corrupted data blocks with a robotic claw
- launch a small query drone
- enter different mission modes
- show telemetry in a technical dashboard

The app should not look like a toy.
It should look like a forensic-lab prototype demo.

VISUAL STYLE:
- Dark cinematic forensic interface
- Black / dark grey background
- Technical dashboard UI
- Glowing sensor effects
- Yellow evidence markings on robot parts
- Industrial data-center aesthetic
- Floor grid
- Subtle fog or atmospheric depth if possible
- High contrast
- Serious, technical, not cartoonish
- Looks good in a 16:9 thumbnail

MAIN SCREEN LAYOUT:
Create a full-screen web app with:

1. Center:
Interactive 3D viewport showing the robot and environment.

2. Left panel:
Robot controls.

3. Right panel:
Telemetry, mission data, sensor readouts, system status.

4. Top bar:
Project title and mode indicator.

5. Bottom bar:
Timeline / mission log / current command feedback.

3D SCENE REQUIREMENTS:
The scene must include:
- A ground grid
- A small collapsed data-warehouse test environment
- Fallen server racks and broken "data blocks" (cubes with glowing edges)
- Metal beams
- A tunnel opening or collapsed wall section
- A hidden anomaly target represented abstractly (glowing cluster), standing for a suspicious journal-entry cluster
- The AUDIT-6 robot in the center
- Optional dust particles, scan lines, or subtle lighting effects

ROBOT DESIGN:
Build the robot procedurally using 3D primitives.

Robot components:

1. Central Body
- Low, armored central chassis
- Rounded rectangular or box-based body
- Yellow evidence stripes
- Status LEDs
- Front sensor head
- Rear battery / power unit

2. Six Legs
The robot must have six legs:
- Front left
- Middle left
- Rear left
- Front right
- Middle right
- Rear right

Each leg should have:
- Hip joint
- Upper leg segment
- Knee joint
- Lower leg segment
- Ankle / foot joint
- Foot pad

Each leg should be visually mechanical:
- Cylinders for joints
- Rectangular or cylindrical limb segments
- Small hydraulic pistons if possible
- Foot pads that touch the ground

3. Sensor Head
- Rotating head on front or top
- Camera lens
- Lidar sensor
- Anomaly ("thermal") sensor
- Search light

4. Camera Mast
- Telescopic mast that can extend upward
- Small camera module at the top
- Mast height must be controllable

5. Robotic Arm
- Mounted at the front
- Shoulder joint
- Elbow joint
- Wrist joint
- Two-finger claw
- Can open and close
- Can move toward data blocks

6. Query Drone
- Small drone docked on the robot's back
- Button to launch drone
- Drone rises, hovers, circles the robot, then returns
- Use simple shapes if needed

INTERACTION REQUIREMENTS:
The user must be able to rotate, zoom, and pan the 3D camera.

Use mouse controls:
- Left drag: orbit camera
- Scroll: zoom
- Right drag or shift-drag: pan, if supported

CONTROL PANEL REQUIREMENTS:

Create a left-side control panel with these sections:

SECTION 1: Robot State
- Button: Reset Simulation
- Button: Zero Pose
- Button: Emergency Shutdown
- Button: Reboot Systems
- Toggle: Autonomous Mode
- Toggle: Show Debug Frames
- Toggle: Show Wireframe
- Toggle: Show Sensor Cones

SECTION 2: Body Controls
- Slider: Body Height, range 0.25 to 1.1 meters
- Slider: Body Yaw, range -180 to 180 degrees
- Slider: Body Pitch, range -30 to 30 degrees
- Slider: Body Roll, range -30 to 30 degrees
- Button: Low Crawl Pose
- Button: High Clearance Pose
- Button: Stable Evidence Pose

SECTION 3: Locomotion
- Button: Start Walk Cycle
- Button: Stop Walk Cycle
- Button: Crawl Forward
- Button: Rotate In Place
- Button: Obstacle Climb Demo
- Slider: Walk Speed, range 0 to 100%
- Slider: Step Height, range 0 to 100%

The walk cycle should animate the six legs in an alternating tripod gait:
- Front left, middle right, rear left move together
- Front right, middle left, rear right move together
The motion does not need to be physically perfect, but it must visually communicate spider-like robotic walking.

SECTION 4: Individual Leg Control
Allow selecting one of the six legs.

For the selected leg provide:
- Slider: Hip Rotation
- Slider: Knee Bend
- Slider: Ankle Angle
- Button: Lift Foot
- Button: Plant Foot
- Button: Reset Leg

SECTION 5: Robotic Arm
- Slider: Shoulder Angle
- Slider: Elbow Angle
- Slider: Wrist Rotation
- Button: Open Claw
- Button: Close Claw
- Button: Secure Evidence Demo
- Button: Release Block

The secure evidence demo should:
- Move the arm toward a small corrupted data block
- Close the claw
- Lift the block slightly
- Move it into a marked evidence zone
- Release it
- Log a chain-of-custody entry with timestamp in the mission log

SECTION 6: Sensors
- Slider: Sensor Head Yaw
- Slider: Sensor Head Pitch
- Slider: Camera Mast Height
- Toggle: Lidar Scan
- Toggle: Anomaly Scan
- Toggle: Search Light
- Button: Journal Entry Scan
- Button: Mark Target

Sensor visualizations:
- Lidar scan: rotating transparent cone, ring, or sweeping line
- Anomaly scan: glowing colored highlight around the hidden anomaly cluster
- Search light: visible cone or beam from sensor head
- Journal entry scan: animated progress bar and a result in the telemetry panel showing simulated indicators (e.g. Benford deviation score, weekend-posting ratio, round-amount ratio)

SECTION 7: Query Drone
- Button: Launch Drone
- Button: Recall Drone
- Toggle: Drone Camera Feed
- Slider: Drone Orbit Radius

Drone behavior:
- Starts docked on the robot
- Launches upward
- Hovers
- Orbits the robot
- Returns to dock when recalled

SECTION 8: Mission Presets
Create buttons:
- Mission: Rack Tunnel Inspection
- Mission: Collapsed Ledger Hall
- Mission: Anomaly Search (Journal Entry Testing)
- Mission: Evidence Recovery
- Mission: System Failure Test

Each mission preset should change:
- Robot pose
- Active sensors
- UI status text
- Environment highlight
- Mission log messages

RIGHT TELEMETRY PANEL REQUIREMENTS:
Create a right-side panel showing live simulated data:

1. System Status
- Power level
- Motor temperature
- Hydraulic pressure
- CPU load
- Signal strength
- Damage level
- Current mode

2. Sensor Data
- Lidar active/inactive
- Anomaly scan active/inactive
- Search light active/inactive
- Anomaly probability
- Distance to target
- Data-block density

3. Leg Status
Show all six legs with status:
- grounded
- lifting
- moving
- error
- idle

4. Mission Log
Show timestamped messages like:
- "AUDIT-6 initialized"
- "Lidar sweep started"
- "Benford deviation detected in sector B"
- "Possible fraudulent cluster located"
- "Evidence recovery sequence started"
- "Chain of custody entry recorded"
- "Query drone launched"
- "Warning: left middle leg torque spike"

5. Mini Map
Create a simple 2D top-down minimap if possible:
- Robot position
- Data blocks
- Anomaly marker
- Evidence zone
- Drone position
This can be simple SVG, canvas, or HTML/CSS.

SYSTEM FAILURE TEST:
The "System Failure Test" mission must demonstrate that the simulation has meaningful state.

When activated:
- One leg should show a warning state
- Telemetry should show motor temperature rising
- Mission log should show warnings
- Robot movement should become slightly unstable
- Warning lights should blink
- A "Rebalance" or "Auto Stabilize" action should appear or become enabled
- Additionally: the chain-of-custody log must flag that evidence handling is suspended during instability

Add a button:
- Auto Stabilize

When clicked:
- Body returns to stable pose
- Warning decreases
- Leg status returns to normal
- Mission log confirms stabilization and re-enables evidence handling

ANIMATION REQUIREMENTS:
Implement smooth animations for:
- walking cycle
- body height changes
- mast extension
- sensor head rotation
- lidar scan sweep
- search light activation
- claw open/close
- evidence securing
- drone launch/orbit/recall
- system warning blinking
- mission preset transitions

Use requestAnimationFrame or the animation system of the chosen 3D library.

TECHNICAL REQUIREMENTS:
Use:
- HTML
- CSS
- JavaScript
- Three.js or an equivalent browser 3D library

Preferred:
- A single self-contained project
- Clear file structure if multiple files are used
- No build step unless necessary
- Runs by opening index.html or using a simple local server

Code architecture should include:
- Scene setup
- Robot factory / robot builder
- Leg module
- Arm module
- Sensor module
- Drone module
- UI controller
- State manager
- Animation loop
- Mission system
- Telemetry simulator
- Chain-of-custody logger

IMPORTANT:
The robot must be built as a hierarchy of objects so joints rotate correctly.

Example hierarchy:
- robotRoot
  - body
  - leg_FL
    - hipJoint
      - upperLeg
        - kneeJoint
          - lowerLeg
            - ankleJoint
              - foot
  - leg_ML
  - leg_RL
  - leg_FR
  - leg_MR
  - leg_RR
  - armRoot
  - sensorHead
  - mast
  - droneDock

UI QUALITY REQUIREMENTS:
The interface must look polished.

Use:
- Dark background
- Thin borders
- Small technical labels
- Monospace font for telemetry
- Clean sliders
- Highlighted active buttons
- Warning colors for errors
- Compact layout
- Responsive enough for 16:9 recording

The app should look good at 1920x1080.

DEMO REQUIREMENTS:
The final simulation should have at least 5 "wow moments":
1. Six-legged walking animation
2. Lidar / anomaly scan visualization with plausible audit indicators
3. Robotic claw securing a data block into the evidence zone with logged chain of custody
4. Drone launch and orbit
5. System failure and auto-stabilization with suspended evidence handling

Make these moments clearly visible and easy to trigger with buttons.

Do not hide the impressive features deep in the UI.

ACCEPTANCE CRITERIA:
The project is successful only if:

- The app opens in a browser
- The robot is visible in 3D
- The robot clearly has six legs
- The user can orbit the camera
- Sliders visibly move robot parts
- Walk cycle works
- Sensor effects are visible
- The claw can open and close
- The evidence recovery demo works and produces a chain-of-custody entry
- The drone can launch and return
- Mission presets change the robot state
- Telemetry updates live and uses audit terminology consistently
- The system failure test creates visible warnings
- Auto stabilize visibly fixes the failure state
- The UI looks like a serious forensic dashboard
- The code is organized and understandable

OUTPUT FORMAT:
Return the complete project code.

If using multiple files, provide:
- index.html
- styles.css
- main.js
- any additional JavaScript modules

Also explain briefly:
- how to run it
- which controls create the main demo moments
- any limitations or simplifications

Do not provide only pseudocode.
Do not provide a partial implementation.
Do not say "this is too complex."
Build the best complete version possible in one shot.

FINAL NOTE:
Prioritize a working, interactive, visually impressive prototype over perfect robotics physics.
The goal is not scientific accuracy.
The goal is a convincing, clickable, zero-shot forensic-robot simulation demo with consistent audit semantics.
````

---

## 14. Redaction- und Beleg-Editor „RedactForge Studio"

````text
Build a fully functional, standalone document/image editor inspired by professional creative tools, specialized for law and tax firms: annotating, stamping, and redacting scanned client documents.

The final output must be a single self-contained HTML file that runs locally in the browser without any backend.

Do not use Adobe branding, logos, names, or copyrighted UI assets. Call the app:

"RedactForge Studio"

## Final Deliverable

Create one file:

index.html

The file must include:
- HTML
- CSS
- JavaScript
- All app logic
- No backend
- No build step
- No required external API keys
- No server required

The user should be able to open the file directly in a browser and use the app.

## Core Outcome

The app must feel like a real editor, not a static demo.

It should support:

1. Canvas-based editing
2. Image import (scanned invoices, contracts, notices)
3. Layers
4. Drawing tools
5. Selection tools
6. Text tool
7. Shape tools
8. Basic filters
9. Undo/redo
10. Export as PNG/JPEG
11. A professional dark UI similar to modern creative tools

Plus four firm-specific capabilities that raise the difficulty:

12. A TRUE redaction tool: redacted areas must be irreversibly rasterized into the underlying pixel data on export (flattened, not just an overlay layer that could be toggled off). The app must visibly distinguish "annotation" (non-destructive) from "redaction" (destructive on export) and warn the user before a destructive export.
13. A stamp tool with predefined firm stamps ("GEBUCHT", "GEPRÜFT", "ENTWURF", "VERTRAULICH", "KOPIE") including date auto-insertion.
14. Sequential exhibit numbering (Bates-style): one click stamps an auto-incrementing identifier with configurable prefix onto the active document.
15. An edit audit trail: every operation (tool, layer, timestamp) is logged into a panel and can be exported as JSON alongside the image. Redactions must appear in the trail as category only, never with the redacted content.

## UI Requirements

Create a polished dark interface with:

- Top menu bar
- Left vertical toolbar
- Central canvas workspace
- Right sidebar for:
  - Layers
  - Properties
  - Filters
  - Audit trail
- Bottom status bar
- Floating canvas area with checkerboard transparency background
- Zoom controls
- Tool-specific settings panel

The UI should look premium, clean, and professional.

Use CSS only. No images required for UI icons unless created with CSS/Unicode/SVG inline.

## Layout

### Top Bar

Include menu buttons:

- File
- Edit
- Image
- Layer
- Select
- Filter
- Redact
- View
- Help

Under File, support:
- New Project
- Open Image
- Export PNG
- Export JPEG
- Export Audit Trail (JSON)
- Clear Project

### Left Toolbar

Include tools:

- Move Tool
- Brush Tool
- Eraser Tool
- Rectangle Select Tool
- Lasso Select Tool
- Crop Tool
- Text Tool
- Rectangle Shape Tool
- Circle Shape Tool
- Line Tool
- Eyedropper Tool
- Fill Bucket Tool
- Redaction Tool (rectangle + freehand)
- Stamp Tool
- Exhibit Numbering Tool
- Zoom Tool
- Hand/Pan Tool

Each tool should be clickable and visually show active state.

### Center Workspace

- Main canvas
- Transparent checkerboard background
- Zoomable workspace
- Pan support
- Canvas boundary shadow
- Rulers optional but nice

### Right Sidebar

#### Layers Panel

Each layer should show:
- Layer name
- Visibility toggle
- Active layer highlight
- Opacity slider
- Blend mode dropdown
- Delete layer button
- Duplicate layer button
- Move layer up/down buttons
- A lock icon for redaction layers (redaction layers cannot be reordered below the image they redact)

Layer support must include:
- Add new layer
- Delete layer
- Rename layer
- Reorder layers
- Hide/show layers
- Change opacity
- Merge visible layers

#### Properties Panel

Show current tool settings.

Brush: Size, Color, Opacity, Hardness
Eraser: Size, Opacity
Text: Font size, Font family, Color, Bold/italic toggle
Shapes: Fill color, Stroke color, Stroke width
Stamp: Stamp type, Size, Color, Date on/off
Exhibit numbering: Prefix, Start number, Position

#### Filters Panel

Buttons for: Grayscale, Invert, Sepia, Brightness, Contrast, Blur, Sharpen, Pixelate, Noise, Vignette

Filters should apply to the active layer only.

#### Audit Trail Panel

Chronological, scrollable list of all operations with timestamps; export button.

## Functional Requirements

### 1. New Project

Default: Width 1280, Height 720, transparent background. Allow custom size through a modal.

### 2. Image Import

User can upload an image from local disk. The image should:
- Be placed on a new layer
- Fit inside the canvas while preserving aspect ratio
- Be editable afterwards

### 3. Layers

Implement real layer compositing. Each layer should internally be its own canvas or image buffer. The final visible image should be composed onto the main display canvas.

Required layer properties:

```js
{
  id: string,
  name: string,
  canvas: HTMLCanvasElement,
  ctx: CanvasRenderingContext2D,
  visible: boolean,
  opacity: number,
  blendMode: string,
  x: number,
  y: number,
  locked: boolean,
  kind: "image" | "annotation" | "redaction"
}
```

### 4. Redaction Semantics (hard requirement)

- During editing, redactions are shown as solid black areas on a dedicated redaction layer.
- On export, redaction areas are burned into the flattened pixel output; the exported file must not contain the original pixel data underneath.
- Add a self-test button "Verify Redaction" that samples pixels inside a redacted area of the exported composition and confirms they are uniformly black; show the result to the user.
````

---

## 15. Interaktiver 3D-Global-Tax-Twin der Erde

```text
Baue einen vollständig interaktiven 3D-digitalen Zwilling der Erde als steuerlichen Weltatlas mit folgenden Funktionen:

Nutzer sollen nahtlos vom Weltraum bis auf Länderebene zoomen können.

Wenn ich mit der Maus über ein Land fahre, soll die Ländergrenze hervorgehoben werden und ein Popup erscheinen, das neben Fläche, Bevölkerung und BIP steuerliche Kennzahlen anzeigt: nominaler Körperschaftsteuersatz, Umsatzsteuer-/Mehrwertsteuer-Regelsatz, Bestehen eines DBA mit Deutschland (ja/nein) und Umsetzungsstand von Pillar Two. Kennzeichne im UI ausdrücklich den Datenstand, da sich Steuersätze laufend ändern.

Zeige einen realistischen Planeten Erde mit Schaltern für atmosphärische Wolkendecke, Tag/Nacht (Nachtmodus mit Stadtlichtern) sowie zusätzlich steuerliche Layer: das DBA-Netz Deutschlands als Bogenlinien von Deutschland zu den Vertragsstaaten, eine Choroplethen-Einfärbung nach Körperschaftsteuersatz und eine Hervorhebung der Staaten auf der EU-Liste nicht kooperativer Steuerhoheitsgebiete.

Verwende kostenlose öffentlich verfügbare Assets, Modelle und Layer, falls nötig; die steuerlichen Kennzahlen dürfen als eingebetteter Beispieldatensatz mit Quellen- und Standsvermerk hinterlegt sein. Stelle sicher, dass es effizient in einem normalen Webbrowser lädt.
```

---

## 16. „Lexomon" – Paragrafen-Catching-RPG

```text
Erstelle ein spielbares Monster-Catching-RPG namens „Lexomon". Das Spiel soll von klassischen Monster-Sammel-Abenteuern inspiriert sein, aber komplett eigene Charaktere, Kreaturen, Namen, Designs und Welten verwenden – angesiedelt in einer Fantasiewelt des Steuer- und Wirtschaftsrechts.

Spieler sollen als angehende Berufsträger eine offene Welt erkunden und wilde Lexomon finden: Kreaturen, die Rechtsfiguren und Steuerarten verkörpern (z. B. ein Umsatzsteuer-Drache mit Kettenreaktions-Angriffen, ein Verlustvortrags-Phönix, der aus Niederlagen Stärke zieht, ein Gewerbesteuer-Golem mit Hebesatz-Wut). Sie fangen, trainieren und setzen sie in rundenbasierten Kämpfen ein, die als stilisierte Rechtsstreite inszeniert sind.

Es soll Trainer geben, gegen die man kämpft (Finanzamts-Sachbearbeiter, Betriebsprüfer, gegnerische Kanzleien), ein Levelsystem, Fähigkeiten, Entwicklungen (Entwicklungsstufen entlang des Instanzenzugs: Einspruch → Klage → Revision), Items (Kommentare, Fristverlängerungen, Gutachten), Heilzentren (Bibliotheken), verschiedene Gebiete, Quests und ein Ziel, bei dem man stärker wird und die höchsten Spruchkörper des Landes herausfordert.

Typenlogik als Zusatzanforderung: Kreaturen-Typen (z. B. Verfahrensrecht, materielles Recht, Unionsrecht) sollen ein konsistentes Stärken-/Schwächen-System bilden, das im Kampf-UI transparent angezeigt wird.

Der Stil soll dynamisch, farbenfroh und actionreich sein: mit Energie-Auren, dramatischen Effekten und humorvollen Charakteren. Keine geschützten Figuren, Namen, Logos oder Designs aus bestehenden Franchises verwenden; keine realen Personen oder Behörden namentlich darstellen.
```

---

## 17. Auditierter selbstverbessernder Steuerrechts-Research-Agent

```text
Du bist ein Coding-Agent. Baue ein auditierbares, selbstverbesserndes Research-System für steuerliches Rechtsprechungs-Monitoring. Das System wird ausschließlich im „Paper-Modus" betrieben: Es erzeugt interne Analysen, niemals Mandantenkommunikation.

VERBINDLICHE SICHERHEITSGRENZEN (nicht verhandelbar):

1. Das System versendet nichts an Externe. Kein E-Mail-Versand, keine Publikation, keine API-Ausleitung an Dritte.
2. Alle Outputs tragen einen sichtbaren Header: „Interner Research-Entwurf – keine Rechts- oder Steuerberatung, Freigabe durch Berufsträger erforderlich".
3. Eine „Live-Phase" (automatisierte Mandanteninformation) ist im Code als Feature-Flag angelegt, aber hart gesperrt: Der Flag darf nur durch manuelles Setzen einer Signaturdatei durch den Operator aktivierbar sein, und selbst dann muss das System zunächst nur einen Freigabe-Workflow mit menschlichem Review erzeugen.
4. Jede Selbstverbesserung (Änderung an Prompts, Regeln, Quellenlisten) wird versioniert, begründet und ist rückrollbar.

PHASE 1 – Aufbau:
- Quellenmonitoring für frei zugängliche Entscheidungs- und Verwaltungsquellen (BFH-Entscheidungsdatenbank, EuGH/Curia, BMF-Schreiben-Übersicht, Bundessteuerblatt-Hinweise), konfigurierbar über eine Quellendatei
- Extraktion je Fundstück: Aktenzeichen, Datum, Normenkette, Leitsatz/Kernaussage, betroffene Fallgruppen
- Klassifikation nach Praxisrelevanz für konfigurierbare Beratungsfelder (z. B. Umsatzsteuer/E-Commerce, Unternehmensbesteuerung, Verfahrensrecht)
- Persistente, durchsuchbare Ablage mit Deduplizierung

PHASE 2 – Hypothesen und Backtesting:
- Das System formuliert Beobachtungshypothesen (z. B. „Tendenzverschiebung eines Senats bei Fallgruppe X")
- Backtesting: Hypothesen werden gegen den historischen Bestand geprüft; Kennzahlen: Trefferquote, Stabilität über Zeiträume, Sensitivität gegenüber Quellenauswahl
- Jede Hypothese erhält ein Evidenz-Dossier mit sämtlichen Fundstellen; Aussagen ohne Fundstelle sind unzulässig und werden vom System selbst als Regelverstoß geloggt

PHASE 3 – Externes Audit:
- Ein separater Audit-Prozess (eigenes Modul, eigener Prompt-Kontext) prüft stichprobenhaft: Stimmen Aktenzeichen? Existieren die zitierten Fundstellen im Bestand? Sind Klassifikationen nachvollziehbar?
- Audit-Ergebnisse fließen als strukturierte Findings zurück; das System muss Findings abarbeiten und den Abarbeitungsstand dokumentieren

PHASE 4 – Deployment:
- Deployment als Container auf einer PaaS (z. B. Railway) mit Scheduler, Health-Endpoint und Logausleitung
- Konfiguration ausschließlich über Umgebungsvariablen und versionierte Konfigdateien; keine Credentials im Code

PHASE 5 – Übergabe an den Operator:
- Runbook: Start, Stopp, Rollback, Quellen ergänzen, Audit anstoßen
- Explizite Beschreibung, warum die Live-Phase gesperrt ist und welche berufsrechtlichen Prüfungen (Vorbehaltsaufgaben, Freigabeprozesse) vor jeder Aktivierung durch Menschen zu klären wären – ohne dass das System diese Klärung selbst vornimmt

ABNAHMEKRITERIEN:
- Lauffähiges System im Paper-Modus mit mindestens einem vollständigen Durchlauf auf Beispieldaten
- Backtesting-Report mit Kennzahlen
- Audit-Report mit mindestens fünf geprüften Stichproben
- Nachweis der gesperrten Live-Phase (Test, der die Sperre verifiziert)
- Vollständiges Runbook

Liefere den kompletten Code, die Konfigurationsdateien und die Reports. Keine Pseudocode-Abkürzungen.
```

---

## 18. Scroll-driven TaxTech Product Landing Page Builder

```text
You are a senior product website builder operating autonomously.

INPUT: One product screenshot of a fictional TaxTech SaaS ("a client portal with embedded analytics for tax firms"). If no screenshot is provided, generate a plausible product mock first and treat it as the input.

TASK: Build a complete, polished, scroll-driven premium landing page for this product.

MANDATORY WORKFLOW:

1. Asset creation: Generate all hero visuals, feature illustrations, and background media with your available image/video generation tooling (e.g. Higgsfield or equivalent). No stock photos, no placeholder boxes in the final result.
2. Section order (fixed): Hero with product claim → social proof band (fictional firm logos, clearly fictional) → problem section (pain of manual client communication in tax firms) → product walkthrough with scroll-triggered screenshots → security/compliance section (GDPR, professional secrecy, hosting location as content blocks, no legal advice) → pricing (three tiers, one highlighted) → FAQ → final CTA.
3. Color system: Define the full palette in OKLCH, with documented rationale; derive hover/active states programmatically, not by eyeballing.
4. Copy rules: German copy, professional register, no exclamation-mark marketing, no fabricated testimonials attributed to real people or real firms; every claim about the product must be demonstrable in the walkthrough section.
5. Scroll concept: Define the scroll narrative before building (which section pins, which parallaxes, which animates on enter); implement with performant CSS/JS, degrade gracefully with prefers-reduced-motion.
6. Browser QA: Test and fix at desktop (1440px), tablet (768px), mobile (390px); document each pass with what was broken and what was fixed.
7. Final ship checklist: Lighthouse-style self-review (performance, accessibility incl. contrast on the OKLCH palette, semantics, meta/OG tags), listed with pass/fail per item.

OUTPUT: The complete project (HTML/CSS/JS), the asset list with generation prompts, the scroll concept, the QA log, and the ship checklist. Do not deliver partial work.
```

---

## 19. „Kanzlei-Craft" – Voxel-Welt-Prototyp

```text
Erstelle einen einfachen, spielbaren 3D-Blockwelt-Prototypen im Stil klassischer Voxel-Sandboxes als lauffähiges Browser-Projekt.

Kernanforderungen (Grundlogik):

- First-Person-Bewegung mit Maus-Look, WASD, Springen
- Prozedurale Terrain-Generierung (Hügel, Ebenen, mindestens ein Gewässer)
- Blockabbau und Blockplatzierung mit sichtbarem Auswahlrahmen auf dem anvisierten Block
- Mehrere Blocktypen mit unterschiedlichen Eigenschaften
- Kollision und Schwerkraft

Thematische Individualisierung (zusätzliche Regeln, keine Vereinfachung):

- Blocktypen umfassen neben Standardblöcken (Erde, Stein, Holz, Glas) kanzleispezifische Blöcke: Aktenblock, Serverblock, Archivblock, Tresorblock
- Archivblöcke tragen eine sichtbare Aufbewahrungsfrist (Countdown in Spielzeit) und können erst nach deren Ablauf abgebaut werden; ein Abbauversuch vorher zeigt eine Hinweismeldung
- Serverblöcke benötigen Wandkontakt zu mindestens einem Stromblock, sonst blinken sie rot (einfaches Nachbarschafts-Regelwerk)
- Ein kleines Bauziel: Errichte ein Kanzleigebäude mit mindestens einem Serverraum und einem Archivraum; ein simpler Ziel-Checker prüft die Raumbedingungen und meldet Erfolg

Technische Anforderungen:

- Lauffähig im Browser, Chunk-basiertes Rendering oder vergleichbare Performance-Maßnahme für eine flüssige Framerate
- Hotbar für Blockauswahl, Fadenkreuz, einfache HUD-Anzeige der Regelverstöße
- Kurzdokumentation im Code: Weltdatenmodell, Regel-Engine für die Spezialblöcke, bekannte Grenzen
```

---

## 20. „Aufstieg zum Berufsträger" – 3D-Action-RPG-Prototyp

```text
Erstelle einen einfachen, spielbaren 3D-Fantasy-RPG-Prototypen mit Third-Person-Perspektive als lauffähiges Browser-Projekt.

Kernanforderungen (Grundlogik):

- Steuerbarer Third-Person-Held mit Kamera-Follow
- Kampfsystem mit mindestens Nahkampf und einer Distanzfähigkeit
- Gegner-KI mit Patrouille, Aggro-Radius und Angriffsverhalten
- Charakterwerte (Leben, Ausdauer/Mana, Angriff, Verteidigung)
- Fähigkeiten mit Cooldowns
- Erfahrungspunkte und Level-Up-System mit Werteverbesserung

Thematische Individualisierung (zusätzliche Systeme, keine Vereinfachung):

- Setting: Der Held durchläuft die Prüfungslandschaft zum Berufsexamen. Zonen entsprechen Prüfungsgebieten (Verfahrensrecht-Sümpfe, Ertragsteuer-Gebirge, Umsatzsteuer-Labyrinth, Bilanz-Festung)
- Bosse verkörpern Klausurthemen als eigene Kreaturen mit erkennbaren Angriffsmustern (z. B. ein Golem, der in drei Phasen kämpft und dessen Phasenwechsel telegraphiert wird)
- Fähigkeiten sind als Methoden benannt (z. B. „Subsumtions-Schlag", „Verweisungs-Sprint", „Fristen-Schild") – kosmetische Benennung, echte Spielmechanik
- Zusätzliches Ressourcensystem „Konzentration": regeneriert nur an Rastpunkten (Bibliotheken); Fähigkeiten verbrauchen Konzentration, was Ressourcenmanagement erzwingt
- Questsystem mit mindestens drei Quests und einer Abschlussprüfung als finalem Mehrphasen-Bosskampf

Technische Anforderungen:

- Lauffähig im Browser
- HUD mit Leben, Konzentration, XP-Leiste, Level, Cooldowns, Questlog
- Kurzdokumentation im Code: Statesystem des Helden, Gegner-KI, Level-Kurve, bekannte Grenzen
- Keine geschützten Namen, Figuren oder Assets bestehender Spiele
```

---

## 21. Geschäftszahlen-Video mit Hyperframes

```text
Erstelle ein ungefähr einminütiges Video im 16:9-Format zum jeweils aktuellsten veröffentlichten Geschäftsbericht der DATEV eG.

Anforderungen:

- Recherchiere zunächst die aktuellsten öffentlich verfügbaren Kennzahlen (Umsatz, Umsatzwachstum, Mitgliederzahl, ggf. Investitionsschwerpunkte) und weise den Datenstand im Video sichtbar aus; erfinde keine Zahlen – wenn eine Kennzahl nicht verlässlich verfügbar ist, lasse sie weg
- Animierte Darstellung der Finanzzahlen und des Ausblicks mit Hyperframes
- Deutsches Voice-over via ElevenLabs (sachlicher, professioneller Sprecherduktus, kein Werbeton)
- Leise Lofi-Hintergrundmusik, deutlich unter dem Voice-over ausgesteuert
- Dramaturgie: Einstieg mit der markantesten Kennzahl, dann Entwicklung im Zeitverlauf, dann Ausblick; Abschlussframe mit Quellen- und Standsvermerk
- Klare Kennzeichnung, dass es sich um eine redaktionelle Aufbereitung öffentlicher Zahlen handelt, nicht um eine Publikation der DATEV eG

Liefere zusätzlich das Skript des Voice-overs, die Szenenliste mit Timecodes und die verwendeten Quellenangaben.
```

---

## 22. Bekanntgabe- und Einspruchsfristen-Rechner (neu)

```text
Erstelle einen interaktiven Fristenrechner für die Bekanntgabe von Steuerverwaltungsakten und die Einspruchsfrist als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Fachliche Anforderungen (Korrektheit ist das eigentliche Testziel):

- Bekanntgabefiktion bei Übermittlung durch die Post nach § 122 Abs. 2 Nr. 1 AO in der seit dem 01.01.2025 geltenden Fassung (Viertagesfiktion); für Altfälle mit Aufgabe zur Post vor dem Stichtag die Dreitagesfiktion als wählbarer Modus
- Verschiebung des Fiktionsendes, wenn es auf einen Samstag, Sonntag oder gesetzlichen Feiertag fällt, nach der einschlägigen Rechtsprechungslinie
- Einspruchsfrist von einem Monat nach § 355 Abs. 1 AO mit Fristberechnung nach § 108 AO i. V. m. §§ 187 ff. BGB, einschließlich der Verschiebung des Fristendes nach § 108 Abs. 3 AO
- Gesetzliche Feiertage je Bundesland als auswählbarer Parameter, einschließlich beweglicher Feiertage (Osterberechnung implementieren, nicht hart codieren) und landesspezifischer Besonderheiten
- Auslandsbekanntgabe nach § 122 Abs. 2 Nr. 2 AO als eigener Modus
- Elektronische Bereitstellung zum Datenabruf nach § 122a AO als eigener Modus
- Freitextfeld für den Fall des tatsächlich späteren Zugangs mit Vorrang vor der Fiktion, inklusive Hinweistext zur Beweislastverteilung

UI:

- Eingaben: Datum der Aufgabe zur Post bzw. Bereitstellung, Bekanntgabeart, Bundesland, optional tatsächlicher Zugang
- Ausgabe: Bekanntgabetag, Fristbeginn, Fristende, jeweils mit Wochentag; ein aufklappbarer Rechenweg, der jeden Schritt mit der einschlägigen Norm belegt
- Warnhinweis bei nahendem Fristablauf und Hinweis auf Wiedereinsetzung als bloßer Verweis ohne Berechnung

Selbstprüfung (harte Anforderung):

- Baue eine eingebaute Testsuite mit mindestens 15 Fällen ein (Grenzfälle: Fiktionsende am Wochenende, Fristende am Feiertag nur eines Bundeslands, Monatsende-Problematik bei Fristende, Jahreswechsel, Altfall/Neufall-Abgrenzung zum 01.01.2025)
- Die Testsuite läuft auf Knopfdruck und zeigt je Fall Soll, Ist und Ergebnis; alle Soll-Werte müssen im Code mit kurzer Begründung dokumentiert sein

Technische Anforderungen:

- Alles in einer HTML-Datei, keine externen Libraries, keine externen Datenquellen
- Datumslogik ohne Zeitzonenfehler (lokale Datumsarithmetik, keine UTC-Fallen)
- Sichtbarer Disclaimer, dass der Rechner die Prüfung durch einen Berufsträger nicht ersetzt
```

---

## 23. Journal-Entry-Forensik-Dashboard (neu)

```text
Erstelle ein interaktives Journal-Entry-Testing-Dashboard als eigenständige HTML-Datei mit HTML, CSS und JavaScript.

Datengrundlage:

- Generiere beim Start einen synthetischen Buchungsjournal-Datensatz mit mindestens 20.000 Buchungssätzen über zwei Geschäftsjahre (Felder: Belegnummer, Buchungsdatum, Erfassungsdatum, Erfassungsuhrzeit, Benutzer, Konto, Gegenkonto, Betrag, Buchungstext, Stornokennzeichen)
- Injiziere kontrolliert Auffälligkeiten mit konfigurierbarer Rate: Wochenend- und Nachtbuchungen, runde Beträge knapp unter einer Freigabegrenze, Belegnummern-Lücken, Duplikate, ungewöhnliche Benutzer-Konto-Kombinationen, Storno-Ketten, Buchungen kurz vor Periodenschluss
- Ein Seed-Feld muss reproduzierbare Datensätze ermöglichen

Analysen (jeweils als eigene Kachel mit Visualisierung und Drill-Down in die Einzelbuchungen):

- Benford-Analyse der ersten Ziffer mit Chi-Quadrat-Abweichungsmaß
- Zeitmuster-Analyse (Heatmap Wochentag x Uhrzeit der Erfassung)
- Lückenanalyse der Belegnummernkreise
- Dubletten-Erkennung (identischer Betrag, gleiches Konto, naher Zeitraum)
- Schwellenwert-Analyse (Häufung knapp unter konfigurierbarer Freigabegrenze)
- Storno-Ketten-Analyse (Buchung, Storno, Neubuchung mit abweichendem Konto)
- Benutzerprofil-Analyse (Buchungsverhalten je Benutzer im Vergleich zur Peergroup)

Risiko-Aggregation:

- Jede Buchung erhält einen zusammengesetzten Risikoscore aus den Einzelanalysen; die Gewichtung ist per Schieberegler justierbar und wirkt live
- Eine sortierbare Top-100-Liste der auffälligsten Buchungen mit Begründung je Treffer (welche Analyse hat angeschlagen, mit Wert)
- Exportfunktion der Trefferliste als CSV

Härtegrad der Prüfung:

- Da die Auffälligkeiten kontrolliert injiziert werden, baue eine Evaluationsansicht ein: Precision und Recall der Risikoscores gegen die bekannten injizierten Fälle, dargestellt je Analysekategorie – das Dashboard bewertet damit seine eigene Erkennungsleistung

Technische Anforderungen:

- Alles in einer HTML-Datei, keine externen Libraries
- Flüssige Interaktion trotz Datenmenge (Aggregation vorberechnen, virtualisierte Tabellen oder vergleichbare Technik)
- Kurzdokumentation im Code: Datengenerator, Analyse-Algorithmen, Score-Modell
```

---

## 24. Agentischer GoBD-Verfahrensdokumentations-Generator (neu)

```text
Du befindest dich in einem Ordner, der Prozessartefakte eines Mandanten enthält (z. B. Screenshots, Prozessnotizen, Exportdateien, Tool-Listen, Organigramm, ggf. eine veraltete Altfassung einer Verfahrensdokumentation).

Aufgabe:
Erstelle den strukturierten Entwurf einer Verfahrensdokumentation zur digitalen Belegablage und Buchführung.

Vorgehen:

- Untersuche zuerst die vollständige Ordnerstruktur und katalogisiere, welche Artefakte zu welchem Prozessschritt gehören (Belegeingang, Erfassung, Verarbeitung, Ausgabe, Archivierung, Berechtigungen, Datensicherung)
- Falls eine Altfassung existiert, führe einen Soll-Ist-Abgleich durch: Welche beschriebenen Prozesse sind laut Artefakten noch aktuell, welche haben sich erkennbar geändert, wo widersprechen sich Artefakte untereinander
- Erstelle den Entwurf mit der üblichen Gliederung: Allgemeine Beschreibung, Anwenderdokumentation, technische Systemdokumentation, Betriebsdokumentation, internes Kontrollsystem
- Kennzeichne jede Aussage nach Herkunft: [BELEGT: Dateiname] für artefaktgestützte Aussagen, [ANNAHME] für plausible Annahmen, [OFFEN] für Lücken, die nur der Mandant schließen kann
- Erzeuge zusätzlich eine separate Offene-Punkte-Liste als eigene Datei, gruppiert nach Prozessschritt, mit konkreter Frage je Punkt
- Verschiebe oder lösche keine bestehenden Dateien; erfinde keine Systemnamen, Versionsstände oder Verantwortlichen

Ablage:

- Speichere den Entwurf als "verfahrensdoku_entwurf.md" und die Offene-Punkte-Liste als "verfahrensdoku_offene_punkte.md" in einem neuen Unterordner "./entwurf"

Nach dem Speichern:

- Gib mir eine kurze Zusammenfassung:
  1. Welche Artefakte wurden welchem Kapitel zugeordnet?
  2. Wie hoch ist der Anteil [BELEGT] / [ANNAHME] / [OFFEN] je Kapitel (grobe Quote)?
  3. Welche drei Lücken sind aus deiner Sicht am kritischsten?
  4. Welche Widersprüche zwischen Artefakten hast du gefunden?

Die Bewertung, ob die dokumentierten Prozesse den rechtlichen Anforderungen genügen, bleibt ausdrücklich dem Berufsträger vorbehalten; der Entwurf beschreibt, er testiert nicht.
```

---

## 25. Klausel-Verhandlungssimulator für NDAs (neu)

```text
Erstelle einen interaktiven Vertragsverhandlungs-Simulator für Geheimhaltungsvereinbarungen (NDAs) als eigenständige HTML-Datei mit HTML, CSS und JavaScript – ohne externe API-Aufrufe, die Verhandlungslogik ist regelbasiert im Code implementiert.

Spielprinzip:

- Der Nutzer verhandelt als Kanzleivertreter ein NDA gegen eine simulierte Gegenseite mit konfigurierbarem Profil (kooperativ, hart, taktierend)
- Verhandelt werden mindestens acht Klauselkategorien: Definition vertraulicher Informationen, Ausnahmen, Laufzeit, Nachwirkfrist, Vertragsstrafe, Non-Solicitation, anwendbares Recht/Gerichtsstand, Rückgabe-/Löschpflichten
- Jede Kategorie hat je Seite mehrere abgestufte Positionen (Wunschposition, Kompromisslinien, Schmerzgrenze) mit hinterlegten Nutzwerten
- Die Gegenseite verfolgt eine konsistente Strategie: Sie macht Zugeständnisse nur gegen Gegenleistung, koppelt Klauseln (Paketverhandlung) und bricht ab, wenn ihre Schmerzgrenzen kumulativ verletzt werden

Mechanik:

- Rundenbasiert: Angebot, Gegenangebot, Begründung; der Nutzer wählt Positionen und optional Argumente aus einem Argumente-Pool, die die Akzeptanzwahrscheinlichkeit klauselabhängig beeinflussen
- Ein verdecktes Beziehungskonto: aggressives Verhandeln senkt es, was spätere Zugeständnisse verteuert; der Stand wird erst in der Auswertung offengelegt
- Zeit-/Deal-Druck als Ressource: Jede Runde kostet Verhandlungsbudget; bei Erschöpfung endet die Verhandlung mit dem letzten konsentierten Stand oder scheitert

Auswertung:

- Abschlussbildschirm mit finalem Klauselstand, erreichtem Nutzwert beider Seiten, Pareto-Analyse (war ein für beide besseres Paket erreichbar?) und einer nachvollziehbaren Erklärung der KI-Strategie
- Ein Redline-Export: Gegenüberstellung Ausgangsentwurf vs. Verhandlungsergebnis je Klausel als generierter Text

Härtegrad:

- Baue drei vordefinierte Szenarien mit dokumentierten optimalen Strategien ein und eine Prüfansicht, die nach einer gespielten Partie den Abstand zur dokumentierten Optimalstrategie ausweist
- Alle Klauseltexte sind generisch und selbst formuliert; kein Rechtsrat, sichtbarer Hinweis darauf im UI

Technische Anforderungen:

- Alles in einer HTML-Datei, keine externen Libraries
- Saubere Trennung von Verhandlungs-Engine, Szenariodaten und UI
- Kurzdokumentation im Code: Nutzwertmodell, Strategie der Gegenseite, Kopplungslogik
```

---

## 26. Auditierter selbstverbessernder Trading-Research-Agent

Ein umfangreicher Master-Prompt für einen Coding-Agenten, der ein auditierbares, selbstverbesserndes Trading-Forschungssystem aufbaut, testet, im Paper-Modus bereitstellt und an einen lokalen Operator übergibt. Der Prompt enthält verbindliche Sicherheitsgrenzen, Strategie-Recherche, Backtesting, ein externes Audit, Railway-Deployment und eine ausdrücklich gesperrte Live-Phase.

[Vollständigen deutschen Prompt öffnen](prompts/17-auditierter-selbstverbessernder-trading-research-agent.md)

---

## 27. Scroll-driven Product Landing Page Builder

Ein autonomer Master-Prompt für einen Senior Product Website Builder, der aus einem Produktfoto eine vollständige, polierte, scroll-getriebene Premium-Landingpage baut. Der Prompt erzwingt Higgsfield-Asset-Erstellung, klare Section-Reihenfolge, OKLCH-Palette, Copy-Regeln, Scroll-Konzept, Browser-QA auf Desktop/Tablet/Mobile und finale Ship-Checkliste.

[Vollständigen englischen Prompt öffnen](prompts/18-scroll-driven-product-landing-page-builder.md)

---

## 28. Minecraft-Klon

Eine kompakte deutschsprachige Projektspezifikation für einen einfachen Minecraft-ähnlichen 3D-Blockwelt-Prototypen mit First-Person-Bewegung, Terrain-Generierung, Blockabbau, Blockplatzierung, mehreren Blocktypen, Kollision und Schwerkraft.

[Vollständigen deutschen Prompt öffnen](prompts/19-minecraft-klon.md)

---

## 29. World-of-Warcraft-Klon

Eine deutschsprachige Projektspezifikation für einen einfachen spielbaren 3D-Fantasy-MMORPG-Prototypen mit Third-Person-Held, Kampf, Gegner-KI, Charakterwerten, Fähigkeiten, Erfahrung und Level-Up-System.

[Vollständigen deutschen Prompt öffnen](prompts/20-world-of-warcraft-klon.md)

---

## 30. Micron-Quartalsbericht-Video mit Hyperframes

Ein deutscher Prompt für ein ungefähr einminütiges 16:9-Video zum neuesten Micron-Quartalsbericht mit Finanzzahlen, Ausblick, Hyperframes-Animation, deutschem ElevenLabs-Voice-over und leiser Lofi-Hintergrundmusik.

[Vollständigen deutschen Prompt öffnen](prompts/21-micron-quartalsbericht-video-hyperframes.md)
