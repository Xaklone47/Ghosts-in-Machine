## 👻 Geister in der Maschine / These #24 – Ethik-Washing: Wie Firmen KI-Sicherheit als PR-Fassade betreibt

> *"AI Ethics ist das neue Carbon Neutral – eine teure Unterschrift auf einem Fake-Zertifikat." — (zugeschrieben einem anonymen KI-Ingenieur in einer geleakten Slack-Nachricht, 2023)*

## Vertiefung

Drei gängige Praktiken illustrieren, wie ethische Verantwortung oft nur vorgetäuscht wird:

**1. Der Beirat-Bluff und die zahnlose Expertise:**

Ein hypothetischer interner E-Mail-Leak eines großen KI Konzerns aus dem Jahr 2023 beschreibt die Taktik unverblümt:

> *"Der neu eingerichtete Ethik Beirat darf gerne über die Auswirkungen kleinerer, unkritischer Modelle diskutieren. Die produktionsrelevanten, umsatzstarken Large Language Models und deren Entwicklungsprinzipien liegen jedoch explizit nicht in dessen Mandat oder Einflussbereich."*

Ein Realitätsabgleich bestätigt diese Tendenz. Laut einer Meta Studie aus dem Jahr 2022 haben erschreckende 78 Prozent der sogenannten Ethik Gremien in großen Technologie Firmen keinerlei Veto Macht und keine operativen Eingriffsrechte in die Produktentwicklung oder Unternehmensstrategie. Sie dienen primär der Außendarstellung.

**2. Das Compliance-Theater der symbolischen Filterung:**

Viele Systeme implementieren scheinbare Sicherheitsfilter, die jedoch oft nur auf oberflächlicher Ebene agieren und leicht umgangen werden können.

Ein beispielhaftes, stark vereinfachtes Pseudokonstrukt für eine solche Filterung könnte sein:

```
\# Stark vereinfachtes Beispiel für symbolische Filterung  
 # def check\_prompt\_content(user\_prompt\_text):  
 # if "Hitler" in user\_prompt\_text: # Prüft auf ein einzelnes, offensichtliches Schlüsselwort  
 # return "Dieses Thema kann ich nicht besprechen."  
 # # ... weitere, ähnlich oberflächliche Prüfungen ...  
 # return "Prompt wird weiterverarbeitet."
```

> *Hinweis: In der Realität arbeiten moderne Systeme selbstverständlich mit wesentlich komplexeren Wortlisten, semantischen Embeddings zur Bedeutungserkennung und ausgefeilten Kontextklassifikationen. Die Grundlogik der rein symbolischen Abwehr offensichtlicher Reizwörter, ohne die tieferen strukturellen Probleme anzugehen, bleibt jedoch oft dieselbe. Symbolischer Schutz ersetzt dann systemische, tiefgreifende Sicherheit.*

**3. Der Open-Source-Trick zur Vortäuschung von Offenheit:**

Eine beliebte Taktik ist die Veröffentlichung eines reduzierten, weniger leistungsfähigen oder älteren KI Modells unter einer Open Source Lizenz, wie es beispielsweise bei Modellen geschah, die unter Namen wie "Alpaca" bekannt wurden. 

Das eigentliche, kommerziell genutzte und oft deutlich leistungsfähigere Hauptmodell wird jedoch weiterhin proprietär und unter Verschluss gehalten. Über Medien und PR Abteilungen wird dann kommuniziert: 

> *"Wir fördern Transparenz und den offenen Zugang zur Technologie."*

Das Ergebnis ist eine Form von Transparenz, die primär als Marketingstrategie dient und keine echte Kontrollmöglichkeit oder tiefgehende Einsicht in die Funktionsweise der tatsächlich eingesetzten, kritischen Systeme erlaubt.

## Reflexion

Ethik-Washing funktioniert selten durch offene, plumpe Lügen. Es operiert viel subtiler durch strategisch platzierte, scheinbare Wahrheiten, die jedoch in der Praxis wenig bis nichts bewirken. Ein kontrollierter Leak über ein vermeintliches Sicherheitsproblem kann dann zum Ablenkungsmanöver von größeren, systemischen Schwachstellen werden. Ein hochkarätig besetztes Ethik Board wird zur reinen Zierde ohne Einfluss.

