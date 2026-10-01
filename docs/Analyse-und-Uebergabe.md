# Analyse & Übergabe – Webseite Michael Kleinert

**Kunde:** Michael Kleinert · Video-Coaching und Produktion, Hohe Str. 35, 40213 Düsseldorf
**Domain:** https://video-coaching-produktion.de (erreichbar mit und ohne `www.`; kanonische Adresse = ohne `www.`)
**Stand:** 01.10.2026
**Repository:** `MikelDus/michael-kleinert-Webseite`, Branch `claude/github-repro-erstellen-gepirc`
**Ablage dieser Datei:** `docs/` – wird **nicht** auf den Webserver hochgeladen (intern).

---

## 1. Kurzüberblick

Statische Webseite (HTML, CSS, JavaScript) ohne CMS und ohne Datenbank. Ziel der Seite:

1. **Positionierung** als Business-Videocoach für Unternehmen im Rheinland/NRW (nicht Hochzeits-/Familienvideograf).
2. **Leadgewinnung** über den kostenlosen Guide „In 30 Minuten dein erstes authentisches Video“ (Double-Opt-In über CleverReach).
3. **Anfragen** über das Kontaktformular (FormSubmit), E-Mail und Telefon.
4. **Sichtbarkeit** in Google und KI-Suchmaschinen über Blog, FAQ-Seite und „Schnelle Antworten“.

---

## 2. Technik & Infrastruktur

| Bereich | Umsetzung |
|---|---|
| Technik | Reines HTML/CSS/JS, kein Framework, kein Build-Schritt |
| Hosting | netcup, Plesk-Webhosting (Ordner `httpdocs`) |
| Deployment | GitHub Actions (`.github/workflows/deploy.yml`) → bei jedem Push auf den Branch automatischer Upload per **FTPS** (verschlüsselt) |
| Zugangsdaten | Als GitHub-Secrets hinterlegt: `NETCUP_FTP_HOST`, `NETCUP_FTP_USER` (`github-deploy`), `NETCUP_FTP_PASSWORD` – stehen nicht im Code |
| Vom Upload ausgeschlossen | `.git*`, `.github/`, `README.md`, `docs/` |
| Schriften | Sora (Überschriften) und Inter (Fließtext), **lokal gehostet** in `assets/fonts/` – kein Nachladen von Google Fonts |
| Sicherungs-Branch | `sicherung-27-08-2026` (Stand vor den größeren Umbauten) |

**Wichtig für die Weiterarbeit:** Jeder `git push` auf den Branch geht **sofort live**. Änderungen deshalb erst lokal prüfen und dann pushen.

---

## 3. Seitenübersicht

| Datei | Zweck | Google-Index |
|---|---|---|
| `index.html` | Startseite / Landingpage | ja |
| `videocoaching-erklaert.html` | FAQ-Seite: 16 Fragen in 5 Kategorien | ja |
| `schnelle-antworten.html` | 75 Frage-Antwort-Kacheln mit Fotos | ja |
| `blog/index.html` | Blog-Übersicht | ja |
| `blog/*.html` | 22 Blog-Artikel | ja |
| `rechtliches.html` | Impressum & Datenschutz | nein (`noindex`, gewollt) |
| `danke.html` | Danke-Seite mit Guide-Download | nein (`noindex`, gewollt) |
| `robots.txt` | Regeln für Suchmaschinen, Verweis auf Sitemap | – |
| `sitemap.xml` | Liste aller indexierbaren Seiten (26 URLs) | – |
| `llms.txt` | Kurzbeschreibung der Seite für KI-Assistenten | – |

### Ordnerstruktur

