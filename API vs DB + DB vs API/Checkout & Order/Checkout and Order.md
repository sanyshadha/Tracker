
| ID  | NAME                    | API vs DB                                                        | DB vs API                               | SQL QUERY                          |
| --- | ----------------------- | ---------------------------------------------------------------- | --------------------------------------- | ---------------------------------- |
| 1   | Validate Cart           | API takes new keys / duplicate keys and shows new alert messages | Works fine                              | select * from spares.cart_items ci |
| 2   | Delete Shipping Details | API works fine                                                   | DB isnt updated                         |                                    |
| 3   | Update Shipping Details | API throws 500 error                                             | DB isnt updated                         |                                    |
| 4   | Order Confirmation      | API action can be changed yet shows 200 OK                       | DB is getting upfated                   |                                    |
| 5   | Payment Initiate        | API takes invalid date                                           | Cart is still active even after payment |                                    |