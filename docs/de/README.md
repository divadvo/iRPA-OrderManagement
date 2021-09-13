
![](../../images/hero.png)

# Einführung

In diesem Hands-on werden wir Bestelldaten aus einer UI5-App extrahieren und in eine Excel mit Hilfe von SAP Intelligent RPA (SAP iRPA) schreiben.

[Video](../images/OrderManagementVideo.mp4 ':include :type=video width=100% controls' )


## Sprache Wechseln / Change Language

[en](https://divadvo.github.io/iRPA-OrderManagement/#/)  [de](https://divadvo.github.io/iRPA-OrderManagement/#/de/)


## Voraussetzungen

Bevor wir beginnen, stellen Sie bitte sicher, dass Sie folgende Schritte durchgeführt haben
- Richten Sie die Testumgebung ein, wie in [diesem Blog](https://blogs.sap.com/2021/03/22/sap-intelligent-rpa-2.0-onboarding-sap-business-technology-platform-trial-account/) beschrieben. Sie sollten den Desktop Agent lokal installiert haben und Zugriff auf die Cloud Studio-Umgebung haben
- Sie haben die Excel-Datei, die wir verwenden werden [Datei hier](/iRPA-OrderManagement/Demo_Procurement.xlsx ':ignore'). 
- Sie haben Zugang zur [UI5 App](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/orderbrowser/webapp/test/mockServer.html)


## Support

Einige Screenshots beziehen sich auf mehrere vorherige Schritte.
Wenn Sie Fragen haben oder nicht weiterkommen, schreiben Sie bitte in den Chat oder sprechen Sie uns an.


## Übersicht

Wir werden die Automatisierung in mehreren Schritten entwickeln. Wir werden: 
1. Ein Projekt erstellen 
2. UI5 Anwendung erfassen
3. Automatisierungen definieren (UI5 und Excel)
4. Automatisierung testen

Wir werden iterativ sicherstellen, dass wir auf dem richtigen Weg sind.