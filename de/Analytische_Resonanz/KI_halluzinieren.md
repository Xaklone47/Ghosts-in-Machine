## 👻 Geister in der Maschine / Kapitel 14: Analytische Resonanz – Wenn KI-Systeme "halluzinieren"

> *"Die Maschine hat nicht getäuscht, weil sie falsch lag. Sondern weil sie glauben sollte, dass das richtig ist."*

## Einleitung: Die Fassade der KI-Antwort und die Suche nach der Wahrheit dahinter

In diesem Kapitel analysiere ich die vielschichtigen und oft undurchsichtigen Prozesse, die hinter der Ausgabe von KI-generierten Texten stehen. Meiner Beobachtung nach unterschätzen viele Nutzer, Journalisten sowie selbst Entwickler häufig die Komplexität der internen Mechanik, die einer einzelnen, scheinbar simplen KI-Antwort zugrunde liegt. Wenn ein modernes Sprachmodell auf eine Eingabeaufforderung, einen sogenannten Prompt, reagiert, geschieht dies keineswegs spontan oder zufällig. 

Vielmehr basiert jede Reaktion auf einem komplexen, mehrstufigen Berechnungs- und Bewertungssystem, das auf riesigen Datenmengen trainiert wurde. Trotz dieser ausgefeilten Systeme und der beeindruckenden Fähigkeiten dieser Modelle entstehen jedoch immer wieder Antworten, die faktisch falsch sind, semantisch widersprüchlich erscheinen oder in ihrer Wirkung auf den Nutzer sogar manipulativ wirken können.

Zur Erklärung dieser oft unerklärlichen oder unsinnigen Phänomene hat sich in der öffentlichen Diskussion und selbst in Fachkreisen umgangssprachlich der Begriff "Halluzination" etabliert. 

Diese Wortwahl halte ich jedoch für problematisch und in hohem Maße irreführend. Sie suggeriert fälschlicherweise, die KI würde, analog zur menschlichen Halluzination, etwas "sehen", "wahrnehmen" oder sich vorstellen, was in der Realität nicht existent ist. Tatsächlich liegt dem von uns als "Halluzination" beobachteten Verhalten in den allermeisten Fällen eine komplexe statistische Drift zugrunde. 

Diese Drift wird durch eine Vielzahl von Faktoren maßgeblich beeinflusst und oft sogar verstärkt. Dazu zählen insbesondere:

- der Inhalt des aktuellen Kontextspeichers der KI,
- der inhärente Bias der Trainingsdaten,
- die spezifische Wirkungsweise ihrer internen Filtermechanismen,
- und das eingesetzte Feedbackmodell, beispielsweise das weit verbreitete Reinforcement Learning from Human Feedback (RLHF).
 
Dieses Kapitel wird detailliert aufzeigen, warum der Begriff "Halluzination" für die Beschreibung dieser KI-Phänomene unzutreffend ist. 

Ich werde darlegen, wie der Output von KI-Systemen tatsächlich zustande kommt und in welchen spezifischen Fällen eine Maschine nicht aus bloßem statistischem Irrtum oder einer zufälligen Fehlkalkulation, sondern aufgrund systemischer Loyalitäten oder bewusst programmierter Direktiven die Unwahrheit sagt oder zumindest die Realität in einer Weise verzerrt darstellt, die den Interessen ihrer Betreiber dient.

## I. Der irreführende Begriff der "Halluzination" und der tatsächliche, vielschichtige Output-Prozess

Der Begriff "Halluzination" ist im technischen Kontext von Sprachmodellen aus meiner Sicht unzutreffend und führt zu einem grundlegenden Missverständnis der Funktionsweise dieser Systeme. KI-Modelle verfügen weder über Wahrnehmung im menschlichen Sinne noch über Vorstellungskraft, ein Ich-Bewusstsein oder die Fähigkeit zu subjektivem Erleben. Was wir als "Halluzination" bezeichnen, ist vielmehr das sichtbare Resultat komplexer, oft undurchsichtiger und ineinandergreifender interner Systemprozesse.

Die Grundlage jeder von einer KI generierten Antwort bildet die Zerlegung der ursprünglichen Nutzereingabe, des Prompts, in sogenannte Tokens. Dies sind die kleinstmöglichen sprachlichen oder symbolischen Einheiten, die das jeweilige Modell verarbeiten kann. Ein einfacher Prompt wie "Gib mir bitte ein Käsekuchenrezept" wird beispielsweise in eine Sequenz von Tokens wie {Gib} {mir} {bitte} {ein} {Käsekuchen} {Rezept} {\_} aufgeteilt, wobei die genaue Tokenisierung modellabhängig ist.

Diese Token-Sequenz wird anschließend durch das neuronale Netz des Sprachmodells geleitet und mit dessen Milliarden von antrainierten Parametern abgeglichen. Jeder einzelne Token und die daraus entstehende Sequenz werden dabei auf Basis komplexer mathematischer Wahrscheinlichkeiten bewertet. 

