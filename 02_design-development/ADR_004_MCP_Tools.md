# ADR 004: Verzicht auf MCP-Tools in der finalen Architektur

**Status:** Abgelehnt
**Beteiligte:** Amy Klein, Dennis Simutin, Felix Schöck

## Kontext

Es wurde geprüft, ob MCP-Tools (z. B. Context7, GitHub MCP, Vercel Grep) als Werkzeuge für den Recommendation Agent eingesetzt werden können. Ziel war es, den Agenten durch den Zugriff auf aktuelle Dokumentationen technischer Frameworks bei Architekturentscheidungen zu unterstützen.

## Entscheidung

Wir haben uns gegen die dauerhafte Einbindung von MCP-Tools in die Kernarchitektur des Agenten entschieden.

## Begründung

Die Evaluation der MCP-Server ergab folgende Hindernisse:

- **Technischer Fokus**: Die getesteten Tools haben einen stark technischen Charakter und eignen sich kaum für High-Level-Architekturentscheidungen.
- **Modell-Kompatibilität**: Das primär genutzte Modell (Gemini 3) zeigte erhebliche Schwierigkeiten beim zuverlässigen Aufrufen der MCP-Server.
- **Effizienz**: Trotz einer deutlich längeren Durchlaufzeit lieferten die Agenten mit MCP-Anbindung keine qualitativ besseren Ergebnisse.
- **Prompting-Komplexität**: Die präzise Ansteuerung der MCP-Tools erwies sich als Herausforderung und erforderte sehr spezifische Fragestellungen, was die Nutzerfreundlichkeit einschränkt.
- **Latenz**: Die zusätzliche Komplexität erhöhte die Antwortzeit des Systems, ohne einen entsprechenden Mehrwert zu generieren.

## Konsequenzen

- **Vereinfachung der Architektur**: Durch den Verzicht auf externe MCP-Server bleibt die Systemumgebung schlanker und weniger fehleranfällig.
- **Fokus auf Modell-Intelligenz**: Die Architektur verlässt sich auf die internen Fähigkeiten aktueller LLMs, die auch ohne MCP-Tools korrekte Lösungen liefern können.
- **Reduzierte Latenz**: Die Antwortzeiten bleiben stabil, da keine zusätzlichen externen Tool-Aufrufe orchestriert werden müssen.
