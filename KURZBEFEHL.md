# iPad-Kurzbefehl: „HTML öffnen“

Die PWA selbst kann unter iPadOS nicht im Teilen-Menü als Dateiziel erscheinen. Ein Apple-Kurzbefehl kann eine Datei jedoch so codieren, dass die Webseite sie anzeigen kann.

## Variante A: Direktübergabe (empfohlen für KLEINE HTML-Dateien)

Voraussetzung: Deine GitHub-Pages-Adresse, etwa `https://DEINNAME.github.io/html-oeffner/`.

In der App „Kurzbefehle“:

1. Mit `+` einen Kurzbefehl anlegen, Name **HTML öffnen**.
2. In den Details **Im Teilen-Menü anzeigen** aktivieren, als empfangenen Inhalt **Dateien** (ggf. außerdem Text) einstellen.
3. Aktion **Base64 codieren** hinzufügen. Eingang ist die **Kurzbefehleingabe**. Wenn auswählbar, Zeilenumbrüche auf **Keine** einstellen.
4. Aktion **Text** hinzufügen. Darin zuerst folgende Adresse eingeben:
   `https://DEINNAME.github.io/html-oeffner/#b64=`
   Gleich **dahinter** die magische Variable **Base64-codiert** aus Schritt 3 einsetzen – ohne Leerzeichen oder Zeilenumbruch.
5. Aktion **URLs öffnen** hinzufügen und das Ergebnis der **Text**-Aktion übergeben.
6. Speichern.

Test: Dateien-App → eine `.html`-Datei lange drücken → **Teilen** → **HTML öffnen**. Der HTML-Öffner sollte die Seite darstellen. Der Kurzbefehl öffnet dabei ggf. Safari anstatt der Homescreen-App, je nach iPadOS-Verhalten.

**Grenze:** Der komplette HTML-Inhalt steckt vorübergehend in der URL. Das funktioniert nicht zuverlässig bei großen Dateien. Für längere HTML-Dateien nutze die direkte Dateiauswahl in der PWA oder Variante B.

## Variante B: Zwischenablage (robuster bei längeren Dateien)

Erstelle einen zweiten Kurzbefehl, zum Beispiel **HTML öffnen (Zwischenablage)**:

1. „Im Teilen-Menü anzeigen“, Eingabe **Dateien**.
2. **Base64 codieren**: Eingang **Kurzbefehleingabe**, Zeilenumbrüche **Keine**.
3. **In Zwischenablage kopieren**: den base64-codierten Text kopieren.
4. **URL** oder **Text**: `https://DEINNAME.github.io/html-oeffner/#clip`
5. **URLs öffnen** mit dieser Adresse.
6. Auf der Webseite **HTML aus Zwischenablage öffnen** antippen und gegebenenfalls Safaris „Einsetzen“-Bestätigung akzeptieren.

Falls die Zwischenablage-Leseberechtigung verweigert wird, bietet der Öffner einen Bereich zum manuellen Einfügen.

## Ohne Kurzbefehl

Öffne deine Homescreen-PWA → **HTML-Datei auswählen** → gewünschte `.html` oder `.htm` auswählen. Das ist der einfachste und zuverlässigste Weg, besonders für größere Dateien.

Hinweis: Vorlagen / Anleitungen aus dem Internet können Kurzbefehle enthalten, die Daten weiterleiten. Verwende nur Kurzbefehle, deren Aktionen du überprüfen kannst.
