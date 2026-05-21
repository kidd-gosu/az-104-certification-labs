# Exercise 01: Create and Configure Virtual Networks

## Objective
Create a hub-and-spoke virtual network architecture with peering.

## Architecture
- **hub-vnet** (10.0.0.0/16) — Hub with AzureFirewallSubnet
- **app-vnet** (10.1.0.0/16) — Spoke with frontend (10.1.0.0/24) and backend (10.1.1.0/24) subnets
- **Peering:** Full bidirectional connectivity between vnets

## Completed Tasks
✅ Created app-vnet with 2 subnets (frontend, backend)
✅ Created hub-vnet with firewall subnet
✅ Configured VNet peering (app-vnet-to-hub ↔ hub-to-app-vnet)
✅ Peering status: Connected

## Key Learnings
- Address space must not overlap between vnets
- Subnets must fall within vnet address space
- VNet peering requires bidirectional link names
- Always verify peering status shows "Connected"

## Resources Used
- Azure Portal Virtual Networks
- VNet Peering configuration
