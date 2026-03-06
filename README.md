# Cisco RIPv2 Routing & Secure Administrative Access Lab

## Overview
This lab demonstrates dynamic routing using RIPv2 protocol on Cisco 2911 
routers and securing network devices with password policies.

## Network Details
- Base Network: 196.79.38.0/24
- Routers: Salman1, Salman2, Salman3
- Hosts: H1, H2, H3
- Routing Protocol: RIPv2

## Subnetting (VLSM)
| Network | Subnet | Mask | Hosts |
|---|---|---|---|
| Net D | 196.79.38.0/27 | 255.255.255.224 | 30 |
| Net A | 196.79.38.32/27 | 255.255.255.224 | 25 |
| Net E | 196.79.38.64/28 | 255.255.255.240 | 10 |
| Net B | 196.79.38.80/30 | 255.255.255.252 | 2 |
| Net C | 196.79.38.84/30 | 255.255.255.252 | 2 |

## IP Address Table
| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| Salman1 | Gi0/1 | 196.79.38.33 | 255.255.255.224 |
| Salman1 | Se0/3/0 | 196.79.38.81 | 255.255.255.252 |
| Salman2 | Se0/3/1 | 196.79.38.82 | 255.255.255.252 |
| Salman2 | Se0/3/0 | 196.79.38.85 | 255.255.255.252 |
| Salman2 | Gi0/1 | 196.79.38.65 | 255.255.255.240 |
| Salman3 | Gi0/1 | 196.79.38.1 | 255.255.255.224 |
| Salman3 | Se0/3/1 | 196.79.38.86 | 255.255.255.252 |
| Host1 | NIC | 196.79.38.62 | 255.255.255.224 |
| Host2 | NIC | 196.79.38.78 | 255.255.255.240 |
| Host3 | NIC | 196.79.38.30 | 255.255.255.224 |

## What Was Configured
- VLSM subnetting across 5 networks
- IP addressing on all router interfaces and hosts
- RIPv2 dynamic routing for full connectivity
- Minimum password length policy (10 characters)
- Enable secret password (MD5 encrypted)
- Console and VTY line passwords with exec-timeout
- Service password encryption
- Login banner (MOTD)

## Key Commands
```bash
# RIPv2 Configuration
router rip
version 2
no auto-summary
network [network-address]

# Security Configuration
security passwords min-length 10
enable secret [password]
line console 0
password [password]
exec-timeout 5 0
login
service password-encryption
banner motd $Unauthorized access strictly prohibited$
```

## Skills Demonstrated
- VLSM Subnetting
- Cisco Router Configuration
- RIPv2 Dynamic Routing
- Network Security Hardening
- Cisco Packet Tracer

## Tools Used
- Cisco Packet Tracer
- Cisco 2911 Series Routers
