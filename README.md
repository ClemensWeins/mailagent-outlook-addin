# MailAgent – Outlook Add-in (Pilot)

Taskpane-Add-in für das Verfassen-Fenster in Outlook (Neues Outlook / Outlook im Web).
Bettet den Copilot-Studio-Agenten **MailAgent** neben dem E-Mail-Text ein und fügt den
erstellten Entwurf per Klick an der Cursorposition ein (Betreff wird automatisch erkannt).

## Dateien
- `manifest.xml` – Add-in-Manifest (Sideload-Datei)
- `taskpane.html` – Taskpane: Agent-Chat (iframe) + Einfügen-Werkzeuge (Office.js)

## Installation (Sideload, pro Nutzer)
1. https://aka.ms/olksideload öffnen (öffnet Outlook-Web mit Add-in-Dialog)
2. **Meine Add-Ins** → **Benutzerdefiniertes Add-In hinzufügen** → **Aus URL**
3. URL eintragen: `https://clemensweins.github.io/mailagent-outlook-addin/manifest.xml`
4. Neue E-Mail verfassen → Menüband „Apps“ → **MailAgent öffnen**

## Sicherheit
- Kein Secret im Code. Der Agent-Link verlangt die Anmeldung mit dem eigenen M365-Konto;
  der Agent arbeitet ausschließlich delegiert (Nutzer sieht nur eigene Daten).
- Berechtigung des Add-ins: `ReadWriteItem` (nur aktuelles Element, kein Versand).

## Bekannte Grenzen (V1)
- Die Inline-Fläche „Mit Copilot verfassen“ ist nicht erweiterbar; dieses Add-in ist der
  offizielle Weg, eigene Agenten ins Compose-Fenster zu bringen.
- Übernahme des Textes per Kopieren/Einfügen bzw. Zwischenablage-Button
  (V2: Direktintegration über Copilot Studio API / M365 Agents SDK).
