# ADR 003: Verzicht auf Document Scanning (Markdown-Kontext)

**Status:** Abgelehnt
**Beteiligte:** Amy Klein, Dennis Simutin, Felix Schöck

## Kontext

Um die Antwortqualität der Agenten zu erhöhen und Halluzinationen zu verringern, wurde die Option geprüft, Framework-Dokumentationen in Markdown zu konvertieren und den Agenten als direkten Kontext ("Document Scanning") zur Verfügung zu stellen. Dies sollte sicherstellen, dass die Agenten Zugriff auf aktuelle technische Details haben.

## Entscheidung

Wir haben uns gegen die Implementierung von Document Scanning als Standardkomponente der Architektur entschieden.

## Begründung

Trotz der theoretischen Vorteile überwogen in der praktischen Evaluation die negativen Faktoren:

- **Token-Effizienz**: Das Einlesen der Dokumentationen führt zu einem massiv erhöhten Token-Verbrauch.
- **Performance**: Die Laufzeit der Agenten-Anfragen verlängert sich deutlich.
- **Quellen-Fokus**: Agenten neigten dazu, sich zu stark auf das Zitieren der Quellen zu konzentrieren, anstatt die eigentliche Aufgabe effizient zu lösen.
- **Skalierbarkeit**: Es kann nur eine limitierte Anzahl an Dokumenten/Texten gleichzeitig verarbeitet werden.
- **Modell-Fähigkeit**: Es wurde festgestellt, dass aktuelle, große Modelle auch ohne zusätzliche Tools oft bereits richtige und aktuelle Lösungen liefern.

## Konsequenzen

- **Modell-Abhängigkeit**: Die Architektur verlässt sich stärker auf das interne Wissen und die Aktualität der gewählten LLM-Modelle.
- **Ressourcenschonung**: Die Systemlatenz und die Betriebskosten bleiben durch den geringeren Token-Durchsatz niedriger.
- **Fokus auf Prompting**: Statt externer Dokumente wird die Qualität primär durch iteratives Refinement der Systemprompts sichergestellt.
