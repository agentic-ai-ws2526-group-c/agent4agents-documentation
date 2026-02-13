# ADR 002: Qualitätssicherung durch „LLM as a Judge“

**Status:** Akzeptiert  
**Beteiligte:** Amy Klein, Dennis Simutin, Felix Schöck

## Kontext

Um die Qualität der Agenten-Antworten objektiv und automatisiert zu bewerten, wurde eine Methode benötigt, die über einfache Ja/Nein-Kategorisierungen hinausgeht. Da rein quantitative Metriken die Nuancen technischer Empfehlungen oft nicht vollständig erfassen, wurde eine Architektur benötigt, die Ergebnisse inhaltlich kritisch hinterfragt.

## Entscheidung

Wir haben uns für die Implementierung einer **„LLM as a Judge“**-Architektur (auch „Critic Agent“ genannt) entschieden. Dabei bewertet ein unabhängiger Agent die Ausgaben des primären Agenten anhand definierter Kriterien direkt innerhalb des Workflows.

## Begründung

Die Wahl dieser Methode basiert auf folgenden Erkenntnissen:

- **Sichtbarkeit von Lücken**: Ein eigener Critic-Agent macht Lücken im Systemprompt des Hauptagenten durch gezieltes Feedback schnell sichtbar.
- **Vielseitigkeit**: Durch einen eigenen Systemprompt kann der Judge verschiedene Kriterien wie Kompatibilität, Form und Schlüssigkeit gleichzeitig berücksichtigen.
- **Feedback-Loop**: Der Judge kann eine erneute Überprüfung durch den Hauptagenten auslösen, falls das Ergebnis nicht den Anforderungen entspricht.
- **Strukturierte Kritik**: Die Methode liefert wertvolles qualitatives Feedback zu Verhaltensauffälligkeiten und zur Tool-Nutzung der KI.

## Konsequenzen

- **Ressourcenverbrauch**: Der Einsatz führt zu einem deutlich erhöhten Token-Verbrauch und einer spürbar längeren Laufzeit des Gesamtsystems.
- **Wissensobergrenze**: Der Judge-Agent kann nur die Schlüssigkeit und Form zuverlässig bewerten; er sollte inhaltlich nicht mehr Fachwissen besitzen als der zu bewertende Agent, um Fehlurteile zu vermeiden.
- **Validierung**: Ergebnisse des Richters können selbst fehlerhaft sein, weshalb sie primär als Unterstützung für die qualitative Analyse dienen.
- **Prozess-Integration**: Der Workflow muss so gestaltet werden, dass er entweder sequenziell oder iterativ auf die Kritik des Richters reagieren kann.