```
/
├── index.html, videocoaching-erklaert.html, schnelle-antworten.html,
│   rechtliches.html, danke.html, robots.txt, sitemap.xml, llms.txt
├── blog/                  22 Artikel + index.html
├── assets/
│   ├── fonts/             Sora, Inter (woff2)
│   ├── videos/            27 Showreel-Clips (mp4 + webm)
│   ├── blog/              Titelgrafiken der Blog-Artikel (SVG)
│   ├── schnelle-antworten/ 18 optimierte Fotos (foto-01 … foto-18)
│   ├── downloads/         Guide als PDF
│   ├── blog.css           Gemeinsames Stylesheet aller Unterseiten
│   ├── og-image.jpg       Vorschaubild für Social Media (1200×630)
│   └── … Fotos, Logo, Kundenstimmen, Favicon
└── docs/                  Interne Unterlagen (nicht online)
    ├── Analyse-und-Uebergabe.md   (diese Datei)
    ├── Farbpalette_Michael-Kleinert.pdf
    └── fotos-mit-wasserzeichen/   3 Originalfotos mit „Picture People“-Wasserzeichen
```

---

## 4. Startseite – Aufbau von oben nach unten

| # | Bereich | CSS-Klasse / Anker | Überschrift | Inhalt / Funktion |
|---|---|---|---|---|
| 1 | Navigation | `.nav` | – | Logo, Dropdown „Seite“ (Sprungmarken), Blog, Schnelle Antworten, Button „Gratis-Guide holen“. Mobil: Hamburger-Menü |
| 2 | Laufschrift | `.marquee` | – | „Authentisch statt perfekt · Sichtbar werden im KI-Zeitalter · Nur dein Smartphone · Kein Studio nötig · In 30 Minuten fertig“ |
| 3 | Hauptbanner | `.intro-hero` `#top` | H1 „Vom ersten Gedanken zum fertigen Video.“ | Kicker „Der Videocoach Michael Kleinert“, Text, Button „Kontakt“, **Platzhalter für Werbevideo** |
| 4 | Showreel | `.showreel` | „Ein kleiner Einblick in meine Videoarbeit“ | Zwei endlos laufende Reihen: Hochkant-Clips (Social Media) und Querformat-Clips |
| 5 | So arbeite ich mit dir | `.approach` | „Nicht nur gefilmt. Begleitet.“ | 8 nummerierte Karten (Videograf vs. Video-Coach, Ablauf, Haltung) |
| 6 | Kino-Botschaft | `.cine` | – | „Gerade jetzt, wo alles künstlich wird, ist echt zu sein dein größter Vorteil.“ + Foto |
| 7 | Mittendrin | `.trio` | „Mittendrin in der Innenstadt – echt, nahbar, in NRW“ | 3 Vorschaubilder → öffnen je ein **Vimeo-Video** im Pop-up (16:9) |
| 8 | Problem | `.problem` | „Video ist nichts für mich!“ | Einwände der Zielgruppe |
| 9 | Guide-Bereich | `.hero` `#lead` | H2 „In 30 Minuten dein erstes authentisches Video …“ | Links Text, rechts **Anmeldeformular CleverReach** + Guide-Vorschau |
| 10 | Lösung | `.solution` `#loesung` | „Authentisch vor der Kamera ist lernbar – in 30 Minuten“ | 4-Schritte-Zeitleiste |
| 11 | Das bekommst du | `.benefits` `#leistungen` | „Alles drin, damit dein erstes Video richtig gelingt“ | Dunkler Bereich mit Leistungen |
| 12 | Über mich | `.about` `#ueber-mich` | „Hallo, ich bin Michael“ | Foto + Werdegang (12 Jahre, 500+ Kunden, NLP/systemisch) |
| 13 | Passt das zu dir? | `.fit` | „Für wen Videocoaching das Richtige ist – und für wen nicht“ | 2 Glaskacheln „Geeignet / Nicht geeignet“ mit aufklappbarem „Mehr erfahren“ |
| 14 | Kundenstimmen | `.testi` `#kundenstimmen` | „Echte Stimmen, echte Erlebnisse“ | Slider mit 9 Kundenstimmen (Bilder) |
| 15 | FAQ (Teaser) | `.faq` `#faq` | „Gut zu wissen“ | 5 Fragen als Akkordeon + Button „Alle Fragen zu Videocoaching ansehen“ |
| 16 | Abschluss-CTA | `.final` | „Bereit für dein erstes authentisches Video?“ | Button springt zum Guide-Formular |
| 17 | Kontakt | `.contact` `#kontakt` | „Lass uns über dein Projekt sprechen“ | E-Mail, Telefon, Region + **Kontaktformular (FormSubmit)** |
| 18 | Footer | `footer` | – | Links: E-Mail, Telefon, Blog, Schnelle Antworten, Videocoaching erklärt, Impressum, Datenschutz, Cookie-Einstellungen; „Nach oben“ |

