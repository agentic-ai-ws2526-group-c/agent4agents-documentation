# User Personas und Use Cases

---

## User Persona 1: Uwe Unerfahren

### Persona-Beschreibung

- Langjähriger Buchhalter bei Bosch
- Kennt Prozesse in und auswendig
- Technikunaffin
- Kennt sich überhaupt nicht mit Agentic AI aus

### User Ziele

- Er hätte gerne einen Agenten, der den Prozess kennt und bei Fragen unterstützen kann
- Er hätte gerne einen Agenten, der Rechnungen liest, auf Fehler überprüft, eine Zusammenfassung der Positionen schreibt und in eine Excel Liste in Sharepoint einträgt

### Workflows

#### Workflow: Einfacher Anwendungsfall (RAG)

Dieser Workflow beschreibt, wie "Agent4Agent" Uwe bei einem einfachen Problem unterstützt, das mit einem RAG-Ansatz (Retrieval-Augmented Generation) gelöst werden kann.

```mermaid
graph TD
    A[Uwe öffnet Agent4Agent in einer Webapplikation] --> B[Agent4Agents begrüßt uwe und erklärt funktionalität];
    B -- ""Beim 1. Mal und nach 2 Wochen"" --> C{Agent erkennt Kenntnisstand von Uwe anhand einiger Fragen und speichert das ab};
    C --> D[Uwe erklärt sein Problem];
    B --> D;
    D --> E[Agent erkennt dass einfacher RAG Ansatz am besten funktioniert];
    E --- F(Würde auch erkennen, wenn Agentic AI nicht nötig ist);
    E --> G[Agent fordert PDF und erstellt direkt RAG Agent bei DIA Brain];
    G --> H[Agent empfiehlt einfachste Plattform um RAG zu nutzen. Und verwendet dabei keine Fachbegriffe];
    H --> I[Agent bietet an, Uwe bei der Erstellung zu unterstützen];
    I --> J[Uwe nimmt die Hilfe an und erstellt einen Agent, dabei kann er immer wieder Rückfragen stellen];
    style F fill:#FFDDFD
```

#### Workflow: Komplexer Anwendungsfall (Ticket-Erstellung)

Dieser Workflow zeigt, wie "Agent4Agent" Uwe hilft, wenn ein komplexes Problem erkannt wird, das professionelle Unterstützung erfordert.

```mermaid
graph TD
    A[Uwe öffnet Agent4Agent in einer Webapplikation] --> B[Agent4Agents begrüßt uwe und erklärt funktionalität];
    B -- ""Beim 1. Mal und nach 2 Wochen"" --> C{Agent erkennt Kenntnisstand von Uwe anhand einiger Fragen und speichert das ab};
    C --> D[Uwe erklärt sein Problem];
    B --> D;
    D --> E[Agent erkennt dass ein Komplexer Ansatz von Nöten ist];
    E --- F(Würde auch erkennen, wenn Agentic AI nicht nötig ist);
    E --> G[Agent empfiehlt ein Ticket zu erstellen um den Agent von einem Professionellen Team erstellen zu lassen];
    G --> H[Agent stellt rückfragen zu genauen Anforderungen];
    H --> I[Agent schickt Ticket ab];
    I --> J[Uwe stellt nach einiger Zeit Fragen um den Stand des Tickets abzufragen];
    J --> K[Agent gibt Bescheid, wenn der angefragte Agent fertig ist];
    style F fill:#FFDDFD
```

---

## User Persona 2: Waltraud Workflow

### Persona-Beschreibung

- Wirtschaftsinformatikerin bei Bosch
- Kennt Prozesse in und auswendig
- Kennt sich ein bisschen mit NoCode/LowCode Tools aus und ein wenig technisches Know How
- Weiß, wie Anforderungen richtig Dokumentiert werden

### User Ziele

- Hat einen repetitiven Prozess in der beschaffungs Abteilung entdeckt
- Braucht einen Agenten, der automatisiert nach Angeboten im Internet recherchiert und in einer Tabelle in Sharepoint dokumentiert

### Workflow

Dieser Workflow beschreibt, wie "Agent4Agent" Waltraud bei der Erstellung eines Agenten mit komplexer Logik über eine NoCode-Plattform unterstützt.

```mermaid
graph TD
    A[Waltraud öffnet Agent4Agent in einer Webapplikation] --> B[Agent4Agents begrüßt Waltraud und erklärt funktionalität];
    B -- "Beim 1. Mal und nach 2 Wochen" --> C{Agent erkennt Kenntnisstand von Waltraud anhand einiger Fragen und speichert das ab};
    C --> D[Waltraud fordert dazu auf eine Technologieempfehlung auszusprechen und stellt eine genaue Prozessbeschreibung mit Anforderungen bereit];
    B --> D;
    D --> E[Agent erkennt, dass komplexe Agentenlogik von Nöten ist];
    E --> F[Agent empfiehlt NoCode Plattform. Und erklärt Waltraud die Agentenlogik adressatenbezogen];
    F --> G[Agent bietet an, Waltraud bei der Erstellung zu unterstützen];
    G --> H[Waltraud nimmt die Hilfe an und erstellt einen Agent, dabei kann sie immer wieder Rückfragen stellen];
```

---

## User Persona 3: Erik Entwickler

### Persona-Beschreibung

- Erfahrener Entwickler bei Bosch
- Kennt Probleme seiner Abteilung gut
- Kann Programmieren und hat überblick über Technologien
- Kennt nicht alle Agentic Frameworks im Detail

### User Ziele

- Erik hat aus seiner Abteilung einen UseCase bekommen, der mehrere miteinander interagierende Agenten benötigt
- **Systemanforderung:**
  - Ein System muss selbstständig den globalen Markt nach einer kritischen Komponente durchsuchen
  - Es analysiert parallel Tausende potenzielle Lieferanten anhand von Preis, Lieferzeit und komplexen Risikofaktoren (z.B. geopolitische Stabilität, Finanz-Compliance)
  - Das System führt autonom parallele Verhandlungen (Ausschreibungen) durch, um den Vertrag mit dem Lieferanten abzuschließen, der das optimale Preis-Risiko-Verhältnis bietet

### Workflow

Dieser Workflow zeigt, wie "Agent4Agent" Erik bei der Auswahl und Implementierung eines komplexen Multi-Agenten-Systems mit einem "Rich Code Framework" unterstützt.

```mermaid
graph TD
    A[Erik öffnet Agent4Agent in einer Webapplikation] --> B[Agent4Agents begrüßt Erik und erklärt funktionalität];
    B -- "Beim 1. Mal und nach 2 Wochen" --> C{Agent erkennt Kenntnisstand von Erik anhand einiger Fragen und speichert das ab};
    C --> D[Erik fordert dazu auf eine Technologieempfehlung auszusprechen und stellt eine genaue Prozessbeschreibung mit Anforderungen bereit];
    B --> D;
    D --> E[Agent erkennt, dass komplexe Agentenlogik von Nöten ist];
    E --> F[Agent empfiehlt Rich Code Framework. Und erklärt Erik die Agentenlogik adressatenbezogen];
    F --> G[Agent bietet an, Erik bei der Erstellung zu unterstützen];
    G --> H[Erik bittet um Links zur Dokumentation des Frameworks];
    H --> I[Agent liefert ihm die Links und steht für weitere Fragen zur Verfügung];
```
