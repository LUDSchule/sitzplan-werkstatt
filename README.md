# Sitzplan-Werkstatt

Sitzpläne bauen: Tische verschieben, Kinder auf Plätze ziehen, Vorgaben und Wünsche eingeben und mehrere bewertete Sitzordnungen automatisch vorschlagen lassen. Speichert auf Wunsch automatisch im Schul-OneDrive.

**Die App enthält keine Schülerdaten.** Namen, Regeln und Sitzordnungen liegen nur im Browser und — nach Anmeldung — im eigenen Schul-OneDrive (Ordner `Apps/Sitzplan-Werkstatt`).

Die App aufrufen: https://ludschule.github.io/sitzplan-werkstatt/

---

## Gut zu wissen

- **iPad:** funktioniert in Safari. Beim Anmelden öffnet sich ein kleines Fenster — Pop-ups für die Seite müssen erlaubt sein (*Einstellungen → Safari → Pop-ups blockieren* aus, oder beim Hinweis erlauben).
- **Mehrere Geräte:** Auf jedem Gerät einmal anmelden. Beim ersten Anmelden fragt die App, ob der Stand aus OneDrive geladen werden soll. Gespeichert wird danach automatisch etwa 1,5 Sekunden nach jeder Änderung.
- **Gleichzeitig bearbeiten:** Nicht auf zwei Geräten zugleich arbeiten — der zuletzt gespeicherte Stand gewinnt.
- **Ohne Anmeldung:** Die App bleibt voll nutzbar und speichert im Browser. Unter *Sichern* gibt es außerdem **Als Datei speichern** und **Datei öffnen**.
- **Datenschutz:** Schülerdaten gehören ins Schul-OneDrive, nicht in ein privates Konto. Im Zweifel mit Schulleitung oder Datenschutzbeauftragten abstimmen.

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
