# HTML öffnen – PWA für iPad

Ein einfacher HTML-Öffner für Dateien, die du lokal in der Dateien-App auf iPad/iPhone gespeichert hast. Keine Cloud-Uploads und kein Server für die HTML-Daten nötig.

## Installation über GitHub Pages

1. Neues öffentliches GitHub-Repository anlegen, z. B. `html-oeffner`.
2. **Alle fünf Dateien** aus diesem Ordner in die oberste Ebene des Repositorys hochladen (`index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`).
3. GitHub → Repository → Settings → Pages → Build and deployment → Deploy from a branch → Branch `main`, Ordner `/(root)` → Save.
4. Adresse `https://DEINNAME.github.io/html-oeffner/` in Safari öffnen.
5. In Safari → Teilen → „Zum Home-Bildschirm“.

## Nutzung

- App öffnen → „HTML-Datei auswählen“ → die `.html` / `.htm`-Datei aus der Dateien-App wählen.
- Die Anzeige erfolgt innerhalb eines Frames im Browser. CSS und JavaScript werden ausgeführt.
- Mit „Andere Datei“ kann jederzeit gewechselt werden.
- „Zuletzt geöffnete Datei“ merkt sich lokal die zuletzt geöffnete HTML-Datei (IndexedDB). Über Browserdaten löschen ist sie wieder entfernbar.

## Mit Kurzbefehl

Die Anleitung steht in `KURZBEFEHL.md`. Der HTML-Öffner unterstützt zwei Übergabewege:

- `https://DEINNAME.github.io/html-oeffner/#b64=...` – Direktübergabe per Base64 URL-Fragment (am besten für kleine HTML-Dateien).
- `https://DEINNAME.github.io/html-oeffner/#clip` – Übergabe über Zwischenablage, für größere Dateien als Alternative.

**Wichtige Hinweise:**

- Die Inhalte werden nicht zu GitHub hochgeladen; im URL-Fragment übergebene Inhalte werden nicht im HTTP-Request an den Server übertragen. Allerdings kann eine Adresse mit Fragment in Browserprotokoll/Synchronisation auftauchen; die PWA entfernt das Fragment beim Laden aus der Adresse.
- **Nur vertrauenswürdige HTML-Dateien öffnen!** Das HTML wird absichtlich mit JavaScript und normalen Browserrechten ausgeführt, weil z. B. Kopierbuttons andernfalls unter iPadOS problematisch sein können. Ein fremdes, manipuliertes HTML-Dokument kann auf Daten und Funktionen derselben GitHub-Pages-Adresse zugreifen.
- HTML mit separat vorhandenen lokalen CSS-, JavaScript- oder Bilddateien funktioniert nicht automatisch. Einzelseiten mit eingebettetem CSS und JS sind ideal.
- Web-APIs sind weiterhin von iPadOS/Safari abhängig. Browser-Speicherung, Pop-ups oder clipboard-Zugriffe können je nach HTML-Datei eingeschränkt sein.
- Der Kurzbefehl über die URL übermittelt große Dateien nicht zuverlässig (URL-Längenbeschränkungen des Systems); dafür bitte die direkte Dateiauswahl nutzen.
- iPadOS bietet keine Möglichkeit, diese PWA als System-Standard-App für `.html`-Dateien einzustellen.

## Testen

Auf der Startseite „Testseite ausprobieren“ auswählen. Mit „Beispieltext kopieren“ lässt sich JavaScript und die Zwischenablage praktisch auf deinem iPad überprüfen.
