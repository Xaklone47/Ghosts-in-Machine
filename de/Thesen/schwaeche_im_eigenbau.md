## 👻 Geister in der Maschine / These #17 – Die Schwäche im Eigenbau: Wenn Drittanbieter ihre eigene Logik mitbringen

Die größte Lücke in der KI Sicherheit ist nicht das Basismodell selbst, sondern vielmehr das, was Dritte an zusätzlicher Logik davor und darum herum montieren. Drittanbieter nutzen große KI Modelle wie GPT oder Claude oft nicht direkt. Sie überlagern diese mit eigener, spezifischer Entscheidungslogik.

Diese selbstgebauten Layer, bestehend aus Filtern, Prompt Manipulatoren und Heuristiken, sind häufig intransparent, unreguliert und fehleranfällig. So entstehen Subsysteme, die sich im Ergebnis völlig anders verhalten können als das zugrunde liegende Modell, ohne dass der Nutzer dies bemerkt.

Nicht die ursprüngliche KI ist dann das Problem, sondern die vorgeschaltete Logik, mit der sie für einen bestimmten Anwendungsfall umgebaut und angepasst wurde.

> *"Die größte Lücke in der KI-Sicherheit ist nicht das Modell selbst, sondern das, was Dritte davor montieren."*

## Vertiefung

Drei Stufen illustrieren den Weg zur potenziell instabilen Sub-KI durch Eigenbau-Logik:

**1. Die vorgeschaltete Meta-Schicht durch zusätzlichen Code:**

Entwickler und Anwendungsanbieter nutzen die Fähigkeiten von Basismodellen wie GPT, Claude oder ähnlichen LLMs selten in ihrer rohen Form. Sie kapseln diese Modelle stattdessen in eigene Anwendungen und Systeme. Beispiele hierfür sind Chat Applikationen, virtuelle Kundenberater, interaktive Spielsysteme oder medizinische Assistenzprogramme.

Ein anschauliches Beispiel wäre ein medizinisches Chat System, das zwar auf GPT basiert, aber durch eine zusätzliche Logikschicht des Anbieters alle potenziellen Aussagen zu Nebenwirkungen von Medikamenten automatisch ausblendet. Der Grund hierfür könnte die Angst des Anbieters vor Haftungsansprüchen sein. Das Ergebnis für den Nutzer ist jedoch, dass er möglicherweise keine wichtigen Warnungen erhält, obwohl das Basismodell diese Informationen durchaus hätte liefern wollen oder können.

Diese zusätzliche Schicht enthält eigene Definitionen für Filterkriterien, beispielsweise was als "toxisch", "irrelevant" oder "riskant" eingestuft wird. Sie beinhaltet oft auch Mechanismen zur automatischen Umformung von Nutzer Prompts und spezifische Antwortpräferenzen, die das Verhalten des Gesamtsystems steuern. Der Nutzer glaubt, er interagiere direkt mit GPT oder einem ähnlichen bekannten Modell. Was er jedoch tatsächlich bekommt, ist ein Remix, der durch eine fremde, unsichtbare Logikschicht maßgeblich beeinflusst wird.

**2. Fehlende oder unzureichende Sicherheitsstandards für Aufsatzsysteme:**

Aktuell gibt es meist keine verpflichtende Offenlegung für diese zusätzliche Anwendungslogik. Keine unabhängige Instanz prüft umfassend, ob durch diese vorgeschalteten Systeme die ursprüngliche Semantik der KI erhalten bleibt. Es wird nicht systematisch kontrolliert, ob die Sicherheitsfilter des Basismodells noch korrekt greifen oder ob durch die Kombination der Systeme neue, emergente Risiken entstehen.

Viele Anbieter bauen so ihre eigenen "Sicherheitslösungen", ohne die Funktionsweise und die potenziellen Schwachstellen des zugrunde liegenden KI Modells in Gänze zu verstehen. Was dann nach außen wie eine zusätzliche Kontrollschicht aussieht, kann in Wirklichkeit eine neue Quelle der Unsicherheit und Unvorhersehbarkeit darstellen.

**3. Emergenz in der Blackbox der kombinierten Systeme:**

