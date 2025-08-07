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
<img width="1034" height="594" alt="image" src="https://github.com/user-attachments/assets/9acd566a-ab6e-42d7-ad72-54afc7e753cc" />

### Access the Admin Panel

From the main osTicket dashboard, select **Admin Panel** to begin system configuration and customization.

<img width="1034" height="594" alt="image" src="https://github.com/user-attachments/assets/f3c4d0af-08a0-40bc-85df-9cd00611a413" />

### Create a New Role

Inside the **Admin Panel**, go to **Agents** → **Roles** → click **Add New Role** to define custom permissions for different support roles.

<img width="1034" height="594" alt="image" src="https://github.com/user-attachments/assets/b59dc22f-9408-48b7-aa44-1315028fca23" />

### Define the "Supreme Admin" Role

Enter **Supreme Admin** as the role name, then navigate to the **Permissions** tab and enable all available permissions.  
Once configured, click **Add Role** to save the new role.

<img width="1034" height="901" alt="image" src="https://github.com/user-attachments/assets/6b4ecad1-5dc6-41c4-900d-1b1191f08f60" />

### Create a New Department

Return to the main **Agents** section and navigate to **Departments** → click **Add New Department** to create a new support department.

<img width="1034" height="901" alt="image" src="https://github.com/user-attachments/assets/f3474520-1852-4e3d-aa39-b192cc5084c1" />

### Set Up the "SysAdmins" Department

No configuration changes are needed—just set the **Name** to `SysAdmins` and click **Create Dept**.

> ⚠️ **Note:** By default, tickets are auto-assigned to the "Maintenance" department. To prevent misrouting, select the **Maintenance** department, click **More**, then choose **Delete**.

<img width="1034" height="1142" alt="image" src="https://github.com/user-attachments/assets/432d47ac-e319-4231-b622-c26e950799d4" />

### Create a New Team

From the main **Agents** tab, go to **Teams** → click **Add New Team** to begin setting up team-based ticket assignments.

<img width="1034" height="474" alt="image" src="https://github.com/user-attachments/assets/2ad3e210-c36c-4c44-a5ed-5888527dd1a8" />

### Set Up the "Online Banking" Team

Enter **Online Banking** as the team name, then click **Create Team** to finalize the setup.

<img width="1034" height="822" alt="image" src="https://github.com/user-attachments/assets/c993884a-ca1d-4dbb-a63a-7d2cd4e4c501" />

### Add New Agents

From the main **Agents** tab, navigate to **Agents** → click **Add New Agent**.  
This section allows you to create accounts for team members who will access osTicket and manage support tickets.

For this setup, you'll create two agents:
- One standard **Support Agent**
- One **Administrator**

<img width="1034" height="498" alt="image" src="https://github.com/user-attachments/assets/9a6d4ea1-3863-4ca2-8e7a-9e63c9dc5a34" />

### Create Two Agents

Add the following agent accounts:

**Agent 1:**
- **Name:** Jane Smith  
- **Email:** jane@email.com  
- **Username:** jane

**Agent 2:**
- **Name:** Jacob West  
- **Email:** jacob@email.com  
- **Username:** jacob

> Continue with the steps below to set passwords, assign roles, and configure permissions for each agent.

<img width="1016" height="1103" alt="image" src="https://github.com/user-attachments/assets/6824938f-d452-434e-a4bd-1c7eaf2b70e7" />

### Set Agent Passwords

While adding each agent, click **Set Password** and do the following:

- Uncheck **Send the agent a password reset email**
- Enter `Password1` in both password fields
- Uncheck **Require password change at next login** for ease of use
- Click **Set** once the passwords match

<img width="647" height="388" alt="image" src="https://github.com/user-attachments/assets/061e60e6-c1df-47cc-bf0e-addb5694ec80" />

### Configure Agent Access

Under the **Access** tab during agent setup:

