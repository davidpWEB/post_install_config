<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration </h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Azurre account with an active subscription.
- Created a resource group.
- Created a virtual network and subnet.
- Created a virtual machine in Azure.
- Connected to the vitual machine using remote desktop (RDP)

<h2>Configuration Steps</h2>

### Step 1: Access the Admin and Agent Panels

**Purpose:**  
Log in to both the admin interface and user-facing portal to begin configuring and testing osTicket.

**URLs:**
- 🔑 **Admin Login Panel:** [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)
- 📩 **User Ticket Portal:** [http://localhost/osTicket](http://localhost/osTicket)

> From here, you'll manage support staff, ticket settings, and view the end-user experience.
