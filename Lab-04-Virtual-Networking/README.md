# Lab 04: Implement Virtual Networking

## Objective
Design and implement virtual networks, subnets, security groups, and DNS zones.

## Architecture

### Virtual Networks
- **CoreServicesVnet** (10.20.0.0/16)
  - SharedServicesSubnet (10.20.10.0/24)
  - DatabaseSubnet (10.20.20.0/24)

- **ManufacturingVnet** (10.30.0.0/16)
  - SensorSubnet1 (10.30.20.0/24)
  - SensorSubnet2 (10.30.21.0/24)

### Security
- **ASG:** asg-web (groups web servers)
- **NSG:** myNSGSecure (associated with SharedServicesSubnet)
  - Inbound: Allow TCP 80,443 from asg-web (Priority 100)
  - Outbound: Deny Internet access (Priority 4096)

### DNS
- **Public:** sentinel.com
  - A record: www → 10.1.1.4
  - Verified with nslookup ✅

- **Private:** private.sentinel.com
  - Linked to ManufacturingVnet
  - A record: sensorvm → 10.1.1.4

## Completed Tasks
✅ Task 1: Created CoreServicesVnet with subnets (Portal)
✅ Task 2: Created ManufacturingVnet with subnets (ARM Template)
✅ Task 3: Created ASG + NSG with security rules
✅ Task 4: Configured public & private DNS zones

## Key Learnings
- ARM templates enable repeatable infrastructure deployment
- NSGs control traffic at subnet/NIC level
- ASGs simplify rule management for grouped resources
- Public DNS resolves external domains; Private DNS resolves within vnets
- TTL values affect caching behavior

## Files
- `template.json` — Exported ARM template (CoreServices)
- `parameters.json` — ARM template parameters
- `screenshots/` — Portal configuration screenshots
