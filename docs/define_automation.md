# Define Automation

## Overview
The screens and elements have been defined. We can now create the actual automation.

Let's think about what our bot should do. On a very high level it should:
- Open Excel and read out some data from there
- Open a webpage and extract some other data from there, based on the data from excel
- Write the found data back into excel

We can start creating our automation from this high level and go down, implementing the details. 

## Creating sub-automations

Let's start by creating 3 automation: one main one, one for the UI5 part, one for Excel one

1. Click on `create` > `automation`

![](images/0600.png)


2. Select the version which is tagged `local`. This is the version of your desktop agent installed locally. Even if a higher version is available in the dropdown, please select the `local` version, to make sure that the automation can run on your machine.

![](images/0601.png)

3. Click `Confirm`

![](images/0602.png)

4. Name the automation, e.g.

```
Order Management
```

![](images/0603.png)


An empty automation has been created.

![](images/0604.png)

Repeat the steps `1` - `4` to create 2 more automations:

```
Web Portal
```

and 

```
Write Excel
```

![](images/0605.png)


## 🔹 How to add automation steps 

We will repeat this process multiple times to add new steps to the automation. Please do this in the following steps.

1. Press on the empty space within the preview to close all other open options

2. Search for the step name in the seach bar

3. If necessary, click on `clear filter` to show all available steps

4. Select the desired action and `drag and drop` it in the correct position

![](images/0700_DropStep.png)

## Main Automation

Let's define the general structure of our automation. Here is the data we want from excel:

![](images/0705.png)

1. We want to open Excel. Repeat the steps above for `Open Excel Instance`.

![](images/0701.png)

2. We want to open the correct workbook. Repeat the steps above for `Open Workbook`.

In the parameters on the right, edit the expression and enter the full path to your file. Make sure the path is within quotation marks `"..."` E.g.

```
"C:\Users\you\Desktop\Demo_Procurement.xlsx"
```


![](images/0702.png)

![](images/07021.png)

3. We want to open a specific worksheet. Repeat the steps above for `Activate Worksheet`. Set `worksheetName` = 

```
Overview
```


![](images/0703.png)


4. We want to get a value from a cell. Repeat the steps above for `Get Values (Cells)`. Set `rangeDefinition` = `B1`. And rename outputParamenter to  

```
supplierName
```

This means that this step will run and the result (value from cell B1) will be saved in a variable called `supplierName`


![](images/0704.png)

5. And `Web Portal` and `Write Excel` subautomations. So far they are not doing anything, but just acting as placeholders. 


![](images/0706.png)

6. At the end we want to make sure that Excel is not used by iRPA anymore. We release the instance. Repeat the steps above for `Release Excel Instance`


![](images/0707.png)


## 🔹 How to test automation

Let's not do too much work without seeing what the bot does and if we make any mistakes. 

1. `Save` the automation, then click on `test`.

2. Select your environment.

3. Click on `test`.


![](images/0708.png)

It takes a while for the desktop agent to download, process and run the automation. Here are some of the messages you will see:

|  |  |  |
:-------------------------:|:-------------------------:|:-------------------------:|
![](images/0709.png)  |  ![](images/0710.png) |  ![](images/0711.png)


After the automation has completed, you can see the debug screen (`Tester`). In here you can either check the output of the `test console` or click on single steps in the automation to see the details on the right side. 

4. For instance, click on the step `Get Values (cells)` and we see the correct output value on the right `Bottom-Dollar Markets`. The automation ran correctly

![](images/0712.png)


## Web Automation

Next we will define the automation within the UI5 app. On a high level it will:
- Enter supplier name in the search box and search
- Click on the result
- This will open the details of the order
- RPA will save all the relevant information, which we will later write into Excel

1. Click on `Web Portal` either in the menu on the left or on the tab at the top.

![](images/0800.png)

2. Drag and drop the screen activity `Orders List Screen`, because we will be interacting with this specific application we defined.

![](images/0801.png)

3. Click on the screen activity and then on `Define Screen Activities`.

![](images/0802.png)

4. Drag and drop `Start screen` onto the screen preview

![](images/0803.png)

5. Make sure the step is inside the screen activity and target is set to `orders list screen`.

![](images/0804.png)

6. Change the navigator from `Internet Explorer` to `Chrome`, so that RPA open the page in Chrome.


|  |  |  |
:-------------------------:|:-------------------------:|:-------------------------:|
![](images/0804.png)  |  ![](images/0805.png) |  ![](images/0806.png)

7. Drag `Wait (Screen)` operator onto the screen preview and make sure the target is set correctly. RPA will wait until the screen actually loads. 


![](images/0807.png)

8. Aditionally, RPA should wait to ensure that the search bar loads as well. Drag `Wait (Element)` onto the search bar preview. Make sure the target is set to search bar element.


![](images/0808.png)

9. Add `Search string` action. Make sure the target is correct. 

![](images/0809.png)

### Input Parameter

But how do we get the name of the supplier we got from Excel? It's not available in the `Web Portal` subautomation yet. That variable is only available in the main automation `Order Management`. But we can pass the variable to the subautomation using `parameters`. 

10. Close the panel

![](images/0810.png)

11. Press on empty space to change the settings of the automation. Click on `I/O` > `Add new input parameter`.


![](images/0811.png)

12. Create input parameter named 

```
CustomerName
```

Type is `string`. Click on the empty space to save these settings. 


![](images/0812.png)

13. Now back in the `search string` step we can select the `CustomerName` variable, which is our input parameter passed to the subautomation.


![](images/0813.png)

However, the value still hasn't been passed from the main automation. To do that

14. Go to the main automation either from the left side or from the tabs at the top. Select the `Web Portal` step and provide the input parameter


![](images/0814.png)

![](images/0815.png)

![](images/0816.png)


## Continuing Web Automation

Next let's wait for the search results to load

1. Add `Wait (Element)` with target of the row


![](images/0817.png)

2. Select `orderFound` element in the popup and `confirm`.

![](images/0818.png)

3. Add `click` step with the target of the row --> `orderFound` element. RPA will wait for the row to appear and then click on it.


![](images/0819.png)

## Details view automation

1. RPA should wait for the details screen to open and load. Add `Wait (Element)` step with `Order Number` as target


![](images/0820.png)