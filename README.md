# AWS VPC Peering Architecture with Public and Private EC2 Instances

## Project Overview

This project demonstrates the implementation of an AWS Virtual Private Cloud (VPC) architecture using two separate VPCs connected through VPC Peering.

The architecture contains public and private subnets, EC2 instances, Internet Gateway connectivity, route tables, and security groups. VPC Peering enables private communication between resources hosted in separate VPCs.

## Architecture

The project consists of:

- Two VPCs configured with separate CIDR blocks.
- One public subnet and one private subnet in VPC-1.
- One private subnet in VPC-2.
- Three Amazon EC2 instances.
- An Internet Gateway attached to VPC-1.
- A VPC Peering connection between VPC-1 and VPC-2.
- Separate route tables and security groups.

## AWS Resources

| Resource | Configuration |
|---|---|
| VPC-1 | 28.0.0.0/16 |
| VPC-2 | 28.200.0.0/16 |
| VPC-1 Public Subnet | 28.0.1.0/24 |
| VPC-1 Private Subnet | 28.0.2.0/24 |
| VPC-2 Private Subnet | 28.200.1.0/24 |
| EC2 Instance 1 | VPC-1 Public |
| EC2 Instance 2 | VPC-1 Private |
| EC2 Instance 3 | VPC-2 Private |

## AWS Services Used

- **Amazon VPC:** Creation of isolated virtual networks.
- **Amazon EC2:** Deployment of virtual servers.
- **Internet Gateway:** Internet connectivity for the public subnet.
- **VPC Peering:** Private communication between the two VPCs.
- **Route Tables:** Routing traffic between subnets and VPCs.
- **Security Groups:** Instance-level network traffic control.

## Implementation Steps

1. Created two separate VPCs with non-overlapping CIDR blocks.
2. Created public and private subnets.
3. Created and attached an Internet Gateway to VPC-1.
4. Configured separate route tables for the subnets.
5. Established a VPC Peering connection between VPC-1 and VPC-2.
6. Added routes to enable communication between the VPCs.
7. Created security groups with appropriate inbound and outbound rules.
8. Launched three EC2 instances across the two VPCs.
9. Connected to the public EC2 instance using SSH.
10. Accessed private EC2 instances through the public EC2 jump host.
11. Verified connectivity using ICMP ping tests.

## Connectivity Testing

The following connectivity tests were successfully completed:

| Source | Destination | Result |
|---|---|---|
| VPC-1 Public EC2 | VPC-1 Private EC2 | Successful |
| VPC-1 Public EC2 | VPC-2 Private EC2 | Successful |
| VPC-2 Private EC2 | VPC-1 Private EC2 | Successful |

All recorded ping tests received 4 out of 4 packets with 0% packet loss.

## Key Concepts Learned

- VPC and subnet configuration
- Public and private subnet architecture
- Internet Gateway configuration
- VPC Peering
- Route table configuration
- Security Group rules
- SSH access to EC2 instances
- Bastion host / SSH jump host access
- Private communication across VPCs

## Security Considerations

- SSH access should be restricted to trusted source addresses.
- Private EC2 instances do not require public IP addresses.
- Security groups should allow only necessary traffic.
- SSH private keys should be stored securely and never uploaded to GitHub.

## Important CIDR Note

The CIDR blocks in this implementation reproduce the supplied architecture diagram. These ranges are public IPv4 address space rather than RFC1918 private address space. For a production deployment, use suitable private ranges such as 10.0.0.0/16 and 10.1.0.0/16, after checking for conflicts with connected networks.

## Conclusion

Successfully implemented and tested a two-VPC AWS architecture with public and private EC2 instances. VPC Peering enabled private communication between the two VPCs, and connectivity was verified in both directions.

This project provided practical experience with AWS networking, EC2 deployment, network security, and cloud infrastructure configuration.
