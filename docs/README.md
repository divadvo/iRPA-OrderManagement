
![](images/hero.png)

# Intro

In this hands-on we are going to automate the extraction of order data from a UI5 app into Excel, with help of SAP Intelligent RPA (SAP iRPA).

[Video](images/OrderManagementVideo.mp4 ':include :type=video width=100% controls' )


## Sprache Wechseln / Change Language

[en](https://divadvo.github.io/iRPA-OrderManagement/#/)  [de](https://divadvo.github.io/iRPA-OrderManagement/#/de/)


## Prerequisites

Before we start, please make sure you have 
- Setup the trial environment, as described in [this blog](https://blogs.sap.com/2021/03/22/sap-intelligent-rpa-2.0-onboarding-sap-business-technology-platform-trial-account/). You should have the Desktop Agent installed locally and have access to the Cloud Studio environment
- You have the Excel file we are going to use. [Download here](/iRPA-OrderManagement/Demo_Procurement.xlsx ':ignore'). 
- Have access to the [UI5 app](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/orderbrowser/webapp/test/mockServer.html)


## Getting help

Please note that both instructions and screenshots are given. Some screenshots are related to multiple previous steps.

If you have any questions or get stuck, please let us know.


## Getting started 

We will develop the automation in multiple steps. We will: 
1. Create a project
2. Capture the application screen
3. Define automation: on UI5 and Excel sides
4. Test automation

We will iteratively ensure that we are on the right track.