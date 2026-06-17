## Active Directory Lab Progress

* **Initial Setup (2026-06-16):**
  * VM (DC01) created with 4GB RAM, 2 CPUs, 50GB disk.
  * Windows Server 2025 Eval installed successfully. 
  * ![Initial Setup](initial-setup.png)
  * ![Disk Config](DISK-CONFIG.png)
  * **Troubleshooting:**
    * Encountered "Error selecting partition" during installation.
    * **Fix:** Deleted the existing partition and created a new one to re-initialize the disk as a basic partition.

* **Network Configuration:**
  * Assigned Static IP: 10.0.2.10
  * Set Primary DNS: 127.0.0.1 (Local loopback)
  * ![Network Settings](NETWORK.png)

* **Role Installation:**
  * Installed AD-Domain-Services role via PowerShell.
  * Command: `Install-WindowsFeature AD-Domain-Services -IncludeManagementTools`
  * Status: Success.
  * ![Installation Progress](AD-Domain.png)

* **Domain Promotion:**
  * Promoted server to Domain Controller for domain: `home.lab`
  * Command: `Install-ADDSForest -DomainName home.lab`
  * Status: Success. Server is now DC01.home.lab
  * ![Promotion Confirmation](home-lab.png)
 
  * ### Domain Controller Verification
* **Objective:** Verify the Active Directory Domain Services installation and forest health.
* **Command:** `Get-ADDomain -Identity home.lab`
* **Result:** Successfully confirmed domain mode and infrastructure roles.
* **Screenshot:**
![Domain Verification](Get-ADDomain.png)

### Directory Structure Setup
* **Objective:** Create an organized directory structure for lab resources.
* **Commands:**
  * `New-ADOrganizationalUnit -Name "Labs" -Path "DC=home,DC=lab"`
  * `New-ADOrganizationalUnit -Name "Users" -Path "OU=Labs,DC=home,DC=lab"`
  * `New-ADOrganizationalUnit -Name "Workstations" -Path "OU=Labs,DC=home,DC=lab"`
* **Status:** Organizational Units created successfully.
