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
    d.Open a command prompt window on PC-A by right-click **Start** >** Command Prompt** Attempt to **ping** the IP address 
    assigned to PC-B. The **ping** command should fail. Repeat the **ping** command on PC-B, attempting to **ping** the address of PC-A. Ping commands 
    from both PCs should fail, indicating that the Windows firewall is active and is blocking ICMP ping requests.
      **Note:** If the **ping** succeeds on either PC, verify that the Windows Firewall is active on both
      machines.

      

  Part 2: Create a new inbound rule allowing ICMP traffic through the firewall.
   ** Step 1: Access Windows Firewall advanced settings.**
          a. Configure the firewall settings on PC-A. Click Start and type **Firewall**. Select **Windows Firewall **
          or **Windows Defender Firewall ** from the results list
          b. In the left pane of the Windows Firewall window, click Advanced settings
  
  **  Step 2: Create a new inbound rule.**
          a. On the Advanced Security window, select Inbound Rules. Right-click Inbound Rules and 
          select New Rule….
          b. In the New Inbound Rule wizard, click Custom in the Rule Type screen. Click Next to continue.
          c. In the left pane, click the Protocol and Ports option. In the Protocol type dropdown menu select   ICMP  V  4
          d.In the left pane, click the Name option and in the Name field, type Allow ICMP Requests. Click Finish 

This new rule should allow your team members to receive ping replies from PC-A

  Repeat the commands in Step 2 to add the new rule on PC-B

  Test the new firewall rule by repeating the ping command. The pings should be successful.
If not, review the firewall settings to ensure that the new rule is configured correctly.

To disable the rule, right-click Inbound Rules select Disable 
Rule. When you choose this option, you will see this 
option change to Enable Rule. You can toggle back and forth between Disable Rule and Enable
Rule; the status of the rule also shows in the Enabled column of the Inbound Rules list

c. o permanently delete the ICMP rule, click Delete. If you choose this option, you must re-create 
the rule again to allow ICMP replies.

d. Execute the ping commands performed in Step 1 to verify that the firewall is now blocking the 
ping requests again.



Setup Steps
1. Connect PCs to Router/SwitchPlug both PCs into separate ports using Ethernet cables.
2. Plug both PCs into separate ports using Ethernet cables.

  Part 3: Disabling or deleting the new ICMP rule.
    After the lab is complete, you may want to disable or even delete the new rule you created in Step 2.
Using the Disable Rule option allows you to enable the rule again. Deleting the rule permanently del
etes it from the list of Inbound Rules.
a. On the Advanced Security window, in the left pane, click Inbound Rules and then locate the rule
you created in a previous step


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
