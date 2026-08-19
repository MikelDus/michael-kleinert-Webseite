# Landingpage Michael Kleinert

## Projekt
Landingpage für Michael Kleinert – Video-Coach & Videograf, Rheinland/NRW.
Zielgruppe: kleine Selbstständige/Coaches (Video-Coaching) UND Firmen (Produktion).
Freebie: "In 30 Minuten dein erstes authentisches Video" (Lead-Magnet, E-Mail-Formular).

## Dateien im Repo

- **`index.html`** – die Landingpage. Bilder liegen als echte Dateien in `assets/`.
- **`rechtliches.html`** – Impressum & Datenschutz, verlinkt aus dem Footer der
  Landingpage (Links: `rechtliches.html` und `rechtliches.html#datenschutz`).
  Muss im selben Ordner wie `index.html` liegen.
- **`assets/`** – alle Bilder, plus `assets/fonts/` (lokal gehostete Schriftdateien)
  und `assets/favicon.svg`.
- **`docs/Farbpalette_Michael-Kleinert.pdf`** – Farbpalette zur Referenz.

## Design-System

- **Farben:** Blau `#1b75bb` (Marke), Orange `#ff9100` (Akzent),
  Signal-Orange `#ff6b00` (nur CTA-Button). Details siehe
  `docs/Farbpalette_Michael-Kleinert.pdf`.
- **Schriften:** Sora (Headlines/Display), Inter (Fließtext) – lokal gehostet in
  `assets/fonts/`, kein Nachladen von Google-Servern mehr.
- **Aufbau der Seite (von oben nach unten):**
  Nav (fixiert) → Laufschrift → Hero (Formular + Foto) →
  Kino-Botschaft ("echt zu sein dein größter Vorteil") →
  Foto-Trio → Problem → Lösung (30-Minuten-Struktur) →
  "Das bekommst du" (dunkler Bereich) → Über mich →
  Testimonials (Slider) → FAQ → Finaler CTA → Kontaktformular → Footer.

## Cookie-Banner

Beim ersten Besuch erscheint ein Cookie-Banner ("Nur notwendige" / "Alle
akzeptieren"). Die Website selbst setzt keine Cookies; die Wahl wird nur lokal
im Browser (Local Storage) gespeichert. Das Banner steuert aktuell, ob das
eingebettete YouTube-Video direkt lädt oder erst nach einem zusätzlichen Klick
("Video laden & abspielen"). Über den Footer-Link "Cookie-Einstellungen" lässt
sich die Auswahl jederzeit ändern.

## Bekannte offene Punkte / To-dos

1. **Formulare senden noch nicht wirklich.** Sowohl das Freebie-Formular im
   Hero als auch das Kontaktformular unten zeigen nur eine Erfolgsmeldung an,
   verschicken aber noch keine echte E-Mail – es gibt aktuell keine
   Backend-Anbindung. Muss noch an einen Dienst angebunden werden (z. B.
   CleverReach/KlickTipp fürs Freebie, ein Formular-Dienst für den
   Kontakt-Bereich). **Wichtig:** `rechtliches.html` Abschnitt 5 & 6 müssen
   angepasst werden, sobald ein echter Dienst angebunden ist.
2. **Hosting noch nicht final bestätigt.** `rechtliches.html` nennt netcup als
   Hoster (Platzhalter-Hinweis in Abschnitt 3) – bitte bestätigen oder den
   tatsächlichen Hoster eintragen.
3. **USt-IdNr. / Kleinunternehmerstatus** in `rechtliches.html` (Impressum)
   noch offen – rot markierter Platzhalter.
4. **Google Analytics ist nicht eingebunden** (Abschnitt 7 in
   `rechtliches.html` wurde entsprechend korrigiert). Falls es später
   eingebunden wird, muss es hinter dem Cookie-Banner-Opt-in laufen und der
   Abschnitt ergänzt werden.

## Bereits erledigt (gegenüber der ursprünglichen Übergabe)

- Fonts (Sora, Inter) werden lokal aus `assets/fonts/` geladen statt von
  Google-Servern – keine IP-Übertragung an Google mehr beim Seitenaufruf.
- Cookie-Consent-Banner ergänzt (siehe oben), inkl. Gate für das
  YouTube-Embed.
- `rechtliches.html`: eingebettetes Base64-Logo durch echte Bilddatei ersetzt
  (kleinere Dateigröße), fälschlich als aktiv beschriebene Funktionen
  (Google Analytics, Newsletter-Versand) korrigiert, Server-Logfile-
  Speicherdauer und Stand-Datum ausgefüllt.
- Favicon ergänzt.

## Hinweis zu Animationen

Die Seite nutzt CSS-Animationen (Herzschlag-Puls am Formular, Schwebe-Effekt
am Kino-Foto, Scroll-Reveals, Slider-Autoscroll). Diese sind bewusst dezent
gehalten. `prefers-reduced-motion` wird respektiert.
