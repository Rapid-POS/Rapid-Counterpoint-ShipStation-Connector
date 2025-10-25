# ShipStation Connector Video

The video is posted on Rapid's YouTube channel: [**Rapid POS: Overview of the ShipStation Connector v2.3 (Released October 2025)**](https://youtube.com/watch?v=lj0hBLYEE0s)

---

Below is a quick outline of the video along with timestamps for easy reference:

#### 1. Overview of Rapid's ShipStation to Counterpoint Connector
(00–00:19)  
- Purpose: Push order release tickets (with ship-to addresses) from Counterpoint to ShipStation for shipping label creation
- Secondary use: Push posted transfer outs for store-to-store shipment label creation

#### 2. Order Creation and Release in Counterpoint (00:29–03:29)  
- Create an order with a ship-to address
- Optionally specify a ship-via code (e.g., USPS, FedEx, 2-Day, Ground) and/or set a target ship date
- Release the order (in full or partial by line), optionally changing the ship-to information if needed

#### 3. Viewing the Order in ShipStation (03:29–04:45)  
- Order appears instantly in ShipStation along with details such as order number, shipping name and address, item details, and requested service

#### 4. Item Weight Configuration (04:45–05:03)  
- Item record in Counterpoint contains a weight value (e.g., 1.5 lb) that is configurable to assume pounds, ounces, or grams
- The weight setting applies globally and must be consistent across all item records in Counterpoint
- ShipStation converts the number and configured unit of measure to pounds and ounces (e.g., 1 lb 8 oz) 

#### 5. Address Formatting and Country Codes (05:03–06:05)  
- If country is blank on an address, ShipStation defaults it to "US"
- Must use valid 2-character country codes (e.g., US for United States, CA for Canada, etc.)
- Invalid codes (e.g., USA, CAN) will create an error

#### 6. Tracking Numbers (06:05–06:33)  
- ShipStation sends tracking numbers back to Counterpoint every 15 minutes
- Tracking numbers are stored in the ticket’s “Package Tracking Numbers” tab

#### 7. Using Transfer Outs with ShipStation (06:33–08:08)  
- Enables label creation for store-to-store (location) inventory transfers
- Transfer outs must include a ship-via code to push to ShipStation
- Once posted, the transfer out shipping information appears in ShipStation
- Only basic address information is pushed (no item-level details)

#### 8. ShipStation Connector Configuration in Counterpoint (08:08–11:14)  
- Key settings include Send Warehouse ID (for multi-location setups), Order Weight Unit (lbs, oz, grams), and ShipStation Store IDs

#### 9. Configuring and Managing Ship-Via Codes (11:14–15:01)  
- Each ship-via code can be configured for use with vendors, customers, and transfers, and set to determine whether related tickets are pushed to ShipStation
- Fully customizable, allowing each client to control which codes trigger label creation in ShipStation

#### 10. Tracking Numbers and Carrier Mapping (15:01–17:04)    
- The ShipStation Carriers feature maps ShipStation carrier codes to Counterpoint ship-via codes
- When a label is created, the actual carrier and tracking number flow back into Counterpoint

#### 11. Summary (17:04–End)  
- The ShipStation connector pushes release tickets (with ship-to addresses) and posted transfer outs (with ship-via codes) to ShipStation for shipping label creation
- The connector pulls tracking numbers from ShipStation back into Counterpoint
