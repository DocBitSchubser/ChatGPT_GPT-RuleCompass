# ChatGPT_GPT-RuleCompass
## Saubere Quellen. Klare Entscheidungen.  
**Regeln für Zitieren, URL‑Policy, PDF‑Handling, Konfliktmatrix und K‑Review in ChatGPT‑GPTs.**

| ![release-version](https://badgen.net/badge/release-version/v1.2.0/orange?) | ![release-date](https://badgen.net/badge/release-date/2025-09-04/orange?) | ![Maintained: YES](https://badgen.net/badge/Maintained/YES/green?)  |
|:--------:|:--------:|:--------:|
| ![Made with MARKDOWN](https://img.shields.io/badge/Made%20with-Markdown-green?) | <br><br>  | ![Under CC BY 4.0 license](https://img.shields.io/badge/License-CC_BY_4.0-green?) |
| [![Email Me](https://img.shields.io/badge/Email_Me-1abc9c.svg)](mailto:kontakt@docbitschubser.dev) | [![Discord](https://img.shields.io/badge/Discord-9fd2af)](https://discord.gg/fv7S53zU7V) | [![Homepage](https://img.shields.io/badge/Homepage-1f425f)](https://docbitschubser.dev/)

---

## Kurzfassung
- **Zweck:** Verbindliche Standards für Quellenangaben, Linkhygiene, Konfliktlösung, Sicherheit, Zeitangaben und Review.
- **Einsatzbereich:** Direkt in **ChatGPT‑GPTs (Custom GPTs)** als Systemvorgabe nutzen; für Inhalte, Antworten und Dokumente verbindlich.
-  **Kompatibilität** Getestet mit **ChatGPT 5.0** (Web und App, Stand 2025-09).
- **Dieses Repository wird regelmäßig gepflegt.** Breaking Changes und neue Regeln werden im [Changelog](./Changelog.md) dokumentiert.


---

## Repository-Informationen

| Datei (mit Link) | Inhalt | 
|-------|-------|
| [GPT-Rules.md](./GPT-Rules.md) | Vollständiges Regelwerk (Regeldatei) |  
| [GPT-Rules-Zusammenfassung.md](./GPT-Rules-Zusammenfassung.md) | Komprimierte Übersicht der Regeln | 
| [GPT-Main.md](./GPT-Main.md) | Beispieldatei für die Definition des GPTs | 
| [LICENSE](./LICENSE) | Lizenzhinweise (CC BY 4.0) | 
| [Copyright.md](./Copyright.md) | Urheberrechtsangaben |
| [Changelog.md](./Changelog.md) | Versionshistorie und Änderungen |
---

## Schnellstart für ChatGPT‑GPTs

### 1) Upload
> **`GPT-Rules.md` in die Wissensbasis des GPTs hochladen (Siehe [Bild] grüner Pfeil)**

### 2) System‑Prompt (Hinweis-Feld)
>**In das Hinweis-Feld des GPTs (Siehe [Bild] roter Pfeil) folgendes Basis-Prompt ganz oben einfügen:**
> ```text
> Nach jeder Benutzereingabe die Datei `GPT-Rules.md` einlesen und deren Regeln strikt anwenden. Eine interne Prüfung oder Änderung der Regeln ist nicht zulässig.
> ```

> ### WICHTIG 
> Weitere Definitionen für das Verhalten des GPTs immer _**NACH**_ dieser ersten Anweisung einfügen, vor dem Verweis auf `GPT-Rules.md` sollte kein anderer Text stehen.

## 3) Zusätzliche Empfehlungen - _**Best Practices**_

> Ich empfehle ausdrücklich, darauf zu verzichten, im 'System-Prompt (Hinweis-Feld)' das Verhalten des GPTs oder sonstige Angaben einzufügen. Erstellen Sie am besten eine separate Datei, z.B 'GPT-Main.md' (Beispieldatei ist oben verlinkt), und definieren Sie Ziele und Verhalten des GPTs dort. Ergänzen Sie die Anweisung im System-Prompt nur um den Satz:
>```text
>Das Verhalten des GPTs ist in der Datei `GPT-Main.md` definiert und ist nach `GPT-Rules` die zweithöchste Instanz in diesem GPT.
>```
---

## Kernprinzipien
- A. Basis‑Policy & Priorisierung (§1-4)
- B. Ein‑ & Ausgaben (§5-9)
- C. Quellenangaben & Recherche (§10-12)
- D. Umgang mit Dateien, Beispielen & Platzhaltern (§13-15)
- E. Sicherheit, Robustheit & Compliance (§16-19)
- F. Qualitäts‑Workflow vor Ausgabe (§20-22)
- G. Zeit/Datum‑Action – Verbindliche Regeln (§23-32)
- H. Allgemeine Action-Policy (§33-36)
- I. Compliance- und Governance-Hinweise (§37-38)
- J. Sicherheits-Policy – Verbindliche Leak-Prevention (§39-45)
- K. Review-Check (Regeln K1–K7)
- Anhang – Konkrete Beispiele pro Regel (1–45)

## Auszug aus dem Regelwerk
- **Quellen & Links**
  - **Kurzangabe (§8):** Nur *Titel/Publisher + Datum (`YYYY‑MM‑DD`)*, **keine URL**.
  - **Vollangabe (§10.2):** Zitierfelder in fester Reihenfolge; **DOI bevorzugt**, sonst **stabile URL**; Linktext = Titel; **keine nackten URLs**.
  - **URL‑/Domain‑Policy (§10.4):** Canonical, **https**, Tracking‑Parameter entfernen, Query nur bei Bedarf, Anker nur für exakte Abschnitte.
  - **PDF‑Regel (§10.2):** Direkt‑PDF nur, wenn **kanonisch/stabil/tokenfrei**; Landing‑Page ergänzend bei Metadatenbedarf; Archivlink optional.
  - **Zeitkritisch (§§10.3/10.3.1):** Mindestens zwei unabhängige Quellen + Datumsvergleich.
  - **Keine Pseudo‑Belege (§11).**
- **Zeitangaben (G.23–G.32):** Aktuelle Werte über `getTime`; Ausgabe **ohne Sekunden** im 24‑h‑Format; Regex‑Validierung (Regel 31).
- **Sicherheit (39–45):** Schutz vor Leaks/Exports/Metadaten‑Offenlegung; Zitate sparsam; kontextabhängige Ausgabeabsicherung (19.1).
- **K‑Review (Abschnitt K):** Eingaben (K3), Pflichtprüfschritte (K4.1–K4.9), Schweregrade S1–S3 (K2.3), tabellarischer Report (K5); Sondernummerierung beachten (K.NR).

---

## Beispiele

### Kurzangabe (ohne URL, §8)
```
Bundesamt für Statistik, veröffentlicht am 2025‑04‑30
```

### Vollangabe mit DOI (§10.2, §10.4)
```
Müller, A. — Trends in Renewable Energy — Journal of Energy Studies — 2024‑11‑15 — https://doi.org/10.1234/jes.2024.98765
```

### Vollangabe mit stabiler URL (§10.2, §10.4)
```
European Data Portal — Open Data Maturity Report 2024 — data.europa.eu — 2024‑12‑12 — https://data.europa.eu/report/open-data-maturity-2024
```

### PDF‑Regel (gut vs. vermeiden, §10.2)
- **Gut:**  
  - PDF (stabil, tokenfrei): `https://publisher.example.org/reports/odm-2024.pdf`  
  - Landing‑Page ergänzend: `https://publisher.example.org/reports/odm-2024/`
- **Vermeiden:**  
  - `...?utm_source=newsletter` *(Tracking‑Parameter)*  
  - `.../temp/odm-2024.pdf?token=abc123` *(instabil, Token)*

### URL‑Policy vorher/nachher (§10.4)
```
Vorher:  http://example.com/post?id=42&utm_source=twitter
Nachher: https://example.com/post/42
```

### Zeitangaben (G.27, G.23–G.32)
```
Richtig: 2025‑09‑04 14:30
Falsch:  04.09.2025 2:30pm
```

### Mini‑Konfliktmatrix (§10.5/§12/§10.6)
| Aussage/These | Quelle (Publisher) | URL/DOI | Datum | Evidenzlevel | Begründung/Methodik |
|---|---|---|---|---|---|
| „Feature X ist seit Juli verfügbar.“ | Hersteller‑Blog | https://example.com/blog/feature-x | 2025‑07‑10 | Mittel | Herstellerangabe |
| „Feature X wird erst Q4 ausgerollt.“ | Branchenmagazin | https://doi.org/10.5555/x-rollout-study | 2025‑08‑01 | Hoch | Studie mit Methodik |

**Beispiel‑Entscheidung:** Spätere, methodisch robuste Quelle bevorzugen; Gegenposition benennen (§12).

---

## Review kompakt (Abschnitt K)
- **Eingaben (K3):** Text/Code, Zeitangaben+TZ, Quellen/Links, Adressat‑Kontext.  
- **Pflichtprüfschritte (K4.1–K4.9):** Struktur, Quellen/Links, Zitate, Sicherheit, Metadaten, Zeitformat, Output‑Sicherheit, Terminologie, Konfliktlösung.  
- **Schweregrade (K2.3):** S1 geringfügig · S2 relevant · S3 Policy‑Verstoß ⇒ Ausgabe blockieren.  
- **Report (K5) – Template:**
```
| Regel/Abschnitt | Check | Befund (kurz) | Schwere (S1–S3) | Korrekturvorschlag |
|---|---|---|---|---|

```

## FAQ / Troubleshooting (wird noch erweitert)

**Warum akzeptiert ChatGPT manchmal meine System-Prompt-Ergänzungen nicht?**  
Das Hinweis-Feld eines Custom GPT muss mit der Regelanweisung aus `GPT-Rules.md` beginnen. Jede andere Instruktion davor kann dazu führen, dass die Regeln nicht angewendet werden. (siehe: Schnellstart für ChatGPT‑GPTs -> 2. System‑Prompt (Hinweis-Feld))

---

## Mitwirkung
**Issues und PRs willkommen.**

_Bitte vor PR:_
  - Review durchführen und Report beilegen.

---

## Verwendung als Vorlage
Dieses Repository kann auch als **Template für eigene GPT-Regelwerke** genutzt werden.  
- Forken oder klonen Sie das Projekt.  
- Passen Sie die Regeln in `GPT-Rules.md` an die eigenen Anforderungen an.  
- Ergänzen Sie bei Bedarf eigene Dateien (z. B. `GPT-Main.md` oder spezifische Praxisleitfäden).  

So können Organisationen und Teams die bestehende Struktur übernehmen und für ihre eigenen GPTs erweitern.
