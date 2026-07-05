🔐 Site-to-Site IPsec VPN
Project Overview

This lab is designed to gain a practical and conceptual understanding of the IPsec framework, which is the foundation of most VPN technologies. IPsec defines how devices securely exchange data over untrusted networks using encryption, authentication, and integrity mechanisms.

Even though modern enterprises increasingly use methods like SSL VPNs, DMVPN, or SD-WAN tunnels, the principles of IPsec are still fundamental. Learning this framework teaches how secure tunnels are negotiated, how traffic is selected for encryption, and how data is protected in transit, which are skills that are transferable to advanced networking technologies.
Objective

    Understand how IPsec secures traffic between two LANs.
    Learn how IKE Phase 1 & 2 establish and maintain encrypted tunnels.
    Apply ACLs to define which traffic is encrypted.
    Integrate IPsec with OSPF routing for full connectivity.
    Gain experience with Cisco IOS security configuration for VPNs.

IP Addressing & Subnetting

| Network        | IP Range        | Subnet Mask      | Description                          |
|--------------- |---------------- |----------------- |--------------------------------------|
| Site-A LAN     | 192.168.10.0/24 | 255.255.255.0    | Site-A internal network              |
| Site-A WAN     | 203.0.113.0/30  | 255.255.255.252  | WAN link to ISP                      |
| ISP to Site-B  | 192.0.2.0/30    | 255.255.255.252  | WAN link to Site-B                   |
| Site-B LAN     | 192.168.20.0/24 | 255.255.255.0    | Site-B internal network              |

How the IPsec VPN Works

The VPN establishes a secure tunnel in several stages:

    Traffic Identification: ACLs define which traffic should be encrypted (LAN-to-LAN only).
    IKE Phase 1 (ISAKMP): Routers authenticate each other, create a secure control channel, and negotiate encryption parameters (AES-256, DH group 5).
    IKE Phase 2 (IPsec Transform Set): Defines how actual data is encrypted (AES) and verified (SHA).
    Crypto Maps: Tie together peers, transform sets, and ACLs; applied to the WAN interface.
    Encrypted Data Transfer: Traffic flows securely between LANs once the tunnel is up.
