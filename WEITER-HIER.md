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

## Stand (2026-08-18)
Git-Sicherheitsnetz steht. Projekt in drei Etappen zerlegt, weil es zu groß für eine Sitzung ist:
1. Die Website selbst (Infos, Fotos, Beschreibung) — noch keine Buchungsfunktion.
2. Verfügbarkeitskalender (zeigt live, was über Airbnb/Booking.com schon belegt ist).
3. Echte Buchungsfunktion inkl. Rückmeldung an Smoobu (der technisch anspruchsvollste Teil,
   entscheidend gegen Doppelbuchungen).

**Etappe 1 ist gestartet und ein erster funktionsfähiger Stand steht:**
- `index.html` + `style.css` — einseitige Info-Website ("Oldenburger Dachperle", warmer/
  gemütlicher Stil), Inhalte aus dem bestehenden Airbnb-Inserat übernommen (Beschreibung,
  Ausstattung, Schlafmöglichkeiten, Lage, eine Gästestimme). Kontaktbereich verlinkt vorerst
  auf Airbnb, da die echte Buchungsfunktion erst in Etappe 3 kommt.
- `impressum.html` — Pflichtangaben (Quartier 261 / Konstantin Kisner) sind eingetragen.
- `material/` — Ablage für Ausgangsmaterial (z. B. Fotos aus dem Airbnb-Konto).
- `bilder/` — noch leer; hier kommen die echten Fotos rein, sobald der Nutzer sie aus seinem
  Airbnb-Gastgeber-Konto heruntergeladen hat.
- Lokale Vorschau läuft über `.claude/launch.json` (Server-Name "website-vorschau").

## Nächster Schritt
Echte Fotos in `bilder/` einfügen und in `index.html` einbauen (aktuell nur Text, kein Bild).
Danach ist Etappe 1 inhaltlich fertig und es kann über Veröffentlichung/Hosting gesprochen
werden — das ist noch offen und kein Teil von Etappe 1/2/3.
