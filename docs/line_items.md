# Line Items

<!-- ## Saving line Items -->

1. Let's start by creating a variable which will contain multiple line items. Add the `Line Item` step, make sure to check the `list` option and rename the output parameter to 

```
lineItems
```

![](images/0841.png)


2. Create a `for each` loop

![](images/0850.png)

3. Select `Products` as a looping list

![](images/0851.png)

4. Inside the for loop add `Get Element` step, set target = `currentMember` and output = `products`. Rename the step if you wish

![](images/0852.png)

5. Now duplicate the step by `right clicking` > `Duplicate` on the `get product` step. 

![](images/0853.png)

6. Rename the step, set target to `unitPrices` and output to `price`

![](images/0855.png)

![](images/0854.png)

7. Again, duplicate the step and similarly set target to `quantities` element and output to `quantity`.

![](images/0856.png)

![](images/0857.png)

8. Repeat the steps for the total prices elements. Target is `totalPrices`. Output is `total`.

![](images/0858.png)

9. Add a line item variable step. Set the output to `lineItem`.

![](images/0859.png)

10. Click on `Edit activity` and adjust the variables for this data type. 

![](images/0860.png)

Now let's add the data type containing just a single line item to the list of all line itmes. 

11. Insert an `add item` step. List = `lineItems`. itemToAdd = `lineItem`

![](images/0861.png)

If we test the automation now we will see that the list is being generated. 

![](images/0862.png)