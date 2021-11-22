# Define Third Screen

## Define Third screen

Next we will add the third screen from within the same UI5 app. This way the bot can recognize the details of a specific order

1. Open the [UI5 app](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/orderbrowser/webapp/test/mockServer.html) is opened in a seperate window, and enter `Bottom-` in the search. Make sure the order `2686` is found. Click on that order to see the detail view. Keep the window open.


![](images/0130_ThirdScreen.png)

2. Within the cloud studio, click on `...` next to the first screen capture and select `Add Capture to Current Screen`.


![](images/0140_AddCaptureToCurrentScreen.png)

3. `Refresh` and Select the window with `Browse Orders`

4. Name the new capture, e.g.

```
Order Details Screen
```

5. Press `Capture`

![](images/0150_PickScreenThird.png)


## Define elements on third screen

### Order Number

1. Select the third screen we just defined `Order Details Screen`

2. Click on the order number in the preview

3. Rename the element, e.g.

```
Order Number
```

4. Don't click on declare element yet.

![](images/0160_SelectOrder.png)

As before, we are going to adjust the criteria.

5. Click on the `text` criteria.

6. A popup will be opened. Change the `operator` to `contains`.

7. Change `value` to `Order ` **with a space at the end**

```
Order
```

8. `Apply` the criteria.

9. Don't forget to click on `Declare Element`

![](images/0170_AdjustOrderCriteria.png)

![](images/0171_AdjustOrderCriteria-Declare.png)


### Price

1. Select the third screen we just defined `Order Details Screen`

2. Click on the price in the preview

3. Remove the text criteria

![](images/0190_PriceDeleteTextCriteria.png)

4. Add the `id` of the element as criteria instead. This will uniquely identify the price.

![](images/0200_SelectIdPrice.png)

5. Rename the element, e.g.

```
Price
```
6. Make sure the correct id criterion is selected and don't forget to click on `Declare Element`

![](images/0210_RenamePrice.png)


### Address

Next, we will define address in a different way, as a collection of multiple elements

1. Click on the name under shipping address in the preview

![](images/0220_SelectAddress.png)

2. Remove the `text` criteria, it's too specific

![](images/0230_RemoveAddressCriteria.png)


3. Select `class` as element

![](images/0240_AddressPickClass.png)

![](images/0241_AddressPickClass.png)

Within IRPA we can also see the underlying technical document structure of the page. We will use this to more precisely select the element that we want.

4. Click on `both` at the top to show both the preview, as well as the technical structure.

5. Select the `div` (the container), instead of `span`. This way we will be able to connect it to the other elements of the address.


![](images/0250_OpenTree.png)

6. `div` is selected. Now let's remove the `text` criteria as it is too specific.

![](images/0260_PickDivAbove.png)

7. Add the `class` criteria instead.

![](images/0270_AddClassToRestrict.png)

8. Class is selected. Set the name, e.g.
```
Shipping Address
```

9. Click on `declare element`
![](images/0280_RenameShipping.png)

Now the element cannot be uniquely identified, because multiple elemnts fulfill the same criteria. RPA shows this in the warning status message as well as a `yellow !` in the `declared elements` section.

10. We can create a collection of these multiple elements, by clicking the `3 tags/triangles` under declared elements, while `shipping address` is selected.

![](images/0290_ShippingAsCollection.png)

As a result, a collection is defined. The `check mark` is now green. The element is uniquely identified. And the technical page structure shows that multiple elements are contained in this collection (0, 1, 2, 3, 4).

![](images/0300_ShippingResult.png)

11. Don't forget to save the progress by clicking on the `save` button at the top right.

![](images/0520_dontForgetToSave.png)
