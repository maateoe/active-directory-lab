# Home Lab with Active Directory using Oracle Virtual Box

This project sets up a home lab environment using Oracle VirtualBox, running Microsoft Windows Server 2019 as a Domain Controller (DC) with Active Directory (AD) and a Windows 10 client. The domain controller manages both internet access and the internal network. The setup includes configuring a private network, installing key services, and creating multiple users via PowerShell.

## Architecture

This lab consists of:
1. A Domain Controller running Windows Server 2019, managing Active Directory and network services.
2. A client machine running Windows 10, connected to the domain.

### Network Configuration
- **Domain Controller**: Two network adapters (Network Internal Controller)
  - One adapter connects to the external internet.
  - The other is for the private internal network.

## Setup Guide

### Step-by-Step Installation

1. **Install Microsoft Windows Server 2019 on the Virtual Machine**
   - Note: Although running an outdated server OS on may have vulnerabilities, this setup is for learning purposes.

2. **Identify Network Interface Cards (NICs)**
   - One NIC for external internet access and another for the private internal network.

3. **Configure IP Addressing and Subnet Mask**
   - Assign IP addresses to the internal NIC and set the DNS server to itself using either the loopback address (127.0.0.1) or the server’s assigned IP.

4. **Install Active Directory Domain Services (AD DS)**
   - AD DS will manage network users and grant them access to resources on the network.

5. **Create the Active Directory Domain**
   - Domain Name: `mydomain.com`

6. **Create an Admin User in Active Directory**
   - Username: `a-mescobar`
   - Password: `Password1`

7. **Configure RAS (Remote Access Server) and NAT (Network Address Translation)**
   - Enable internet access for internal network clients through the domain controller.
   - Install the Routing and Remote Access Service (RRAS) role.

8. **Configure DHCP (Dynamic Host Configuration Protocol)**
   - Set up a DHCP server to automatically assign IP addresses to client machines.
   - Create a DHCP scope for a defined range of IP addresses.

9. **Create 1000+ Users Using PowerShell Script**
   - The script reads from a text file and creates users in a new organizational unit (OU) called `Users`.
   - Each user is assigned a simple password with no additional group policy restrictions.

10. **Configure Windows 10 Client VM**
    - Connect the client to the internal network and verify that it can obtain an IP address from the DHCP server.

11. **Add the Client to the Domain**
    - Assign a user account to the client and verify that it appears in `Address Leases`.

12. **Verification**
    - Ensure that the client is correctly connected to the domain and can access the internet.

## Diagram

![alt text]([https://imgur.com/a/mH44GJL])
