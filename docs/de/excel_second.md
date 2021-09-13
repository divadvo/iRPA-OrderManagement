# Excel - Zweites Arbeitsblatt

Gewünschte Ergebnis:

![](../images/0921.png)

1. Fügen Sie den Schritt `Active Worksheet`, um das zweite Arbeitsblatt mit den Auftragspositionen zu öffnen. worksheetName = `Details`

![](../images/0909.png)

2. Erstellen Sie eine For `For Each` Schleife, um die Auftragspositionen zu durchlaufen. Die Liste für die Schleife ist `lineItems`

![](../images/0910.png)

3. Fügen Sie den Schritt `Set Values (Cells)` innerhalb der Schleife ein.

![](../images/0911.png)

4.	Passen Sie die Parameter an. Die Zellen beginnen in Zeile `2`, der Index beginnt bei `0`. Aus diesem Grund können wir diese Formel verwenden, um die richtige Zelle zu bestimmen:

```
"A" + (Step9.index + 2)
```

`Values` = 

```
Step9.currentMember.Product
```

![](../images/0912.png)

5. Duplizieren Sie den Schritt und wiederholen Sie den Vorgang für den Stückpreis und Spalte `B`.


![](../images/0913.png)

6. Duplizieren Sie den Schritt und wiederholen Sie den Vorgang für die Menge und Spalte `C`.

![](../images/0914.png)

6. Duplizieren Sie den Schritt und wiederholen Sie den Vorgang für den Gesamtpreis und Spalte `D`.

![](../images/0915.png)

8. Speichern Sie alle Automatisierungen

9. Innerhalb der Hauptautomatisierung `Order Management` übergeben wir nun die Ausgaben aus `Web Portal` in die Eingaben von `Write Excel`

![](../images/0916.png)