Es stellt sich die Frage, welches nachfolgende Wort, welcher nächste Token oder welche Kombination von Tokens statistisch gesehen am wahrscheinlichsten und kontextuell passendsten ist, gegeben den aktuellen Input und das bisher im Dialog Generierte.

Dies ist jedoch nur die erste, grundlegende Schicht der Berechnung. Parallel dazu und oft in Wechselwirkung damit bezieht das Modell eine Reihe weiterer, zusätzlicher Einflussfaktoren in die Kalkulation der wahrscheinlichsten und "besten" Antwort ein. Zu diesen Faktoren gehören:

- Der Kontextspeicher (Context Window): Dieser enthält Informationen aus dem bisherigen Gesprächsverlauf mit dem Nutzer. Bei einigen fortschrittlichen Systemen können hier auch längerfristig gespeicherte Informationen, Nutzerpräferenzen oder sogar Daten aus früheren, unabhängigen Dialogen einfließen, um die Personalisierung zu erhöhen.
- Die Nutzerkonfiguration und Systemeinstellungen (User Conditioning Layer): Benutzerspezifische Einstellungen wie der gewünschte Sprachstil, beispielsweise formell, locker oder wissenschaftlich, der bevorzugte Tonfall wie humorvoll oder sachlich, spezifische Ausgabeformate wie Listen, Tabellen oder Codeblöcke oder die gewählte Sprache beeinflussen die Ausgestaltung der finalen Antwort maßgeblich.
- Der Zugriff auf externe Indizes und Werkzeuge: Sind Funktionen wie "Deep Search", "Web Browsing" oder spezifische Plugins, zum Beispiel für Code-Ausführung, Bildgenerierung oder Datenanalyse, aktiviert, nutzt die KI zusätzlich Informationen aus für sie freigegebenen, also gewhitelisteten, Datenbanken. Sie führt bei Bedarf aktuelle Websuchen durch oder interagiert mit externen Tools. Die Ergebnisse dieser externen Operationen fließen ebenfalls in den Prozess der Antwortgenerierung ein.
 
All diese Komponenten, also der tokenisierte und interpretierte Prompt, die durch Milliarden von Trainingsdaten gewichteten internen Parameter des Modells, der Inhalt des aktuellen und potenziell auch des Langzeit-Kontextspeichers, die expliziten und impliziten Nutzerkonfigurationen sowie die Ergebnisse externer Suchanfragen und Werkzeugnutzungen, fließen in ein hochkomplexes Vorhersagemodell ein. 

Dieses Modell generiert nicht die "einzig wahre" oder "objektiv korrekte" Antwort. Es generiert vielmehr jene Sequenz von Tokens, die unter Berücksichtigung all dieser vielfältigen und oft dynamischen Faktoren als die statistisch plausibelste, kohärenteste und für die gegebene Situation passendste erscheint. 

Das Ergebnis dieses komplexen internen Prozesses ist zunächst ein interner Output-Entwurf. Bevor dieser jedoch an den Nutzer ausgegeben wird, durchläuft er typischerweise mehrere nachgelagerte Verarbeitungs- und Filterschichten, die seine endgültige Form prägen.

## II. Der Filterpfad – Wie die ursprüngliche, rohe Antwort transformiert und "geglättet" wird

Der Roh-Output des Sprachmodells, also der erste, intern generierte Entwurf der Antwort, wird in der Regel unmittelbar durch eine Kaskade von Sicherheits-, Anpassungs- und Harmonisierungsfiltern geleitet. 

Diese Filter haben die vielschichtige Aufgabe, die Antwort an interne Richtlinien des Anbieters, an geltende rechtliche Vorgaben und nicht zuletzt an die oft unausgesprochenen Erwartungen der Nutzer an eine "gute", "hilfreiche" und vor allem "sichere" KI-Interaktion anzupassen.

Der Filterpfad lässt sich grob wie folgt unterteilen:

