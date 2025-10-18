# Azure Cloud Environment SOC + Honeypot + Live Malicous Traffic
This lab allows me to demonstrates how an Azure honeypot can be used to capture live attacker activity and feed that data into Azure Sentinel for visibility and threat hunting. It shows the lifecycle from spinning up a vulnerable Windows OS machine to visualizing geolocated attacks on a Sentinel workbook.

Goals:
- Deploy a vulnerable Windows 10 virtual machine (honeypot) in Azure.
- Open NSG (Network Security Group) rules to generate inbound traffic (intentionally vulnerable).
- Forward security logs into a LAW (Log Analytics workspace).
- Ingest logs into Azure SIEM (Sentinel) and create visual attack maps.
- Run KQL (Kusto Query Language) to geolocate and analyze attack sources.
- Harden the environment and compare pre/post results.

## Architecture Overview
![Architecture Screenshot](images/Architecture.PNG)

Architecture Components:
- Resource Group
- Virtual Network / Subnet
- Honeypot VM
- Network Security Group (open rules)
- Log Analytics Workspace
- Azure Sentinel (Microsoft Cloud SIEM)
- Watchlist (GeoIP CSV)
- Sentinel Workbook (Attack Map)

## Deployment Summary
1. Create Resource Group.
![No resource group Screenshot](images/Resourcegroup1.png)
![New resource group screenshot](images/Resourcegroup2.png)

3. Create Virtual Network and Subnet.
![No network screenshot](images/Nonetwork.PNG)
![New network screenshot](images/Newnetwork.PNG)

5. Create a virtual machine (honeypot).
![No VM screenshot](images/VM1.PNG)
![New VM screenshot](images/VM2.PNG)

At this point, the infrastructure looks like this:
![New infrastructure screenshot](images/Infrastructure.PNG)

7. Edit NSG to open inbound traffic (for lab only).
![No NSG screenshot]()
![New NSG screenshot]()

8. Disable local Windows Firewall on the VM (if Windows).

9. Create Log Analytics workspace and connect VM.

10. Create/enable Azure Sentinel and connect workspace.

11. Import GeoIP watchlist into Sentinel.

12. Run KQL queries to geo-locate traffic.

13. Create Sentinel workbook visualizing attack map.

14. Harden environment and re-run analysis.