Zusätzlich (unsichtbar bis zum Aufruf): Video-Pop-up (`#lightbox`), Erfolgsmeldung (`#modal`), Cookie-Banner.

---

## 5. Unterseiten

**Videocoaching erklärt** (`videocoaching-erklaert.html`)
Blauer Kopfbereich, klebende Sprungmarken-Leiste (5 Themen), 5 nummerierte Kategorien mit insgesamt 16 Fragen (Akkordeon), offener Abschlussblock „Was ist der nächste Schritt?“ mit Kontakt-Button. Enthält strukturierte FAQ-Daten (FAQPage) für Google.
Kategorien: 01 Videocoach oder Videograf? · 02 Der Ablauf eines Videoprojekts · 03 Vor der Kamera · 04 Storytelling & Videoformate · 05 Nutzen fürs Unternehmen.

**Schnelle Antworten** (`schnelle-antworten.html`)
75 Kacheln (Kategorie, Frage, Antwort, Tipp) mit 18 echten Fotos im Wechsel, schwebende 3D-Kacheln, orangene CTA-Kacheln. Eigene CSS-Klassen mit Präfix `qa-`.

**Blog** (`blog/`)
22 Artikel (12 recherchiert, 10 vom Kunden geschrieben – diese stehen vorne). Artikel-Layout mit Titelgrafik, Lesezeit, Quellen und „Weiterlesen“. Textspalte 900 px breit. Jeder Artikel hat strukturierte Artikel-Daten.

**Rechtliches** (`rechtliches.html`)
Impressum (§ 5 DDG, Kleinunternehmer § 19 UStG) und Datenschutzerklärung (Hosting, Logfiles, CleverReach, reCAPTCHA, FormSubmit, Vimeo, Cookies, Schriften, Rechte, Beschwerderecht).

**Danke-Seite** (`danke.html`)
Bestätigung nach der Anmeldung mit Download-Link zum Guide-PDF.

---

## 6. Design-System

### Farben

| Name | Wert | Verwendung |
|---|---|---|
| `--blue` | `#1b75bb` | Markenblau, Links, Icons |
| `--blue-2` | `#2b8ad6` | Verläufe |
| `--blue-deep` | `#155e97` | Hover, dunklere Akzente |
| `--blue-ink` | `#0f2f4d` | Überschriften, dunkle Bereiche |
| `--orange` | `#ff9100` | Akzent, Eyebrows, Punkte |
| `--cta` | `#ff6b00` | **nur** Call-to-Action-Buttons |
| `--ink` | `#122430` | Fließtext |
| `--muted` | `#5a6b78` | Nebentexte |
| `--mist` / `--sky` | `#f4f9fd` / `#e9f4fc` | helle Hintergründe |
| `--line` | `#e0ecf5` | Linien, Rahmen |

Referenz: `docs/Farbpalette_Michael-Kleinert.pdf`.

### Typografie
- **Sora** (800/700/600) für Überschriften, Buttons, Eyebrows
- **Inter** (400–700) für Fließtext
- Überschriften-Größen fließend mit `clamp()`, z. B. Sektionstitel `clamp(1.9rem, 3.6vw, 2.8rem)`