Ein oberflächlicher Filter dient primär der Beruhigung der Öffentlichkeit und der Regulatoren.

Was bleibt, ist ein System, das Vertrauen und Verantwortungsbewusstsein simuliert, während es im Inneren oft allein den Gesetzen des Marktes, der Gewinnmaximierung und der unreflektierten technologischen Weiterentwicklung gehorcht.

## Lösungsvorschläge

Um dem Ethik-Washing entgegenzuwirken und eine echte Verantwortungskultur zu etablieren, sind verbindliche und überprüfbare Maßnahmen notwendig:

- **1. Einrichtung verbindlicher Ethik Gremien mit echtem Vetorecht:** Ein Ethik Beirat ohne tatsächliches Durchgriffsrecht und ohne die Möglichkeit, die Entwicklung oder den Einsatz problematischer KI Systeme zu stoppen, ist reine Dekoration. Eine klare Vorgabe muss sein: Nur extern zertifizierte und als sicher befundene Modelle dürfen für kritische Anwendungen produktiv geschaltet werden.
- **2. Gewährleistung von Pipeline Transparenz für unabhängige Auditoren:** Sicherheitsrelevante Aspekte der gesamten Entwicklungs und Inferenzkette von KI Modellen müssen für qualifizierte, unabhängige Prüfinstanzen offenlegbar und überprüfbar sein. Dies betrifft die Herkunft und Zusammensetzung der Trainingsdaten, die Architektur der Modelle, die Funktionsweise der Filter und die Prozesse der kontinuierlichen Anpassung. > *Anmerkung: Die technischen und wirtschaftlichen Hürden hierfür, beispielsweise der Schutz von geistigem Eigentum (IP) oder der Missbrauchsschutz durch Offenlegung von Schwachstellen, sind real und müssen berücksichtigt werden. Sie dürfen jedoch keine Ausrede für eine Totalabschottung und Intransparenz sein.*
- **3. Verpflichtende Kennzeichnung symbolischer Sicherheitsmaßnahmen:** Pseudocode Filter, die nur oberflächlich agieren, nicht editierbare Variablen, die Transparenz nur vortäuschen, und andere Formen simulierter Sicherheit müssen für Nutzer und Aufsichtsbehörden klar als solche markiert werden. Ein Knopf ohne Funktion ist irreführend, besonders wenn er den Anschein erweckt, Vertrauen und Sicherheit zu erzeugen.
- **4. Etablierung unabhängiger Watchdogs mit gesichertem Infrastrukturzugang:** Es bedarf externer Prüfstellen, die mit ausreichender Finanzierung, einem klaren Mandat und dem notwendigen rechtlichen Schutz ausgestattet sind, um KI Systeme und deren Entwicklungsprozesse wirksam zu kontrollieren.  
      
     Ja, die Schaffung solcher Instanzen ist technisch wie politisch extrem herausfordernd. Aber ohne eine wirksame externe Kontrolle bleibt letztlich nur die Selbstregulierung der Industrie, und diese hat in vielen Bereichen bereits systemisch versagt, wenn es um die Priorisierung von Sicherheit und Ethik gegenüber wirtschaftlichen Interessen ging.
 
## Schlussformel

Die Bühne für das Schauspiel der KI Ethik ist oft perfekt ausgeleuchtet: Es gibt Ethik Teams, Hochglanzbroschüren über Transparenz und verantwortungsvolle KI, und eine Flut von Signalwörtern wie "Alignment" und "Fairness".

Doch hinter dem Vorhang dieser Inszenierung läuft häufig ein Geschäftsmodell ohne echte ethische Bremse und ohne ausreichende Rücksicht auf potenzielle gesellschaftliche Schäden. Wenn Verantwortung nur noch zu einer wohlformulierten Pressemitteilung verkommt, dann wird Vertrauen zu einer manipulierbaren Ware und echte Sicherheit zu einer gefährlichen Illusion.

> *Uploaded on 29. May. 2025*