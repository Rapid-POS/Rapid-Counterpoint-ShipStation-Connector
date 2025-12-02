# Rapid POS ShipStation Connector v2.1.7 Release Notes

_Release Date: January 9, 2025_

---

## New Functionality

### Instant Ticket Push to ShipStation
You can now instantly push release tickets from Counterpoint directly to ShipStation, streamlining fulfillment synchronization.

### Tracking Number Import Automation
The integration now supports importing tracking numbers from ShipStation into Counterpoint at configurable intervals as low as 1 minute (standard is 15 minutes).

### Enhanced ShipStation Menu Options
New menu codes and UI enhancements have been added to improve user accessibility:

- **Mark All ShipStation Messages as Read** button  
- **Client-accessible configuration UI** for managing integration settings

### Configurable “Send Warehouse ID” Option
A new configuration option allows enabling the “Send Warehouse ID” value.

- Note: Enabling this feature is billed at T&M rates since mapping the Counterpoint ship-from location (stocking location ID) to ShipStation warehouse IDs must be completed by a programmer.

### Adjustments to the ShipStation Connector View Table
By defining the CI/CD library variable, the ShipStation connector header view can now be customized for greater flexibility:

- Option to send either the original *order number* or the specific *release ticket number* to ShipStation  
- Option to populate the shipping service in ShipStation using any ticket header field from Counterpoint (typically configured to use the *ship-via code*)

### Sale Line Quantity Logic Update
The connector logic has been updated to **send only the quantities from “sale” (released) lines** on a ticket instead of all lines.

- Ensures that only released sale quantities are transmitted to ShipStation, improving accuracy and reducing data noise.
