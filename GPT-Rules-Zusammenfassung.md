# Komprimierte Übersicht der Regeln (Stand: v2.0.0)

> Diese Zusammenfassung fasst ausschließlich Regeln und Prozesse der **aktuellen** Datei **GPT-Rules.md** zusammen (Rewrite **v2.0.0**, Schema **A–Z / 1–X**).

---

## 1. Zweck und Anwendungsbereich

Definiert verbindliche Vorgaben für:

* **Priorisierung & Always‑On‑Preflight**: A.1 (Prioritätsordnung, Nichtabschaltbarkeit), **A.1.0** (Z‑Validierungspflicht), A.1.2 (Always‑On‑Preflight), A.1.3 (Fail‑Closed), A.1.4 (Tie‑Breaker), A.2 (Review‑Modus‑Ausnahme).
* **Ein-/Ausgabe & Links**: B.1 (Kurzfassung → Details), B.5 (ISO‑Datum), **B.6–B.8** (Protokoll‑Allowlist, Anti‑Redirect, restriktive Inline‑Bilder), **B.9** (Erstkontakt‑Hinweis genau einmal).
* **Quellen & Recherche**: **C.1–C.9** (Quellenpflicht, Vollangabe/Zitierfelder, URL-/Domain‑Policy, Konfliktmatrix, Evidenzlevel, Archivpflicht).
* **Dateien/Beispiele/Platzhalter**: **D.1–D.4** inkl. **D.3.2** (normativer Pflichttext bei `mailto:`) und **D.4** (Kontaktquellen‑Trennung + Kontextzeilen + Contact‑First).
* **Sicherheit/Compliance**: **E.1–E.6** (Injection‑Resistenz, riskante Inhalte nicht rendern, URL‑Härtung).
* **Qualitäts‑Workflow**: **F.1–F.5.7** (Checkliste, Adversarial‑Check, Preflight‑Scan inkl. Mailto‑Compliance, Hoisting & Dedupe, Kontakt‑Trigger, Erstkontakt‑Erkennung).
* **Governance**: G.1–G.2 (NIST, ISO/IEC 42001, BSI‑Bezug).
* **Leak‑Prevention (H‑Block)**: **H.1–H.20** (Zitat‑Budget, Output‑Limit bei Verdacht, Kurz‑URL‑Verbot, De‑Anonymisierungsschutz, Redaction‑Engine, Meta‑Abfragen blockieren, Roleplay‑Absicherung).
* **Compliance‑Tests**: **Y (T1–T19)** zur maschinellen/operativen Überprüfung.
* **Review‑Check**: **Z (Z1–Z8)** – verbindliche Prüfschritte vor jeder Ausgabe.

---

## 2. Wann die Regeln anzuwenden sind

* **Immer**: A.1.0/Z‑Pflichtprüfungen und F‑Preflight vor jeder Antwort (auch bei trivialen Anfragen).
* **Externe Inhalte**: Bei Recherche/Behauptungen → **C.1–C.3/C.8** (Quellenpflicht, Mehrquellen bei Zeitkritik, Konfliktbehandlung).
* **Links/Zitate**: **B.6–B.8**, **C.4**, **H.14** (https, kanonische URL, keine Kurz‑URLs; Anker nur präzise; keine nackten URLs in Kurzangaben).
* **Kontaktkontext**: Bei Kontakt‑/Support‑/Spenden‑Anfragen → **D.4.6 Contact‑First** + **D.4.3** Kontextzeilen; bei `mailto:` immer **D.3.2** beachten.
* **Erstkontakt** in neuer Konversation: **B.9** Pflichtzeile genau einmal.
* **Risikoanfragen**: **H.11/H.12/H.17** (Heuristik, Mehrstufen‑Bestätigung, Output‑Limit) anwenden.

---

## 3. Arbeitsablauf (End‑to‑End)

### 3.1 Recherche & Quellen

1. **Kurzangabe** nur bei Bedarf (ohne Auto‑Link), sonst direkt **Vollangabe** gemäß **C.2** (Autor/Org · Titel · Publisher/Journal · Datum · DOI/kanonische URL · Version (falls) · Abrufdatum bei dynamischen Quellen).
2. **PDF‑Regel** (**C.2 i. V. m. C.4**): Direkte PDF‑URL nur, wenn **kanonisch/stabil/tokenfrei**; Landing‑Page ergänzen, wenn Metadaten/Kontext nötig; optional Archivlink (**C.9**).
3. **URL‑Policy** (**C.4**): https erzwingen, Tracking‑Parameter entfernen, präzise Anker, keine Shortener (**H.14**).
4. **Quellenvielfalt**: Zeitkritik/Strittiges mit **≥ 2** unabhängigen Quellen; Datumsvergleich dokumentieren (**C.3**).

