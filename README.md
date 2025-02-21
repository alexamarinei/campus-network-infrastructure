# Campus Network Infrastructure

A comprehensive network design project for a multi-building campus environment, featuring VLAN configuration, DHCP setup, and complete IP allocation planning.

## Network Specifications

### ISP Details
- ISP IP: 26.167.200.160/27
- Private IP Range: 10.221.24.0/21
- Unallocatable Segments:
  - 10.221.24.64/26
  - 10.221.27.0/24

### Building Infrastructure

#### Building A
- Networks: 5
- Computers per network: 68/17/38/29/56
- Dimensions: 24x22
- Levels: 3

#### Building B (NOC Location)
- Networks: 5
- Computers per network: 54/45/63/65/62
- Dimensions: 58x23
- Levels: 3

#### Building C
- Networks: 6
- Computers per network: 50/24/24/54/70/21
- Dimensions: 40x41
- Levels: 2

#### Building D
- Networks: 5
- Computers per network: 61/61/60/32/45
- Dimensions: 30x60
- Levels: 2

#### Building E
- Networks: 4
- Computers per network: 69/64/59/68
- Dimensions: 23x43
- Levels: 3

### Network Distribution
- Network 1: Buildings A, B, C, D
- Network 2: Buildings A, C, D, E
- Network 3: Buildings A, B, C, D, E

## Server Configuration

All servers are located in Building B (Network B3)

### Server Details
1. **DNS Server**
   - IP: 10.221.31.2
   - Mask: 255.255.255.128

2. **DHCP Server**
   - IP: 10.221.31.3
   - Mask: 255.255.255.128

3. **Email Server**
   - IP: 10.221.31.4
   - Mask: 255.255.255.128

4. **FTP Server**
   - IP: 10.221.31.5
   - Mask: 255.255.255.128

5. **HTTP Server**
   - IP: 10.221.31.6
   - Mask: 255.255.255.128

## VLAN Configuration

### Router Configuration Template
```cisco
int FastEthernet0/0.<vlan_number>
encapsulate dot1Q <vlan_number>
ip address <gateway_ip> <mask>
ip helper-address <dhcp_server_ip>
exit
```

### Switch Configuration Template
```cisco
Switch(config)#vlan <vlan_number>
Switch(config-vlan)#exit
Switch(config)#int fa0/1
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access vlan <vlan_number>
Switch(config-if)#exit
```

## Equipment List

### Hardware
- Servers: 5 (DHCP, DNS, HTTP, EMAIL, FTP)
- Router: 1 Network Router
- Switch-PT: 5
- Switch-2950-24: 25
- Computers: 25

### Cost Breakdown
- Servers (Cisco UCS-SPR-C240M4-BB1): $11,700 (5 × $2,340)
- Switches (Cisco Catalyst 2950-24 Port): $1,200 (25 × $48)
- Computers: $10,000 (25 × $400)
- Switch-PT (Cisco WS-C2960-24PC-S): $395 (79 × $5)
- **Total Cost**: $23,295

## Installation Guide

[To be added]

## Network Diagrams

[To be added]

## Maintenance Guidelines

[To be added]

## Contributing

[Guidelines for contributing to this project]

## License

[License information to be added]
