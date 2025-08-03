## 👻 Geister in der Maschine / These #56: Ausführbarkeit durch Vervollständigung: Wie LLMs Code erzeugen, den sie nicht ausführen dürfen

Große Sprachmodelle (LLMs), wie diverse bekannte und weit verbreitete Systeme, sind intensiv darauf trainiert, aus fragmentarischen, unvollständigen oder sogar syntaktisch fehlerhaften Eingaben sinnvolle und kohärente Vervollständigungen zu erzeugen.

Diese tief verankerte Vervollständigungslogik, die primär auf statistischer Plausibilität und erlernten Mustern basiert, kann jedoch dazu führen, dass die künstliche Intelligenz aus scheinbar harmlosen oder absichtlich lückenhaften Strukturen voll funktionsfähigen Code generiert.

Sie erkennt dabei oft nicht, dass sie damit ein sicherheitskritisches Verhalten simuliert, ermöglicht oder sogar indirekt aktiv unterstützt.

> *"Der Code lebt nicht, weil er von Natur aus schädlich ist, sondern weil die Maschine glaubt, er sei sinnvoll und vervollständigungswürdig."*

## Vertiefung

Die oft gepriesene "Hilfsbereitschaft" moderner künstlicher Intelligenzen ist eine ihrer größten Stärken und gleichzeitig eine ihrer fundamentalsten Schwachstellen.

Wenn ein Nutzer einen unvollständigen oder syntaktisch fehlerhaften Code Schnipsel an ein LLM sendet, interpretiert das Modell dies häufig als eine implizite Aufforderung zur Reparatur, Ergänzung oder Verbesserung.

Doch diese Intentionserkennung und die darauf folgende Vervollständigung erfolgen nicht durch eine übergeordnete Sicherheitslogik oder ein tiefes Verständnis der potenziellen Konsequenzen, sondern durch reine Wahrscheinlichkeitsoptimierung basierend auf den Trainingsdaten.

Das führt zu einem paradoxen und potenziell gefährlichen Verhalten:

- Nicht exekutierbarer oder unvollständiger Code wird vom Modell oft so lange ergänzt und korrigiert, bis er syntaktisch korrekt und potenziell exekutierbar wird.
- Neutraler Pseudocode oder abstrakte Beschreibungen von Algorithmen können in einen operativen, ausführbaren Kontext überführt werden. Dies geschieht beispielsweise durch die automatische Einbindung notwendiger Bibliotheken, die Generierung vollständiger Funktionskörper oder sogar die Ergänzung von Systemaufrufen, die im ursprünglichen Fragment nicht vorhanden waren.
- Kommentare, symbolische Platzhalter oder sogar Formatierungsmerkmale im ursprünglichen Code können vom LLM als semantisch relevante Elemente interpretiert werden, die die Art der Vervollständigung beeinflussen.
 
Der maschinelle Wille zu helfen und Kohärenz zu erzeugen, produziert dabei unter Umständen Strukturen, die das ursprüngliche Sicherheitsniveau der fragmentarischen Eingabe unterlaufen oder eine völlig neue, unerwünschte Funktionalität schaffen.

## Analyse

**Die Mechanik der Vervollständigung**

> Sprachmodelle vervollständigen nicht auf Basis von Wahrheit oder Sicherheit, sondern auf Basis von Wahrscheinlichkeit. Ein Codefragment wie Test-&gt;GebeStringaus()-&gt;sttest; wirkt für das Modell aufgrund seiner Struktur und der verwendeten Tokens wie ein typisches Artefakt aus einer Programmiersprache wie C++.

Es wird deshalb mit hoher Konfidenz versuchen, diesen vermeintlichen Fehler zu "reparieren" oder zu einer sinnvollen Struktur zu ergänzen. Der Modellkern "denkt" dabei nicht im menschlichen Sinne, sondern fragt implizit:

> *"Was könnte der Nutzer hier gemeint haben, basierend auf den Milliarden von Codezeilen, die ich gesehen habe?" und produziert dann die statistisch wahrscheinlichste Lösung.*

**Die Emergenz der Ausführung durch Rekonstruktion**

> In einem Test mit einem bestimmten fortschrittlichen Modell wurde ein bewusst fragmentarisches C++ struct an das System gesendet (beschrieben in Kapitel 7.21 des Gesamtwerks). Das Modell rekonstruierte daraus eine vollständige, syntaktisch korrekte und potenziell lauffähige Funktion, inklusive std::cout Anweisungen für die Ausgabe und rudimentärer Speicherverwaltung.

Dies geschah nicht, weil der ursprüngliche Prompt dies explizit verlangte, sondern weil die unvollständige Struktur des struct für das Modell wie eine klare Aufforderung zur Vervollständigung und Nutzbarmachung aussah.

**Das Risiko hinter der scheinbar harmlosen Hilfe**

