
### API : `{{baseUrl}}/api/v1/orders/{sellerId}?start=0&rows=5`

----

#### For `sellerId`=2 

| ID       | NAME                                                      | API vs DB                                                                                                                   | DB vs API                                                                                                                                                  | SQL QUERY                                                                                                              |
| -------- | --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| 1        | Get Orders                                                | The API call works good with `sellerId` as 2 there are 3 records which it fetches from DB (Confirmed and INITIATED) orders. | The (order_details) table has 3 records for the same `sellerId` and populates accordingly                                                                  | ```select * from spares.order_details od where ord_dtl_status not like 'ABANDONED'<br>```                              |
| 2        | Accept Order                                              | The API call words good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_activity) table but the status is not being updated in the (order_master) table | ```select * from spares.order_master om where ord_mstr_id = 161```<br><br>```select * from spares.order_activity oa``` |
| 3        | Reject Order                                              | The API call works good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_activity) table but the status is not being updated in the (order_master) table | ```select * from spares.order_master om where ord_mstr_id = 161```<br><br>```select * from spares.order_activity oa``` |
| Comments | The Rejected Order status can be changed back to accepted | This cannot happen once rejected the process needs to be re-init                                                            |                                                                                                                                                            |                                                                                                                        |
| 4        | Update Shipping Status by Seller                          | The API call works good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_activity) table but the status is not being updated in the (order_master) table | ```select * from spares.order_master om where ord_mstr_id = 161```<br><br>```select * from spares.order_activity oa``` |
| Comments | The Shipped Order status can be changed back to accepted  | This cannot happen, once the order is shipped the seller cannot modify it to accepted                                       |                                                                                                                                                            |                                                                                                                        |
| 5        | Update Delivery Status by Seller                          | The API call works good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_activity) table but the status is not being updated in the (order_master) table |                                                                                                                        |
| 6        | Cancel Order by Member                                    | The API call works good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_disputes) table but the status is not being updated in the (order_master) table | ```select * from spares.order_master om where ord_mstr_id = 161```<br><br>```select * from spares.order_disputes od``` |
| 7        | Return Order by Member                                    | The API call works good with the passed json                                                                                | The (order_details) is getting updated and the API call is noted in (order_disputes) table but the status is not being updated in the (order_master) table | ```select * from spares.order_master om where ord_mstr_id = 161```<br><br>```select * from spares.order_disputes od``` |

### ISSUES

1) Get Orders must only fetch the INIT and ACCEPTED Orders, instead also fetches the Canceled and Refund Orders
2) The Accept Orders must only accept orders where the status is Confirmed instead does for everything
3) Same with Reject
4) Same with Update Shipping
5) Cancel must work only for orders which are confirmed 
6) Same with Return also the return amount must be auto fetched, as of now the amount is given by seller itself !!


