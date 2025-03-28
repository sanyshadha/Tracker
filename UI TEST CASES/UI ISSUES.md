- [ ] Copart Parts Logo overlaps the Advance Driver Assistance System option in the header (Responsiveness Issue)
- [ ] Scrolling on additional categories drop-down scrolls the entire page 
- [ ] Typing in the search box must give dynamic suggestions
- [x] Cannot add vehicle to the garage if it is not present in the DB (vehicle_master)
	- [x] ![[Pasted image 20250204120932.png]]
- [x] Cannot add vehicle using VIM 
- [x] Cannot remove vehicle from garage

----

| Id  | Location                                                                                     | Issue                                                                                                                                                                                                                                                                         |
| --- | -------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Search Box in Home Page                                                                      | After entering the search-key, when the logo is clicked, the search parameter doesnt reset and when still search is hit it doesnt give the search result                                                                                                                      |
| 2   | Header                                                                                       | The Air & Fuel delivery renders the products which are in DB but clicking the Brake & Brake Pads doesnt render the Acura Brake Pads                                                                                                                                           |
| 3   | Cart                                                                                         | Procced to Pay is enabled even when the cart is empty                                                                                                                                                                                                                         |
| 4   | Cart                                                                                         | Proceed to Pay works even when user is not logged in                                                                                                                                                                                                                          |
| 5   | Cart                                                                                         | +/- options unavailable for the products in cart                                                                                                                                                                                                                              |
| 6   | Cart - Post Login                                                                            | Adding one item adds +3 items                                                                                                                                                                                                                                                 |
| 7   | CheckOut - Post Login                                                                        | +/- options unavailable for reviewing                                                                                                                                                                                                                                         |
| 8   | CheckOut - Post Login                                                                        | The sum of items dont add up to the total bill amount                                                                                                                                                                                                                         |
| 9   | Product-Listing page ([Copart Spares](https://g2-member-qa4.copart.co.uk/spares/product/34)) | Count of Number of Items in the Inventory on listing page doesnt match with the count of items in inventory on the review-items page during checkout                                                                                                                          |
|     |                                                                                              |                                                                                                                                                                                                                                                                               |
| 1   | Cart Button                                                                                  | During the checkout page the cart button must be disabled / if enabled must again redirect to show the cart, instead its populating the cart items again even while checking out, for the guest user clicking the cart is not displaying the cart items on the check out page |
| 2   |                                                                                              |                                                                                                                                                                                                                                                                               |
|     |                                                                                              |                                                                                                                                                                                                                                                                               |
| 1   | Save for Later                                                                               | The status must be displayed as OUT of STOCK                                                                                                                                                                                                                                  |
| 2   | Cart Icon During Checkout                                                                    | The Cart Icon must be diabled                                                                                                                                                                                                                                                 |
| 3   | Order not gettng abandoned                                                                   | The order must be reflected as abandoned in the db after navigating back from checkout                                                                                                                                                                                        |
| 4   | Quantity adj                                                                                 | The quantity must not be automatically adjusted, from db (the cart item must be active but aval. quantity must be shown) + (Push notification "Cart Quantity Changed" )                                                                                                       |


#2025-02-25

| Id  | Name                        | Desc                                                                                  | Expected                                                       |
| --- | --------------------------- | ------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| 1   | Reset Search Filters        | The user doesn't have a dedicated reset search filters button                         | Clear Filters button must be available near breadCrumbs (EBay) |
| 2   | Add to cart -> buy now flow | When user clicks on add to cart, and then again clicks on buy now the quantity get x2 | The quantity must remain same as selected by user              |


#2025-02-28
1) Reset Filters status
2) Whishlist



--------

1) The logout button must redirect to spares page, but is redirecting to the G2 portal
2) The session expired message / pop-up is not being displayed
3) The back button must be disabled after a successful payment completion