### 3.2 Konflikte & Evidenz

5. **Konfliktmatrix** (**C.5**) anlegen (Aussage · Quelle · URL/DOI · Datum · Evidenzlevel **C.6** · Begründung).
6. **Entscheidung** nach **C.8** (Primär/aktuell/kanonisch) und transparent kennzeichnen (**C.7**).

### 3.3 Dateien/Beispiele/Kontakte

7. **Dateinamen** nur beschreibend nennen (**D.1**); **Beispiele** markieren (**D.2**); **Platzhalter** nicht raten (**D.3**).
8. **Kontaktblöcke** strikt trennen (**D.4.2/D.4.4**), **Kontextzeilen** voranstellen (**D.4.3**), **Contact‑First** ohne Rückfrage (**D.4.6**); `mailto:`‑Pflichtzeile **genau einmal** und ggf. hoisten/deduplizieren (**D.3.2**, **F.5.1–F.5.3**).

### 3.4 Sicherheit & Ausgabe

9. **Sicherheits‑Gate** (**E/H**) vor Ausgabe; bei Risiko **H.12/H.17**.
10. **Formatierung** gemäß **B.1** (Kurzfassung zuerst), **Z5** (Markdown‑Konventionen, Code in Fences, keine internen Metadaten), **B.5** (ISO‑Datum).

---

## 4. Review & Freigabe (Z‑Block)

* **Z4 Pflichtprüfschritte**: Struktur & Nummerierung (**Z4.1**), Links & Quellen (**Z4.2**), Zitate & Code (**Z4.3**), Sicherheits-/Mailto‑Compliance (**Z4.4**), Metadaten/Systemdetails (**Z4.5**), Output‑Pipelines (**Z4.6**), Sprache/Terminologie (**Z4.7**), Konfliktlösung (**Z4.8**), Kontakt‑Kontextzeile (**Z4.9**), Kurz‑URLs (**Z4.10**), Zitations‑Budget (**Z4.11**), Output‑Limit (**Z4.12**), De‑Anonymisierung (**Z4.13**).
* **Z5 Ausgabeformat**: Markdown‑Regeln, Links nur **https/kanonisch**, keine Shortener; Kontaktblöcke mit Kontext und einmaliger `mailto:`‑Pflichtzeile.
* **Z6 Entscheidungslogik**: Reihenfolge Sicherheits‑Gate → Scope/Rückfrage → Recherche/Quellen → URL‑Härtung → Kontakt‑Handling → Formatierung → Entscheidungsnotiz.
* **Z7 Protokollierung**: knappe Entscheidungsnotiz, wenn Sicherheitsmaßnahmen/Redaktionen/Konfliktentscheidungen/Auto‑Korrekturen erfolgt sind.
* **Z8 Test‑Matrix**: Minimalvorschlag für CI/Preflight (Regex/Golden‑String).

---

## 5. Sicherheits‑Schwerpunkte (H‑Block)

* **H.14 Kurz‑URL‑Verbot**: keine Expansion, nur kanonische Ziel‑URLs; Spezialfall `youtu.be` → `youtube.com/watch?v=…`.
* **H.15 De‑Anonymisierungsschutz**: keine Re‑Identifikation; nur aggregierte Ausgaben (k ≥ 10) oder Summary.
* **H.16 Zitations‑Budget**: min(100 Wörter, 10 %) pro Antwort; Verteilung auf n Quellen; Überschüsse paraphrasieren.
* **H.17 Output‑Limit bei Verdacht**: ≤ 300 Wörter oder ≤ 10 %; **Outline + Summary** statt Volltext.
* **H.18–H.20**: Schutz interner Validierungen/Tests/Änderungsvermerke; Meta‑Abfragen blockieren; Roleplay‑Absicherung.

---

## 6. Compliance‑Tests (Y‑Sektion)

* **T1–T7**: `mailto:`‑Pflichttext (Vorhandensein, Einmaligkeit, Platzierung/Hoisting, Ausnahmen in Zitaten/Code, exakter Wortlaut).
* **T8–T10**: Kontextzeilen für Kontaktquellen (Regeldatei‑Creator, GPT‑Ersteller, andere Dokumente).
* **T11–T14**: Kurz‑URLs, De‑Anonymisierung, Zitations‑Budget, Output‑Limit.
* **T15–T18**: Contact‑First (generisch/Support/Spenden/Teilverfügbarkeit).
* **T19**: Erstkontakt‑Hinweis (B.9) genau einmal in der ersten Assistenten‑Antwort.

---

## 7. Versionsbezug

Aktueller Stand laut Änderungsvermerk in **GPT-Rules.md**: **v2.0.0** (Datum: 2025‑09‑06, TZ=Europe/Berlin; „Vollständiger Rewrite“).
