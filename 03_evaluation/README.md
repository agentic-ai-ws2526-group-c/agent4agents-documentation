# Evaluation Agentic AI Prototyp

Dieser Ordner dokumentiert die quantitative Evaluation des Agent4Agent Prototyps. Zur Bewertung wurden UseCases erstellt welche anhand eines Evaluationsbaumes einem Framework zugeordnet wurden. Die Einordnung wurde im Anschluss mit den Ergebnissen des Agenten verglichen und quantifiziert. Im Folgenden werden die einzelnen Schritte genauer erläutert.

## 1. Methodik & Evaluationsbaum
Die Zuordnung der Use Cases zu den passenden Frameworks erfolgt über einen eigens entwickelten **Evaluationsbaum**. Dieser ordnet die einzelnen UseCases nach dem Ausschlussprinzip einem Framework zu.

* **KISS-Prinzip:** Um Overengineering zu vermeiden, wird durch den Baum stets die einfachste Architektur gewählt, die die gestellten Anforderungen noch vollumfänglich erfüllt.
* **Entscheidungslogik:** Komplexe Multi-Agenten-Systeme werden erst dann in Betracht gezogen, wenn einfachere, deterministische Ansätze für das Ziel unzureichend sind.

<img width="2750" height="887" alt="image" src="https://github.com/user-attachments/assets/0c1bc717-e18a-4eef-a415-ff85d00bb7e2" />


## Datengrundlage: Das Golden Dataset
Um die Frameworkauswahl der Agenten Prototypen messbar zu machen, wurde ein Referenzdatensatz erstellt:

1. **User-Simulation:** Jedes Teammitglied formulierte Use Cases, um reale Anfragen aus verschiedenen Fachabteilungen abzubilden.

2. **Manuelle Konsolidierung:** Diese Szenarien wurden gesammelt und manuell durch den (KISS-orientierten) Evaluationsbaum geführt.

3. **Ground Truth:** Die resultierende Liste stellt unser Golden Dataset dar. Es definiert für jeden Use Case das ideale Framework als Vergleichswert für die quantitative Evaluation.

### Struktur der Use-Case-Tabelle
Jeder der 17 Use Cases wird anhand der folgenden Kriterien dokumentiert:

| Spaltenname | Beschreibung |
| :--- | :--- |
| **use_case_description** | Detaillierte Beschreibung des Szenarios und der Aufgabe. |
| **preferred_model_ecosystem** | Bevorzugte Modell-Umgebung (z. B. OpenAI, Anthropic, keine Präferenz). |
| **interaction_channel** | Schnittstelle zum Nutzer (Dashboard / UI, Hintergrundprozess / Automatisierung, Chatbot / Konversation, Anderer Kanal). |
| **integration_targets** | Zielsysteme für die Agenten-Aktionen (z. B. Sharepoint, Confluence, Jira, Outlook). |
| **Empfehlung** | Das durch den Evaluationsbaum ermittelte Ziel-Framework (Ground Truth). |
| **Begründung** | Herleitung der Entscheidung basierend auf dem Evaluationsbaum. |

## 3. Quantitative Evaluation & Validierung
Der Prototyp nutzt das Golden Dataset, ließt die Daten der UseCases ein und bewertet sie. Im Anschluss werden die Ergebnisse in das Google Sheet geschrieben und dort ausgewertet (siehe n8n Prototyp).

### Metriken & LLM-as-a-Judge

1.  **Categorization (0/1):** Eine binäre Zuordnung, ob das vom System gewählte Framework mit der Empfehlung im Golden Dataset übereinstimmt (0 = nicht getroffen, 1 = getroffen).
2.  **Qualitative Bewertung (1-10):** Eine tiefgehende Analyse durch ein LLM as a Judge, welcher die Eignung des Use Cases sowie die Stichhaltigkeit der Agenten-Begründung auf einer Skala von 1 bis 10 bewertet.
  

---

## Begleitende Unterlagen
* `UseCases.xlsx`: Enthält das Golden Dataset mit den 17 Use Cases.
* `agent_eval_n8n.xlsx`: Testdurchläufe mit dem n8n Prototypen.
