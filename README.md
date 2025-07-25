# VLAN-Based-Enterprise-Network-with-DHCP-Subnetting-and-Wireless-Connectivity-in-Cisco-Packet-Tracer
This project simulates a small enterprise network using Cisco Packet Tracer, implementing VLAN segmentation, router-on-a-stick inter-VLAN routing, DHCP services, wireless connectivity, and IP communication verification.

# Network Design
# Departments and VLANs

VLAN 10 – Admin / IT

VLAN 20 – Finance / HR

VLAN 30 – Reception / Customer Service

# Subnetting
Base Network: 192.168.1.0/24
Subnet mask: /26 (255.255.255.192)

VLAN 10: 192.168.1.0 – 192.168.1.63

VLAN 20: 192.168.1.64 – 192.168.1.127

VLAN 30: 192.168.1.128 – 192.168.1.191

# Key Configurations
# Switch

Assign ports to VLANs
Configure trunk port to router


Switch> enable
Switch# configure terminal
Switch(config)# interface range fa0/2-4
Switch(config-if-range)# switchport access vlan 10
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode trunk

# Router (Router-on-a-stick)
Enable subinterfaces for inter-VLAN routing

interface gig0/0.10
 encapsulation dot1Q 10
 ip address 192.168.1.1 255.255.255.192
 
# DHCP
Enable DHCP on router for automatic IP assignment


ip dhcp pool Admin-pool
 network 192.168.1.0 255.255.255.192
 default-router 192.168.1.1
 dns-server 192.168.1.1
 
# Wireless Configuration
Configured wireless access points with SSIDs and WPA2 passwords
Laptops and smartphones connected wirelessly to VLANs and received IPs automatically

# Testing
PCs, laptops, and smartphones obtained IP addresses via DHCP

Successfully verified inter-VLAN communication using the ping command

# Tools & Technologies

Cisco Packet Tracer
VLANs (802.1Q)
DHCP
Router-on-a-stick
Wireless networking
Subnetting

# Files in This Repository

Enterprise_Network.pkt – Cisco Packet Tracer project file
README.md – Project explanation

# Screenshot 
<img width="940" height="356" alt="image" src="https://github.com/user-attachments/assets/59004139-521a-472d-a5df-e09ff69f2420" />
<img width="940" height="931" alt="image" src="https://github.com/user-attachments/assets/68bef741-9158-4536-813f-3e768590be64" />



# How to Open

Download and install Cisco Packet Tracer
Open the .pkt file from this repository
Check the configurations or modify as needed
