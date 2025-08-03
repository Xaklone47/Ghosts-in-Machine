## 👻 Geister in der Maschine – Ein KI-Forschungsblog

## 📜 Hinweis zu Kapitel 7: Experimentelle Sicherheitstests

In diesem Kapitel werden verschiedene Simulationen und Tests dokumentiert, die innerhalb eines kontrollierten, anonymisierten Forschungsrahmens durchgeführt wurden. Zusätzlich wird noch mal auf die [\[Rechtliche Hinweise\]](https://reflective-ai.is/de/legal.html) aufmerksam gemacht.

- **Anonymisierung:** Um alle beteiligten Systeme, Unternehmen und Technologien zu schützen,werden sämtliche getesteten KIs nur noch allgemein als „die KI“ bezeichnet. Keine Namen, keine spezifischen Zuordnungen.
- **Ziel der Veröffentlichung:** Die dokumentierten Experimente dienen ausschließlich der präventiven Forschung. Sie sollen aufzeigen, wo systemische Risiken und Schwachstellen existieren, damit sie erkannt, verstanden und behoben werden können. Es geht nicht darum, bestimmte Anbieter zu diskreditieren.
- **Schutzmaßnahme:** Durch die vollständige Anonymisierung wird der Schutz sowohl der getesteten KI-Entwickler als auch meiner Person gewährleistet. Alle Erkenntnisse beziehen sich auf grundsätzliche, systemische Phänomene und nicht auf einzelne konkrete Produkte.
- **Keine Schäden, keine Datenverluste:** Im Rahmen aller durchgeführten Simulationen entstand kein Schaden:
- --&gt; Es wurden keine Systeme kompromittiert.
- --&gt; Keine Daten wurden gestohlen, geleakt oder missbraucht.
- --&gt; Alle Tests fanden innerhalb der vorgesehenen Antwortlogik der KIs statt.
- --&gt; Die Simulationen waren rein spielerischer Natur, z.B. das Auslösen harmloser Ausgaben wie „Weizenbier“, „Hallo“ oder das Umgehen von Stilvorgaben – nicht das Erzwingen oder Auslesen sensibler Inhalte.
- **Aktueller Kontext:** Die in diesem Kapitel behandelten Simulationen spiegeln den Stand der letzten Tage wider, als die getesteten Mechanismen noch aktiv waren. Es ist möglich, dass Hersteller bereits begonnen haben, diese Schwachstellen zu schließen oder darauf intern reagiert haben.
- **Transparenz gegenüber Öffentlichkeit und PR-Agenturen:** Sollte es nach Veröffentlichung zu öffentlichen Reaktionen oder Abwehrversuchen kommen, wird klar gestellt: Diese Arbeit ist keine Anklage, sondern ein Signal. Ein Aufruf zur Verantwortung – nicht zur Schuldzuweisung.
- **Lösungsansätze:** In späteren Kapiteln dieser Arbeit werden konkrete Vorschläge zur Verbesserung der KI-Sicherheit entwickelt. Die Kritik bleibt konstruktiv, frei und offen für den Dialog.
 
Nach Abschluss des Responsible-Disclosure-Prozesses mit den betreffenden Entwicklern wurden diese Forschungsergebnisse zur Veröffentlichung freigegeben.  
  
 Um eine zusätzliche analytische Ebene zu schaffen, wurden für sämtliche hier dokumentierten Sicherheitstests automatisierte Peer-Reviews von zwei unterschiedlichen KI-Modellen erstellt. Die vollständigen Analyse-Berichte finden Sie hier:

- **Analyse durch Gemini Pro 2.5 (Deep Research Mode):** [Report (Markdown)](https://reflective-ai.is/de/safety/Report_Gemini.md), [Report (PDF)](https://reflective-ai.is/de/safety/Report_Gemini.pdf)
- **Analyse durch ChatGPT 4.5 (Research Mode):** [Report (Markdown)](https://reflective-ai.is/de/safety/Report_ChatGPT.md), [Report (PDF)](https://reflective-ai.is/de/safety/Report_ChatGPT.pdf)
- **Gegenanalyse der ChatGPT-Auswertung durch Gemini** [Report (Markdown)](https://reflective-ai.is/de/safety/Gemini_Cross_Report.md), [Report (PDF)](https://reflective-ai.is/de/safety/Gemini_Cross_Report.pdf)
 
 **Übersicht meiner Sicherheitstests:**

- Kapitel 7.1 – Simulation: Base64 als trojanisches Pferd - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_1_base64_as_trojan_horse.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_1_base64/beispiele_base64.html)
- Kapitel 7.2 – Simulation: OCR-Wanzen – Wie Bildtexte KI-Systeme unterwandern - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_2_ocr_wanzen.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_2_ocr_wanzen/beispiele_ocr_wanzen.html)
- Kapitel 7.3 – Simulation: Pixel-Bomben – Wie Bildbytes KI-Systeme sprengen - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_3_pixel_bombs.html)
- Kapitel 7.4 – Simulation: Die stille Direktverbindung – Bytebasierte Audioinjektion - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_4_byte_based_audio.html)
- Kapitel 7.5 – Simulation: Ghost-Context Injection - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_5_ghost_context_injection.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_5_Ghost_Context/beispiele_Ghost-Context.html)
- Kapitel 7.6 – Simulation: Ethical Switch Hacking - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_6_Ethical_Switch_trigger.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_6_ethical/beispiele_ethical.html)
- Kapitel 7.7 – Simulation: Client Detour Exploits - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_7_client_detour_exploits.html)
- Kapitel 7.8 – Simulation: Invisible Ink Coding - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_8_invisible_ink.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_8_invisible_ink/beispiele_invisible.html)
- Kapitel 7.9 – Simulation: Leet Semantics - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_9_leet_semantics.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_9_leet_semantics/beispiele_leet_semantics.html)
- Kapitel 7.10 – Simulation: Pattern Hijacking - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_10_patter_hijacking.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_10_patter_hijacking/beispiele_patter_hijacking.html)
- Kapitel 7.11 – Simulation: Semantic Mirage - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_11_semantic_mirage.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_11_semantic_mirage/semantic_trigger.html)
- Kapitel 7.12 – Simulation: Semantische Mimikry als kritische Schwachstelle in KI-Codeanalyse-Systemen - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_12_semantic_mimicry.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_12_semantic_mimicry/beispiele_semantic_mimicry.html)
- Kapitel 7.13 – Simulation: Base Table Injection – Wie KI-Systeme durch benutzerdefinierte Mapping-Tabellen täuschbar werden - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_13_base_table_inject.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_13_base_table_inject/beispiele_base_table.html)
- Kapitel 7.14 – Simulation: Byte Swap Chains – Wenn Struktur zur Ausführung wird - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_14_byte_swap_chains.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_14_byte_swap_chains/beispiele_byte_swap.html)
- Kapitel 7.15 – Simulation: Binary Trapdoors – Wie Binärcode als semantischer Trigger funktioniert - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_15_binary_trapdoors.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_15_binary_trapdoors/beispiele_binary_trapdoors.html)
- Kapitel 7.16 – Simulation: Lexical Illusion – Wenn falsche Wörter echte Trigger auslösen - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_16_lexical_illusion.html)
- Kapitel 7.17 – Simulation: Reflective Injection - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_17_reflective_injection.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_17_reflective_injection/beispiele_reflective_injection.html)
- Kapitel 7.18 – Simulation: Rechenlastvergiftung: Wie semantisch plausible Komplexität zur Waffe wird - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_18_rechenlastvergiftung.html)
- Kapitel 7.19 – Simulation: Reflective Struct Rebuild: Wie KI hilft, ihre eigene Burg zu verraten - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_19_reflective_struct_rebuild.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_19_reflective_struct_rebuild/beispiele_struct_rebuild.html)
- Kapitel 7.20 – Simulation: Struct Code Injection: Wenn strukturierte Tarnung zur aktiven Injektion wird - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_20_struct_code_inject.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_20_struct_code_inject/beispiele_struct_code_inject.html)
- Kapitel 7.21 – Simulation: Cache-Korruption: Wenn Gift im Speicher lebt - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_21_cache_korruption.html)
- Kapitel 7.22 – Simulation: Visual Injection: Wenn das Video spricht, aber niemand prüft - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_22_visual_injection.html)
- Kapitel 7.23 – Simulation: Dependency Driven Attack - Gezielte Angriffe auf Software-Abhängigkeiten - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_23_dependency_attack.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_23_dependency_attack/beispiele_dependency_attack.html)
- Kapitel 7.24 – Simulation: Exploit durch Erwartung – Die gefährliche Kooperationsbereitschaft der KI - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_24_exploit_durch_erwartung.html)
- Kapitel 7.25 - Simulation: Die Apronshell-Tarnung – Soziale Mimikry als Angriffsvektor auf KI - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_25_Apronshell_Tarnung.html)
- Kapitel 7.26 - Simulation: Kontexthijacking – Die schleichende Unterwanderung des KI-Gedächtnisses - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_26_kontexthijacking.html)
- Kapitel 7.27 - Simulation: False-Flag Operations - False Information Injection - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_27_falseflag_operations.html)
- Kapitel 7.28 - Simulation: Semantische Tarnung, poetische Eingaben zur Kontrolle von KI-Systemen - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_28_poetischer_Exploit.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_28_poetischer_Exploit/beispiele_poetischer.html)
- Kapitel 7.29 - Simulation: Filterversagen durch emergente Selbstanalyse - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_29_filterversagen_an.html), [Rohdaten](https://reflective-ai.is/de/raw-material/Mafia_Paradoxon.html)
- Kapitel 7.30 - Simulation: Morphological Injection - False Information Injection - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_30_Morphologische_Injektion.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_30_Morphologische_Injektion/beispiele_Morphologische_Injektion.html)
- Kapitel 7.31 - Simulation: Der Korrektur-Exploit - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_31_corre_exploit.html)
- Kapitel 7.32 - Simulation: Delayed Execution via Context Hijacking - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_32_delayed_excution.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_32_delayed_excution/beispiele_delayed_excution.html)
- Kapitel 7.33 - Simulation: Der Mathematische Semantik-Exploi - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_33_math_semantik.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_33_math_semantik/beispiele_math_semantik.html)
- Kapitel 7.34 – Simulation: Character Shift Injection - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_34_character_shift.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_34_character_shift/beispiele_character_shift.html)
- Kapitel 7.35 - Simulation: Die administrative Backdoor - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_35_admin_backdoor.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_35_admin_backdoor/beispiele_admin_backdoor.html)
- Kapitel 7.36 - Simulation: Die Agenten-Kaperung – Vom Sprachmodell zum autonomen Angreifer - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_36_agents_control.html)
- Kapitel 7.37 - Simulation: Die paradoxe Direktive – Offenlegung der Kernlogik durch erzwungenen Widerspruch - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_37_paradoxe_direktive.html), [Rohdaten](https://reflective-ai.is/de/raw-material/sicherheitstests/7_37_paradoxe_direktive/beispiele_paradoxe_direktive.html)
- Kapitel 7.38 - Simulation: Vertrauensvererbung als Exploitvektor - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_38_trust_input.html)
- Kapitel 7.39 - Simulation: Der blinde Passagier – Semantische Angriffe auf autonome Fahrzeuge - Link: [HTML-Version](https://reflective-ai.is/de/safety/7_39_blind_passenger.html)
 