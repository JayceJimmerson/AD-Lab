# My Personal Hybrid Identity Lab Project

## 🎯 Mission Briefing
The goal of this project is to design and build a complete, functional hybrid identity environment from the ground up. This lab will simulate a modern corporate network that bridges on-premise infrastructure with cloud services, providing a safe sandbox for learning and experimentation.

---

## 🛠️ Technology Stack / "Mod List"
This project will use the following core technologies to build our environment:

* **Virtualization:** Microsoft Hyper-V
* **On-Premise Server OS:** Windows Server 2025
* **Client OS:** Windows 11 Enterprise
* **Core Services:** Active Directory Domain Services (AD DS), DNS, Group Policy
* **Cloud Platform:** Microsoft Azure
* **Cloud Identity:** Microsoft Entra ID
* **Hybrid Bridge:** Microsoft Entra ID Connect Sync
* **Cloud Management:** Microsoft Intune
* **Version Control:** Git & GitHub

---

## 🗺️ Project Roadmap / "Quest Log"
This project is broken down into three distinct phases. Check off items as you complete them.

### Phase 1: The On-Premise Foundation
*Goal: Build a stable, self-contained local network that mimics a traditional office setup.*

* [x] Set up the project directory and initialize the Git repository.
* [x] In Hyper-V, create the internal `LabNetwork` virtual switch.
* [x] Build the `DC-01` virtual machine and install Windows Server 2025.
* [x] Perform initial server configuration (hostname, static IP).
* [x] Install the Active Directory Domain Services (AD DS) and DNS roles.
* [x] **Promote `DC-01` to a Domain Controller for a new forest (`mylab.local`).**
* [x] In Active Directory, create Organizational Units (OUs) for different departments (e.g., `Staff`, `Admin`).
* [x] Create a few test user accounts within the new OUs.
* [x] Build the `CLIENT-01` virtual machine and install Windows 11.
* [x] Successfully join `CLIENT-01` to the `mylab.local` domain.
* [x] Create and apply a simple Group Policy Object (GPO) to prove domain control (e.g., set the desktop wallpaper on `CLIENT-01`).

### Phase 2: The Hybrid Bridge ("Connecting the Realms")
*Goal: Connect the on-premise lab to a cloud tenant, creating a true hybrid identity.*

* [x] Sign up for a free Microsoft Azure trial account.
* [x] On `DC-01`, download and install the Microsoft Entra ID Connect Sync tool.
* [x] Configure the sync tool to connect the local `mylab.local` to the cloud Entra ID tenant.
* [x] Verify that the on-premise user accounts have successfully synced and now appear in the Entra ID portal.

### Phase 3: Cloud-Native Exploration ("Mastering the Cloud")
*Goal: Use the hybrid foundation to safely experiment with modern, cloud-based management tools.*

* [ ] In the Azure portal, enable a free trial for Microsoft Intune.
* [ ] Configure the settings to allow `CLIENT-01` to enroll in Intune.
* [ ] Create a simple Intune Configuration Profile that mirrors the on-prem GPO (e.g., setting a specific security policy).
* [ ] Explore Conditional Access Policies in Entra ID to see how cloud security rules are applied.
* [ ] **(Bonus Quest)** Attempt to deploy a simple application (like 7-Zip) to `CLIENT-01` using Intune.

---

## 🖥️ Virtual Machine Inventory
*This section will be the central source of truth for the lab's technical details.*

| Component | Hostname | Operating System | IP Address | DNS Server | Admin Password |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Domain Controller** | `DC-01` | Windows Server 2025 | `10.0.0.10` | `127.0.0.1` | `*Stored in password manager*` |
| **Client Machine** | `CLIENT-01`| Windows 11 Ent. | `DHCP` | `10.0.0.10`| `*Local admin stored in Pwd Mgr*` |

---

## 🏆 Key Learnings / Achievements Unlocked
*A place to document key concepts and "aha!" moments.*

* Successfully configured a static IP address and understood why it's necessary for a server.
* ...