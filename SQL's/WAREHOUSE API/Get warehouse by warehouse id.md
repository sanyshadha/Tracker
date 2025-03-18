```SQL
select
sw.slr_wh_id as "sellerWarehouseId",
sw.slr_id as "sellerId",
sw.wh_nm as "warehouseName",
sw.wh_addr_line_1 as "warehouseAddressLine1",
sw.wh_addr_line_2 as "warehouseAddressLine2",
sw.wh_addr_line_3 as "warehouseAddressLine3",
sw.wh_city as "warehouseCity",
sw.wh_state_cd as "warehouseStateCode",
sw.wh_cntry_cd as "warehouseCountryCode",
sw.wh_postal_cd as "warehousePostalCode",
sw.wh_postal_cd2 as "warehousePostalCode2",
sw.wh_lat as "warehouseLatitude",
sw.wh_long as "warehouseLongitude",
sw.status as "status"
from spares.seller_warehouses sw
where sw.slr_wh_id = 2
```

