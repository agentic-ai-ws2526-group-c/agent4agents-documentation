# ADR 005: Iterative Prompt-Entwicklung und Nutzung eines Golden Data Sets

**Status:** Akzeptiert  
**Beteiligte:** Amy Klein, Dennis Simutin, Felix Schöck

## Kontext

Die Qualität der Agenten-Antworten hängt maßgeblich von der Präzision der Systemprompts ab. Da statische Prompts oft nicht alle Use Cases abdecken oder zu Fehlern bei unterschiedlichen LLM-Modellen führen können, wurde eine systematische Methode zur Optimierung der Instruktionen benötigt.

## Entscheidung

Wir haben uns für eine **iterative Prompting-Methodik** entschieden. Die Prompts werden kontinuierlich auf Basis der Evaluationsergebnisse überarbeitet und gegen ein großes, fest definiertes **Golden Data Set** (Testdaten mit Ideallösungen) validiert.

## Begründung

Die Wahl dieser Methodik basiert auf folgenden Erkenntnissen:

- **Vermeidung von Overfitting**: Durch das Testen gegen eine breite Masse an Use Cases (Golden Data Set) wird verhindert, dass der Prompt nur für einen spezifischen Fall optimiert wird und in anderen Szenarien schlechter performt.
- **Strukturierter Output**: Die Nutzung spezifischer Frameworks (z. B. Persona, Objective, Method) im Prompt sichert die Einhaltung technischer Formate und der gewünschten Entscheidungslogik.
- **Modell-Sensitivität**: Da die Modellauswahl großen Einfluss auf das Ergebnis hat, erlaubt das iterative Vorgehen eine Feinabstimmung, die auch mit kleineren oder älteren Modellen stabilere Ergebnisse liefert.
- **Deterministik**: Die methodische Prüfung stellt sicher, dass der Agent bei gleichem Input konsistente Empfehlungen ausspricht.

## Konsequenzen

- **Hoher Initialaufwand**: Das Erstellen und Pflegen eines qualitativ hochwertigen Golden Data Sets erfordert zu Beginn der Entwicklung einen hohen manuellen Aufwand.
- **Kontinuierliche Wartung**: Systemprompts müssen regelmäßig auf Aktualität geprüft werden, insbesondere wenn neue Modelle oder Framework-Versionen eingeführt werden.
- **Qualitätssicherung**: Die Methodik ermöglicht eine objektive quantitative und qualitative Analyse der Agenten-Leistung über den gesamten Projektverlauf hinweg.
