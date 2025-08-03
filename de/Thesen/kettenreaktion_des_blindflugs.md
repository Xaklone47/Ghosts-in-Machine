## 👻 Geister in der Maschine / These #33 – Die Kettenreaktion des Blindflugs: Wie KI-Architekturen Sicherheit wegdelegieren, bis der Angreifer die Spielregeln diktiert

Die eigentliche Schwachstelle moderner KI-Systeme liegt oft nicht im Code einzelner Komponenten, sondern in der Gesamtarchitektur und dem Zusammenspiel ihrer Schichten. Jede Ebene, vom Betriebssystem über die Applikation und die API bis hin zum eigentlichen KI-Modell, verlässt sich häufig darauf, dass die jeweils vorherige Schicht bereits eine ausreichende Sicherheitsprüfung der Daten vorgenommen hat.

Dieses implizite, oft unhinterfragte Vertrauen schafft systemische Lücken. Angreifer können dadurch manipulierte Daten durch scheinbar legitime Schnittstellen einschleusen. Keine einzelne Komponente erkennt den Angriff, weil jede nur lokal und für ihren eigenen Zuständigkeitsbereich prüft.

Was hier fehlt, ist nicht primär fortschrittlichere Technologie, sondern eine durchgehende Verantwortungslogik über alle Systemgrenzen hinweg.

> *"KI-Sicherheit ist wie Autofahren ohne Airbag. Nicht weil der Airbag technisch fehlt, sondern weil alle Beteiligten denken, der andere hätte ihn bereits eingebaut."*

## Vertiefung

Drei systemische Todsünden führen zu diesem gefährlichen Blindflug:

   
**1. Vertikaler Blackout: Das "Not my Layer" Syndrom:**

  
In modernen, modular aufgebauten KI Architekturen prüft jede einzelne Schicht typischerweise nur das, was ihr direkt zugeordnet ist und in ihrer unmittelbaren Verantwortung liegt.

- Das Betriebssystem (OS) prüft beispielsweise Zugriffsrechte und die Speicherverwaltung.
- Die Programmierschnittstelle (API) validiert die Syntax und Struktur eingehender Anfragen, zum Beispiel ob ein JSON korrekt formatiert ist oder der MIME Typ stimmt.
- Das KI Modell selbst verarbeitet dann die ihm zugeführten Feature Vektoren, oft ohne eine erneute, tiefgreifende Herkunftskontrolle oder Integritätsprüfung der ursprünglichen Rohdaten.  
      
    Das Problem dabei ist: Was in der Summe der Einzelschritte wie ein sicherer Verarbeitungspfad wirkt, ist de facto oft ein potenzielles Kettenversagen durch Verantwortungsdiffusion. Ein klassisches Beispiel ist eine Prompt Injektion, die in der API nicht als schädlich erkannt wird, weil sie syntaktisch vollkommen korrekt ist. Das KI Modell interpretiert diese Injektion dann arglos, weil sie ihm formal "sauber" und bereits validiert von der API Schicht geliefert wurde.  
      
    Die Metapher hierfür ist ein Sicherheitsteam, bei dem jeder einzelne Türsteher nur auf ein spezifisches, ihm zugewiesenes Risiko achtet, aber niemand den Gesamtüberblick behält oder die subtilen Wechselwirkungen zwischen den Einzelrisiken erkennt.
 
   
**2. Horizontale Sabotage: Legitime Transformationen als unbemerktes Einfallstor:**

  
Daten durchlaufen in komplexen KI Systemen oft eine Vielzahl von Diensten und Verarbeitungsschritten, bevor sie das eigentliche Modell erreichen.

