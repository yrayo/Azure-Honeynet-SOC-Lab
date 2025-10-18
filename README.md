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

2. Create Virtual Network and Subnet.
![No network screenshot](images/Nonetwork.PNG)
![New network screenshot](images/Newnetwork.PNG)

3. Create a virtual machine (honeypot).
![No VM screenshot](images/VM1.PNG)
![New VM screenshot](images/VM2.PNG)

  At this point, the infrastructure looks like this:
![New infrastructure screenshot](images/Infrastructure.PNG)

4. Edit Network Security Group to open inbound traffic.
![NSG screenshot1](images/NSG1.png)
![NSG screenshot2](images/NSG2.png)
![NSG screenshot3](images/NSG3.PNG)

5. Disable local Windows Firewall on the VM (Windows OS Machine). With your local machine, RDP into the VM machine. Then, ping your vulnerable machine to confirm that it's accessible to everyone.
![RDP screenshot](images/RDP1.png)

![FIREWALL screenshot](images/FIREWALL1.png)

![PING screenshot](images/PING1.png)

  At this point, our architecture looks like this:
![Architecture2 screenshot](images/Architecture2.PNG)

6. Create Log Analytics workspace and connect VM.
   
![No LAW screenshot](images/LAW1.png)
![New LAW screenshot](images/LAW2.png)

7. Create/enable Azure Sentinel and connect workspace.
![New Sentinel screenshot](images/SentinelInstalled.PNG)

8. Import GeoIP watchlist into Sentinel.

9. Run KQL queries to geo-locate traffic.

10. Create Sentinel workbook visualizing attack map.

11. Harden environment and re-run analysis.
