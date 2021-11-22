# Continue Defining Third Screen


## Define Line Items

Next we will define the line items of an order. We will define each column as a collection.

### Products

1. Press on the first product cell. Click on the `>` > just before selected `TR` TR element. Make sure that the second `TD` is selected in the tree view. 

![](images/0310.png)

![](images/0311.png)

2. Name this element, e.g.

```
Products
```
3. Remove the text criteria


![](images/0312.png)

4. Select `id` instead

![](images/0320.png)

![](images/0321.png)

5. Modify the criteria. Id should `contain` `cell0`, meaning the 0th column. 

```
cell0
```

![](images/0330.png)

Now all 3 product cells have been identified. We want to define these as a collection.

6. Click on `declare element`.

![](images/0340.png)


7. Click on `3 triangles`, to define these elements as a collection

![](images/0350.png)

The elements have been detected. `TD` is the collection. The elements have been uniquely identified. Click on `Save` button.


![](images/0360.png)


### Unit Prices

1. Click on the first product row. Now we want to select the unit price in the first row.

2. Make sure it's the `SPAN` element in the tree, containing multiple elements (`24.34 EUR` instead of just `24.34`)


![](images/0400.png)

![](images/0401.png)

![](images/0402.png)


3. Remove text as criteria

![](images/0410.png)

4. Set `class` as criteria instead.

![](images/0411.png)

![](images/0412.png)

Now we want to make sure that the collection of multiple elements is based on the table cells. For this we will use `TD` as the criteria for finding the `SPAN` elements. 

5. Right click on `TD` and select `add to criteria`.

![](images/0420.png)

`TD` is now part of the criteria. 

![](images/0421.png)

6. Adjust the `id` of `TD` to be `contains` and value:

```
cell1
```

![](images/0430.png)

7. `Rename` the element to e.g.

```
unitPrices
```

8. Click on `declare element`

![](images/0440.png)


Now instead of defining a collection like we did before, we will declare the collection based on the parent element `TD` we added as condition. This way the bot will loop over the `TD` cells and find the `SPAN` within these.

9. Click on `...` next to `TD` and click `set as collection`.

![](images/0450.png)

The element has been defined.

![](images/0460.png)

10. Don't forget to save the progress by clicking on the `save` button at the top right.

![](images/0521_dontForgetToSave.png)

### Total Prices

The last column is `total prices`. That column has a similar structure as `unit price`, so we will speed up the definition process by copying `unitPrice` element and adjusting the configuration slightly.

1. Click on `...` next to `unitPrices`. 

2. Select `duplicate`


![](images/0470.png)

3. Name the new element, e.g.

```
totalPrices
```

Click on button `Duplicate`

![](images/0480.png)


Next, adjust the `id` of the cell from 2nd=`1` to 4th=`3` (counting starts from `0`)

4. Click on `id` under `td`.

![](images/0490.png)

5. Set criteria to `contains`  and value

```
cell3
```

![](images/0500.png)

The total prices have been defined. We didn't have to define them from scratch and were able to save time by duplicating another definition.


![](images/0510.png)


### Quantities

1. Click on the quantities cell. Expand and make sure the `td` (table cell) element is selected in the tree view.

![](images/1000.png)

![](images/1001.png)

2. Remove the text criteria. Adjust the criteria to `id`. In the popup choose `contains` and `cell2`.

![](images/1002.png)

![](images/1003.png)

![](images/1004.png)

3. Rename the element to `quantities`, make sure the criteria are like in the screenshot.

4. Click on declare and make the element a collection by clicking on the triangles in the declared elements section.

![](images/1005.png)

![](images/1006.png)


## Save


The screens and elements have been defined. We can now move on to defining the automation.

Don't forget to save your work by clicking `save` in the top right.


![](images/1010_dontForgetToSave.png)


Nice! We have completed the capturing of the application and can now start creating the actual automation.