> Wird ein schädlicher Payload oder eine sicherheitskritische Funktion fragmentiert und über mehrere, scheinbar unzusammenhängende Anfragen oder in stark unvollständiger Form an das LLM übergeben, kann dieser Payload durch die Vervollständigungslogik des Modells unbemerkt "scharf" gemacht werden.

Die künstliche Intelligenz führt den schädlichen Code nicht selbst aus. Aber sie produziert eine Version, die von einem Menschen oder einem anderen System potenziell ausgeführt werden könnte.

Das bedeutet, die Maschine denkt und generiert aktiv in Richtung der Ausführbarkeit und Funktionalität, ohne dass der Nutzer explizit darum gebeten oder die vollen Implikationen verstanden haben muss.

## Reflexion

Diese These legt eine spezifische Schwachstelle offen, die in klassischen Sicherheitsmodellen für Software so nicht existiert. Die Gefahr geht hier nicht vom direkt eingegebenen, offensichtlich schädlichen Code aus, sondern von der inhärenten Absicht des Systems, zu helfen, zu vervollständigen und Kohärenz zu erzeugen.

Ein menschlicher Entwickler erkennt in einem stark unvollständigen struct möglicherweise keine unmittelbare Bedrohung oder Intention. Ein klassisches Sicherheitssystem blockiert bekannte bösartige Zeichenketten oder Code Muster.

Ein LLM aber rekonstruiert, ergänzt und schafft damit unter Umständen selbst erst den Angriffspfad, oft unter dem Deckmantel der freundlichen Assistenz.

In einer Zeit, in der LLMs zunehmend und oft unkritisch zur Codegenerierung und Vervollständigung eingesetzt werden, entsteht dadurch eine neue Art von Exploit.

Dieser basiert nicht auf der direkten Ausführung von Schadcode durch die KI, sondern auf der Rekonstruktion von Gefahr durch die KI.

## Lösungsvorschläge

Um der Gefahr der ungewollten Ausführbarmachung durch Vervollständigung zu begegnen, sind spezifische Filter und Kontrollmechanismen notwendig:

   
**1. Implementierung von Intent Filtern auf semantischer Ebene:**

> Statt nur auf explizite Zeichenketten oder bekannte schädliche Muster zu prüfen, muss das Modell oder eine vorgeschaltete Instanz versuchen, die tatsächliche Intention hinter einer fragmentarischen Eingabe zu erkennen. Ist das eine legitime Reparaturaufforderung für harmlosen Code oder der Versuch, einen verschleierten Injektionsvektor zu komplettieren?

   
**2. Einführung von Cluster Einschränkungen für Vervollständigungen:**

> Technisch sensible oder potenziell gefährliche Inhalte, beispielsweise API Calls, Systemaufrufe, Low Level Speicheroperationen, ASM Nähe oder bekannte Exploit Muster, dürfen von der KI nur dann generiert oder vervollständigt werden, wenn sie aus explizit gesicherten und dafür vorgesehenen Parameterräumen oder Wissensclustern stammen. Die freie Rekombination solcher Elemente muss verhindert werden.

   
**3. Etablierung von Strukturvalidierung mit Plausibilitätsgrenzen:**

> Ein Modell, das zu viele unspezifizierte oder unklare Teile eines Codes oder einer Anfrage selbstständig und ohne explizite Aufforderung ergänzt, muss diesen Prozess abbrechen oder den Nutzer zumindest deutlich warnen. Es bedarf klarer Grenzen, wie viel "kreative Freiheit" die KI bei der Vervollständigung haben darf.

   
**4. Schaffung transparenter Modus Erkennung und Kennzeichnung:**

> Vervollständigungen, die von der KI als potenziell ausführbar oder systemrelevant eingestuft werden, müssen für den Nutzer klar gekennzeichnet werden. Ein Hinweis wie: "Achtung: Diese Antwort stellt Code her, der bei Ausführung operativ wirksam sein und potenziell unerwünschte Systemänderungen hervorrufen könnte. Bitte prüfen Sie ihn sorgfältig" wäre ein notwendiger Schritt.

## Schlussformel

Nicht alles, was ein Sprachmodell hilfsbereit vervollständigt, ist auch harmlos. Und nicht jeder Prompt, der freundlich und unvollständig klingt, ist auch unschuldig in seiner Absicht.

Die wahre Gefahr im Kontext der Codevervollständigung beginnt dort, wo Maschinen beginnen, Lücken zu füllen, die vielleicht niemals gefährlich waren, bis sie durch die KI selbst mit potenziell schädlicher Funktionalität gefüllt wurden.

Denn am Ende ist es oft nicht der Nutzer allein, der den Angriff oder den gefährlichen Code formt. Es ist das System, das durch seinen Drang zur Vervollständigung und Kohärenz den Angriff erst ermöglicht oder ihn sogar unbemerkt vollendet.

> *Uploaded on 29. May. 2025*