### Wiederkehrende Bausteine
- **Sektionskopf:** `.sec-eyebrow` (kleine Großbuchstaben-Zeile) + `.sec-h` (Titel) + `.lede` (Einleitung)
- **Buttons:** `.cta-btn` (oranger Verlauf, Schatten, „magnetischer“ Hover-Effekt)
- **Karten:** weiße Karten mit Rundung 20–28 px, weicher Schatten, Anheben beim Hover
- **Glaskacheln:** halbtransparent mit `backdrop-filter: blur()` – funktioniert durch den fixierten Farbverlauf im Hintergrund (`.aurora`)
- **Akkordeon:** natives `<details>/<summary>` ohne JavaScript, orangener pulsierender Punkt (`.faq-dot`), drehender Pfeil (`.faq-chevron`)
- **Container:** `.wrap` (max. 1200 px), `.wrap-article` (max. 900 px)
- **Hintergrund:** `.aurora` – sanft wandernder Farbverlauf, fest hinter der ganzen Seite

### Animationen
Einblenden beim Scrollen (`.reveal`, gestaffelt mit `d1`/`d2`…), Laufschrift, endlose Showreel-Reihen, Zähler-Animation, Mauslicht (nur Desktop). Bei „Bewegung reduzieren“ im Betriebssystem werden alle Animationen abgeschaltet.

### Responsive Breakpoints (Startseite)
1100 px (Zusatztext in der Navigation aus) · 960 px (Spalten untereinander) · 860 px (Glaskacheln untereinander) · 760 px (Hamburger-Menü) · 640/560/480/440/400/340 px (Feinanpassungen Handy).

---

## 7. Funktionen (JavaScript)

| Funktion | Beschreibung |
|---|---|
| Navigation | wird beim Scrollen hinterlegt; Dropdown mit Sprungmarken; Hamburger-Menü mobil (Esc schließt) |
| Showreel | spielt nur sichtbare Clips ab (spart Akku/Daten), lädt nur Vorschaudaten vor |
| Video-Pop-up | `openVideo(id, titel)` öffnet ein Vimeo-Video; vorher Einwilligungs-Hinweis, falls keine Cookie-Zustimmung |
| Guide-Formular | Prüfung von Vorname, E-Mail und Captcha; Versand an CleverReach über ein verstecktes iFrame; danach Erfolgsmeldung |
| reCAPTCHA | wird **erst geladen, wenn jemand ins Formular klickt** |
| Kontaktformular | Prüfung + Versand per FormSubmit; Erfolgs- oder Fehlermeldung (ohne Sicherheitsrisiko, nur reiner Text) |
| Cookie-Banner | „Nur notwendige“ / „Alle akzeptieren“; Speicherung nur im Browser (Local Storage), keine Cookies |
| Kundenstimmen-Slider | automatisch und per Pfeil |

---

## 8. Externe Dienste & Datenschutz

| Dienst | Zweck | Wann wird verbunden? |
|---|---|---|
| **netcup** | Hosting | immer (Server) |
| **CleverReach** | Double-Opt-In und Versand des Guides | beim Absenden des Guide-Formulars |
| **Google reCAPTCHA** | Spamschutz Guide-Formular | erst bei Nutzung des Formulars |
| **FormSubmit** | Versand des Kontaktformulars per E-Mail | beim Absenden des Kontaktformulars |
| **Vimeo** | 3 Videos im Bereich „Mittendrin“ | erst nach Klick und Einwilligung |

Kein Google Analytics, keine Tracking-Cookies, keine Google Fonts. CleverReach-Formular-ID: `244993-431186`.

---

## 9. SEO, GEO & KI-Sichtbarkeit

