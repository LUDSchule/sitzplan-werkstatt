# Sitzplan-Werkstatt

Sitzpläne bauen: Tische verschieben, Kinder auf Plätze ziehen, Vorgaben und Wünsche eingeben und mehrere bewertete Sitzordnungen automatisch vorschlagen lassen. Speichert auf Wunsch automatisch im Schul-OneDrive.

**Die App enthält keine Schülerdaten.** Namen, Regeln und Sitzordnungen liegen nur im Browser und — nach Anmeldung — im eigenen OneDrive. Dieses Repository darf öffentlich sein.

---

## Einrichtung in drei Schritten

### Schritt 1 · Auf GitHub veröffentlichen

1. Auf github.com ein **neues Repository** anlegen, Name: `sitzplan-werkstatt`, Sichtbarkeit **Public**.
2. Auf der Repository-Seite **Add file → Upload files** und diese vier Dateien hineinziehen:
   - `index.html`
   - `redirect.html`
   - `README.md`
   - `.nojekyll` (versteckte Datei — im Explorer ggf. unter *Ansicht → Ausgeblendete Elemente* sichtbar machen)
3. Unten **Commit changes**.
4. **Settings → Pages**. Unter *Build and deployment*: Source **Deploy from a branch**, Branch **main**, Ordner **/ (root)**, dann **Save**.
5. Nach ein bis zwei Minuten steht oben die Adresse, etwa:
   `https://LUDSchule.github.io/sitzplan-werkstatt/`

Ab hier funktioniert die App bereits — nur noch ohne OneDrive.

### Schritt 2 · Bei Microsoft registrieren

Das geht entweder selbst oder über die Schul-IT. Die meisten Schulen erlauben Lehrkräften nicht, selbst Apps zu registrieren. **Dann den Text unten an die IT weitergeben.**

Wenn Sie es selbst dürfen:

1. <https://entra.microsoft.com> öffnen, mit dem **Schulkonto** anmelden.
2. **Anwendungen → App-Registrierungen → Neue Registrierung**.
3. Name: **Sitzplan-Werkstatt** — genau so, denn daraus entsteht der Ordnername im OneDrive.
4. Unterstützte Kontotypen: **Nur Konten in diesem Organisationsverzeichnis**.
5. Umleitungs-URI: Plattform **Single-Page-Anwendung (SPA)** — nicht „Web“! — und als Adresse:
   `https://LUDSchule.github.io/sitzplan-werkstatt/redirect.html`
6. **Registrieren**.
7. Auf der Übersichtsseite die **Anwendungs-ID (Client-ID)** kopieren, außerdem die **Verzeichnis-ID (Mandanten-ID)**.
8. Links **API-Berechtigungen → Berechtigung hinzufügen → Microsoft Graph → Delegierte Berechtigungen** → `Files.ReadWrite.AppFolder` anhaken → hinzufügen.

### Schritt 3 · ID eintragen

1. `index.html` auf GitHub öffnen, auf das **Stift-Symbol** (Bearbeiten).
2. Mit Strg+F nach `CONFIG` suchen und so ausfüllen:

   ```js
   const CONFIG={
     clientId: "hier-die-Anwendungs-ID",
     authority: "https://login.microsoftonline.com/hier-die-Mandanten-ID",
     file: "sitzplan.json"
   };
   ```

3. **Commit changes**. Nach einer Minute ist die neue Fassung online.

Beim ersten Klick auf **Mit OneDrive verbinden** fragt Microsoft nach Zustimmung. Erscheint stattdessen *„Genehmigung erforderlich“* oder *„Administratorgenehmigung“*, muss die Schul-IT einmalig zustimmen — siehe unten.

---

## Text für die Schul-IT

