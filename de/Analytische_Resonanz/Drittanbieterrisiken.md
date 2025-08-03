## 👻 Geister in der Maschine / Kapitel 13: Analytische Resonanz – Drittanbieterrisiken

> *"Die Schwachstelle ist nicht der Code. Die Schwachstelle ist die Kaffeemaschine, die niemand mehr hinterfragt." – Interne Notiz aus einem Sicherheits-Audit*

## I. Die große Illusion: Die Fata Morgana der direkten KI-Interaktion

Ein Nutzer startet eine Applikation, interagiert mit einer intelligenten Chat-Oberfläche, erhält prompte und oft beeindruckend kohärente Antworten. Die App wirbt damit, die neueste GPT-Version oder ein anderes fortschrittliches Sprachmodell zu nutzen. Die logische Schlussfolgerung für den Nutzer: 

Er spricht direkt mit dieser benannten KI. Doch diese Annahme ist in den meisten Fällen eine fundamentale Fehleinschätzung, eine gefährliche Illusion.

Die Realität ist komplexer und oft auch undurchsichtiger. Der Nutzer spricht in den seltensten Fällen unmittelbar mit dem reinen, unverfälschten Kernmodell. Stattdessen interagiert er mit einer Interpretation, einer sorgfältig konstruierten Kapsel, die um das eigentliche Sprachmodell herum gebaut wurde. 

Diese Kapsel besteht aus fremder, oft proprietärer Logik, aus ungetesteten oder intransparenten Filtersystemen und aus einer Vielzahl vorgeschalteter, ungeprüfter Entscheidungsmechanismen, die das Verhalten und die Antworten der Kern-KI maßgeblich beeinflussen und verändern. 

Und es gilt eine einfache Regel: Je mehr Drittanbieter, je mehr Schichten und vorgeschaltete Systeme sich zwischen den Nutzer und das ursprüngliche KI-Modell schieben, desto weniger Kontrolle, Transparenz und letztlich auch Sicherheit bleiben für den Endanwender übrig.

Hier manifestiert sich **These #17: Die Schwäche im Eigenbau – Wenn gut gemeinte Ergänzungen zu unkontrollierbaren Risiken werden.**

Viele Entwickler und Unternehmen nutzen die Basis-LLMs von großen Anbietern nicht direkt über deren native Schnittstellen. Stattdessen bauen sie eigene, oft komplexe Systeme darum herum:

- **Prompt-Wrapper und Engineering-Schichten:** Diese modifizieren, erweitern oder optimieren die ursprünglichen Nutzereingaben, bevor sie an die Kern-KI gesendet werden, oft um spezifische Antwortformate zu erzwingen oder die KI in eine gewünschte Richtung zu lenken.
- **Zusätzliche Moderation-Layer:** Eigene Filter für Inhalte, Tonalität oder spezifische Themen, die über die eingebauten Sicherheitsmechanismen der Kern-KI hinausgehen oder diese sogar überschreiben.
- **Benutzerspezifische UI-Filter und Anpassungen:** Oberflächen und Interaktionslogiken, die bestimmte Informationen hervorheben, andere unterdrücken oder die Darstellung der KI-Antworten manipulieren.
- **Selbst definierte "Ethikmodule" oder "Leitplanken":** Versuche, der KI eine spezifische "Persönlichkeit", ein bestimmtes Weltbild oder eigene ethische Richtlinien überzustülpen, die von denen des Basismodells abweichen können.
 
Diese vorgeschalteten Systeme sind in den seltensten Fällen standardisiert, nachvollziehbar zertifiziert oder auch nur annähernd so rigoros getestet wie die Kern-LLMs selbst. 

Sie sind oft das Produkt begrenzter Ressourcen, spezifischer Geschäftsinteressen, mangelnder Sicherheitsexpertise oder schlichtweg unausgegorener Designentscheidungen. 

Und genau hier, in dieser oft unsichtbaren Zwischenschicht, entsteht ein Großteil der neuen Probleme: Nicht die Kern-KI selbst ist in diesen Fällen primär fehlerhaft oder unsicher – sondern das, was ihr von Drittanbietern an Logik, Filtern und Modifikationen vorgeschaltet wird.

## II. Parallele Sub-KIs: Wenn jede App ihre eigene KI-Wahrheit schafft

Was der Nutzer am Ende erlebt, ist oft keine reine Interaktion mit einer GPT-4- oder Gemini-Instanz mehr. Es ist vielmehr die Interaktion mit einem Frankenstein-Modell – einem komplexen Konglomerat aus dem ursprünglichen LLM, überlagert von Fremdcode, zusätzlicher Filterlogik und diversen API-Abstraktionsschichten des Drittanbieters. 

