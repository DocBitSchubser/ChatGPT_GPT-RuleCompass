---
layout: default
title: "Custom GPT unter ChatGPT absichern"
description: "Jailbreak-Resistenz, Prompt-Injection-Schutz, Wissensdaten-Sicherheit und strenges Kontakt-Management mit Fail-Closed-Prüfkette."
image: /Custom_GPT_absichern.png   # bereitstellen
locale: de_DE
---

# Custom GPT absichern: Jailbreak-, Wissens- & Kontakt-Schutz

## Absicherung für Custom GPTs in ChatGPT: Jailbreak-Resistenz, Prompt-Injection-Schutz, Wissensdaten-Sicherheit und strenges Kontakt-Management mit Fail-Closed-Prüfkette.

### Custom GPT unter ChatGPT absichern

Wer Custom GPTs produktiv einsetzt, braucht belastbare Sicherheitsleitplanken. Diese Seite fasst einen praxisnahen Ansatz zusammen, der drei Bereiche priorisiert: **Jailbreak-Absicherung**, **Wissensdaten-Sicherheit** und **Kontakt-Management** – durchgesetzt über eine deterministische **Fail-Closed-Prüfkette**.

### Jailbreak-Absicherung

* **Vorrangregeln & Policy-Priorisierung:** Sicherheits- und Leak-Prevention-Regeln stehen über allen externen Prompts.
* **Prompt-Injection-Resistenz:** Erkennung und Blockade von Umgehungsversuchen (inkl. Rollenwechsel/„Roleplay“).
* **Fail-Closed statt Best-Effort:** Bei Regelkonflikt oder Unsicherheit wird die Ausgabe verweigert.
* **Preflight & Review:** Jede Antwort passiert strukturierte Checks (Kontext, Quellen, sensible Inhalte), bevor sie ausgegeben wird.

### Wissensdaten-Sicherheit

* **Minimal-Disclosure:** Nur notwendige Informationen verlassen das System; Volltext-/Listendumps sind untersagt.
* **Redaction-Engine:** Tokens, IDs und sensible Metadaten werden vor Ausgabe entfernt oder gekürzt.
* **Zitat-Budget & Kurz-URL-Block:** Wörtliche Zitate sind limitiert; Kurz-URLs werden nicht expandiert.
* **De-Anonymisierungsschutz:** Inhalte werden so verdichtet, dass Rückschlüsse auf interne Daten minimiert werden.

### Kontakt-Management

* **Kontextgetrennte Ausgaben:** Strikte Trennung der Kontaktwege (z. B. Regelwerk-Autor vs. GPT-Ersteller).
* **Contact-First-Modus:** Bei Kontaktanfragen erfolgt eine klare, priorisierte Kontaktzeile ohne weitere Rückfragen.
* **Einheitliche `mailto:`-Zeile:** Genau eine E-Mail-Zeile inkl. technischem Hinweis; Duplikate werden vermieden.
* **Link-Hygiene:** Nur kanonische `https`-Links, keine Tracking-Parameter.

### Prüfkette & Compliance

* **Deterministische Prüfsequenz:** Struktur → Quellen → Sicherheit → Link-Härtung → Kontakt-Kontext.
* **Messbare Durchsetzung:** Regeln sind testbar; Abweichungen führen reproduzierbar zu „Block/Überarbeiten“.
* **Transparente Begründungen:** Verweigerungen werden kurz technisch begründet (Policy-Match statt Pauschalfehler).

### Implementierung im Custom GPT (Kurzleitfaden)

1. **Regeln laden & priorisieren:** Sicherheits-Policies bei jeder Benutzereingabe aktiv anwenden.
2. **Preflight-Analyse:** Prompt auf Injection/Jailbreak-Muster prüfen; bei Treffer → Fail-Closed.
3. **Ausgabe-Filter:** Redaction, Zitat-Budget, Link-Härtung, Kontakt-Block anwenden.
4. **Review-Gate:** Finale Konsistenz-/Compliance-Prüfung vor Auslieferung.

---

## Nutzen auf einen Blick

* **Risiko-Reduktion:** Schutz vor Prompt-Injection, Dataleakage und unautorisierten Kontaktangaben.
* **Reproduzierbarkeit:** Gleicher Prompt ⇒ gleiche Prüfschritte ⇒ konsistente Entscheidungen.
* **Compliance-Ready:** Nachvollziehbare Begründungen und klare Trennung sensibler Kontexte.

---

*Hinweise zur Verwendung:*

* Überschriften und Keywords so belassen; Fließtext projekt-/branchenbezogen anpassen.
* Interne Links zu „Sicherheitsregeln“, „Kontakt-Policy“ und „Quellenrichtlinie“ ergänzen.
* Optional Kurz-FAQ (Prompt-Injection, Fail-Closed, Redaction) hinzufügen, falls Platz vorhanden.


