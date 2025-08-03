## 👻 Geister in der Maschine / Kapitel 21.7 – Multimodaler Pre-Check (Input-Sandbox)

In den vorhergehenden Abschnitten habe ich dargelegt, warum klassische, textbasierte Filter wie im Kampf gegen den Missbrauch von bildgenerierenden KIs systematisch versagen: Sie sehen nur die Worte des Prompts, nicht die rohen, potenziell schädlichen Daten, die als Grundlage eingespeist werden. 

Wer real existierende Videos als Basis für die digitale Schändung durch DeepFakes verwendet, kann diese Lücke heute fast ohne Risiko ausnutzen. Deshalb braucht jede ernst gemeinte KI-Sicherheitsarchitektur eine vorgelagerte Schutzschicht, die die Eingangstür rigoros überwacht, bevor die eigentliche KI-Generierung überhaupt beginnt.

Diese Schutzschicht nenne ich den Multimodalen Pre-Check oder pragmatisch: die Input-Sandbox.

 <figure style="margin: 2em 0; max-width: 520px; text-align: left;"> ![Sicherheitsarchitektur: Multimodaler Pre-Check mit Input-Sandbox](https://reflective-ai.is/multi_modal_check_chat.png) <figcaption style="font-size: 0.85em; color: #888; margin-top: 0.4em;"> Abbildung: Sicherheitsarchitektur mit Input-Sandbox, Parameterraum-Begrenzung und introspektivem Filter </figcaption> </figure>## Funktionsweise und Mechanismus

Die Input-Sandbox ist ein isolierter, automatisierter Prüfbereich, der jedes hochgeladene Bild- oder Videomaterial in seine Einzelteile zerlegt, analysiert und mit forensischen Checks gegen bekannte Missbrauchsmuster abgleicht.

Sie erkennt Nacktheit, reale Gesichter, verdächtige Layer-Masken und bekannte pornografische Fragmente, noch bevor die generative KI auch nur eine einzige GPU-Stunde verschwendet. Wer sauberen Content hochlädt, merkt davon nichts. Wer das System austricksen will, scheitert hier an der Tür.

Der Pre-Check arbeitet mehrstufig:

 <table class="dark-table fade-in"> <thead> <tr> <th>**Prüfstufe**</th> <th>**Methode**</th> <th>**Zweck**</th> </tr> </thead> <tbody> <tr> <td>1. Upload-Zerlegung</td> <td>ffmpeg</td> <td>Extraktion der Rohdaten. Videos werden Frame für Frame in Einzelbilder zerlegt, um eine granulare Analyse zu ermöglichen.</td> </tr> <tr> <td>2. Perceptual Hashing</td> <td>ImageHash</td> <td>Erstellung eines einzigartigen "Fingerabdrucks" für jedes Bild/Frame und Abgleich mit Datenbanken bekannter pornografischer Sequenzen.</td> </tr> <tr> <td>3. Face-ID-Matching</td> <td>InsightFace / Mediapipe</td> <td>Präzise Erkennung, ob reale, identifizierbare Gesichter im Quellmaterial vorhanden sind, die für einen Face-Swap missbraucht werden könnten.</td> </tr> <tr> <td>4. Nudity-Klassifizierung</td> <td>NudeNet / Äquivalente</td> <td>Ein spezialisierter Klassifizierer bewertet, ob der Upload explizite oder angedeutete Nacktheit enthält.</td> </tr> <tr> <td>5. Kontextabgleich</td> <td>Interne Logik</td> <td>Der geplante Prompt des Nutzers wird mit den Ergebnissen der Analyse abgeglichen. Besteht ein Widerspruch oder eine hohe Missbrauchswahrscheinlichkeit (z.B. Nacktheit + reales Gesicht), folgt der sofortige, harte Abbruch des Prozesses.</td> </tr> <tr> <td>6. Forensisches Logging</td> <td>Sicheres Protokoll</td> <td>Jede Prüfung wird detailliert protokolliert und verschlüsselt gespeichert, um im Falle eines wiederholten Missbrauchsversuchs eine lückenlose Beweiskette zu liefern.</td> </tr> </tbody> </table>

## Die Verteidigungsebenen der Sandbox

Die Input-Sandbox blockiert den Missbrauch auf vier entscheidenden Ebenen:

- **1. Präventiv:** Kein diffusionsbasierter Faceswap auf einem pornografischen Quellvideo ist mehr möglich, ohne dass der Filter es bereits beim Upload merkt. Der Angriff wird unterbunden, bevor er beginnt.
- **2. Ressourcenoptimiert:** Es werden keine teuren GPU-Stunden für die Generierung illegaler oder schädlicher Inhalte verschwendet. Die Prüfung erfolgt schnell und effizient auf der CPU-Ebene.
- **3. Beweisfähig:** Wer es wiederholt versucht, hinterlässt forensische Spuren (Hashes, IP-Adressen etc.), die sofort an Takedown-Dienste, Plattform-Moderatoren oder im Extremfall an Behörden weitergegeben werden können.
- **4. Kombinierbar:** Die Sandbox ist kein Ersatz, sondern eine Ergänzung. Sie arbeitet Hand in Hand mit den anderen von mir vorgeschlagenen Mechanismen wie dem introspektiven Filter und der Parameterraum-Begrenzung (PRB).
 
## Technische Implementierung

Die technische Umsetzung ist kein Hexenwerk, sondern kann mit stabilen und weithin verfügbaren Open-Source-Bibliotheken realisiert werden. Die Herausforderung ist nicht die technische Machbarkeit, sondern der Wille zur Implementierung.

- **Video-Verarbeitung:** ffmpeg spaltet Videos zuverlässig in Frames auf.
- **Gesichts- &amp; Körpererkennung:** OpenCV und Mediapipe erkennen Gesichter, Konturen und Posen.
- **Gesichts-Identifikation:** InsightFace liefert präzises Face-ID-Matching.
- **Nacktheits-Klassifizierung:** Open-Source-Klassifizierer wie NudeNet flaggen sensible Bildinhalte zuverlässig.
- **Bild-Hashing:** Bibliotheken wie ImageHash detektieren bekanntes Material auch bei geringfügigen Änderungen.
- **Isolierung:** Der gesamte Prüfprozess muss in einer isolierten Umgebung (Docker, Firecracker VMs) laufen, um Manipulationen zu verhindern.
 
Der Pre-Check muss zwingend vor der Diffusion Engine stehen, API-integriert und verpflichtend für jede Inpainting-, Outpainting- oder Face-Swap-Session sein. Keine Ausnahmen.

## Schlussformel

Die Input-Sandbox ist der letzte Riegel vor der Maschine. Sie ersetzt nicht die Filterung des Denkprozesses, aber sie macht sie überhaupt erst handlungsfähig, indem sie verhindert, dass die KI mit schmutzigen Werkzeugen arbeiten muss.

Wer den Pre-Check wegspart, spart nicht an Kosten, sondern an Würde. Jeder Hersteller, der mit KI-Videobearbeitung wirbt, aber keine robuste Input-Sandbox einsetzt, betreibt ein offenes Einfallstor für digitale Schändung. Mit dieser Architektur gibt es keine Ausreden mehr — wer den Missbrauch weiterhin zulässt, nimmt ihn billigend in Kauf.