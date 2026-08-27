# osiro docs

Mintlify-Dokumentation für osiro (Produkte: **Portal**, **Convert**, **Message**, **Hunter**, plus **API Reference**). Struktur in [docs.json](docs.json).

## Sprache

- **Immer Sie-Form**, nie "Du". Gilt für Fließtext, FAQ-Antworten, Tipps, Warnungen – ausnahmslos.
- Deutsch für Titel, Beschreibungen und Inhalt. Dateinamen dürfen englisch/kebab-case sein (z. B. `colors.mdx`, `funnel-editor.mdx`).

## Navigation (docs.json)

- **Tabs** = echte Produkte (Portal, Convert, Message, Hunter, API Reference) – keine Themen-Tabs.
- **Groups bleiben grundsätzlich flach**, keine Group-in-Group-Verschachtelung. Grund: Mintlify klappt nur verschachtelte Groups ein (`expanded`), Top-Level-Groups sind immer voll sichtbar – wir haben uns bewusst für viele flache Groups statt weniger verschachtelter entschieden und verlassen uns auf Suche/KI-Chat (`contextual` in docs.json) statt auf eingeklappte Navigation.
  - **Ausnahme**: Eine verschachtelte Sub-Group ist okay, wenn mehrere Seiten einen in sich geschlossenen Themenblock bilden, der als Einheit ein-/ausklappbar sein soll (z. B. die 4 Baustein-Seiten "Blöcke" innerhalb von Flows). Im Zweifel flach lassen, nur auf ausdrücklichen Wunsch verschachteln.
  - Jede verschachtelte Sub-Group bekommt `"expanded": true`, damit sie standardmäßig aufgeklappt ist und die Hierarchie direkt sichtbar bleibt (Nutzer können sie zwar manuell einklappen, aber der Default zeigt die Struktur).
- Zielbild: pro Produkt-Tab ca. 8–10 Groups mit je 5–10 Artikeln
- Neue Feature-Artikel dürfen erstmal ohne docs.json-Eintrag entstehen, wenn der Ort noch unklar ist – Platzierung kann später nachgezogen werden.

## Artikel-Konventionen

- Frontmatter: `title` + `description` (description = prägnanter Ein-Satz-Nutzen, kein Feature-Dump).
- Abschnitte mit `##`, getrennt durch `---`.
- Bilder als `<img src="/images/{produkt}/{bereich}/{name}.png"/>` (Pfad folgt der Ordnerstruktur unter `images/`), alternativ `<Frame>` bei mehreren zusammengehörigen Bildern.
- FAQ-Abschnitt meist als letzter Abschnitt: `## Häufige Fragen` mit `<AccordionGroup>` / `<Accordion>`.
- Wenn Detailwissen fehlt: **Platzhalter explizit markieren** ("Platzhalter – ...") statt zu raten oder Fakten zu erfinden. Bei echter Unsicherheit lieber kurz nachfragen.
- Granularität: lieber mehrere kleine, aufgabenspezifische Artikel als eine breite Sammelseite (z. B. eigene Artikel für Farben, Typografie, Element-Einstellungen, Layout statt einer "Design"-Sammelseite).
- Der `title` einer Index-Seite darf nie 1:1 dem Namen ihrer Group entsprechen (sonst zeigt die Sidebar z. B. "Funnels / Funnels"). Stattdessen konkreter/fragend formulieren, z. B. "Was ist ein Funnel?", "Was ist Convert?", "Account erstellen".
- Verwandte Artikel sollen aufeinander verweisen (inline-Link im Fließtext oder eigener Verweis am Abschnittsende), damit Nutzer einfach zwischen zusammenhängenden Themen navigieren können. Beim Schreiben oder Ändern eines Artikels aktiv prüfen, ob es thematisch verwandte Artikel gibt, und ggf. Links in beide Richtungen ergänzen.

## Convert – Design-Bereich

Farben, Typografie, Element-Einstellungen, Layout und der Styleguide sind **inhaltlich und funktional identisch** zwischen Funnel Editor und Landing Page Editor (inkl. geteilter Styleguide-Presets). Deshalb:

- Nur **ein** Artikel pro Design-Thema unter `convert/design/`, nicht doppelt pro Editor.
- Jeder Design-Artikel beginnt mit `<Note>Dieser Design-Bereich ist identisch für Funnel Editor und Landing Page Editor.</Note>`.
- Jeder Design-Artikel (außer Styleguide selbst) verlinkt auf `/convert/design/styleguide`; der Styleguide-Artikel verlinkt zurück auf die vier anderen.

## Sonstiges

- Bei mehrdeutigen Produktdetails (z. B. genaue Anzahl/Bedeutung von Einstellungen) nicht spekulieren – nachfragen.