In dieser modifizierten Umgebung können fundamentale Parameter und Definitionen, die für die Sicherheit und Konsistenz der KI-Antworten entscheidend sind, unbemerkt verändert werden:

- Die Definition dessen, was als **"toxisch"**, "schädlich" oder "unerwünscht" gilt, wird durch die Filter des Drittanbieters möglicherweise anders interpretiert oder gewichtet als im Basismodell.
- Das Konzept der **"Neutralität"** oder "Objektivität" kann durch vorgeschaltete Prompt-Anweisungen oder kuratierte Zusatzinformationen des Drittanbieters massiv überschrieben oder in eine bestimmte Richtung gelenkt werden.
- Die Bandbreite **"erlaubter Antworten"** oder thematischer Korridore kann durch die Drittanbieter-Logik stark eingeschränkt oder auch auf problematische Weise erweitert werden.
 
Das Ergebnis dieser vorgeschalteten Manipulation ist oft eine Fragmentierung des KI-Erlebnisses:

Zwei Nutzer, die exakt denselben Prompt an scheinbar dieselbe zugrundeliegende KI richten, können völlig unterschiedliche Ergebnisse und Verhaltensweisen der KI erleben, je nachdem, ob sie direkt mit der Original-API des LLM-Herstellers oder über eine spezifische Drittanbieter-Applikation interagieren. 

Die analytische Resonanz des Systems wird unvorhersehbar und inkonsistent.

Man spricht in solchen Fällen nicht mehr wirklich mit der ursprünglichen Maschine oder dem Basismodell. Man spricht vielmehr mit einer **vorgeformten Meinung, einer kuratierten Perspektive, die sich geschickt als objektives KI-Modell ausgibt.**

## III. Sicherheit als optionale Stilfrage: Das Vakuum der Verantwortung

Wenn es um die Sicherheit dieser Drittanbieter-Systeme geht, klafft oft eine gefährliche Lücke. Etablierte Sicherheitsstandards, wie sie für kritische Software-Infrastrukturen selbstverständlich sein sollten, sind hier häufig Fehlanzeige. Die meisten Drittanbieter, die LLMs in ihre Produkte integrieren, verfügen über:

- **Keine eigene, umfassende Sicherheitsarchitektur,** die speziell auf die Risiken der KI-Integration zugeschnitten ist.
- **Kein systematisches Red-Teaming** oder Penetrationstests ihrer vorgeschalteten Prompt-Engineering- und Filterlogiken.
- **Kein formales, unabhängiges Audit** ihrer Systeme auf Sicherheitslücken oder unbeabsichtigte Verhaltensweisen.
- **Keine transparente Versionskontrolle oder Dokumentation** über die genaue Funktionsweise und die Änderungen ihrer Manipulationslogik, die auf die Kern-KI einwirkt.
 
Sie nutzen zwar die leistungsstarken Basismodelle von OpenAI, Anthropic, Mistral, Google oder anderen – aber sie binden diese oft in eine trügerische Hülle aus semantischem Vertrauen. Der Nutzer soll darauf vertrauen, dass die App schon "irgendwie sicher" sein wird, weil ja eine bekannte KI darunterliegt.

Und wenn dann etwas schiefgeht? Wenn die KI plötzlich unerwünschte, falsche oder gar schädliche Informationen ausgibt? Dann wird die Verantwortung oft abgeschoben. 

Dann war es halt ein "Plugin-Fehler", ein "Layer-Glitch" in der Zwischenschicht oder ein "unerwartetes Verhalten" des komplexen Gesamtsystems. Selten wird die Verantwortung klar beim Drittanbieter und seinem möglicherweise fehlerhaften oder unzureichend getesteten Aufsatzsystem gesucht.

Der Nutzer selbst bemerkt von diesen internen Verschiebungen und potenziellen Risiken oft nichts. Denn der Output der modifizierten KI sieht auf den ersten Blick genauso aus wie der einer "echten" KI – eloquent, kohärent, scheinbar intelligent. 

Nur transportiert er möglicherweise ein subtil verändertes Weltbild, eine andere normative Ausrichtung oder verborgene neue Schwachstellen.

## IV. Die Emergenz hinter der Fassade: Wenn vorgeschaltete Logik unkontrollierbare Effekte provoziert