> Betreff: Registrierung einer Unterrichts-App in Entra ID (Microsoft 365)
>
> Ich nutze eine selbst gehostete Web-App zur Sitzplanung. Sie soll ausschließlich in einem eigenen App-Ordner meines OneDrive speichern. Bitte registrieren Sie dafür eine App bzw. erteilen Sie die Zustimmung:
>
> - **Name:** Sitzplan-Werkstatt
> - **Kontotyp:** nur dieser Mandant
> - **Plattform:** Single-Page-Anwendung (SPA)
> - **Umleitungs-URI:** `https://LUDSchule.github.io/sitzplan-werkstatt/redirect.html`
> - **Berechtigung:** Microsoft Graph, delegiert: `Files.ReadWrite.AppFolder`
>
> Diese Berechtigung ist auf den Ordner `Apps/Sitzplan-Werkstatt` im OneDrive der jeweils angemeldeten Person beschränkt. Die App hat keinen Zugriff auf andere Dateien, keinen Server und keine eigene Datenhaltung; der Quelltext ist öffentlich einsehbar unter `https://github.com/LUDSchule/sitzplan-werkstatt`.
>
> Ich benötige anschließend die **Anwendungs-ID (Client-ID)** und die **Mandanten-ID**. Falls die Einwilligung durch Nutzer im Mandanten gesperrt ist, bitte zusätzlich die **Administratorzustimmung** für diese Berechtigung erteilen.

---

## Gut zu wissen

- **iPad:** funktioniert in Safari. Beim Anmelden öffnet sich ein kleines Fenster — Pop-ups für die Seite müssen erlaubt sein (*Einstellungen → Safari → Pop-ups blockieren* aus, oder beim Hinweis erlauben).
- **Mehrere Geräte:** Auf jedem Gerät einmal anmelden. Beim ersten Anmelden fragt die App, ob der Stand aus OneDrive geladen werden soll. Gespeichert wird danach automatisch etwa 1,5 Sekunden nach jeder Änderung.
- **Gleichzeitig bearbeiten:** Nicht auf zwei Geräten zugleich arbeiten — der zuletzt gespeicherte Stand gewinnt.
- **Ohne Anmeldung:** Die App bleibt voll nutzbar und speichert im Browser. Unter *Sichern* gibt es außerdem **Als Datei speichern** und **Datei öffnen**.
- **Datenschutz:** Schülerdaten gehören ins Schul-OneDrive, nicht in ein privates Konto. Im Zweifel mit Schulleitung oder Datenschutzbeauftragten abstimmen.
- **Aktualisierung:** Neue Fassungen von `index.html` einfach auf GitHub ersetzen. Die gespeicherten Daten bleiben erhalten.

---

## Räume

Unter *Raum* lassen sich Klassenräume einrichten und speichern.

- **Vorlagen:** *Standardraum* (8 × 9 m, 15 Doppeltische) und *Beispielraum*. Vorlagen bleiben unverändert — Änderungen unter eigenem Namen speichern.
- **Eigene Räume:** Namen eingeben, **Speichern**. Später über die Auswahlliste wieder **Laden**, verändern und erneut speichern. Beim Laden eines anderen Raums wird die Sitzordnung geleert, Namen und Regeln bleiben.
- **Größe:** Breite und Tiefe in Metern. Mit *Inhalt mitskalieren* wird alles mitgezogen — praktisch, um eine Skizze an die echten Maße anzupassen.
- **Elemente:** Tisch, Tafel, Smartboard, Pult, Tür, Fenster, Waschbecken, Schrank, Fächer, Regal, Wand / Säule und ein freies Element mit eigener Beschriftung. Im Modus **Raum** ziehen, über die blaue Ecke vergrößern, **Drehen** oder Taste `R`, **Löschen** oder Entf-Taste.
- **Form:** Der Raum ist ein Rechteck. Nischen, L-Formen oder Säulen mit *Wand / Säule* abdecken.
- **Bewertung:** Tür und Waschbecken gelten als unruhig, Tafel und Smartboard als vorne, das Pult zählt fürs Blickfeld. Fehlen solche Elemente, fließt das jeweilige Bedürfnis nicht in die Bewertung ein.

---

## Regeln als Text

Unter *Regeln → Regeln als Text* lassen sich fertige Regeln einfügen:

```
# Regeln
Ruhe: Anna, Ben, Carla
Vorne: David
Blick: Emil
Nicht: Ben | Finn
Gern: Carla | Gül; Hana | Ida
Ungern: Jonah | Kemal
Junge: Ben, Finn
Mädchen: Carla, Hana
```

- **Ruhe / Vorne / Blick** — Bedürfnisse
- **Nicht** — Vorgabe der Lehrkraft, wird nie gebrochen
- **Gern / Ungern** — Wünsche der Kinder, fließen in die Bewertung ein
- **Junge / Mädchen** — nur nötig für die Mischung
- Paare mit `|` verbinden, mehrere Paare mit `;` trennen, alles hinter `#` ist Kommentar