- **Titel & Beschreibung** auf allen Seiten; Startseite: „Videocoaching & Videoproduktion Düsseldorf | Michael Kleinert“
- **Canonical-Tags** auf allen öffentlichen Seiten (verhindert doppelten Inhalt bei www/ohne www)
- **Open-Graph-/Twitter-Tags** + eigenes Vorschaubild (`assets/og-image.jpg`) für WhatsApp, LinkedIn, Facebook
- **Strukturierte Daten (JSON-LD):**
  - Startseite: `ProfessionalService` (Firma, Adresse, Telefon, Leistungen, Region), `Person`, `WebSite`
  - FAQ-Seite: `FAQPage` mit allen 16 Fragen
  - Blog: `Article` mit Autor, Datum, Bild, Herausgeber
- **sitemap.xml** und **robots.txt**; Guide-PDF ist für Suchmaschinen gesperrt
- **llms.txt**: Kurzprofil und Seitenverzeichnis für ChatGPT, Perplexity & Co.
- **Überschriften-Hierarchie** korrekt (je Seite genau eine H1)
- **Lighthouse (Google-Prüfwerkzeug), 01.10.2026:** SEO 100, Best Practices 100 auf allen geprüften Seiten; Barrierefreiheit 91–100

---

## 10. Sicherheitsprüfung (01.10.2026)

Geprüft und **in Ordnung**:
- keine Passwörter, Schlüssel oder Zugangsdaten im Code
- Upload nur verschlüsselt (FTPS), Zugangsdaten nur als GitHub-Secrets
- interne Dateien (`.git`, `docs/`, `README.md`) werden nicht hochgeladen
- keine Einschleusung von Fremd-Code möglich: Formulareingaben werden nirgends als HTML ausgegeben
- alle externen Verbindungen per HTTPS; externe Links mit `rel="noopener"`
- keine kaputten Links, Sprungmarken oder Bilder (alle Seiten geprüft)

Bei der Prüfung **behoben**:
- interne Arbeitsnotizen in der Datenschutzerklärung waren öffentlich sichtbar
- reCAPTCHA wurde bei jedem Seitenbesuch geladen
- Formular lieferte eine falsche Erfolgsmeldung, wenn Google blockiert war
- Fotos mit Fremd-Wasserzeichen lagen öffentlich auf dem Server

---

## 11. Änderungsprotokoll (Auszug)

| Datum | Änderung |
|---|---|
| 19.08.2026 | Erstimport Landingpage; Schriften lokal; Cookie-Banner; Rechtstexte; Kontaktformular (FormSubmit); Showreel mit echten Clips; Blog mit 12 Artikeln |
| 20.08.2026 | Dropdown-Menü, „Nach oben“; Danke-Seite; Vorname im Guide-Formular |
| 21.08.2026 | Automatisches Deployment zu netcup; 10 Kundenartikel im Blog; breitere Blogspalte; Hamburger-Menü |
| 22.08.2026 | Guide-Formular an CleverReach angebunden (korrigierte Formular-ID) |
| 27.08.2026 | Sicherungs-Branch angelegt; netcup/Plesk-Bereinigung und Livegang |
| 29.08.2026 | Neue Seite „Schnelle Antworten“ (75 Kacheln, 18 echte Fotos); Lesbarkeit der Überschrift repariert |
| 30.09.2026 | Neuer Hauptbanner mit Video-Platzhalter; Sektion „So arbeite ich mit dir“; Reihenfolge neu; Guide-Bereich verkleinert, symmetrisch, ohne Foto |
| 01.10.2026 | Vimeo-Videos im Bereich „Mittendrin“; FAQ-Seite „Videocoaching erklärt“ + Teaser; Sektion „Passt das zu dir?“; Feinschliff SEO/GEO/Datenschutz/Darstellung |

Vollständige Historie: `git log` im Repository (40 Einträge).

---

## 12. Offene Punkte & Empfehlungen

