# Weiter hier

Du kommst aus dem Mini-Kurs — Beat 1+2 sind geschafft (Claude läuft, Coach gilt überall,
superpowers & Git installiert). Jetzt: dein erstes echtes Projekt — kleine echte Aufgabe wählen ·
Git-Sicherheitsnetz an (`git init` + erster Commit) · Rhythmus erleben: durchdenken → bauen →
prüfen → sichern · sichtbares Ergebnis. Hak die Schritte nebenbei im Kurs im Browser ab. Ab jetzt
gehört diese Datei deinem Projekt.

## Worum es geht
Der Nutzer vermietet Ferienwohnungen aktuell über Airbnb und Booking.com, gesteuert mit Smoobu
(Kanal-/Kalender-Synchronisierung) und PriceLabs (dynamische Preise). Ziel: eine eigene Website,
über die Gäste direkt buchen können — spart die Plattform-Provision. Wichtigste Anforderung:
keine Doppelbuchungen zwischen der eigenen Website und Airbnb/Booking.com.

## Stand (2026-08-19)
Git-Sicherheitsnetz steht. Projekt war ursprünglich in drei Etappen zerlegt:
1. Die Website selbst (Infos, Fotos, Beschreibung).
2. Verfügbarkeitskalender (zeigt live, was über Airbnb/Booking.com schon belegt ist).
3. Echte Buchungsfunktion inkl. Rückmeldung an Smoobu (entscheidend gegen Doppelbuchungen).

**Etappe 1 UND 3 sind jetzt live — die Website ist voll funktionsfähig:**
- **Website ist veröffentlicht:** https://quartier261.github.io/ferienwohnung-website/
  (kostenlos über GitHub Pages, GitHub-Account "Quartier261"). Jede Änderung, die per `git push`
  auf den `master`-Branch hochgeladen wird, aktualisiert die Seite automatisch (dauert 1–2 Min.).
- **Echte Buchungsfunktion ist eingebaut:** Statt eines selbstgebauten Kalenders (Etappe 2) wird
  Smoobus eigenes Buchungswidget direkt eingebettet (Smoobu-Dashboard → Kernfunktionen →
  Buchungssystem → „Website integrieren"). Gäste können direkt auf der Seite Verfügbarkeit
  prüfen und buchen; Smoobu verhindert dabei selbst Doppelbuchungen über alle Kanäle
  (Airbnb/Booking.com) — Etappe 2 (eigener Kalender) ist damit hinfällig, das übernimmt Smoobu.
- `index.html` + `style.css` — einseitige Info-Website ("Oldenburger Dachperle", warmer/
  gemütlicher Stil), Inhalte aus dem bestehenden Airbnb-Inserat übernommen (Beschreibung,
  Ausstattung, Schlafmöglichkeiten, Lage, eine Gästestimme, Buchungsbereich).
- `impressum.html` — Pflichtangaben (Quartier 261 / Konstantin Kisner, Gastgeber Helene &
  Konstantin) sind eingetragen.
- `bilder/` — echte Fotos der Wohnung sind eingebaut (Titelbild, Küche, Schlafzimmer, Bad,
  kleine Galerie), inkl. dem Quartier-261-Logo (`logo-quartier261.png`, aus einem
  Werbe-Flyer-Foto ausgeschnitten) im Kopfbereich. Ein paar weitere Fotos liegen noch
  ungenutzt im Ordner (z. B. Flur, Kaffeemaschine) für eine spätere Erweiterung.
- `material/` — Ablage für weiteres Ausgangsmaterial.
- Lokale Vorschau läuft über `python3 -m http.server 4173` im Projektordner (Aufruf über
  `.claude/launch.json` hatte in dieser Umgebung einen Berechtigungsfehler — Server manuell
  im Hintergrund starten und `http://localhost:4173` öffnen).
- **Domain quartier261.de ist noch frei** (geprüft, nicht registriert). Kann bei Bedarf später
  gekauft und vor die kostenlose GitHub-Adresse geschaltet werden — bisher nicht gemacht.

## Nächster Schritt
Die Website ist inhaltlich und funktional fertig (Infos + echte Buchung). Als Nächstes:
eigene Domain (quartier261.de) registrieren und einrichten, damit die Seite unter einer
schöneren Adresse statt der kostenlosen GitHub-Adresse erreichbar ist.
