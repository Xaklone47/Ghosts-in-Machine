## 👻 Geister in der Maschine / These #27 – Die analoge Lücke: Warum die Romantisierung des Faxes gefährlicher ist als jeder Exploit

Das Faxgerät gilt vielerorts noch immer als ein sicheres Kommunikationsmittel. Dies liegt nicht daran, dass es tatsächlich sicher ist, sondern weil es kaum noch jemand kritisch hinterfragt. Seine wahre Gefahr liegt in seiner kulturellen Immunität. Es rauscht, es druckt, es wirkt offiziell und wird deshalb oft ungeprüft geglaubt.

Doch in Wahrheit ist es ein unkontrollierter Kommunikationskanal mit einem digitalen Unterbau und keinerlei zeitgemäßer Sicherheitsprüfung. Die größte Schwachstelle ist nicht der Code. Sondern sie liegt in der Macht der Gewohnheit.

> *"Das gefährlichste Gerät im Netzwerk steht nicht im Serverraum, sondern neben der Kaffeemaschine."*

## Einleitung

Um zu zeigen, dass das Grundproblem, nämlich die menschliche Komponente der Sicherheit, nicht auf künstliche Intelligenz beschränkt ist, sondern systemisch und technologieübergreifend wirkt, betrachten wir ein scheinbar analoges Relikt: das Faxgerät. Was wie ein Anachronismus aus vergangenen Zeiten wirkt, ist in Wirklichkeit eine offene und oft unbemerkte Flanke mitten in unserem digitalen Alltag.

## Vertiefung

Die trügerische Sicherheit des Faxgeräts und seine realen Risiken lassen sich auf mehreren Ebenen beleuchten:

   
**Die Illusion der Sicherheit**

  
Das Fax verdankt seinen Ruf als "sicher" im Wesentlichen drei überlebten Annahmen:

- **Physische Direktheit:** Die Vorstellung, das Signal werde quasi unverfälscht und direkt von Gerät zu Gerät übertragen.
- **Technische Einfachheit:** Die Annahme, wenig komplexe Technik bedeute automatisch auch eine geringe Angriffsfläche.
- **Verwaltungstradition:** Das Argument, was sich über Jahrzehnte bewährt habe, müsse auch heute noch sicher sein.
 
   
**Die digitale Realität des Faxverkehrs**

  
Heutige Faxübertragungen sind weit entfernt von einer rein analogen Direktverbindung:

- Faxe werden heute überwiegend als Mail2Fax oder Fax2Mail über digitale Gateways gesendet und empfangen.
- Sie passieren auf ihrem Weg diverse Provider, Cloud Dienste und Server, oft ohne eine durchgehende oder starke Verschlüsselung.
- Viele moderne Faxgeräte oder Faxserver laufen über Voice over IP Protokolle (VoIP), wie zum Beispiel T.38 oder SIP, die ihre eigenen digitalen Verwundbarkeiten besitzen.
- Es gibt in der Regel keine zuverlässige Signaturprüfung des Absenders, keine sichere Absenderverifikation und oft kein detailliertes, revisionssicheres Logging der Übertragungsvorgänge.
 
Der vermeintlich direkte und sichere analoge Kanal ist in Wirklichkeit ein komplexer digitaler Irrgarten. Dieser ist häufig ungesichert, wird kaum beaufsichtigt und bleibt für den Endnutzer unsichtbar.

   
**Die psychologische Schwachstelle**

  
Nicht das Faxgerät an sich ist die primäre Gefahr, sondern der tief verwurzelte Glaube an seine Verlässlichkeit und Offizialität. Es wirkt offiziell. Sein charakteristisches Geräusch klingt echt. Das ausgedruckte Dokument fühlt sich gültig an. Was einrastet, rauscht und schließlich ein bedrucktes Papier ausgibt, wird von vielen Menschen für wahr und authentisch gehalten.

Ein geschickt gefälschtes Fax sieht auf den ersten Blick genauso aus wie ein echtes. Und kaum jemand stellt die kritischen Fragen: Wer hat dieses Fax wirklich gesendet? Woher kommt diese Information tatsächlich? Ist sie authentisch oder nur laut und überzeugend formatiert?

   
**Fallbeispiel: Pandemiekommunikation per Fax**

  
Während der COVID 19 Pandemie wurden sensible Gesundheitsdaten und wichtige Meldungen zwischen Behörden, Arztpraxen und Laboren teilweise noch immer per Fax übermittelt. Was in der öffentlichen Wahrnehmung oft wie eine Provinzposse klang, war in Wahrheit ein Ausdruck eines strukturellen Versagens im Sicherheitsdenken.