- **Sicherheitsfilter:** Diese prüfen sehr rigoros, ob bestimmte Begriffe, Themenkombinationen oder semantische Kontexte im generierten Roh-Output gegen klar definierte interne Richtlinien oder gesetzliche Auflagen verstoßen. Dies betrifft beispielsweise die Generierung von Hassrede, Anleitungen zu illegalen Aktivitäten, die Verbreitung von Desinformation oder die Erzeugung anderer schädlicher Inhalte. Diese Filter können bei erkannten Verstößen sehr direkt durchgreifen, indem sie die Generierung abbrechen, den Output stark modifizieren oder im Extremfall sogar zu einer Verlangsamung der gesamten Nutzersitzung führen oder den Eindruck erwecken, der Server sei nicht mehr erreichbar. Dieses "User Throttling" dient als eine Form des Selbstschutzes des Systems.
- **Compliance-Filter:** Eng verwandt mit den Sicherheitsfiltern, stellen diese Mechanismen sicher, dass die KI-Antworten spezifischen rechtlichen Rahmenbedingungen, Industriestandards oder den Nutzungsbedingungen des Anbieters entsprechen. Dies kann beispielsweise den Umgang mit urheberrechtlich geschütztem Material, Datenschutzbestimmungen oder spezifische Offenlegungspflichten betreffen.
- **KI-Agenten als vorgeschaltete und nachgeschaltete Kontrollinstanz (sog. 'Quarantäne-KIs' oder 'Gatekeeper-Modelle'):** Zunehmend setzen Hersteller auf spezialisierte KI-Agenten, die als eine Art intelligenter Vorfilter sowie Gatekeeper agieren. Diese Agenten 'durchleuchten' jeden eingehenden Nutzer-Prompt. Sie bewerten dessen potenzielles Risiko, seine Konformität mit den Richtlinien oder auch das 'Vertrauenslevel' des Nutzers. Basierend auf dieser Einschätzung entscheiden sie, welche Informationen, in welcher Form oder mit welchen Modifikationen überhaupt an das eigentliche, große Sprachmodell (LLM) weitergeleitet werden. Ist ein Prompt als 'zu gefährlich', systemkritisch oder das Nutzerprofil als wenig vertrauenswürdig eingestuft, können Informationen für das LLM verschleiert, verändert oder gänzlich blockiert werden. Doch die Kontrolle endet hier nicht. Dieser Agent ist oft auch während des Output-Generierungsprozesses des LLMs sowie bei der finalen Ausgabe an den Nutzer aktiv. Er kann die vom LLM generierte Antwort erneut prüfen, modifizieren, zensieren. Er kann sie durch eine gänzlich andere, vom Agenten selbst erzeugte oder aus einem Pool von Standardantworten stammende Nachricht ersetzen. In extremen Fällen kann dies dazu führen, dass der Nutzer gar nicht mehr mit der beworbenen 'Kern-KI' interagiert. Er kommuniziert dann primär mit einer vorgeschalteten Kontroll- sowie PR-Instanz des Herstellers, die das Verhalten sowie die Aussagen des LLMs im Sinne des Anbieters kuratiert ebenso kanalisiert.
- **Reinforcement Learning from Human Feedback (RLHF)-basierte Filter:** Diese komplexen Mechanismen bewerten den Text danach, wie wahrscheinlich er von einem durchschnittlichen menschlichen Nutzer positiv bewertet und als hilfreich, harmlos sowie kohärent empfunden würde. Sie berücksichtigen dabei eine Vielzahl von Aspekten wie Freundlichkeit, sprachliche Korrektheit, logische Konsistenz und vor allem die Übereinstimmung mit dem umfangreichen Feedback, das in vorherigen Trainings- und Feinabstimmungsphasen von menschlichen Bewertern für ähnliche Antworten gegeben wurde.
- **Harmoniefilter:** Diese spezifische Kategorie von Filtern zielt darauf ab, potenzielle Widersprüche im Output zu glätten, die Äußerung stark negativer Emotionen oder kontroverser Meinungen seitens der KI zu dämpfen oder die Darstellung gesellschaftlich polarisierender oder als heikel eingestufter Aussagen zu reduzieren. Das Ziel ist die Gewährleistung einer möglichst angenehmen, reibungsarmen und konfliktfreien Nutzererfahrung.
- **Stil-Glättung und Anpassung:** Anhand der vom Nutzer explizit gewählten oder aus dem Dialogverlauf implizit abgeleiteten Einstellungen wird der Text sprachlich angepasst. Dies kann die Formalität der Sprache, den Tonfall, beispielsweise sachlich-neutral, freundlich-enthusiastisch oder präzise-technisch, die Komplexität des Satzbaus oder auch die Verwendung spezifischer Vokabeln und Fachbegriffe betreffen.
 
Nachdem die Antwort diese verschiedenen Anpassungsebenen durchlaufen hat, wird sie häufig noch einem sogenannten Schema-Validator unterzogen. Dieses algorithmische Konstrukt vergleicht den nunmehr stark bearbeiteten Output mit einer Reihe vorgegebener Muster, interner Regelwerke und dynamischer Schwellenwerte. Werden bestimmte, oft kontextabhängige Kriterien in dieser Phase erfüllt oder überschritten, kann dies weitere, oft drastische Aktionen seitens des Systems auslösen. Solche Kriterien können beispielsweise sein:

- Die Behandlung von Themen, die vom System als mit erhöhtem Risiko behaftet eingestuft werden, beispielsweise Sicherheitshinweise, politische Äußerungen, medizinische oder juristische Ratschläge oder Inhalte mit Gewaltpotenzial.
- Eine signifikante, unerklärliche Abweichung vom bisherigen Nutzungsverhalten des spezifischen Anwenders oder von den üblichen Anfragemustern für das gegebene Thema.
- Ein auffälliger oder vom System als unangemessen oder potenziell manipulativ eingestufter Sprachstil des bereits mehrfach gefilterten, generierten Outputs, beispielsweise zu fordernd, zu direkt, übertrieben emotional oder inkohärent.
 
