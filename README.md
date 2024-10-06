<h1>Home Lab with Active Directory using Oracle Virtual Box</h1>
    
  <p>
        This project sets up a home lab environment using Oracle VirtualBox, running Microsoft Windows Server 2019 as a Domain Controller (DC) with Active Directory (AD) and a Windows 10 client. The domain controller manages both internet access and the internal network. The setup includes configuring a private network, installing key services, and creating multiple users via PowerShell.
    </p>
    <h1>Home Lab with Active Directory using Oracle Virtual Box</h1>

  <h2>Utilities Used</h2>
    <ul>
        <li><b>Oracle VirtualBox</b></li>
        <li><b>Windows Server 2019</b></li>
        <li><b>Windows 10</b></li>
        <li><b>PowerShell</b></li>
    </ul>

  <p>
        This project sets up a home lab environment using Oracle VirtualBox, running Microsoft Windows Server 2019 as a Domain Controller (DC) with Active Directory (AD) and a Windows 10 client. The domain controller manages both internet access and the internal network. The setup includes configuring a private network, installing key services, and creating multiple users via PowerShell.
    </p>

  <p>This lab consists of:</p>
    <ol>
        <li>A Domain Controller running Windows Server 2019, managing Active Directory and network services.</li>
        <li>A client machine running Windows 10, connected to the domain.</li>
    </ol>


  <h2>Setup Guide</h2>

  <h3>Step-by-Step Installation</h3>

  <ol>
        <li>
            <strong>Install Microsoft Windows Server 2019 on the Virtual Machine</strong>
            <br>Note: Although running a server OS on a virtualized environment may have vulnerabilities, this setup is for learning purposes.
            <p align="left">
                <img src="https://imgur.com/gyE52Se.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
            </p>
        </li>
    <br />
        <li>
            <strong>Identify Network Interface Cards (NICs)</strong>
            <ul>
                <li>One NIC for external internet access and another for the private internal network.</li>
                <br /> 
                <strong>Configure IP Addressing and Subnet Mask</strong>
                <li>Assign IP addresses to the internal NIC and set the DNS server to itself using either the loopback address (127.0.0.1) or the server’s assigned IP.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/3CcGbxM.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
            </p>
        </li>
    <br />
        <li><strong>Install Active Directory Domain Services (AD DS)</strong>
            <ul>
                <li>AD DS will manage network users and grant them access to resources on the network.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/HrXC3Da.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Create the Active Directory Domain</strong>
            <ul>
                <li>Domain Name: <code>mydomain.com</code></li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/D1HDeun.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Create an Admin User in Active Directory</strong>
            <ul>
                <li>Username: <code>a-mescobar</code></li>
                <li>Password: <code>Password1</code></li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/w7LTi4x.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Configure RAS (Remote Access Server) and NAT (Network Address Translation)</strong>
            <ul>
                <li>Enable internet access for internal network clients through the domain controller.</li>
                <li>Install the Routing and Remote Access Service (RRAS) role.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/qEEc5YV.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Configure DHCP (Dynamic Host Configuration Protocol)</strong>
            <ul>
                <li>Set up a DHCP server to automatically assign IP addresses to client machines.</li>
                <li>Create a DHCP scope for a defined range of IP addresses.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/etaIHv7.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Create 1000+ Users Using PowerShell Script</strong>
            <ul>
                <li>The script reads from a text file and creates users in a new organizational unit (OU) called <code>Users</code>.</li>
                <li>Each user is assigned a simple password with no additional group policy restrictions.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/8oXiQbL.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Configure Windows 10 Client VM</strong>
            <ul>
                <li>Connect the client to the internal network and verify that it can obtain an IP address from the DHCP server.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/wkeL5yZ.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Add the Client to the Domain</strong>
            <ul>
                <li>Assign a user account to the client and verify that it appears in the <code>Computers</code> section of <code>AD Users and Computers</code>.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/wswnh6v.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    <br />
        <li><strong>Verification</strong>
            <ul>
                <li>Ensure that the client is correctly connected to the domain and can access the internet.</li>
            </ul>
            <p align="left">
                <img src="https://imgur.com/3N7Ts98.png" height="60%" width="60%" alt="Installation of Windows Server 2019"/>
                <br />
        </li>
    </ol>

  <h2>Diagram</h2>

  <p>(Add your network topology diagram here)</p>
