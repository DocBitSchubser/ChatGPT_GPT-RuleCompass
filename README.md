# ChatGPT_GPT-RuleCompass
**Saubere Quellen. Klare Entscheidungen.**  
*Regeln für Zitieren, URL‑Policy, PDF‑Handling, Konfliktmatrix und K‑Review in ChatGPT‑GPTs.*

---

## Kurzfassung
- **Zweck:** Verbindliche Standards für Quellenangaben, Linkhygiene, Konfliktlösung, Sicherheit, Zeitangaben und Review.
- **Einsatzbereich:** Direkt in **ChatGPT‑GPTs (Custom GPTs)** als Systemvorgabe nutzen; für Inhalte, Antworten und Dokumente verbindlich.
- **Dateien:**  
  - `01-GPT-Rules.md` – vollständiges Regelwerk  
  - `01-GPT-Rules-Zusammenfassung.md` – komprimierte Übersicht
- **Kernprinzipien:** Kurzangabe (§8) vs. Vollangabe (§10.2), URL-/Domain‑Policy (§10.4), PDF‑Regel (§10.2), Konfliktmatrix & Evidenz (§§10.5/10.6), Entscheidung (§12), Zeitangaben (G.23–G.32), Sicherheitsregeln (39–45), K‑Review (Abschnitt K).

---

## Inhalte (aus dem Regelwerk)
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

## Schnellstart für ChatGPT‑GPTs

### 1) System‑Prompt (Kern)
> **Befolge strikt „01‑GPT‑Rules.md“.** Quellen/Links gemäß **§§8–12** inkl. **§10.4**; Zeitangaben nach **G.23–G.32** (keine Sekunden, `getTime` für aktuelle Werte); Sicherheit **(39–45)**; vor Abgabe **K‑Review** (Abschnitt **K**). Bei Unklarheiten **nachfragen statt raten** (Regel 3).

### 2) Arbeitsablauf
1. **Recherchieren:** Kurzangaben notieren; zeitkritische Themen erkennen; ggf. zweite Quelle suchen.  
2. **Belegen:** Vollangaben erstellen; **URL‑Policy** & **PDF‑Regel** prüfen.  
3. **Schreiben:** Linktexte = Titel; **keine nackten URLs** im Fließtext.  
4. **Konflikte klären:** **Konfliktmatrix** anlegen; Evidenzlevel angeben; Entscheidung begründen.  
5. **K‑Review:** K4.1–K4.9 prüfen; Befunde S1–S3 dokumentieren; Korrekturen einpflegen.

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

## K‑Review kompakt (Abschnitt K)
- **Eingaben (K3):** Text/Code, Zeitangaben+TZ, Quellen/Links, Adressat‑Kontext.  
- **Pflichtprüfschritte (K4.1–K4.9):** Struktur, Quellen/Links, Zitate, Sicherheit, Metadaten, Zeitformat, Output‑Sicherheit, Terminologie, Konfliktlösung.  
- **Schweregrade (K2.3):** S1 geringfügig · S2 relevant · S3 Policy‑Verstoß ⇒ Ausgabe blockieren.  
- **Report (K5) – Template:**
```
| Regel/Abschnitt | Check | Befund (kurz) | Schwere (S1–S3) | Korrekturvorschlag |
|---|---|---|---|---|
```

---

## Dateien
- [`01-GPT-Rules.md`](./01-GPT-Rules.md) – vollständiges Regelwerk  
- [`01-GPT-Rules-Zusammenfassung.md`](./01-GPT-Rules-Zusammenfassung.md) – kompakte Übersicht

> **Stand/Version:** siehe Kopf von `01-GPT-Rules.md` (Änderungsvermerk).

---

## Mitwirkung
- Issues/PRs willkommen. Bitte vor PR:
  - K‑Review durchführen und Report beilegen.
  - Quellen/Links gemäß §§8–12/§10.4 prüfen; PDF‑Regel beachten.
  - Zeitkritische Aussagen mit ≥2 Quellen belegen (§§10.3/10.3.1).

