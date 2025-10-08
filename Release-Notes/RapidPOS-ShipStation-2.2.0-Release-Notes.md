# Rapid POS ShipStation Connector v2.2.0 Release Notes

_Release Date: April 8, 2025_

---

## New Functionality

### Connector Configuration for Item Unit Weight
Added a connector configuration option for the value pushed to ShipStation as the **Item’s Unit Weight**.

- The three available unit choices are **pounds**, **ounces**, or **grams**, with the default being **pounds**.  
- This configuration applies globally to all items pushed from Counterpoint to ShipStation.

### Country Code Support
Added functionality to send the Country value (from both billing and shipping addresses) to ShipStation.

- This field must contain a valid [**two-character ISO country code**](https://www.shipstation.com/docs/api/models/address/). If client data contains other values, the data will need to be remediated.  
- When left empty—or if the country code contains a dash (for example, when the field is used for an FFL number)—the value defaults to **US**.  
- Previously, the connector always defaulted to US, but this enhancement allows for additional country codes to be sent.

### Instant Send of Completed Release Tickets
Added functionality to send release tickets immediately upon completion in Counterpoint.

- Previously, release tickets were sent in batches according to the CRON schedule.  
- Now, the CRON job functions as a fallback mechanism, ensuring that any tickets not sent initially (due to connectivity or API issues) are still transmitted.

### ShipStation Carrier Code Mapping UI
Added a client-accessible UI for mapping **ShipStation carrier codes** (imported from ShipStation with tracking numbers) to corresponding **ship-via codes** in Counterpoint.

---

## Bug Fixes and Performance Enhancements

- Modified the header view to include release tickets **without payment**, allowing released lines to transmit even when their value is $0.  
- Added **NOLOCK** hints to SELECT statements in stored procedures and views to prevent deadlocks and improve performance.  
- Updated line item unit weight logic to support **decimal values** instead of rounding to the nearest integer.  
- Implemented validation to **skip sending a release ticket** if it already exists in ShipStation, preventing accidental duplicate orders (due to timinig issues with the fallback mechanism).  
- Excluded **hold and recall tickets** from being sent to ShipStation.  
- Optimized several database queries to enhance overall connector performance.  
- Made **API calls asynchronous**, enabling multi-threaded execution for faster processing and improved efficiency.
