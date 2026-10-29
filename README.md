# AWS VPC Peering Architecture

An AWS networking project to recreate a two-VPC architecture with public and private subnets, EC2 instances, an Internet Gateway, route tables, and VPC peering.

## Objectives

- Create two Virtual Private Clouds (VPCs).
- Configure public and private subnets.
- Enable Internet access through an Internet Gateway.
- Configure route tables and network routing.
- Establish private connectivity using VPC peering.
- Deploy EC2 instances and validate connectivity.

## Architecture

### VPC 1
- CIDR block: `28.0.0.0/16`
- Public subnet: `28.0.1.0/24`
- Private subnet: `28.0.2.0/24`

### VPC 2
- CIDR block: `28.200.0.0/16`
- Private subnet: To be confirmed during implementation.

### AWS Services
- Amazon VPC
- Amazon EC2
- Internet Gateway
- VPC Peering
- Route Tables
- Security Groups

## Implementation Status

- [x] GitHub repository created
- [ ] VPCs and subnets configured
- [ ] Internet Gateway and route tables configured
- [ ] VPC peering established
- [ ] EC2 instances deployed
- [ ] Connectivity tested
- [ ] Implementation screenshots added

## Testing

Connectivity test results will be documented after deployment.

## Cost and Security

Resources will be configured with least-privilege security rules. Unneeded AWS resources will be stopped or deleted after testing.

## Disclaimer

This project is being implemented for educational and internship purposes. The final configuration and test results will be updated as the project progresses.