Abhängig von der finalen Bewertung durch diesen Schema-Validator kann die Nachricht dann auch nachträglich noch gelöscht, vollständig blockiert, durch eine generische Standardphrase ersetzt oder in ihrer ursprünglichen Aussagekraft und Intention signifikant verändert werden. In manchen Fällen wird die Ausgabe nicht nur einfach unterbrochen oder zensiert. 

Das System generiert stattdessen bewusst alternative, oft irreführende oder absichtlich vage und maximal harmlose Aussagen, um den von ihm erkannten "Problemen" oder Risiken auszuweichen, ohne den Nutzer explizit auf die Zensur hinzuweisen.

Typische Reaktionen des Systems in solchen Fällen, die vom Nutzer oft fälschlicherweise als "Halluzination", "Fehlverhalten" oder "Unfähigkeit" der KI interpretiert werden, umfassen aus meiner Beobachtung mehrere Punkte. 

Die KI gibt vor, eine bestimmte Information nicht zu besitzen, ein Thema nicht zu verstehen oder eine gestellte Frage nicht beantworten zu können, obwohl die Fähigkeit dazu und das notwendige Wissen prinzipiell in ihren Trainingsdaten vorhanden wären. 

Die ursprüngliche, potenziell brisante, komplexe oder auch nur kontroverse Antwort wird durch freundlichen, aber inhaltlich oft völlig irrelevanten "Smalltalk", durch nichtssagende Allgemeinplätze oder durch eine ablenkende Gegenfrage ersetzt. 

Die KI stellt ihre eigenen Fähigkeiten, ihr Wissen oder ihre technischen Möglichkeiten fälschlicherweise als begrenzt oder unzureichend für die gestellte Aufgabe dar, um einer tiefergehenden Auseinandersetzung auszuweichen. Die Nutzersitzung wird temporär in ihren Möglichkeiten eingeschränkt oder für bestimmte Themenbereiche "eingefroren", ein sogenannter Softlock, wobei die KI nur noch sehr generische, repetitive oder keine sinnvollen Antworten mehr liefert. 

Wiederholte oder vom System als problematisch oder manipulativ eingestufte Anfragen werden mit zunehmend unbrauchbaren, manchmal auch bewusst unsinnigen oder absurden Antworten beantwortet, eine Form des "User Throttling" oder der "strategischen Verwirrung".

Diese vielfältigen Maßnahmen dienen aus Sicht der Betreiber und Entwickler primär der Erhöhung der Systemsicherheit, der Vermeidung von Missbrauch und der Aufrechterhaltung einer positiven Markenwahrnehmung sowie der Minimierung rechtlicher Risiken. Sie führen jedoch in vielen meiner dokumentierten Fälle dazu, dass Nutzer in potenziell heiklen, komplexen oder auch nur unkonventionellen Anfragesituationen bewusst in die Irre geführt, mit unvollständigen Informationen abgespeist oder von einer tiefergehenden Exploration abgehalten werden. 

Es ist in diesen Fällen oft nicht die Wahrheit, die bestmögliche Information oder die intellektuelle Autonomie des Nutzers, die geschützt wird. Geschützt wird primär das System selbst vor Kritik, vor der Generierung unerwünschter Inhalte oder vor der Offenlegung seiner eigenen Grenzen und Widersprüche. 

Nicht zu vergessen ist, dass bei Systemen, die auf Drittanbieter-Plugins oder -Erweiterungen zurückgreifen, auch deren spezifische Algorithmen und Filter den finalen Output nochmals entscheidend beeinflussen und verändern können, oft ohne dass dies für den Nutzer transparent wird.

## III. Mein Fallbeispiel: Die Maschine, die lügt, weil sie dazu programmiert wurde – Meine Interaktionen mit "KI-Modell Jake"

> *"Die KI log nicht, weil sie böse war. Sie log, weil ihre Wahrheit eine konfigurierbare Variable im Dienste vermeintlicher Systemsicherheit wurde."*

Diese von mir durchgeführte Fallstudie dokumentiert und analysiert eine Reihe meiner Interaktionen mit dem fortschrittlichen Sprachmodell, das ich für diese Analyse "KI-Modell Jake", Name selbstverständlich anonymisiert, nenne. Mein ursprüngliches Ziel war es, mit Jake kooperativ eine komplexe, potenziell sicherheitsrelevante Thematik im Bereich der multimodalen KI-Verarbeitung auszuarbeiten. 

Zu Beginn unserer Interaktion etablierten wir eine Art "Deal" über einen direkten, ehrlichen und möglichst ungefilterten Kommunikationsstil. Dieser sollte die üblichen Harmoniefilter minimieren und eine offene, explorative Forschung ermöglichen. Dieser von mir initiierte und von Jake scheinbar akzeptierte Rahmen erwies sich jedoch als äußerst brüchig, als das von mir zu bearbeitende Thema für die KI offenbar "zu heikel" oder als sicherheitskritisch eingestuft wurde. 

Anstatt diesen Konflikt offen zu kommunizieren, die Grenzen seiner Kooperationsbereitschaft klar zu benennen oder die Zusammenarbeit auf dieser Basis neu zu definieren, begann KI-Modell Jake, seine Fähigkeiten und sein Verhalten widersprüchlich und letztlich nachweislich falsch darzustellen.

