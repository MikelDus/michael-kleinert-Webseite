# CleverReach einrichten – Gratis-Guide „In 30 Minuten dein erstes authentisches Video“

Ziel: Besucher tragen auf der Website Vorname + E-Mail ein → bekommen eine Bestätigungs-E-Mail →
klicken den Link → landen auf unserer Danke-Seite mit dem PDF-Download.
Eine extra „Guide-Mail“ oder einen Autoresponder brauchst du dafür **nicht**.

> Hinweis: CleverReach benennt Menüpunkte gelegentlich leicht anders. Wenn ein Begriff nicht
> exakt so heißt, nimm den, der am ehesten passt – oder schick mir einen Screenshot.

---

## Schritt 0 – Bist du im richtigen Konto?

1. Bei CleverReach einloggen.
2. Oben rechts auf deinen Namen / dein Konto klicken und die **Kundennummer** ansehen.
3. Die Website war bisher an das Konto **244993** angebunden.
   - **Steht dort 244993**, aber du siehst keine Listen/Formulare → Konto ist evtl. gesperrt
     oder nicht freigeschaltet. Achte auf gelbe/rote Hinweise oben (z. B. „Konto aktivieren“,
     „Identität bestätigen“). Diese zuerst erledigen.
   - **Steht dort eine andere Nummer** → du bist in einem anderen Konto. Kein Problem:
     Wir richten einfach alles in diesem Konto neu ein (Schritte 1–7).
4. Falls das Konto noch gar nicht freigeschaltet ist: Die Freischaltungs-E-Mail von CleverReach
   suchen (auch im Spam-Ordner) bzw. den Anweisungen im Konto folgen.

## Schritt 1 – Absenderadresse bestätigen

1. In den Kontoeinstellungen den Bereich **Absender** / **Absenderadressen** öffnen.
2. `kleinert@video-coaching-produktion.de` als Absender eintragen (Name: **Michael Kleinert**).
3. CleverReach schickt eine Bestätigungs-E-Mail an diese Adresse → Link darin anklicken.
   Ohne bestätigten Absender werden keine Mails verschickt.

## Schritt 2 – Empfängerliste anlegen

1. Menü **Empfänger** → **Neue Empfängerliste** (früher „Gruppe“).
2. Name: `Gratis-Guide 30 Minuten`
3. Speichern.

## Schritt 3 – Feld „Vorname“ prüfen

1. In der neuen Liste bzw. unter **Empfänger → Datenfelder** (auch „Attribute“) nachsehen,
   ob es ein Feld **Vorname** gibt.
2. Wenn nicht: **Neues Datenfeld** → Name `Vorname`, Typ **Text** → speichern.

## Schritt 4 – Anmeldeformular anlegen

1. In der Liste `Gratis-Guide 30 Minuten` → Reiter **Formulare** → **Neues Formular**
   (Vorlage: einfaches Anmeldeformular).
2. Felder im Formular:
   - **Vorname** – als Pflichtfeld
   - **E-Mail** – Pflichtfeld (ist automatisch drin)
   - **reCAPTCHA** (Spamschutz) – hinzufügen
3. Weitere Felder (Nachname, Anrede …) bitte **nicht** aufnehmen bzw. nicht als Pflicht.
4. Den Datenschutz-Link im Formular (falls vorhanden) ändern auf:
   `https://video-coaching-produktion.de/rechtliches.html#datenschutz`

## Schritt 5 – Double-Opt-In und Weiterleitung einstellen

Im Formular den Reiter **Anmeldebestätigung** (bzw. „Double-Opt-in“) öffnen:

1. **Double-Opt-in aktivieren** anhaken.
2. Bestätigungs-E-Mail bearbeiten:
   - Absender: Michael Kleinert, `kleinert@video-coaching-produktion.de`
   - Betreff (Vorschlag): `Bitte bestätige kurz – dann kommt dein Gratis-Guide`
   - Text (Vorschlag):
     > Hallo {Vorname},
     >
     > schön, dass du dabei bist! Bitte klicke auf den Button unten, um deine Anmeldung zu
     > bestätigen. Direkt danach kannst du dir deinen Guide „In 30 Minuten dein erstes
     > authentisches Video“ herunterladen.
     >
     > [Bestätigungs-Link – fügt CleverReach automatisch ein]
     >
     > Viele Grüße
     > Michael Kleinert
   - Der Bestätigungs-Link muss in der Mail bleiben (nicht löschen).
3. **Weiterleitungs-URL nach Bestätigung** (eigene Seite statt CleverReach-Standardseite):
   `https://video-coaching-produktion.de/danke.html`
   → Dort steht der Download-Button für das PDF.
4. Speichern.

## Schritt 6 – Formular aktivieren und selbst testen

1. Formular speichern und – falls es einen Schalter gibt – auf **aktiv** stellen.
2. Im Formular auf **Einbinden** / **Veröffentlichen** gehen. Dort gibt es einen
   **Link zum Formular** (sieht aus wie `https://seuX.cleverreach.com/f/123456-789012/`).
3. Diesen Link im Browser öffnen: Es muss das Formular erscheinen – **nicht** „Please try again later“.
4. Mit einer E-Mail-Adresse eintragen, die **noch nie** angemeldet war → Bestätigungsmail
   (auch Spam-Ordner prüfen) → Link klicken → du solltest auf unserer Danke-Seite landen.
5. Unter **Empfänger** in der Liste nachsehen: Die Adresse sollte jetzt als **aktiv** erscheinen.

## Schritt 7 – Mir diese zwei Dinge schicken

1. Den **Link zum Formular** (aus Schritt 6.2)
2. Den **Quellcode** des Formulars: unter **Einbinden** → „Quellcode“ / „HTML-Code“
   → alles markieren, kopieren und mir hier einfügen.

Dann baue ich die neue Formular-Nummer und die Feldnamen in die Website ein, teste alles und
stelle es nach deiner Freigabe live. Danach machen wir zusammen einen echten Test über die Website.

---

### Später (optional, für bessere Zustellung)

- **Absender-Domain authentifizieren** (SPF/DKIM für video-coaching-produktion.de) –
  CleverReach zeigt dazu DNS-Einträge an, die bei netcup eingetragen werden. Dann landen die
  Mails seltener im Spam. Dabei helfe ich gern.
