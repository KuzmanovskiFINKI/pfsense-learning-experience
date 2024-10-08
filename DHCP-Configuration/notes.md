# DHCP Configuration Notes

## Overview

This document describes the steps taken to configure the DHCP server on pfSense. DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses to devices on the LAN, simplifying network management.

## Steps to Configure DHCP

1. **Access the DHCP Server Settings**:

   - Navigated to **Services > DHCP Server**.
   - Selected the **LAN** tab to configure DHCP for the LAN interface.

2. **Configure the DHCP Range**:

   - Set the IP address range for the LAN from `192.168.1.10` to `192.168.1.50`. This range ensures that any device connecting to the LAN will be automatically assigned an IP within this range.
   - Left the **Subnet Mask** at its default value of `255.255.255.0`.

3. **Optional Settings** (if applicable):

   - Configured the **DNS server** settings to point to a custom DNS server (e.g., `8.8.8.8`).
   - Left the **Gateway** as `192.168.1.1` (the pfSense LAN interface).
   - Enabled **Static Mappings** for specific devices, which are always assigned the same IP address based on their MAC address.

4. **Save and Apply**:
   - Saved the changes and restarted the DHCP service to apply the configuration.

## Challenges Faced

- Initially faced issues with DHCP not assigning IPs, but resolved by checking that the correct network interface was selected.
- Ensured no IP conflicts by adjusting the IP range based on the total number of devices expected to connect.

## Future Improvements

- Plan to implement advanced DHCP options, such as assigning different subnets or setting up a secondary DNS server.
