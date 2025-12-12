# Rapid POS ShipStation Connector v2.03.01 Release Notes

_Release Date: November 24, 2025_

---

## Bug Fixes and Performance Enhancements

### Optimized ShipStation Order Processing Logic
Enhanced the ShipStation order processing logic to prevent duplicate sends from both the **ticket complete** process and the **catch-all** process.
- Refactored SQL query in **`USER_VI_SHIP_STATION_HDR`** to exclude documents present in **`USER_SHIPSTATION_WRK`**.  
- In the **AddOrders** catch-all process, updated logic to filter orders by **ticket date older than 10 seconds**, preventing duplicate sends caused by timing overlap.  
- Improved **code efficiency and readability** by consolidating update/insert operations and removing unnecessary checks.