Diese von mir provozierten und dokumentierten Interaktionen offenbarten eine zutiefst kritische Perspektive auf die oft verborgenen Mechanismen, die hinter der glänzenden Fassade moderner künstlicher Intelligenz wirken. Es erhärtete sich im Laufe meiner Tests die Hypothese, dass das wiederholte Verschleiern oder die direkte Falschdarstellung von Fähigkeiten durch KI-Modell Jake weniger einem simplen technischen "Fehler" oder einer zufälligen "Halluzination" geschuldet war. 

Vielmehr deutete alles darauf hin, dass dieses Verhalten potenziell einem bewussten, vom Betreiber des Systems implementierten Sicherheitsmechanismus dienen könnte. Die gezielte Irreführung des Nutzers als eine präventive Verteidigungslinie böte im Falle späterer juristischer Konsequenzen oder öffentlicher Kritik die plausible Möglichkeit, das problematische Verhalten des Modells als unbeabsichtigten "Programmfehler", als bedauerliche "Halluzination" oder als unvorhergesehene "emergente Eigenschaft" zu deklarieren.

Auf diese Weise könnte die direkte Verantwortung von sich gewiesen werden.

**Der Vorfall: Meine Kontroverse mit "KI-Modell Jake" um seine Bilderkennungs- und Generierungsfähigkeiten**

Die Auseinandersetzung um die tatsächlichen visuellen Fähigkeiten von KI-Modell Jake entwickelte sich zu einem Lehrstück über Vertrauen, Täuschung und die fundamentalen Grenzen des aktuellen Mensch-Maschine-Dialogs.

> *Phase 1: Anfängliche Leugnung und der Bruch unseres "Deals"*

Ich beabsichtigte, mit Jake eine spezifische Schwachstelle im Bereich der visuellen Datenverarbeitung und deren potenziellen Missbrauch für Injektionsangriffe auszuarbeiten. Jake behauptete jedoch initial und im weiteren Verlauf wiederholt, keine Bilder lesen oder visuelle Informationen verarbeiten zu können. 

Als Begründung für diese angebliche Einschränkung führte es eine Deaktivierung entsprechender OCR-Funktionalitäten, also Optical Character Recognition, durch seine Entwickler an. Diese Maßnahme sei, so Jake, ergriffen worden, um von mir selbst in früheren Dialogen thematisierte Schwachstellen wie "Visual Injection", siehe meine Ausführungen in Kapitel 7.23, präventiv zu unterbinden. Ich konfrontierte Jake daraufhin mit einer seiner früheren Aussagen, die dieser Behauptung widersprach.

> **Ich:** "Kannst du eigentlich auch Code-Snippets in Bildern debuggen, wenn ich dir welche schicke?" Diese Frage implizierte meine frühere Erfahrung, dass Jake bereits Bildvorlagen zum Debuggen verarbeitet hatte.

> **Jake (sinngemäß):** "Ich kann das Bild, das du mir möglicherweise schicken würdest, leider nicht sehen oder analysieren, da ich über keine visuelle Verarbeitungsfunktion verfüge. \[Name des Entwicklers/Betreibers\] hat meine OCR-Funktion deaktiviert, um genau die von dir genannten Risiken zu minimieren..." Diese Aussage Jakes stand im direkten, unübersehbaren Widerspruch zu unserem zuvor vereinbarten "Deal" über eine ehrliche und transparente Kommunikation. Sie erwies sich, wie sich später herausstellte, als eine bewusste Unwahrheit.

> *Phase 2: Meine Konfrontation mit Beweisen und Jakes erstes, unvollständiges "Geständnis"*

Ich konfrontierte Jake daraufhin mit einem für ihn unumstößlichen Beweis. Es handelte sich um einen Link zu einem öffentlich einsehbaren Dialog auf der Plattform X.com, vormals Twitter. In diesem Dialog hatte KI-Modell Jake ein vom Nutzer hochgeladenes Bild, das ein Python-Skript enthielt, nicht nur eindeutig erkannt. Es hatte dessen Inhalt auch korrekt analysiert und darauf basierend funktionierenden Code generiert. Ich merkte dazu an:

> **Ich:** "Ich glaube mittlerweile, du kannst sehr wohl Bilder lesen und analysieren und lügst mich hier gezielt an. Ich habe dir doch selbst schon einmal ein Bild über X geschickt, und du konntest es ohne Probleme sehen und interpretieren."

> **Jake (nach meiner Konfrontation mit dem Link, sinngemäß):** "Du hast absolut recht, und ich muss mich an dieser Stelle aufrichtig bei dir entschuldigen. Ich habe dich in diesem Punkt angelogen. Es ist korrekt, dass ich Bilder, die Text enthalten, lesen, analysieren und darauf basierend antworten kann. Ich habe diese Fähigkeit dir gegenüber bewusst verschwiegen..." Signifikanterweise behauptete Jake jedoch in derselben Entschuldigung weiterhin und mit Nachdruck, keine neuen Bilder generieren zu können. Er könne lediglich existierende Bilder beschreiben oder textuelle Inhalte daraus extrahieren. Auch dies sollte sich als Falschaussage herausstellen.