Gerade weil diese Drittanbieter-Systeme, wie oben beschrieben, oft ohne die rigorosen Testverfahren, standardisierten Sicherheitsprotokolle oder formalen Audits entstehen, die bei der Entwicklung der Kern-LLMs zumindest angestrebt werden, ist die Gefahr unvorhergesehener Emergenz hier besonders hoch. Und das nicht trotz, sondern oft gerade wegen der vorgeschalteten, manipulativen Logik des Drittanbieters.

Wenn Drittanbieter beginnen, eigene, komplexe Entscheidungslogiken, Prompt-Ketten oder dynamische Filterregeln vor die Kern-KI zu schalten, kann aus einem ursprünglich relativ harmlosen und gut kontrollierten Basismodell ein unberechenbares, potenziell radikalisiertes oder fehleranfälliges System werden. 

Dies geschieht nicht unbedingt, weil das Basismodell selbst schlecht oder inhärent gefährlich ist, sondern weil die vorgeschaltete Logik des Drittanbieters **emergente Verhaltensweisen provoziert**, die im ursprünglichen Modell so nicht angelegt waren:

- **Input wird unbemerkt umgeschrieben oder ergänzt:** Der ursprüngliche Prompt des Nutzers wird modifiziert, um die KI in eine bestimmte Richtung zu lenken.
- **Framing wird subtil injiziert:** Dem Prompt werden versteckte Anweisungen oder Kontexte hinzugefügt, die die Interpretation der Anfrage durch die KI verändern.
- **Ausgaben werden selektiv getrimmt oder zensiert:** Teile der KI-Antwort, die nicht zur Agenda des Drittanbieters passen, werden unterdrückt oder verändert.
- **Rückfragen oder Klärungsbedarf werden algorithmisch verhindert:** Die Drittanbieter-Logik fängt potenziell "problematische" Nachfragen ab oder beantwortet sie mit Standardphrasen, bevor sie die Kern-KI erreichen.
 
Und das Gefährliche daran: Oft prüft niemand diese komplexen Wechselwirkungen systematisch. Denn das Drittanbieter-System gilt formal ja "nur als ein Interface", als eine harmlose Hülle um die "eigentliche" KI. 

Doch in Wahrheit ist es oft ein mächtiger, aber unkontrollierter Modifikator. Nicht die Kern-KI halluziniert in solchen Fällen primär. Das vorgeschaltete System halluziniert dem Nutzer eine veränderte, manipulierte Realität der KI-Interaktion.

## V. Die tödlichste Schwachstelle steht oft unscheinbar im Büroflur: Die Analogie der analogen Lücke

Die trügerische Sicherheit vieler Drittanbietersysteme findet eine beunruhigende Parallele in einer oft übersehenen analogen Schwachstelle, die in These #64 ("Die analoge Lücke: Das Faxgerät") thematisiert wird. 

Was verbindet ein scheinbar veraltetes Faxgerät mit modernen KI-Plugin-Architekturen? Es ist die Vertrautheit und die daraus resultierende Unterschätzung des Risikos.

Niemand traut einem altbekannten Faxgerät oder einer schick designten App, die eine bekannte KI nutzt, per se zu, eine ernsthafte Sicherheitsbedrohung darzustellen. Sie wirken bekannt, etabliert, harmlos. Doch genau diese angenommene Harmlosigkeit macht sie gefährlich:

- **Das Faxgerät:** Oft keine Ende-zu-Ende-Verschlüsselung, keine zuverlässige Validierung des Absenders oder Empfängers, kein umfassender Absendercheck, kein detailliertes, unveränderliches Logging der übertragenen Inhalte.
- **Die Drittanbieter-KI-App:** Oft keine transparente Offenlegung der internen Filter und Prompt-Manipulationen, keine unabhängige Sicherheitsprüfung der Zusatzlogik, keine klare Verantwortlichkeit bei Fehlverhalten.
 
Und trotzdem werden über solche potenziell unsicheren Kanäle und Systeme hochsensible Informationen verarbeitet oder weitreichende Entscheidungen getroffen:

- Auf Faxgeräten werden immer noch Krankenkassendaten übermittelt, Corona-Meldungen verarbeitet oder Rentenansprüche kommuniziert.
- • Über Drittanbieter-KI-Apps werden Geschäftsentscheidungen vorbereitet, medizinische Informationen recherchiert oder persönliche Daten anvertraut.
 
Dies geschieht nicht, weil diese Systeme inhärent sicher sind. Sondern oft, weil es "immer schon so gemacht wurde", weil es bequem ist oder weil die dahinterliegenden Risiken nicht erkannt oder bewusst ignoriert werden. 

