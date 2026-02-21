# LaTeX-Vorlage – APA7

LaTeX-Vorlage für wissenschaftliche Arbeiten nach **APA7** (7. Auflage).
Geeignet für Hausarbeiten, Bachelor- und Masterarbeiten an Hochschulen.

## Struktur

```
main.tex                  ← Hauptdatei (hier Angaben zur Arbeit eintragen)
einstellungen/
  pakete.tex              ← Paketimporte & Grundkonfiguration
  formatierung.tex        ← APA7-Überschriften, Tabellen, Abbildungen
  kopfzeile.tex           ← Seitenzahl oben rechts (APA7)
titelseiten/
  abschlussarbeit.tex     ← Titelseite für Bachelor-/Masterarbeit
  hausarbeit.tex          ← Titelseite für Hausarbeit/Seminararbeit
kapitel/
  abstract.tex            ← Abstract (eigene Seite, 150–250 Wörter)
  kapitel1.tex            ← Einleitung
  kapitel2.tex            ← Theoretischer Hintergrund
  kapitel3.tex            ← Methodik
  kapitel4.tex            ← Ergebnisse
  kapitel5.tex            ← Diskussion
  kapitel6.tex            ← Fazit und Ausblick
  anhang.tex              ← Anhang A, B, …
  erklaerung.tex          ← Eigenständigkeitserklärung
  apa7_hinweise.tex       ← Formatierungsbeispiele (nach Fertigstellung entfernen)
literatur/
  quellen.bib             ← Literatureinträge (BibTeX/APA7)
bilder/                   ← Abbildungen (jpg, png, pdf, …)
```

## Schnellstart

**1. Angaben in `main.tex` eintragen:**

```latex
\title{Titel der Arbeit}
\author{Vorname Nachname}
\matrikelnr{s0000000}
\submitDate{\today}
\firstExaminer{Vorname Nachname}
\institution{Name der Hochschule / Fachbereich}
```

**2. Titelseite wählen** (in `main.tex`):

- Abschlussarbeit → `\include{titelseiten/abschlussarbeit}` (Standard)
- Hausarbeit → die andere Zeile einkommentieren

**3. Kapitel schreiben** – neue Dateien unter `kapitel/` anlegen und in `main.tex` einbinden:

```latex
\input{kapitel/methodik} \clearpage
```

**4. Quellen** in `literatur/quellen.bib` eintragen, im Text zitieren mit:

```latex
\autocite{Schlüssel}          % (Autor, Jahr)
\textcite{Schlüssel}          % Autor (Jahr)
\autocite[S.~45]{Schlüssel}   % (Autor, Jahr, S. 45)
```

## Kompilierung

Reihenfolge für vollständige Ausgabe (Literaturverzeichnis, Querverweise):

```
pdflatex main
biber main
pdflatex main
pdflatex main
```

Mit `latexmk` (empfohlen) reicht ein Befehl:

```
latexmk -pdf main
```

**Benötigte LaTeX-Pakete** (alle in TeX Live / MiKTeX enthalten):
`biblatex-apa`, `biblatex`, `biber`, `newtxtext`, `newtxmath`, `setspace`, `geometry`, `scrlayer-scrpage`, `booktabs`, `tabularx`, `caption`, `csquotes`, `babel`, `microtype`, `hyperref`

## Umgebung

| Betriebssystem | Empfehlung |
|---|---|
| Windows | [MiKTeX](https://miktex.org/) + [TeXstudio](https://www.texstudio.org/) |
| macOS | [MacTeX](https://www.tug.org/mactex/) + TeXstudio |
| Linux | TeX Live (`sudo apt install texlive-full`) |


## APA7 – Wichtigste Formatvorgaben

| Vorgabe | Einstellung |
|---|---|
| Schriftart | Times New Roman, 12 pt |
| Seitenränder | 2,54 cm (1 Zoll) alle Seiten |
| Zeilenabstand | Doppelt |
| Absatzeinzug | 1,27 cm (0,5 Zoll) |
| Seitenzahl | Oben rechts, ab Titelseite |
| Zitierweise | Autor-Jahr `(Müller, 2021)` |
| Literaturverzeichnis | Einheitliche Liste, alphabetisch |
| Überschriften | 5 Ebenen (zentriert-fett bis eingerückt-fett-kursiv) |


## Lizenz

Ursprünglich basierend auf [LaTeX Master Vorlage](https://github.com/a-czyrny/LaTeX-Master-Vorlage) von Alexander Czyrny (CC BY-NC-SA 4.0).
Grundlegend überarbeitet und auf APA7 umgestellt.
