# Hauptautomatisierung

## Schritte definieren

Lassen Sie uns die allgemeine Struktur unserer Automatisierung definieren. Hier sind die Daten, die wir aus Excel benötigen:

![](../images/0705.png)

1. Wir möchten Excel öffnen. Wiederholen Sie die zuvor beschriebenen Schritte, um den Schritt `Open Excel Instance` hinzuzufügen.

![](../images/0701.png)

2. Wir möchten die richtige Arbeitsmappe öffnen. Fügen Sie den Schritt `Open Workbook` hinzu.

Bearbeiten Sie in den Parametern auf der rechten Seite, ändern Sie `expression` und geben Sie den vollständigen Pfad zu Ihrer Datei ein. Stellen Sie sicher, dass der Pfad in Anführungszeichen `"..."` steht, z.B.

```
"C:\Users\you\Desktop\Demo_Procurement.xlsx"
```


![](../images/0702.png)

![](../images/07021.png)

3. Wir möchten ein bestimmtes Arbeitsblatt öffnen. Fügen Sie den Schritt `Activate Worksheet` hinzu. `worksheetName` = 

```
Overview
```


![](../images/0703.png)


4. Wir möchten einen Wert aus einer Zelle auslesen. Fügen Sie den Schritt `Get Values (Cells)` hinzu. `rangeDefinition` = `B1`. Und benennen Sie `outputParamenter` um in

```
supplierName
```

Dies bedeutet, dass dieser Schritt ausgeführt wird und das Ergebnis (Wert aus Zelle B1) in einer Variablen namens `supplierName` gespeichert wird.


![](../images/0704.png)

5. Fügen Sie `Web Portal` and `Write Excel`  Unter-Automatisierungen hinzu. Bislang tun sie nichts, sondern dienen nur als Platzhalter.


![](../images/0706.png)

6. Am Ende möchten wir sicherstellen, dass Excel nicht mehr von iRPA verwendet wird. Wir geben die Instanz frei. Fügen Sie den Schritt `Release Excel Instance` hinzu.


![](../images/0707.png)

## 🔹 Umgebung einrichten

Bevor wir unsere Automatisierung testen können, müssen wir eine Umgebung einrichten, die eine Landschaft innerhalb von iRPA darstellt. Zum Beispiel können wir Umgebungen für Dev, Test und Prod definieren. Wir werden Ihren lokalen Desktop-Agenten zu einer Testumgebung hinzufügen, damit wir unsere Automatisierungen testen können.

1. Zurück auf dem Startbildschirm der Cloud Factory, gehen Sie zu `environemnts`. Dann klicken Sie auf `New Environment`

![](../images/1010.png)

2. Benennen Sie die Umgebung, z.B. `Test` mit type = `Test`

![](../images/1011.png)

3. Die Umgebung ist nun erstellt. Fügen wir nun einen `agent` hinzu, in unserem Fall Ihren lokalen Desktop-Agenten, der die Automatisierung tatsächlich ausführen wird. Klicken Sie `Add Agent`.

![](../images/1012.png)

4. Wählen Sie Ihren Agenten aus und klicken Sie auf `Add agent`.

![](../images/1013.png)

5. Wir können nun die Liste der Agenten aufrufen, indem wir auf  `Agents` klicken.

![](../images/1014.png)

6. Hier sehen Sie Ihren Agenten, den Sie gerade hinzugefügt haben. Wir können nun fortfahren und die Automatisierung testen.

![](../images/1015.png)


## 🔹 Wie testet man die Automatisierung?

Wir sollten uns nicht zu viel Änderungen vornehmen, ohne zu sehen, was der Bot macht und ob wir Fehler machen.

1. Speichern Sie die Automatisierung (auf `Save` klicken) und klicken Sie dann auf `test`.

2. Wählen Sie Ihre Umgebung aus.

3. Klicken Sie auf `test`.


![](../images/0708.png)

Es dauert eine Weile, bis der Desktop-Agent die Automatisierung heruntergeladen, verarbeitet und ausgeführt hat. Hier sind einige der Meldungen, die Sie sehen werden:

|  |  |  |
:-------------------------:|:-------------------------:|:-------------------------:|
![](../images/0709.png)  |  ![](../images/0710.png) |  ![](../images/0711.png)


Nachdem die Automatisierung abgeschlossen ist, sehen Sie den Debug-Bildschirm (`Tester`). Hier können Sie entweder die Ausgabe der Testkonsole (`test console`) überprüfen oder auf einzelne Schritte in der Automatisierung klicken, um die Details auf der rechten Seite zu sehen.

4. Klicken Sie zum Beispiel auf den Schritt `Get Values (cells)` und wir sehen den korrekten Ausgabewert auf der rechten Seite: `Bottom-Dollar Markets`. Die Automatisierung wurde korrekt ausgeführt

![](../images/0712.png)

5. Bitte vergessen Sie nicht, sowohl Excel als auch die UI5-App nach jedem Test der Automatisierung zu schließen.