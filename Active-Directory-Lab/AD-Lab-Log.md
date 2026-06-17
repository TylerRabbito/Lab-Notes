## Active Directory Lab Progress

* **Initial Setup (2026-06-16):**
  * VM (DC01) created with 4GB RAM, 2 CPUs, 50GB disk.
  * Windows Server 2025 Eval installed successfully. 
  * ![Initial Setup](initial-setup.png)
  * ![Disk Config](DISK-CONFIG.png)
  * * **Troubleshooting:** * Encountered "Error selecting partition" during installation.
  * **Fix:** Deleted the existing partition and created a new one to re-initialize the disk as a basic partition.
 



   * **Network Configuration:**
  * Assigned Static IP: 10.0.2.10
  * Set Primary DNS: 127.0.0.1 (Local loopback)
  * ![Network Settings](NETWORK.png) 