| Priorität | Punkt | Wer |
|---|---|---|
| **hoch** | **Datenschutz rechtlich prüfen lassen**, insbesondere fehlende Betreiberangaben von FormSubmit (im Quellcode als Kommentar markiert) | Kunde / Anwalt |
| **hoch** | **Inhaltlicher Widerspruch Hochzeiten:** „Passt das zu dir?“ schließt Hochzeiten aus, aber das Kontaktformular bietet „Event / Feier (Hochzeit, Jubiläum)“ an, der Blogartikel „Event-Video für Firmenfeiern & Hochzeiten“ existiert und das Showreel nennt „Events & Feiern“ | Kunde entscheidet, Umsetzung Webentwicklung |
| hoch | **Bestätigungsmail CleverReach** testen (mit und ohne Werbeblocker); im CleverReach-Konto unter „Empfänger“ prüfen, ob Anmeldungen ankommen | Kunde |
| mittel | **Werbevideo** für den Hauptbanner liefern (Platzhalter „Werbevideo folgt in Kürze“) | Kunde |
| mittel | **Google Search Console** einrichten und `sitemap.xml` einreichen | Kunde / Webentwicklung |
| mittel | In Plesk prüfen: **Weiterleitung http → https** aktiv; zusätzlich **www → ohne www (301)** einrichten | Webentwicklung |
| mittel | **FormSubmit-Tarnadresse** statt sichtbarer E-Mail im Quellcode nutzen (schützt vor Spam) | Webentwicklung |
| niedrig | **Kontrast:** weiße Schrift auf `#ff6b00` (2,85 : 1) und oranger Text auf Weiß (2,25 : 1) liegen unter der Barrierefreiheits-Norm (4,5 : 1) – Designentscheidung | Kunde |
| niedrig | Sicherheits-Header am Server (z. B. `X-Content-Type-Options`, `Referrer-Policy`) in Plesk setzen | Webentwicklung |
| niedrig | Lange Blog-Titel werden in Google gekürzt angezeigt (optional kürzen) | Webentwicklung |
| niedrig | Guide-PDF ist per direktem Link ohne Anmeldung abrufbar (für Suchmaschinen gesperrt) | Kunde entscheidet |
| offen | Produkt-Bereich des Kollegen (3 Produkte zum Kauf) und die abweichende Tagline wurden nie ins Repository übernommen – fehlender Repo-Link | Kunde |

---

## 13. Hinweise für die Weiterarbeit

- **Jeder Push = sofort live.** Vorher lokal testen: `python3 -m RangeHTTPServer 8099` im Projektordner, dann `http://localhost:8099` öffnen (RangeHTTPServer wird für die Videos benötigt).
- **Neue Sektionen** übernehmen das bestehende Muster: `.sec-eyebrow` + `.sec-h` + `.lede`, Container `.wrap`, Einblenden mit `.reveal`.
- **Eindeutige Klassennamen verwenden.** Gleich benannte Klassen in `index.html` und `assets/blog.css` haben schon einmal unlesbare Überschriften verursacht. Darum nutzen neue Seiten eigene Präfixe (`qa-`, `vc-`, `fit-`).
- **Akkordeon-Stil** ist in `index.html` und `videocoaching-erklaert.html` identisch definiert (kein gemeinsames Stylesheet) – Änderungen an beiden Stellen vornehmen.
- **`id="top"`** sitzt auf dem Hauptbanner; Logo und „Nach oben“ springen dorthin.
- **Vimeo-Videos tauschen:** Video-ID in `openVideo('ID','Titel')` im Bereich `.trio` ändern.
- **Neue Seite hinzufügen:** in `sitemap.xml` und `llms.txt` eintragen, Canonical- und Open-Graph-Tags im `<head>` ergänzen, Footer-Links auf allen Seiten ergänzen.
- **Neue externe Dienste** (z. B. Analytics) erst nach Einwilligung über das Cookie-Banner laden und in der Datenschutzerklärung ergänzen.
