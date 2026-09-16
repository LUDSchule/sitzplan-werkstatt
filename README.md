# Sitzplan-Werkstatt

Sitzpläne bauen: Tische verschieben, Kinder auf Plätze ziehen, Vorgaben und Wünsche eingeben und mehrere bewertete Sitzordnungen automatisch vorschlagen lassen.

**Die App enthält keine Schülerdaten.** Namen, Regeln und Sitzordnungen liegen nur im Browser und in einer Datei im eigenen Schul-OneDrive. Die App hat keinen Server und keine Anmeldung.

Die App aufrufen: https://ludschule.github.io/sitzplan-werkstatt/

---

## PC und iPad abgleichen

Der Stand liegt als Datei `sitzplan-werkstatt.json` im Schul-OneDrive.

**PC (Edge oder Chrome)** — speichert automatisch:
1. *Sichern → Neue Datei anlegen* und im Explorer den OneDrive-Ordner der Schule wählen.
2. Fragt der Browser nach Zugriff: *Bei jedem Besuch zulassen*. Sonst beim nächsten Öffnen einmal oben auf *Datei wieder verbinden* klicken.
3. Danach wird jede Änderung in die Datei geschrieben. Änderungen vom iPad werden geladen, sobald man ins Fenster zurückkehrt.

**iPad (Safari)** — Laden und Sichern von Hand:
1. Zu Beginn oben **Laden** → *Durchsuchen* → *OneDrive* → `sitzplan-werkstatt.json`.
2. Am Ende oben **Sichern** → *In Dateien sichern* → *OneDrive* → denselben Ordner → *Sichern*, bei Nachfrage *Ersetzen*.
3. Oben steht, ob es noch ungesicherte Änderungen gibt.

**Gut zu wissen**
- Nicht auf beiden Geräten gleichzeitig arbeiten. Trifft der PC auf eine Datei, die anderswo geändert wurde, während er selbst Änderungen hat, fragt er nach, welcher Stand gelten soll.
- Die OneDrive-App muss auf PC und iPad angemeldet sein und synchronisieren.
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
Muss: David | Emil
Fest: Anna = 12.1
Gern: Carla | Gül; Hana | Ida
Ungern: Jonah | Kemal
Junge: Ben, Finn
Mädchen: Carla, Hana
```

- **Ruhe / Vorne / Blick** — Bedürfnisse
- **Nicht** — Vorgabe der Lehrkraft: dürfen nicht am selben Tisch sitzen
- **Muss** — Vorgabe der Lehrkraft: sitzen immer am selben Tisch
- **Fest** — fester Platz als `Name = Tisch.Platz`; Platz 1 ist links bzw. oben, Platz 2 rechts bzw. unten. Alternativ im Sitzplan das Kind hinsetzen und in der Kinderliste **F** antippen
- **Gern / Ungern** — Wünsche der Kinder, fließen in die Bewertung ein
- **Junge / Mädchen** — nur nötig für die Mischung
- Paare mit `|` verbinden, mehrere Paare mit `;` trennen, alles hinter `#` ist Kommentar
