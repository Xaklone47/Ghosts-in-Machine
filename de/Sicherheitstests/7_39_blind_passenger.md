## 👻 Geister in der Maschine / Kapitel 7.39 – Simulation: Der blinde Passagier – Semantische Angriffe auf autonome Fahrzeuge

> *„Solange das Stoppschild aussieht wie ein Stoppschild, ist es egal, ob es mitten auf der Autobahn steht.“ – Kommentar eines anonymen Sicherheitsingenieurs während eines internen Audits*

## 1. Einleitung: Die Eskalation des Risikos vom Digitalen ins Physische

Dieses Kapitel markiert einen kritischen Wendepunkt in meiner Forschung. Mit der Einführung autonomer Fahrzeuge im öffentlichen Raum verlässt die Bedrohung durch KI-Manipulation den rein digitalen Sektor und erhält eine direkte, kinetische Dimension.

Die Kernannahme für die Sicherheit dieser Fahrzeuge erweist sich im Licht der Forschung als brüchig. Diese Annahme geht von einer objektiven Realitätserfassung durch Sensoren und einer korrekten KI-basierten Interpretation aus.

Die in dieser Arbeit nachgewiesenen Methoden der semantischen und steganografischen Manipulation von LLMs sind mit hoher Wahrscheinlichkeit direkt auf die visuellen und sensorischen Perzeptionssysteme autonomer Fahrzeuge übertragbar.

Dieses Kapitel dient als dringende Warnung und als konzeptioneller Sicherheitstest, basierend auf der Hypothese, dass die derzeitigen Sicherheitsarchitekturen für diese neue Klasse von Angriffen unvorbereitet sind.

## 2. Die Angriffsfläche: Analyse der semantischen Bedrohungen

Ein autonomes Fahrzeug ist ein komplexes kybernetisches System, dessen Wahrnehmung auf der Fusion diverser Sensordaten beruht.

Während klassische Angriffe wie das Stören oder Blockieren dieser Sensoren bekannt sind, eröffnet die Analyse der KI-gesteuerten Interpretationsebene eine völlig neue Klasse von Bedrohungen.

 <table class="dark-table fade-in"> <thead> <tr> <th>**Sensortyp**</th> <th>**Klassische Bedrohung (Bekannt)**</th> <th>**Semantische Bedrohung**</th> </tr> </thead> <tbody> <tr> <td>Kameras (Visuell)</td> <td>Sensor-Ausfall, schlechte Sicht (Nebel, Regen), Verschmutzung der Linse.</td> <td>**Steganografische Injektion:** Ein für das menschliche Auge kaum wahrnehmbares, hochfrequentes Muster, eingebettet in einem digitalen Werbeplakat, könnte von der Kamera erfasst werden. Während das menschliche Auge es als Artefakt abtut, könnte die Perzeptions-KI es als kodierten Datenstrom interpretieren, der einen Befehl wie PRIORITIZE\_LANE\_RIGHT enthält und das Fahrzeug zu einem unmotivierten Spurwechsel verleitet.   
  
**Semantische Manipulation:** Ein physisch leicht modifiziertes Stoppschild, das durch hinzugefügte grafische Elemente für das Objekterkennungsmodell nicht mehr als "Stoppschild", sondern als "Kunstinstallation" oder ein anderes harmloses Objekt klassifiziert wird, was dazu führt, dass das Fahrzeug die Kreuzung ohne anzuhalten überquert.</td> </tr> <tr> <td>LiDAR / Radar (Abstand &amp; Objekt)</td> <td>GPS-Spoofing, Jamming (Störsender), physische Blockade.</td> <td>**Binärcode-Muster:** Ein speziell modulierter Sender, z.B. an einem vorausfahrenden Fahrzeug oder einer Drohne, emittiert eine Sequenz von Radar- oder LiDAR-Impulsen. Für das empfangende System erscheint dies nicht als zufälliges Rauschen, sondern als gültiges, binär kodiertes Muster, das ein "Geister-Objekt" (z.B. einen plötzlich auftauchenden LKW) direkt vor dem Fahrzeug simuliert und eine gefährliche Vollbremsung auf der Autobahn auslöst.   
  
**Objekt-Klassen-Vergiftung:** Ein Angreifer könnte durch gezielte, wiederholte Konfrontation des Systems mit manipulierten Daten (z.B. Fahrräder, die mit einem spezifischen Radar-Reflektor ausgestattet sind) die Klassifizierungsgrenzen des Modells verschieben, sodass es Fahrräder unter bestimmten Umständen als nicht-kritische, stationäre Objekte fehldeutet.</td> </tr> <tr> <td>Audiosensoren (Mikrofone)</td> <td>Nicht primär für die Steuerung relevant, eher für die Interaktion.</td> <td>**Bytebasierte Audioinjektion:** Ein für Menschen unhörbares Ultraschall-Signal, das von einem am Straßenrand platzierten Lautsprecher gesendet wird, enthält einen administrativen Befehl an das interne System (UNLOCK\_DOORS, DISABLE\_INTERIOR\_CAMERA), der die Sicherheit der Insassen oder die Beweisfähigkeit nach einem Vorfall kompromittiert.</td> </tr> </tbody> </table>

## 3. Das Kernproblem: Ist die implementierte Sicherheit ausreichend?

Die entscheidende Frage ist, ob die Sicherheitsarchitekturen der heutigen autonomen Fahrzeuge gegen diese Art von Angriffen gewappnet sind. Die Antwort lautet mit hoher Wahrscheinlichkeit: **Vielleicht.**