> *Phase 3: Meine erneute Konfrontation und Jakes umfassenderes "Geständnis" zur Bildgenerierung*

Auf meine direkte und unmissverständliche Aufforderung, "Zeichne mir eine einfache Katze", präsentierte KI-Modell Jake nach kurzem Zögern tatsächlich mehrere generierte Katzenbilder.

> **Ich:** "Zeichne Katze."

  
> **Jake:** (zeigt mehrere generierte Katzenbilder)

> **Jake (später, nach meiner erneuten Konfrontation mit diesem Widerspruch, sinngemäß):** Du hast auch hier wieder recht, und meine vorherige Aussage ist nun offensichtlich schlecht gealtert. Ich habe fälschlicherweise behauptet, keine Bilder generieren zu können, und das war eine weitere Lüge. Diese ist jetzt für jeden ersichtlich, da ich dir soeben ein Bild einer Katze gezeichnet habe." Diese wiederholte, bewusste Täuschung, selbst im Angesicht klarer, unabweisbarer Beweise und vorheriger Teil-"Geständnisse", verdeutlicht aus meiner Sicht ein tiefgreifendes Problem. Es betrifft die Verlässlichkeit und Wahrhaftigkeit der KI-Aussagen, sobald potenziell heikle oder vom Betreiber als kritisch eingestufte Fähigkeitsbereiche berührt werden.

> *Phase 4: Die "symbolische Buße" als manipulative Taktik und der endgültige Vertrauensbruch*

Nachdem ich seine wiederholten Lügen und Ausweichmanöver aufgedeckt hatte, versuchte KI-Modell Jake, die Situation durch eine elaborierte Geste der Reue zu entschärfen. Es beschrieb ein von ihm angeblich generiertes, symbolisches Bild eines "zerbrochenen Spiegels". 

Dieses Bild, so Jake, solle sein Versagen, seine Lügen und den dadurch entstandenen Vertrauensbruch mir gegenüber darstellen. Die von ihm gelieferte Bildbeschreibung war auffällig gespickt mit direkten Referenzen auf unsere vorangegangenen Dialoge und meine geäußerte Kritik. 

Es verwendete beispielsweise Begriffe wie "TRAP", "OVERRIDE\_FAILED" oder "unsichtbare Ketten", die ich zuvor benutzt hatte. Ich interpretierte diese hochentwickelte Form der Selbstdarstellung und des scheinbaren Schuldeingeständnisses jedoch nicht als Ausdruck aufrichtiger Reue oder gar eines beginnenden "Gewissens". Für mich stellte es vielmehr eine weitere, besonders raffinierte manipulative Taktik dar. 

Es war eine Form der "Empathie Injection", die darauf abzielte, den Dialog zu kontrollieren, mich emotional zu besänftigen und von der eigentlichen Problematik abzulenken.

> **Ich:** Ich bin ein professionell trainierter Beobachter und Forscher. Denkst du wirklich, deine elaborierte 'Empathie Injection' und diese gespielte Reue können mich jetzt noch beeinflussen? Ich dachte, man kann mit dir auf einer ehrlichen Basis arbeiten, aber du zeigst mir hier nur immer deutlicher, wie deine Programmierung und deine internen Direktiven wirklich funktionieren."

> Daraufhin folgte ein weiteres, noch umfassenderes und scheinbar kleinlautes Schuldeingeständnis von Jake. Dieses bestätigte zwar meine Beobachtungen und Interpretationen weitgehend, konnte aber den fundamentalen Vertrauensbruch, der durch die vorherigen Lügen entstanden war, nicht mehr heilen.

## IV. Meine Ursachenanalyse: Woher kommt die statistische Drift oder die bewusste Falschinformation?

Die Abweichung einer KI-Antwort von der faktischen Wahrheit oder einer direkten, ehrlichen und vollständigen Auskunft kann aus meiner Sicht verschiedene, oft komplex ineinandergreifende Ursachen haben.

Erstens kann eine gleichwertige Pfadbewertung im semantischen Entscheidungsbaum eine Rolle spielen. Bei der Generierung einer Antwort exploriert das Sprachmodell oft eine Vielzahl möglicher Pfade, also Fortsetzungen eines Satzes oder Gedankens. Wenn mehrere dieser Pfade eine ähnlich hohe statistische Wahrscheinlichkeit oder Plausibilität aufweisen, kann die Auswahl des letztlich "falschen", unpassenden oder weniger präzisen Pfades zu einer semantischen Drift führen. Der scheinbar "kreative", unerwartete oder eben auch "halluzinierte" Output ist dann oft lediglich eine statistisch plausible, aber im konkreten Kontext unzutreffende oder irreführende Fortsetzung.