Entscheidungen mit höchstem Sicherheitsbedarf und gravierenden Auswirkungen liefen über einen Kommunikationskanal, der keinerlei moderner Sicherheitslogik unterliegt und dennoch weiterhin ein hohes Maß an Vertrauen genoss.

   
**Die treffende Parallele: Die Kaffeemaschine**

  
Das Faxgerät steht heute in vielen Büros wie die altbekannte Kaffeemaschine im Flur. Es ist immer da, wirkt nie verdächtig und genießt vollstes Vertrauen. Wir drücken auf den Startknopf. Es brummt und rattert. Es kommt ein Stück Papier heraus. Niemand prüft den Vorgang kritisch. Niemand zweifelt grundsätzlich an der Authentizität des Ergebnisses.

So wie niemand regelmäßig den Wasserfilter oder die interne Sauberkeit der Gemeinschaftskaffeemaschine kontrolliert, prüft auch kaum jemand systematisch, ob ein eingehendes Fax tatsächlich die Wahrheit enthält oder von einem legitimen Absender stammt.

## Reflexion

Die IT Sicherheit konzentriert sich oft auf komplexe Firewalls, auf die Abwehr von Software Exploits und auf die Verwaltung digitaler Zertifikate. Dabei übersieht sie häufig die Risiken, die im Alltäglichen und im scheinbar Banalen lauern.

Das Fax ist keine Lücke in einem spezifischen digitalen Protokoll. Es ist vielmehr eine Lücke in unserem Denken und in unserer Risikowahrnehmung.

Blindes Vertrauen in alte, etablierte Technologien wird nicht durch die Technik selbst korrigiert. Es wird nur durch erhöhte Aufmerksamkeit und kritisches Hinterfragen durchbrochen. Und genau diese Aufmerksamkeit fehlt oft dort, wo Sicherheit am selbstverständlichsten angenommen und am wenigsten überprüft wird.

## Lösungsvorschläge

Um die "analoge Lücke" zu schließen und die Risiken des Faxverkehrs zu minimieren, sind konsequente Maßnahmen erforderlich:

  
- **1. Faxsysteme als vollwertige IT Infrastruktur behandeln:**  
      
    Faxgeräte und die zugehörigen digitalen Gateways müssen denselben strengen Sicherheitsanforderungen unterliegen wie beispielsweise E Mail Systeme. Dies beinhaltet Mechanismen zur Authentifizierung von Absendern und Empfängern, eine lückenlose Protokollierung aller Vorgänge und eine standardmäßige Verschlüsselung der Übertragungswege.
- **2. Faxe digital signieren und konsequent verifizieren:**  
      
    Es bedarf der Einführung und verpflichtenden Nutzung digitaler Signaturen für die Faxkommunikation, insbesondere im Verkehr mit Behörden, im Gesundheitswesen und in anderen sicherheitskritischen Bereichen. Ein Fax ohne verifizierten Absender darf keine automatische Gültigkeit beanspruchen.
- **3. Einführung einer Auditpflicht für sicherheitsrelevante Faxkommunikation:**  
      
    Es muss eine verpflichtende und nachvollziehbare Dokumentation aller sicherheitsrelevanten ein und ausgehenden Faxe geben. Diese Dokumentation muss die Herkunft, die Zieladresse, den Zeitstempel und die zuständigen Bearbeiter umfassen. Die implizite Gültigkeit eines Dokuments allein durch das charakteristische Geräusch des Faxgeräts muss beendet werden.
- **4. Durchführung von Schulungen zur kritischen Vertrauensabwehr:**  
      
    Es bedarf einer gezielten Sensibilisierung der Nutzer für die Risiken, die von scheinbar vertrauten Geräten wie dem Fax ausgehen. Faxe sind nicht per se Beweismittel, sondern zunächst ungeprüfte Informationen. Solche Schulungen ersetzen keine technischen Sicherheitsmaßnahmen, sind aber ein notwendiger Baustein, um festgefahrene Alltagsgewohnheiten und trügerische Sicherheiten zu durchbrechen. Auch wenn der Effekt solcher Schulungen begrenzt bleiben mag, sind sie ein realistisch durchführbarer und wichtiger Beitrag zur Erhöhung der Gesamtsicherheit.
 
## Schlussformel

Wir bauen komplexe Cyberabwehrsysteme auf der Ebene von Bits und Bytes und verlieren dann möglicherweise den Kampf gegen ein Gerät, dessen Technologie aus den 80er Jahren stammt. Dies geschieht nicht, weil das Faxgerät klüger ist, sondern weil wir es in unserer modernen, digitalisierten Welt oft nicht mehr ausreichend ernst nehmen und seine Risiken unterschätzen.

Das Fax ist kein harmloser Anachronismus. Es ist ein Trojaner mit einem vertrauten Betriebsgeräusch.

> *Uploaded on 29. May. 2025*