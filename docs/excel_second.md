# Excel - Second Worksheet

Desired result:

![](images/0921.png)

9. Add `Active Worksheet` step to which to the second worksheet with the order details. worksheetName = `Details`

![](images/0909.png)

10. Create a `For Each` loop to loop through the order line items. The looping list is `lineItems`

![](images/0910.png)

11. Drop `Set Values (Cells)` step inside the loop

![](images/0911.png)

12. Adjust parameters. The data cells start at row `2`, the index starts at `0`, so we use this formula to termine the correct cell

```
"A" + (Step9.index + 2)
```

`Values` = 

```
currentMember.Product
```

![](images/0912.png)

13. Duplicate and repeat for unit price, with column `B` instead.


![](images/0913.png)

14. Duplicate and repeat for quantity, with column `C` instead.

![](images/0914.png)

14. Duplicate and repeat for total, with column `D` instead.

![](images/0915.png)

15. Within the main automation `Order Management` we now pass the outputs from `Web Portal` into inputs of `Write Excel`

![](images/0916.png)