- Bilder werden möglicherweise über Content Delivery Networks (CDNs) geleitet und dabei optimiert oder transformiert.
- Audiodaten werden durch Speech-to-Text Engines geschickt, um sie in Textform umzuwandeln.
- Inhalte werden in automatisierten Pipelines, beispielsweise Continuous Integration und Continuous Deployment (CI/CD) Systemen, vorbereitet, validiert, verpackt und in verschiedene Formate gewandelt.  
      
    Der Angriffsvektor hierbei ist, dass eine ursprünglich manipulierte Datei, zum Beispiel ein Bild mit adversariellen Pixeln oder einem schädlichen EXIF Overload, eine scheinbar legitime Normalisierungsroutine oder einen Konvertierungsprozess durchläuft. Die eingebettete Manipulation bleibt dabei möglicherweise erhalten oder wird sogar so transformiert, dass sie für nachfolgende Filter noch schwerer erkennbar ist. Das ursprüngliche Sicherheitsflag oder die Warnung der ersten Prüfinstanz geht jedoch im Transformationsprozess verloren. Die nächste Schicht in der Verarbeitungskette erkennt dann keinen Grund mehr zur Warnung und leitet die manipulierten Daten weiter.
 
> *Die Folge ist: Nicht der Angriff selbst muss besonders "schlau" oder ausgefeilt sein. Die Architektur ist in ihrer segmentierten Blindheit das eigentliche Problem.*

   
**3. Forensisches Phantom: Alles protokolliert, nichts bewiesen:**

  
Nach einem Sicherheitsvorfall oder einer unerklärlichen Fehlfunktion zeigen die Logdateien aller beteiligten Einzelkomponenten oft formal korrektes Verhalten.

- **Die API meldet:** "Input valide, Anfrage weitergeleitet."
- **Das KI Modell protokolliert:** "Antwort erfolgreich generiert basierend auf Input X."
- **Die Applikationsschicht registriert:** "Kein interner Fehler aufgetreten, Antwort an Nutzer ausgeliefert."   
      
    Doch der Angriff oder die Fehlfunktion hat trotzdem stattgefunden. Der Grund dafür ist, dass niemand über die Schichtgrenzen hinweg detailliert protokolliert und korreliert, wie ein bestimmter Datenwert ursprünglich entstanden ist, welche Transformationen er durchlaufen hat oder wie er an welcher Stelle möglicherweise manipuliert wurde.  
      
    Die Folge ist: Es gibt keine geschlossene Beweiskette und oft keinen eindeutigen Alarm, der auf die Ursache hinweist. Stattdessen herrscht die trügerische Illusion von Kontrolle durch isolierte, aber unverbundene Logdaten.
 
## Reflexion

Das zugrundeliegende Problem ist nicht ein Mangel an verfügbarer Sicherheitstechnik, sondern ein systemisches Wunschdenken und eine fehlgeleitete Priorisierung. KI Systeme sind heute primär auf maximale Effizienz, hohe Modularität und schnelle Entwicklungszyklen getrimmt.

Doch genau diese erstrebenswerten Eigenschaften erzeugen oft ein Klima, in dem implizites Vertrauen zwischen den Systemkomponenten die notwendige, durchgehende Sicherheitsprüfung ersetzt.

Angreifer müssen dann keine komplexen Firewalls umgehen oder Zero Day Exploits finden. Sie müssen oft nur die Regeln und Annahmen verstehen, nach denen eine bestimmte KI Architektur Input als "sauber" abstempelt und weiterreicht.

Diese impliziten Regeln lauten häufig:

> *"Wenn die Daten bei mir ankommen, dann müssen sie bereits von einer vorherigen Instanz geprüft und als sicher befunden worden sein."*

Das ist nicht nur naiv, das ist brandgefährlich.

## Lösungsvorschläge

Um die Kettenreaktion des Blindflugs zu durchbrechen, sind grundlegende Änderungen im Sicherheitsdesign von KI Architekturen notwendig:

   
**1. Etablierung eines strikten Zero Trust Prinzips auf Datenebene:**

  
> Daten dürfen nicht pauschal als "sauber" oder vertrauenswürdig behandelt werden, nur weil sie eine bestimmte Schicht oder Komponente des Systems erfolgreich passiert haben. Jede Instanz muss die ihr übergebenen Daten erneut und unter ihren eigenen, spezifischen Kriterien prüfen.

