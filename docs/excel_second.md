# Excel - Second Worksheet

Desired result:

![](images/0921.png)

1. Make sure that `Activate Worksheet` is added in the previous step. This action will switch to the second worksheet with the order details. worksheetName = `Details`

![](images/0909.png)

2. Create a `For Each` loop to loop through the order line items. The looping list is `lineItems`

![](images/0910.png)

3. Drop `Set Values (Cells)` step inside the loop

![](images/0911.png)

4. Adjust parameters. The data cells start at row `2`, the index starts at `0`, so we use this formula to termine the correct cell

```
"A" + (Step9.index + 2)
```

`Values` = 

```
Step9.currentMember.Product
```

IMPORTANT: Make sure that you use button `Edit Expression` to enter formulas in `rangeDefinition`. Text should be in blue colloer, not black!

![](images/0912.png)

1. Duplicate and repeat for unit price, with column `B` instead.


![](images/0913.png)

6. Duplicate and repeat for quantity, with column `C` instead.

![](images/0914.png)

7. Duplicate and repeat for total, with column `D` instead.

![](images/0915.png)

8. Save all automations 

9. Within the main automation `Order Management` we now pass the outputs from `Web Portal` into inputs of `Write Excel`

![](images/0916.png)

10. Make shure that output parameters are defined for both sub-automation as shown on pictures below:

![](images/0930.png)

![](images/0931.png)
