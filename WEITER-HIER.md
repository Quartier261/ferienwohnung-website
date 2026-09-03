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

## Stand (2026-08-20)
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
  Ausstattung, Schlafmöglichkeiten, Lage, eine Gästestimme, Buchungsbereich). Im
  Buchungsbereich zusätzlich: Alternative Links zu Airbnb und Booking.com, sowie Kontakt
  per E-Mail und WhatsApp (0173 3672361).
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
- **Eigene Domain quartier261.de ist eingerichtet:** bei INWX registriert (Kundenkonto beim
  Nutzer), DNS-Einträge zeigen auf GitHub Pages (4× A-Record auf die GitHub-IPs + CNAME für
  „www"), GitHub kennt die Domain (`CNAME`-Datei im Repo, per `gh api ... PATCH .../pages`
  gesetzt). **Funktioniert bereits über `http://quartier261.de`** (mobil getestet, funktioniert;
  am Heimnetz des Nutzers zog die DNS-Änderung zunächst noch nicht, das ist normal/Wartezeit).
  ✅ **HTTPS-Zertifikat ist jetzt aktiv** (Stand 2026-09-03): Das automatische Zertifikat für
  `quartier261.de` hing wochenlang fest, obwohl die DNS-Einstellungen korrekt waren (bekannter
  GitHub-Fehler). Der Fix: Domain in den GitHub-Pages-Einstellungen kurz entfernt und sofort
  wieder eingetragen — das hat eine frische Zertifikatsanfrage ausgelöst. `https_enforced` ist
  jetzt `true`, die Seite läuft unter `https://quartier261.de` mit einem eigenen Zertifikat
  (gültig bis 2026-12-02, erneuert sich automatisch).
- **QR-Code für die Domain** liegt in `ergebnisse/qr-code-quartier261.png` (zeigt auf
  `https://quartier261.de`, erzeugt mit `qrencode`), z. B. zum Ausdrucken für die Wohnung.
- **Kontaktformular "Individuelle Anfrage"** (Name, E-Mail, Nachricht) im Buchungsbereich, für
  Gäste mit Sonderwünschen (z. B. längere Aufenthalte). Verschickt die Nachricht über den
  kostenlosen Dienst FormSubmit.co direkt an quartier261@gmx.de, ohne dass der Gast eine
  eigene E-Mail-App braucht. ⚠️ **Wichtig:** Beim allerersten echten Absenden auf der Live-Seite
  schickt FormSubmit eine Bestätigungs-Mail an quartier261@gmx.de — die muss einmal bestätigt
  werden, sonst kommen weitere Anfragen nicht an. Am besten das Formular einmal selbst live
  testen.
- `datenschutz.html` — neue Pflichtseite (Datenschutzerklärung), nötig geworden durch das
  Kontaktformular (Daten laufen kurz über FormSubmit, Server in den USA). Verlinkt im Footer
  und im Impressum. Deckt Kontaktformular, Smoobu-Widget und GitHub-Pages-Hosting ab — ein
  guter Standardtext, aber keine anwaltlich geprüfte Rechtsberatung.

## Nächster Schritt
Die Website ist inhaltlich, funktional und technisch fertig (Infos + echte Buchung +
Kontaktformular + eigene Domain + HTTPS). Offen: das Kontaktformular einmal live testen und
die FormSubmit-Bestätigungsmail bestätigen.

**Neue Idee für eine künftige Sitzung (noch nicht begonnen):** Ein Rechnungsprogramm, mit dem
sich Mietern nach ihrem Aufenthalt eine Rechnung ausstellen lässt. Das ist ein eigenständiges,
größeres Thema (Pflichtangaben auf Rechnungen, ggf. Kleinunternehmer-Status) und braucht einen
frischen, eigenen Anlauf mit Detailfragen. Erster Schritt dabei: prüfen, ob Smoobu nicht
bereits eine Rechnungsfunktion mitbringt, bevor etwas Eigenes gebaut wird (gleiches Prinzip wie
beim Buchungswidget — nicht doppelt bauen, was es schon gibt).
