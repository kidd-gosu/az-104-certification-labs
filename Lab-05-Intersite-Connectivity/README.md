# Lab 05: Implement Intersite Connectivity

## Objective
Configure VNet peering and test connectivity between virtual machines in different networks.

## Architecture

### Virtual Networks
- **CoreServicesVnet** (10.0.0.0/16)
  - Core subnet (10.0.0.0/24)
  - Perimeter subnet (10.0.1.0/24)

- **ManufacturingVnet** (172.16.0.0/16)
  - Manufacturing subnet (172.16.0.0/24)

### Virtual Machines
- **CoreServicesVM** (10.0.0.4) — Windows Server 2025
- **ManufacturingVM** (172.16.0.4) — Windows Server 2025

### Routing
- **Route Table:** rt-CoreServices
- **Custom Route:** Perimeter → Core (via NVA 10.0.1.7)

## Completed Tasks
✅ Task 1: Created CoreServicesVM in CoreServicesVnet
✅ Task 2: Created ManufacturingVM in ManufacturingVnet
✅ Task 3: Network Watcher test (Unreachable before peering)
✅ Task 4: Configured bidirectional VNet peering
✅ Task 5: PowerShell test (TcpTestSucceeded after peering)
✅ Task 6: Created custom route & associated with perimeter subnet

## Key Learnings
- VNet peering enables cross-network communication
- Network Watcher diagnoses connectivity issues
- PowerShell test-connection validates peering success
- Custom routes direct traffic through network appliances
- Route tables must be associated with subnets to take effect

## Test Results
- **Before Peering:** Unreachable (316 probes failed)
- **After Peering:** TcpTestSucceeded on port 3389