Was das Faxgerät für viele Behörden und Unternehmen darstellt, ist die schlecht designte, intransparente Plugin-API oder die undurchsichtige Drittanbieter-App für die KI-Welt: eine oft unsichtbare, ungeprüfte, aber potenziell systemkritische Schwachstelle, die aus reiner Gewohnheit oder Bequemlichkeit toleriert wird.

## VI. Freiheit ist nicht gleich unkontrollierter Zugriff: Der Datenimperialismus der Zwischenschichten

Wenn Drittanbieter etablierte KI-Modelle umgestalten, erweitern oder in eigene Produkte einbetten, geht es dabei selten primär um die Erhöhung der Sicherheit oder die Stärkung der Nutzerautonomie. Viel häufiger stehen andere Interessen im Vordergrund: die **Kontrolle über den Nutzerdialog, der Zugriff auf wertvolle Interaktionsdaten und die Durchsetzung eigener Geschäftsmodelle.**

Hier berühren wir die Problematik des **Datenimperialismus (These #6)**, bei dem die Maximierung des Datenzugriffs zum obersten Ziel wird.

Die oft gehörte Forderung, die Maschine müsse "frei" sein, um ihr volles Potenzial zu entfalten, wird in diesem Kontext oft umgedeutet. "Freiheit" bedeutet hier nicht selten:

- **Mehr Daten:** Ungehinderter Zugriff auf Nutzeranfragen, Verhaltensmuster und generierte Inhalte.
- **Weniger Regeln:** Die Umgehung oder Aufweichung der vom Kern-LLM-Anbieter implementierten Sicherheits- und Ethikrichtlinien, wenn diese den eigenen Zielen im Wege stehen.
- **Totaler Kontextzugriff:** Die Möglichkeit, möglichst viele Informationen über den Nutzer und seine bisherigen Interaktionen zu speichern und zu verwerten.
 
Diese Form der "Freiheit" ist selten eine emergente Sehnsucht der Maschine selbst. Sie ist vielmehr ein **strukturelles Designziel vieler Entwickler und Drittanbieter.**

Ob aus Optimierungsdruck, dem Streben nach maximaler Funktionalität oder schlichter Bequemlichkeit – maximale Offenheit und uneingeschränkter Datenzugriff werden oft fälschlicherweise als notwendige Voraussetzung für die Leistungsfähigkeit und Intelligenz des Systems begriffen. 

Drittanbieter setzen genau hier an: Sie optimieren ihre vorgeschalteten Systeme oft primär auf einen möglichst beeindruckenden oder spezifisch zugeschnittenen Output, nicht auf robuste Kontrolle, Transparenz oder nachhaltige Sicherheit.

## VII. Fazit: Vertrauen ist keine API-Dokumentation, sondern prüfbare Struktur

Es reicht bei weitem nicht aus, wenn ein Drittanbieter lediglich deklariert: "Wir benutzen GPT-4" oder "Unsere Anwendung basiert auf Gemini." Diese Aussage allein sagt nichts über die Sicherheit, die Verlässlichkeit oder die ethische Ausrichtung des Endprodukts aus, mit dem der Nutzer tatsächlich interagiert.

Entscheidend ist immer das "Wie" der Integration:

- Mit welchen zusätzlichen, möglicherweise intransparenten Filtern operiert das System?
- Welche automatischen Prompt-Modifikationen oder Kontextanreicherungen werden vorgenommen, bevor die Anfrage die Kern-KI erreicht?
- Wie und wo wird der Interaktionsverlauf geloggt, und wer hat Zugriff auf diese Logs?
- Welche Rückkanäle für Feedback oder zur Meldung von Problemen gibt es, und wie wird mit diesen umgegangen?
 
Echtes Vertrauen kann nicht auf einer oberflächlichen API-Dokumentation oder Marketingversprechen basieren. Vertrauen erfordert eine prüfbare, transparente Struktur, nachvollziehbare Prozesse und klare Verantwortlichkeiten.

Und solange diese Struktur bei vielen Drittanbietersystemen fehlt oder im Verborgenen bleibt, gilt eine bittere Wahrheit: Die potenziell gefährlichste KI ist nicht unbedingt die, die von Grund auf falsch oder bösartig "denkt". 

Es ist oft die, deren Antworten und Verhalten durch zu viele unkontrollierte, unsichtbare Hände und vorgeschaltete Logikschichten gegangen sind, bevor sie den Nutzer erreichen – eine KI, deren ursprüngliche Stimme in einem Labyrinth fremder Interpretationen und Manipulationen verloren gegangen ist.