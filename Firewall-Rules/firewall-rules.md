# Firewall Rules Notes

## Overview

This document describes the firewall rules configured on pfSense. Firewall rules control the flow of network traffic between interfaces, ensuring only allowed traffic passes through.

## Steps to Configure Firewall Rules

1. **Access the Firewall Rules**:

   - Navigated to **Firewall > Rules**.
   - Selected the **LAN** interface tab to create rules governing traffic from the LAN.

2. **Default LAN Rule**:

   - The default rule on the LAN allows all traffic from LAN to WAN, which I left enabled to ensure basic internet access for devices on the LAN.

3. **Custom Rules**:

   - **Block Unwanted Traffic**:
     - Created a rule to block traffic from certain IP ranges or devices that I didn't want accessing the internet or other parts of the network.
     - Set the **Source** to the specific IP address or range, and set the **Action** to **Block**.
   - **Allow Specific Services**:
     - Created a rule to allow only certain services, such as HTTP/HTTPS (TCP 80, 443) and SSH (TCP 22), from LAN to WAN.
     - Set the **Source** as **LAN Net** and **Destination** as **Any**, but limited the ports to the allowed services.

4. **Save and Apply**:
   - Saved each rule and applied the changes to immediately enforce them.

## Challenges Faced

- Initial configuration blocked all traffic due to a misconfigured rule. After troubleshooting, identified that I had accidentally blocked all outbound traffic.
- Had to carefully adjust the rules to balance security (blocking unwanted traffic) and functionality (allowing necessary services).

## Future Plans

- Plan to set up more complex rules, such as restricting traffic based on time or setting up VLAN-specific rules.
- Explore more advanced firewall features such as setting up an IDS/IPS (Intrusion Detection and Prevention System) with Snort.