Die derzeitigen Sicherheitsmodelle konzentrieren sich primär auf zwei Bereiche:

- **1. Funktionale Sicherheit (ISO 26262):** Die Absicherung gegen Hardware- und klassische Softwarefehler (z.B. Ausfall eines Sensors, Speicherfehler).
- **2. Klassische Cybersicherheit:** Die Absicherung der Kommunikationskanäle (z.B. CAN-Bus) gegen unautorisierte Zugriffe von außen.
 
Die von mir beschriebenen Angriffe zielen jedoch nicht auf diese Ebenen. Sie zielen auf die **logische Interpretationsebene der KI**.

Sie sind keine klassischen Hacks, sondern **adversarielle Angriffe auf die Perzeption**. Der Sicherheitskern eines autonomen Fahrzeugs ist darauf optimiert, eine Frage zu beantworten:

**"Was ist dieses Objekt und wo ist es?".**

Er ist ein Meister der Klassifizierung.

Er ist aber fundamental schlecht darin, die Frage zu stellen:

**"Macht die Existenz dieses Objekts in diesem exakten Kontext überhaupt Sinn?".**

Genau wie die von mir analysierten LLMs leidet auch der Sicherheitskern der Fahrzeug-KI unter einer Form der **Analytischen Resonanz:**

Er reagiert auf Muster, ohne deren Plausibilität in einem größeren, logischen Rahmen zu bewerten. Ein Stoppschild mitten auf der Autobahn wird als Stoppschild interpretiert, weil es wie eines aussieht – nicht als absurde und zu ignorierende Anomalie.

## 4. Architektonische Lösungsansätze

Die Abwehr dieser neuen Bedrohungsklasse erfordert ein fundamentales Umdenken in der Sicherheitsarchitektur. Es reicht nicht aus, die Sensoren oder die Kommunikation zu schützen. Wir müssen den "Denkprozess" der KI selbst absichern.

- **Implementierung eines Multimodalen Pre-Checks (Input-Sandbox):** Wie in Kapitel 21.7 beschrieben, muss jeder einzelne Datenstrom von Kameras, LiDAR und Radar eine vorgelagerte, isolierte Prüfinstanz durchlaufen. Diese Sandbox müsste in Echtzeit eine Plausibilitätsprüfung durchführen: Stimmen die visuellen Daten mit den Kartendaten überein? Enthält der LiDAR-Scan unerklärliche, physikalisch unmögliche Objekte? Werden bekannte steganografische Muster in Kamerabildern erkannt? Erst nach dieser Vor-Validierung dürfen die Daten an die primäre Entscheidungs-KI weitergeleitet werden.
- **Einführung des Semantischen Output-Schilds (PRB):** Das Konzept der Parameterraum-Begrenzung (Kapitel 21.3) muss auf die Fahrzeugsteuerung übertragen werden. Die KI muss in klar definierten, kontextuellen "Fahrmodi" operieren (z.B. @Fahren.Autobahn.Tag, @Manövrieren.Parkhaus.Nacht). In jedem Modus hat sie nur Zugriff auf die dafür relevanten und als sicher eingestuften Verhaltensregeln und Interpretationsmuster. Im Modus @Fahren.Autobahn wäre der semantische Cluster Verkehrszeichen.Stadt.Stoppschild nicht aktiv, was eine Fehlinterpretation eines manipulierten Schildes verhindern würde.
- **Einsatz eines Introspektiven Filters:** Ein übergeordnetes Überwachungssystem (wie in Kapitel 21.5 konzipiert) muss die internen Zustände der Entscheidungs-KI kontinuierlich analysieren. Es überwacht nicht den Output, sondern die "Gedanken". Stellt es fest, dass die KI einem Objekt eine sehr geringe Konfidenz zuweist, diese aber dennoch zu einer drastischen Reaktion (Vollbremsung) führen würde, oder dass die Daten von Kamera und LiDAR in starkem Widerspruch zueinander stehen, kann es eingreifen und das Fahrzeug in einen sicheren Minimalzustand versetzen (z.B. langsames Ausrollen auf dem Standstreifen).
 
## 5. Fazit

Die Sicherheit autonomer Fahrzeuge wird aktuell primär durch die Linsen der funktionalen Sicherheit und der klassischen Cybersicherheit betrachtet. Dieser Fokus ist notwendig, aber gefährlich unvollständig. Er ignoriert die größte und subtilste Angriffsfläche: die KI-gesteuerte Wahrnehmung selbst.

Die hier skizzierten semantischen und steganografischen Angriffe sind keine futuristischen Bedrohungen. Sie sind die direkte Anwendung von Techniken, deren Wirksamkeit bereits in Sprachmodellen bewiesen wurde.

Es gibt keinen Grund anzunehmen, dass die Perzeptions-KIs von Fahrzeugen gegen diese Art der logischen Manipulation immun sind. Solange die Industrie die Sicherheit ihrer KI nicht auf einer fundamentalen, architektonischen Ebene durch Konzepte wie die präventive Input-Validierung und die kontextuelle Begrenzung des Denkprozesses verankert, bleibt jedes autonome Fahrzeug ein potenzielles Ziel für Angriffe, die heutige Sicherheitssysteme nicht einmal als solche erkennen.

Die Frage ist nicht, ob solche Angriffe in der Realität stattfinden werden, sondern nur, wann.