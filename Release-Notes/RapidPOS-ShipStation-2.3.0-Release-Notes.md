# Rapid POS ShipStation Connector v2.3.0 Release Notes

_Release Date: October 7, 2025_

---

## New Functionality

### Store-to-Store Transfer Out Shipping Information
Added functionality to push up shipping information for **store-to-store transfers**.

- Refer to the [**client guide**](/README.md) for details (now provided as a README file in GitHub).  
- Added a field on the **Custom Tab** of transfer outs that can  be populated with a ship-via code
- This upgrade adds two new flags to each **ship-via code**:
    - **Valid for Transfer** allows the ship-via code to be applied to transfers
    - **ShipStation Send Transfers** determines whether the transfer is sent to ShipStation
- Implemented functionality to **save a single tracking number per transfer**, visible on the **Transfer Out lookup table**, accessible via **Select Transfer** on the Transfer In screen.
    - If a **ship-via code** is **blank on a transfer out**, the transfer **will not be sent** to ShipStation.

### Ship-Via Code Controls for Release Tickets
Introduced a new flag for **ShipStation Send Release Ticket** within the ship-via Code table.

- Refer to the [**client guide**](/docs/README.md) for details (now provided as a README file in GitHub).  
- Theis flag allow users to specify which release tickets should be sent to ShipStation.  
  - If a **ship-via code** is **blank on a release ticket**, the ticket **will still be sent** to ShipStation.  

### ShipStation Store ID Configuration Options
Added new **ShipStation configuration options** for defining **Store IDs** for both **release tickets** and **transfer outs**.

- Refer to the [**client guide**](/docs/README.md) for details (now provided as a README file in GitHub).
