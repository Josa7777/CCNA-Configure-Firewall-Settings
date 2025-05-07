# CCNA-Configure-Firewall-Settings
Securely Enabling Ping Communication via Windows Firewall ICMP Rule

This lab demonstrates how to securely restore ping (ICMP Echo Request) functionality between two Windows PCs on a local area network (LAN) by configuring a custom inbound rule in Windows Firewall. The goal is to allow diagnostic communication **without disabling firewall protections**, following best practices in endpoint security.


Required Equipment
- Two Windows 10 PCs (or virtual machines)
- One wireless router or unmanaged switch
- Two Ethernet cables

INSTRUCTIONS:
Part 1: Verify that the Windows Firewall is active and is blocking ICMP requests.
  a. Right-click **Start**. Select** Network Connections**.
  
  b. Click **Change adapter options**. Right-click the desired network adapter and select **Properties**.

  c. Select **Internet Protocol Version 4 (TCP/IPv4)**. Click **Properties** to configure the two PCs with 
  the static IP addresses shown in the addressing table. No configuration is necessary for a default gateway 
  or a DNS server in this lab, as both PCs are on the same IP network and will use IP addresses instead of domain names.

  Open a command prompt window on PC-A by right-click **Start** > ****Command Prompt**. Attempt to ping the IP address 
  assigned to PC-B. The ping command should fail. Repeat the ping command on PC-B, attempting to ping the address of PC-A. Ping commands 
  from both PCs should fail, indicating that the Windows firewall is active and is blocking ICMP ping
  requests.

  Note: If the ping succeeds on either PC, verify that the Windows Firewall is active on both
  machines.

Setup Steps
1. Connect PCs to Router/SwitchPlug both PCs into separate ports using Ethernet cables.
2. Plug both PCs into separate ports using Ethernet cables.

Assign Static IP address to both Windows PC-A and PC-B
Control Panel > Network and Sharing Center > Change Adapter Settings
- Right-click the adapter > Properties > Internet Protocol Version 4 (TCP/IPv4)

Use the following IPs:

PC-A: 192.168.1.10
PC-B: 192.168.1.11
Subnet Mask: 255.255.255.0


Test Ping (Pre-Firewall Rule)

From PC-A, run:
ping 192.168.1.11
Result: Request timed out (ICMP blocked by default)
Navigate to:
