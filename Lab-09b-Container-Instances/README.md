# Lab 09b: Implement Azure Container Instances

## Objective
Deploy and test Azure Container Instances using Docker images.

## Architecture
- **Container Image:** mcr.microsoft.com/azuredocs/aci-helloworld:latest (Linux)
- **Deployment:** Serverless container on Azure Container Instances
- **Access:** Public IP with DNS name label

## Completed Tasks
✅ Task 1: Deployed Azure Container Instance with Docker image
✅ Task 2: Tested and verified container deployment

## Container Details
| Property | Value |
|----------|-------|
| **Container name** | az104-c1 |
| **Region** | East US |
| **Image** | aci-helloworld:latest |
| **Status** | Running |
| **Type** | Public IP with DNS |

## Test Results
✅ Welcome to Azure Container Instances page displayed
✅ HTTP GET requests logged in container logs
✅ Page refreshes created multiple log entries

## Key Learnings
- ACI is serverless (no VM management needed)
- Supports both Linux and Windows containers
- Public IP can be assigned via DNS name label
- Container logs are easily viewable in portal
- Perfect for short-lived workloads and batch jobs

## Logs Verified
- Container logs show HTTP GET requests
- Each page refresh created a new log entry
- Demonstrates successful traffic routing to container
