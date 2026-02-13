# ADR 001: Auswahl von n8n als Low-Code-Alternative

**Status:** Akzeptiert  
**Beteiligte:** Amy Klein, Dennis Simutin, Felix Schöck

## Kontext

Das Ziel des Projekts war die Umsetzung eines Agenten-Prototyps in verschiedenen Frameworks, um eine fundierte Vergleichsbasis für die Agentic AI Evaluation zu schaffen. Während die Frameworks **Google ADK** und **LangGraph** (via LangChain) als SDK-basierte, Code-zentrierte Werkzeuge fest vorgegeben waren, fehlte eine Perspektive, die sich grundlegend von der klassischen Softwareentwicklung abgrenzt.

## Entscheidung

Wir haben uns entschieden, denselben Prototyp zusätzlich in **n8n** umzusetzen. Diese Wahl dient dazu, eine alternative, Workflow-orientierte Herangehensweise im direkten Vergleich zu den code-lastigen SDKs zu evaluieren.

## Begründung

Die Wahl von n8n zur gezielten Abgrenzung von Google ADK und LangGraph basiert auf folgenden Faktoren:

- **Paradigmenwechsel**: n8n verfolgt einen visuellen Workflow-Ansatz, während die anderen Frameworks auf klassischer Programmierung (z. B. NestJS oder FastAPI) basieren.
- **Vorgefertigte Abstraktion**: n8n bietet native App-Integrationen und vorgefertigte Workflows, was die Implementierung beschleunigt und die technische Hürde für Drittsystem-Anbindungen senkt.
- **Einfachheit (Easy to Learn)**: Das Framework grenzt sich durch eine flachere Lernkurve ab, was einen Vergleich der Wartbarkeit und Zugänglichkeit ermöglicht.
- **Spezifische Stärken**: Im Vergleich der drei Frameworks zeigt n8n deutliche Vorteile bei der schnellen Orchestrierung von Prozessen, während Google ADK die stabilste Gemini-Anbindung und LangGraph die komplexeste Agenten-Logik bietet.

## Konsequenzen

- **Vergleichbarkeit**: Durch die dreifache Umsetzung desselben Prototyps konnten Unterschiede in der Entwicklungserfahrung (Developer Experience) direkt gemessen werden.
- **Architektonische Erkenntnis**: Die Abgrenzung verdeutlichte, dass n8n besonders stark in der Prozess-Automatisierung ist, jedoch bei der Tiefe der Agenten-Logik und den Debugging-Möglichkeiten (limitierte Logs) gegenüber den SDKs zurücksteht.
- **Methodik**: Es wurde bestätigt, dass je nach Anwendungsfall ein strukturierter Workflow (wie in n8n) sinnvoller sein kann als ein freier Chat.