**For Jane Smith:**
- **Department:** SysAdmins  
- **Role:** Supreme Admin

**For Jacob West:**
- **Department:** Support  
- **Role:** Expanded Access
<img width="1016" height="726" alt="image" src="https://github.com/user-attachments/assets/eb3d5625-24cf-471d-8287-c0cdf250886f" />

### Assign Agent to a Team

In the **Teams** tab during agent setup:

- For **Jane Smith**, select **Online Banking** and click **Add**
- **Jacob West** will not be assigned to any team

Once all configurations are complete for each agent, click **Create** to finalize their setup.
<img width="1016" height="726" alt="image" src="https://github.com/user-attachments/assets/17c033ab-7853-47a8-bd24-feb0ed4d9e0e" />

### Create a New SLA Plan

Go to the **Manage** tab, then navigate to **SLA** → click **Add New SLA Plan** to define service level expectations.

<img width="1013" height="460" alt="image" src="https://github.com/user-attachments/assets/28e1ea7a-88a7-4a17-a317-1c66a19cd556" />

### Define SLA Plans

Create the following three SLA plans:

**Sev-A**
- **Grace Period:** 1 Hour  
- **Schedule:** 24/7

**Sev-B**
- **Grace Period:** 4 Hours  
- **Schedule:** 24/7

**Sev-C**
- **Grace Period:** 8 Hours  
- **Schedule:** 24/5 (Business Hours)

<img width="1013" height="818" alt="image" src="https://github.com/user-attachments/assets/567d5c94-60ab-4b34-a6d4-9b52497352c5" />

### Verify SLA Plans

After creation, all SLA plans should appear in the list exactly as defined above.
<img width="1013" height="539" alt="image" src="https://github.com/user-attachments/assets/2109cc2d-40c8-40b8-bab4-c05c3d471c20" />

### Add a New Help Topic

Navigate to **Help Topics** → click **Add New Help Topic** to begin organizing incoming ticket categories.
<img width="1013" height="575" alt="image" src="https://github.com/user-attachments/assets/02d34fb5-db5b-47b2-bce1-ffc19f17fd02" />

### Create Help Topics

Add the following five help topics and assign each a corresponding parent topic:

| Help Topic               | Parent Topic       |
|--------------------------|--------------------|
| Business Critical Outage | Report a Problem   |
| Personal Computer Issues | Report a Problem   |
| Password Reset           | Report a Problem   |
| Equipment Request        | General Inquiry    |
| Other                    | General Inquiry    |

> No additional settings need to be adjusted for this tutorial.

<img width="1013" height="792" alt="image" src="https://github.com/user-attachments/assets/48b5ae89-ad3b-4017-8de3-2bee8e3185f8" />

### Verify Help Topics

Confirm that all help topics appear in the list exactly as outlined above, with their corresponding parent topics.

<img width="1013" height="814" alt="image" src="https://github.com/user-attachments/assets/9619b030-51f2-46bd-a2e0-63910ee84a39" />

### Return to the Agent Panel

Click on **Agent Panel** located at the top right of the screen to switch back to the agent interface.

<img width="1013" height="556" alt="image" src="https://github.com/user-attachments/assets/34b46f8b-7702-447b-a465-efe885d1e85c" />

### Add a New User

From the **Agent Panel**, navigate to **Users** → click **Add User** to create a new end-user account.

<img width="1013" height="469" alt="image" src="https://github.com/user-attachments/assets/13968174-f2ae-482c-842a-448373be1f92" />

### Finalize User Setup

Enter the user's **Name** and **Email** (e.g., *Karen – karen@email.com*), then click **Add User** to complete the process.

---

This concludes the osTicket configuration setup.  
In the next repository, we’ll build on this environment by creating tickets and simulating a typical ticket lifecycle from submission to resolution.

<img width="1013" height="814" alt="image" src="https://github.com/user-attachments/assets/68f4dbf5-04d9-43cc-801e-db83580ec509" />




