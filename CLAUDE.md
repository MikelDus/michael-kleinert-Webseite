# Arbeitsregeln für diese Website (verbindlich)

Website von Michael Kleinert (Videocoach & Videoproduktion, Düsseldorf/NRW).
Branch `claude/github-repro-erstellen-gepirc` – **jeder Push geht automatisch live**
(GitHub Actions → FTPS → netcup, Domain video-coaching-produktion.de).

## 1. Texte sind freigegeben – nicht eigenständig ändern

- Alle sichtbaren Texte der Startseite sind von Michael Kleinert Abschnitt für Abschnitt
  freigegeben (Stand 16.10.2026). Der freigegebene Wortlaut steht in
  `docs/freigegebene-texte.md`.
- **Keine Formulierung ändern, kürzen, „verbessern“ oder umstellen**, auch nicht bei
  Layout-, Technik- oder SEO-Arbeiten – nur wenn Michael es ausdrücklich verlangt.
- Neue Texte (z. B. Fehlermeldungen) immer erst vorschlagen und freigeben lassen.
- Wird ein Text auf Wunsch geändert: Wortlaut 1:1 übernehmen und
  `docs/freigegebene-texte.md` mit aktualisieren.
- FAQ-Antworten müssen auf Startseite, FAQ-Seite (`videocoaching-erklaert.html`) und im
  FAQPage-JSON-LD identisch bleiben.
- Keine erfundenen Inhalte: keine Preise, Zitate, Zahlen oder Kundenstimmen ausdenken.

## 2. Ablauf bei jeder Änderung

1. Änderung lokal machen und testen.
2. **Ergebnis immer zuerst als Screenshot zeigen** (Desktop + Handy).
3. Lokal committen.
4. **Erst pushen, wenn Michael freigibt** („passt“, „pushen“, „commiten“, „ich gebe frei“).
5. Nach dem Push prüfen, ob der Workflow „Deploy to netcup“ erfolgreich war, und Bescheid geben.

## 3. Technische Fixpunkte

- Guide-Formular: CleverReach-Formular `244993-431186`, Felder `1013922` (Vorname),
  `email`, `cr_subunsubscribe=true`, reCAPTCHA-Sitekey von CleverReach. Nicht ändern ohne
  neuen Einbettungscode aus CleverReach.
- Kontaktformular: FormSubmit an kleinert@video-coaching-produktion.de.
- YouTube/Vimeo nur nach Klick (Datenschutz), reCAPTCHA erst bei Nutzung des Formulars.
- WhatsApp-Links: `https://wa.me/491705817102`.