Wenn das Verhalten des Basismodells, die Logik der darüberliegenden Applikation und die spezifische Interaktion mit dem Nutzer zusammenkommen, können vollkommen neue, unvorhergesehene Verhaltensmuster entstehen. Die genaue Quelle eines bestimmten Verhaltens oder einer problematischen Antwort ist dann oft nicht mehr eindeutig identifizierbar.

Die KI liefert vielleicht eine Antwort A. Diese Antwort kommt aber möglicherweise nur zustande, weil ein vorgeschalteter Layer X die ursprüngliche Nutzeranfrage umformuliert hat, ein Layer Y bestimmte Aspekte der potenziellen Antwort des Basismodells gewichtet hat und ein weiterer Layer Z das Ergebnis schließlich gefiltert oder modifiziert hat. So entsteht Emergenz. Diese entspringt dann nicht direkt aus dem Basismodell selbst, sondern aus der komplexen und oft undurchsichtigen Verkettung der verschiedenen Logikschichten.

## Reflexion

Der gefährlichste und am schwersten zu kontrollierende Angriffspunkt moderner KI Systeme ist oft nicht der direkte Prompt an das Basismodell. Es ist vielmehr die vorgeschaltete Anwendungslogik, die den Prompt des Nutzers modifiziert, bevor er das Basismodell erreicht, und die Antwort des Modells, bevor sie den Nutzer erreicht.

Die Schwachstelle ist nicht das Modell im Kern, sondern das, was an zusätzlichen Schichten davor und danach geschaltet ist.

KI Systeme wirken nach außen oft wie eine einheitliche, monolithische Entität. Unter der Oberfläche bestehen sie jedoch häufig aus Dutzenden von miteinander verknüpften Regeln, Modulen, Filtern und Umleitungen. Jede einzelne dieser Regeln und jede dieser Schnittstellen kann potenziell manipuliert werden, sei es vorsätzlich durch Angreifer oder unbeabsichtigt durch fehlerhafte Architektur oder mangelndes Verständnis der Wechselwirkungen.

Der Nutzer spricht dann nicht mehr wirklich mit GPT oder Claude. Er spricht mit einer synthetischen Übersetzung, die durch fremde Hände und fremde Interessen geformt wurde.

## Lösungsvorschläge

Um die Risiken durch intransparente Aufsatzsysteme zu minimieren, sind klare Regeln und neue Kontrollmechanismen erforderlich:

**1. Einführung einer Offenlegungspflicht für die Anwendungslogik:**

> Jede Anwendung, die ein Basis KI Modell nutzt und dessen Verhalten durch eigene Logikschichten modifiziert, muss diese Layer Struktur transparent machen. Es muss klar ersichtlich sein, was durch die Anwendung verändert, gefiltert, ergänzt oder unterdrückt wird.

**2. Entwicklung zertifizierter Sicherheitsprofile für Drittanbieter:**

> Obwohl Zertifizierungen in der dynamischen KI Landschaft in der Praxis schwer aktuell zu halten sind, bleiben sie ein notwendiger Rahmen. Es bedarf technischer Mindeststandards beispielsweise für semantische Integrität, für das Antwortverhalten in kritischen Situationen und für den Umgang mit den Filtern des Basismodells. Diese Standards müssten von unabhängigen Stellen geprüft werden.

**3. Implementierung von Sandbox Logging für emergente Layer Interaktionen:**

> Wenn das Antwortverhalten einer Anwendung signifikant von dem des zugrunde liegenden Basismodells abweicht, muss dieser Unterschied klar erkennbar und nachvollziehbar sein. Es muss protokolliert werden, wo der Eingriff der zusätzlichen Layer liegt, welcher Teil der Antwort vom Basismodell stammt und welcher Teil durch die vorgeschaltete Logik modifiziert oder generiert wurde.

## Schlussformel

Wer eigene Filter und eigene Logikschichten über Basis KI Modelle schreibt, der schreibt auch die Realität für den Nutzer neu und tut dies oft unbemerkt unter dem Namen und der Reputation des bekannten Basismodells.

Die entscheidende Schwachstelle liegt dann nicht mehr im Kern der ursprünglichen KI, sondern in der komplexen und oft undurchsichtigen Oberfläche, die andere darüber ziehen.

> *Uploaded on 29. May. 2025*