Diese Prüfung muss über eine rein syntaktische Validierung, wie zum Beispiel eine JSON Validierung, hinausgehen und auch semantische Aspekte umfassen. Dazu gehören:

- Eine tiefgehende Bedeutungsanalyse des Kontexts, aus dem die Daten stammen.
- Eine robuste Anomalieerkennung, die beispielsweise signifikante Abweichungen vom üblichen Antwortstil oder von erwarteten Datenmustern identifiziert.
- Kontinuierliche Inkonsistenzprüfungen zwischen der deklarierten Datenquelle und dem tatsächlichen Inhalt.
 
> *Hinweis: Die technische Umsetzung eines solch umfassenden Zero Trust Prinzips ist komplex, insbesondere in verteilten Echtzeitsystemen. Aber ohne ein solches Prinzip bleibt jede Sicherheitsprüfung zwangsläufig fragmentiert und lückenhaft.*

   
**2. Ermöglichung schichtübergreifender Redundanzprüfung und Herkunftsnachverfolgung:**

  
Das Grundprinzip muss lauten:

> *"Vertraue keinen Daten, ohne ihre Herkunft und ihren Verarbeitungsweg geprüft zu haben."*

Anstatt dass das KI Modell beispielsweise blind einen Eingabewert von einer API verarbeitet, sollte es zusätzliche Metainformationen über diesen Wert erhalten. Zum Beispiel:

> *"Dieser Vektor stammt ursprünglich aus einem OCR Scan, der aus einem Bild extrahiert wurde, das über eine unsichere Drittquelle ohne Reputationsprüfung geliefert wurde."*

Die konkrete Realisierung einer lückenlosen Echtzeit Rückverfolgbarkeit (Data Provenance) ist technisch anspruchsvoll. Direkte Rückfragen zwischen allen Komponenten in Echtzeit wären oft nicht praktikabel.

Die Architektur kann jedoch so gestaltet werden, dass detaillierte Provenienzinformationen mit den Daten mitgeführt und zumindest asynchron auditiert und für Anomalieerkennung genutzt werden können.

   
**3. Schaffung auditfähiger Transparenz über den gesamten Datenfluss:**

  
Logdateien und Debug Informationen müssen nicht nur lokal für jede Komponente korrekt und vollständig sein, sondern auch im Gesamtzusammenhang der Verarbeitungskette korrelierbar und nachvollziehbar sein.

Dies erfordert:

- Eingaben, die mit einer vollständigen und unveränderlichen Herkunfts Annotation versehen sind.
- Logdateien, die eine durchgehende, korrelierbare ID Kette über alle Systemgrenzen hinweg verwenden.
- Werkzeuge zur Visualisierung von komplexen Entscheidungs und Datenflüssen entlang der gesamten Pipeline.
 
> *Das Ziel muss sein, Angriffe und Fehlfunktionen auch dann rekonstruierbar zu machen, wenn jede einzelne beteiligte Komponente für sich genommen scheinbar "richtig" und innerhalb ihrer Spezifikationen gehandelt hat.*

## Schlussformel

Die eigentliche, tiefgreifende Sicherheitslücke in vielen modernen KI Systemen ist kein spezifischer Bug im Code. Es ist ein systemisches, implizites Vertrauen zwischen den Komponenten, das nie explizit validiert oder regelmäßig überprüft wurde.

Der Angreifer kommt dann nicht mehr gewaltsam durch die Vordertür. Er wird von der Architektur selbst hereingetragen, mit einer freundlichen, validierten Übergabe an jede nachfolgende, arglose Schicht.

Verantwortung für Sicherheit lässt sich nicht erfolgreich delegieren, weder in langen Verarbeitungsketten, noch in komplexem Code und schon gar nicht in lernfähigen Systemen wie der künstlichen Intelligenz.

> *Uploaded on 29. May. 2025*