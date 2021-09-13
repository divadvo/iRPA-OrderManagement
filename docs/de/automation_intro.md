# Einführung in die Automatisierung

## Übersicht
Die Bildschirme und Elemente sind definiert. Wir können nun die eigentliche Automatisierung erstellen.

Lassen Sie uns darüber nachdenken, was unser Bot tun sollte. Im Groben sollte er: 
- Excel öffnen und einige Daten von dort auslesen 
- Eine Webseite öffnen und basierend auf den Daten aus Excel einige andere Daten von dort extrahieren 
- Die gefundenen Daten zurück in Excel schreiben

Wir können mit der Erstellung unserer Automatisierung auf dieser hohen Ebene beginnen und dann die Details implementieren.

## Unter-Automatisierungen Erstellen

Beginnen wir mit der Erstellung von 3 Automatisierungen: eine Hauptautomatisierung, eine für den UI5-Teil und eine für Excel.

1. Klicken Sie auf  `create` > `automation`

![](../images/0600.png)


2. Wählen Sie die Version, die als lokal (`local`) gekennzeichnet ist. Dies ist die lokal installierte Version Ihres Desktop-Agenten. Auch wenn im Dropdown-Menü eine höhere Version verfügbar ist, wählen Sie bitte die lokale Version aus, um sicherzustellen, dass die Automatisierung auf Ihrem Computer ausgeführt werden kann.

![](../images/0601.png)

3. Klicken Sie auf  `Confirm`

![](../images/0602.png)

4. Benennen Sie die Automatisierung, z.B.

```
Order Management
```

![](../images/0603.png)


Es wurde eine leere Automatisierung erstellt.


![](../images/0604.png)

Wiederholen Sie die Schritte `1` - `4` um 2 weitere Automatisierungen zu erstellen:

```
Web Portal
```

und 

```
Write Excel
```

![](../images/0605.png)


## 🔹 Automatisierungsschritte hinzufügen

Wir werden diesen Vorgang mehrmals wiederholen, um neue Schritte zur Automatisierung hinzuzufügen. Bitte wiederholen sie diesen Vorgang in den nachfolgenden Abschnitten.

1. Klicken Sie auf das leere Feld in der Vorschau, um alle anderen offenen Optionen zu schließen

2. Suchen Sie in der Suchleiste nach dem Schrittnamen

3. Falls nötig, klicken Sie auf `clear filter`, um alle verfügbaren Schritte anzuzeigen.

4. Wählen Sie die gewünschte Aktion aus und ziehen Sie diese per `drag and drop` an die richtige Stelle.

![](../images/0700_DropStep.png)