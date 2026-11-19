# Ticket #1: Internal Application Connectivity Issue

**Environment:** SysDesks IT Support Simulation  
**Category:** Network Troubleshooting  
**Status:** Resolved

## 1. Issue
An employee reported that the Inventory Scan application on a company-managed Slate Pad could not connect to its internal service, even though public websites were accessible. The employee needed the application to complete warehouse receiving inventory counts.

## 2. Investigation
I checked the device's network connection and discovered that it was connected to the **Northline Guest** Wi-Fi network. Although the device could access the public internet, the guest network did not advertise the private routes required to reach internal company resources.

## 3. Root Cause
The device was connected to the guest Wi-Fi network instead of the corporate network. As a result, it could access public websites but could not reach the internal service required by Inventory Scan.

## 4. Resolution
I switched the device from **Northline Guest** Wi-Fi to **Northline Corporation** Wi-Fi, allowing it to connect through the appropriate corporate network.

## 5. Verification
After switching networks, I confirmed that the Inventory Scan application was back online and accessible.

## 6. Key Takeaway
This troubleshooting exercise reinforced that internet connectivity does not necessarily mean internal company resources are reachable. When an internal application fails, checking the device's network connection and confirming that it is connected to the correct network are important early troubleshooting steps.
