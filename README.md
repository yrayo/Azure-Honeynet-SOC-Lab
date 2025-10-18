# Azure Cloud Environment SOC + Honeynet + Live Malicous Traffic
This lab allows me to demonstrates how an Azure honeypot can be used to capture live attacker activity and feed that data into Azure Sentinel for visibility and threat hunting. It shows the lifecycle from spinning up a vulnerable Windows OS machine to visualizing geolocated attacks on a Sentinel workbook.

Goals:
- Deploy a vulnerable Windows 10 virtual machine (honeypot) in Azure.
- Open NSG (Network Security Group) rules to generate inbound traffic (intentionally vulnerable).
- Forward security logs into a LAW (Log Analytics workspace).
- Ingest logs into Azure SIEM (Sentinel) and create visual attack maps.
- Run KQL (Kusto Query Language) to geolocate and analyze attack sources.
- Harden the environment and compare pre/post results.

## Architecture Overview
<img width="1149" height="585" alt="Architecture" src="https://github.com/user-attachments/assets/a6c916e7-62ef-4739-bc3e-1c686ac44c36" />
