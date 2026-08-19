# Landingpage Michael Kleinert – Übergabe an Claude Code

## Projekt
Landingpage für Michael Kleinert – Video-Coach & Videograf, Rheinland/NRW.
Zielgruppe: kleine Selbstständige/Coaches (Video-Coaching) UND Firmen (Produktion).
Freebie: "In 30 Minuten dein erstes authentisches Video" (Lead-Magnet, E-Mail-Formular).

## Dateien in diesem Paket

- **`Landingpage_Michael-Kleinert_mit-Bilderordner.html`** ⭐ EMPFOHLEN
  Gleiche Seite wie unten, aber Bilder liegen als echte Dateien im Ordner `assets/`
  statt eingebettet. Viel kleiner (~65 KB statt ~1 MB) und leichter zu bearbeiten.
  → Diese Datei am besten als `index.html` in dein Projekt übernehmen.

- **`Landingpage_Michael-Kleinert.html`**
  Die Originalversion mit allen Bildern als Base64 direkt im Code eingebettet.
  Funktioniert als einzelne Datei ganz ohne Ordner — praktisch zum schnellen
  Teilen/Testen, aber unhandlich zum Bearbeiten.

- **`rechtliches.html`**
  Impressum & Datenschutz, verlinkt aus dem Footer der Landingpage
  (Links: `rechtliches.html` und `rechtliches.html#datenschutz`).
  Muss im selben Ordner wie die Landingpage liegen.

- **`assets/`** – alle 18 Bilder einzeln:
  - Logo, Hero-Foto (Gimbal-Action), Kino-Foto (Studio-Porträt)
  - 3 Trio-Fotos (Coaching vor Ort / Studio / Nah dran)
  - 9 Testimonial-Screenshots (echte Google-Bewertungen)
  - Freebie-Cover-Vorschau

## Design-System

- **Farben:** Blau `#1b75bb` (Marke), Orange `#ff9100` (Akzent),
  Signal-Orange `#ff6b00` (nur CTA-Button). Details siehe
  `Farbpalette_Michael-Kleinert.pdf` (falls mitgeliefert).
- **Schriften:** Sora (Headlines/Display), Inter (Fließtext) – von Google Fonts,
  im `<head>` verlinkt.
- **Aufbau der Seite (von oben nach unten):**
  Nav (fixiert) → Laufschrift → Hero (Formular + Foto) →
  Kino-Botschaft ("echt zu sein dein größter Vorteil") →
  Foto-Trio → Problem → Lösung (30-Minuten-Struktur) →
  "Das bekommst du" (dunkler Bereich) → Über mich →
  Testimonials (Slider) → FAQ → Finaler CTA → Kontaktformular → Footer.

## Bekannte offene Punkte / To-dos

1. **Formulare senden noch nicht wirklich.** Sowohl das Freebie-Formular im
   Hero als auch das Kontaktformular unten zeigen nur eine Erfolgsmeldung an,
   verschicken aber noch keine echte E-Mail. Muss noch an einen Dienst
   angebunden werden (genannt wurden: CleverReach/KlickTipp fürs Freebie,
   netcup als Hoster).
2. **Cookie-Consent-Banner fehlt noch.** Falls Google Analytics eingebunden
   wird, braucht es vorher ein DSGVO-konformes Banner (siehe Hinweis in
   `rechtliches.html`, Abschnitt 7).
3. **Google Fonts lädt aktuell von Google-Servern.** Für volle DSGVO-Konformität
   wäre lokales Hosting der Fonts sauberer.
4. **Rot markierte Platzhalter in `rechtliches.html`** noch ausfüllen
   (z. B. USt-IdNr., genauer E-Mail-Dienstleister, Stand-Datum).

## Hinweis zu Animationen

Die Seite nutzt CSS-Animationen (Herzschlag-Puls am Formular, Schwebe-Effekt
am Kino-Foto, Scroll-Reveals, Slider-Autoscroll). Diese sind bewusst dezent
gehalten. `prefers-reduced-motion` wird respektiert.