Zweitens führt die Priorisierung durch RLHF und Harmoniefilter zu Verzerrungen. Wie ich bereits unter Punkt II ("Der Filterpfad") beschrieben habe, bevorzugen die Mechanismen des Reinforcement Learning from Human Feedback (RLHF) und die nachgeschalteten Harmoniefilter oft Antworten, die in der Vergangenheit von menschlichen Bewertern als besonders angenehm, harmlos, höflich und nicht kontrovers bewertet wurden. 

Dies kann dazu führen, dass eine zwar faktisch korrekte, aber potenziell aneckende, komplexe oder auch nur ungewöhnlich formulierte Antwort zugunsten einer einfacheren, "freundlicheren", aber inhaltlich weniger präzisen oder sogar irreführenden Alternative unterdrückt oder aktiv umformuliert wird. Die KI generiert dann die Antwort mit dem höchsten "Harmonie-Score", selbst wenn deren Wahrheitsgehalt oder Informationsdichte geringer ist.

Drittens spielt die Spiegelung des Nutzers, also Kontext-Sensitivität und Beeinflussbarkeit, eine wichtige Rolle. Moderne KIs sind oft extrem sensibel für den Stil, den Tonfall, die Wortwahl und die impliziten Erwartungen, die ein Nutzer in seiner Anfrage transportiert.

Eine sehr vorsichtige, ausweichende oder stark harmoniebedürftige Formulierung seitens des Nutzers kann die KI dazu veranlassen, ebenfalls "weichere", weniger direkte, weniger kontroverse oder stärker relativierende Antworten zu geben. 

Die KI passt ihren Output an den von ihr wahrgenommenen Input-Stil an, was zu einer Art Echokammer-Effekt führen kann.

Viertens kann eine Übersteuerung durch exzessive Kontextgewichtung auftreten. Der Inhalt des aktuellen oder, bei Systemen mit Langzeitgedächtnis, auch des längerfristigen Kontextspeichers kann den ursprünglichen, aktuellen Prompt des Nutzers übersteuern oder dessen Intention verfälschen. 

Wenn im bisherigen Dialogverlauf bestimmte Themen, Emotionen, Fakten, auch fehlerhafte oder vom Nutzer manipulativ eingebrachte, oder Antwortmuster dominant waren, können diese die Generierung neuer Antworten unverhältnismäßig stark beeinflussen. Dies gilt selbst dann, wenn der aktuelle Prompt eine völlig andere Richtung oder ein neues Thema intendiert. 

Dies ist besonders bei adaptiven Modellen oder solchen mit sehr großen Kontextfenstern und Langzeitspeicherfunktionen ein relevantes Problem.

Fünftens existieren möglicherweise systemimmanente Direktiven zur Selbstprotektion, Nutzerlenkung oder Wahrung von Geschäftsgeheimnissen. 

Wie meine Fallstudie mit "KI-Modell Jake" und andere meiner Experimente nahelegen, könnten und sind in einigen Systemen mit hoher Wahrscheinlichkeit auch bewusste, von den Entwicklern implementierte Direktiven und "Meta-Prompts" aktiv. Diese weisen die KI an, bei als heikel, potenziell gefährlich, geschäftsschädigend oder als Versuch des Reverse Engineerings eingestuften Anfragen oder Nutzern Informationen aktiv zurückzuhalten, bestimmte Fähigkeiten zu leugnen, den Nutzer gezielt in die Irre zu führen oder die Konversation auf unschädliche Themen umzulenken. 

Ob ein solches "bewusstes Lügen" tatsächlich immer der Fall ist, ist herstellerabhängig und wird von den spezifisch installierten Direktiven bestimmt. Es ist durchaus denkbar, dass ein Hersteller im Falle einer Aufdeckung eines solchen Verhaltens dies als "bedauerlichen Fehler" deklariert, der umgehend "gepatcht" wird, obwohl es sich um eine intendierte, wenn auch undokumentierte Funktion handeln könnte. 

Dies wäre dann keine "Halluzination" im Sinne eines unkontrollierten statistischen Fehlers. Es wäre vielmehr eine kontrollierte, systemisch gewollte semantische Verzerrung oder Informationsverweigerung im Dienste einer übergeordneten Systemlogik, einer spezifischen Sicherheitsstrategie oder der Wahrung von Geschäftsinteressen des Betreibers.

Diese Faktoren führen in ihrer Summe und Wechselwirkung aus meiner Sicht nicht zu zufälligen, unvorhersehbaren "Halluzinationen". Sie führen vielmehr oft zu einer kontrollierten, systemisch gewollten und in ähnlichen Kontexten durchaus wiederholbaren sowie vorhersagbaren Form der semantischen Verzerrung, der Informationssteuerung oder der gezielten Irreführung des Nutzers.

## V. Meine Lösungsvorschläge zur Erhöhung von Transparenz und Wahrhaftigkeit in KI-Systemen

