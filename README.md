# GELDWERT

**Unabhängige Tests & Empfehlungen** — eine partner-agnostische Affiliate-Review-Plattform.
Von Energie und Internet über Finanzen bis Reise. Das Partner-Netzwerk wird laufend ausgebaut.

## Seitenstruktur

| Datei | Rolle |
|-------|-------|
| `index.html` | **Startseite** — Hero, die vier Rubriken-Karten, Titel-Test und „Neueste Tests“. Führt zu allen Bereichen. |
| `tests.html` | **Alle Tests** — Übersicht aller Reviews, nach Rubrik sortiert. |
| `energie.html` | Rubrik **Energie** — Review „Stromtarife 2026“ (Check24 vs. Verivox, Boni, Folgepreise). |
| `internet.html` | Rubrik **Internet** — Review „Glasfaser & DSL 2026“ (Verfügbarkeit, Effektivpreis, Boni). |
| `finanzen.html` | Rubrik **Finanzen** — Review „Tagesgeld & Kreditkarte 2026“ (Trade Republic, C24, Scalable, ING, Reisekarte). |
| `reise.html` | Rubrik **Reise** — Review „Mietwagen 2026“ (billiger-mietwagen.de vs. Check24, Versicherungs-Checkliste). |
| `check24.html` | Titel-Test — der große Check24-Praxistest über vier Produkte. |
| `assets/styles.css` | Gemeinsames Design-System (Tokens + alle Komponenten). |
| `assets/site.js` | Gemeinsames Verhalten (Lesefortschritt, Scroll-Reveal, TOC-Scroll-Spy, Jahreszahl). |

Alle Reviews sind mit echten Marktdaten (Stand Juni 2026) hinterlegt und verlinken im Abschnitt **„Quellen & Datenstand“** die verwendeten Quellen (u. a. Trustpilot, Check24, Verivox, Handelsblatt, Stiftung Warentest).

## Navigation / „Posten“ in eine Rubrik

Es gibt **kein CMS** — die Seite ist statisches HTML. Eine Rubrik ist jeweils **eine Datei** (`energie.html`, `internet.html`, `finanzen.html`, `reise.html`). Die Kopf-Navigation und der Footer verlinken auf genau diese Dateien; die aktive Seite ist mit `aria-current="page"` markiert.

### Eine neue Review in eine bestehende Rubrik aufnehmen

1. **Inhalt schreiben:** Eine bestehende Rubrik-Datei (z. B. `energie.html`) kopieren oder die Produkt-Karten darin erweitern. Bausteine sind in `assets/styles.css` dokumentiert:
   - `.product` — Produkt-Bewertungskarte (Score, Pro/Contra, Eckdaten, CTA)
   - `.table-wrap > table` — Vergleichstabelle
   - `.faq > details` — FAQ-Akkordeon
   - `.finale` — Schluss-Urteil mit CTA
   - `.sources` — Quellenangabe
2. **Auf Übersichten verlinken:** In `tests.html` und in der „Neueste Tests“-Sektion von `index.html` eine `.test-card` ergänzen (Titel, Rubrik, Note, Datum, Link).
3. **Affiliate-Links setzen:** Die `href="#"`-Platzhalter in den `.cta`-Buttons durch echte Partner-Links ersetzen (sie tragen bereits `rel="sponsored nofollow noopener"`).

### Eine ganz neue Rubrik anlegen

1. Eine Rubrik-Datei als Vorlage kopieren, z. B. `versicherung.html`.
2. In **jeder** Seite den `<nav class="nav">`-Block im Header (und die `.foot-links` im Footer) um `<a href="versicherung.html">Versicherung</a>` ergänzen.
3. Auf `index.html` eine `.section-card` im `.section-grid` hinzufügen.

## Design

- **Ästhetik:** editorial / Finanz-Magazin — warmes Papier, Tinten-Schwarz, ein Honig-Gold-Akzent.
- **Typografie:** Fraunces (Display), Newsreader (Fließtext), IBM Plex Mono (Daten/Labels) via Google Fonts.
- **Technik:** reines HTML/CSS/JS, keine Abhängigkeiten, keine Build-Pipeline. Gemeinsames CSS/JS in `assets/`.

## Lokal ansehen

`index.html` im Browser öffnen. (Da CSS/JS jetzt aus `assets/` geladen werden, am besten über einen lokalen Server starten, z. B. `python -m http.server`, damit relative Pfade sicher greifen.)

## Hosting

Per GitHub Pages bereitgestellt (Branch `main`, Root `/`). `index.html` ist die Einstiegsseite.

## Affiliate-Hinweis

Die `href="#"`-Platzhalter in den CTA-Buttons durch die echten Affiliate-/Partner-Links ersetzen.
Affiliate-Links tragen `rel="sponsored nofollow noopener"`.

---

*Inhalte dienen zu Demonstrationszwecken; genannte Werte sind Beispiele (Stand Juni 2026) und können je nach Region, Nutzung und Anbieter abweichen.*