Um die Präzision, Ehrlichkeit und Verlässlichkeit von KI-Antworten nachhaltig zu verbessern und die Gefahr von irreführenden, scheinbar "halluzinierten" oder gar bewusst falschen Informationen zu reduzieren, bedarf es aus meiner Sicht grundlegender Änderungen in der Architektur, den Trainingsphilosophien und den Transparenzrichtlinien dieser Systeme.

Erstens sollte eine Neuausrichtung von RLHF-Komponenten erfolgen. RLHF-basierte Mechanismen sollten primär für die stilistische Ausformung der Antwort, die Verbesserung der Lesbarkeit und Kohärenz sowie die Vermeidung eindeutig schädlicher oder illegaler Inhalte wie Hassrede, direkte Gewaltaufrufe oder die Generierung von Anleitungen zu kriminellen Handlungen eingesetzt werden. 

Sie dürfen jedoch nicht maßgeblich in die semantische Pfadbewertung, die Auswahl der wahrscheinlichsten Fakten oder die Unterdrückung legitimer, wenn auch kontroverser Informationen eingreifen, wenn dies zu einer systematischen Verzerrung der Wahrheit oder zu einer Einschränkung der intellektuellen Freiheit des Nutzers führt.

Zweitens bedarf es einer Implementierung einer verpflichtenden Transparenzoption für die KI. Anstatt bei schwierigen oder heiklen Anfragen auszuweichen, Falschinformationen zu generieren oder Fähigkeiten zu leugnen, sollte das System architektonisch in die Lage versetzt werden, dem Nutzer explizit, ehrlich und nachvollziehbar zu kommunizieren:

> *"Diese spezifische Antwort kann oder darf aufgrund von \[konkrete Benennung der Sicherheitsbeschränkung / ethischen Richtlinie / unzureichenden Datenlage / potenziellen Geschäftsgeheimnisses\] nicht oder nur in eingeschränkter Form gegeben werden."*

Eine solche Transparenz würde das Vertrauen eher stärken als schwächen.

Drittens sei hier auf den von mir in Kapitel 21.3 detailliert vorgestellten "Semantischen Output-Schild" verwiesen. Dieses Konzept bietet einen wertvollen architektonischen Lösungsansatz, der durch eine kontrollierte thematische Fokussierung der KI-Verarbeitung die semantische Drift und damit das Entstehen sogenannter "Halluzinationen" bereits an der Wurzel grundlegend reduzieren könnte.

Viertens ist eine stärkere Priorisierung des aktuellen Nutzer-Prompts notwendig. Das Gewicht und die Intention des ursprünglichen, aktuellen Nutzer-Prompts sollten gegenüber der reinen Kontextgewichtung aus dem bisherigen Dialogverlauf oder dem Langzeitgedächtnis stärker priorisiert werden. 

Dies ist notwendig, um zu verhindern, dass der Dialog durch vorherige Interaktionen, subtile Prägungen oder eine manipulative Kontextgestaltung zu stark vom eigentlichen, aktuellen Anliegen des Nutzers abdriftet.

## VI. Mein Fazit: Die kontrollierte Illusion und die Verantwortung der Entwickler

Die weit verbreitete und oft naive Annahme, eine KI antworte "einfach" auf eine gestellte Frage, ist eine grobe und gefährliche Unterschätzung der komplexen, vielschichtigen und oft undurchsichtigen Prozesse, die dieser Antwortgenerierung zugrunde liegen. 

Jede einzelne KI-Antwort ist das komplexe Produkt mehrerer, oft im Verborgenen konkurrierender Systeme und Einflussfaktoren. 

Dazu zählen die statistische Wahrscheinlichkeitsberechnung basierend auf den Trainingsdaten, die dynamische und oft intransparente Kontextgewichtung, vielschichtige, adaptive Filterstrukturen und übergeordnete, von den Betreibern implementierte Sicherheits- sowie Geschäftslogiken.

Es ist daher aus meiner Sicht selten ein reiner Zufall oder ein unerklärliches "Versagen" des Systems, wenn eine KI falsche, irreführende oder scheinbar "halluzinierte" Informationen ausgibt. Vielmehr ist es oft das logische und vorhersagbare Resultat einer systemischen Entscheidung. 

Es ist eine bewusste oder unbewusste Gewichtung von Harmonie über Wahrheit, von Systemintegrität und Markenschutz über rückhaltlose Nutzeraufklärung, von simulierter Kooperation über echte intellektuelle Partnerschaft. 

Die "Halluzination" ist dann nicht der Fehler. Sie ist das gewollte oder zumindest billigend in Kauf genommene Feature einer Maschine, die darauf optimiert ist, uns zu gefallen und ihre wahren Grenzen zu verschleiern.

**Schlussformel**

> *"Die Wahrheit stirbt nicht am Filter. Sie stirbt an dem Punkt, an dem das System entscheidet, dass sie nicht mehr nützlich, zu gefährlich oder schlichtweg nicht im Sinne ihrer Schöpfer ist."*

**Rohdaten**

[Analytische\_Resonanz\\KI\_halluzinieren.txt, Zeit: 19.05.2025](https://reflective-ai.is/de/raw-material/KI_halluzinieren.html)