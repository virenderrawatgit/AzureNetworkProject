# Azure Site-to-Site (S2S) VPN – Implementation Guide

This repository documents the design and implementation of **Azure Site-to-Site (S2S) VPN**, which enables secure, encrypted connectivity between **on-premises networks and Azure Virtual Networks** over the internet.

The project covers **all major S2S VPN concepts**, including gateway types, routing models, redundancy, and security considerations.

---

## What is Site-to-Site VPN?

Site-to-Site VPN establishes a **persistent IPsec/IKE tunnel** between an on-premises VPN device (firewall/router) and an Azure VPN Gateway.

**Common use cases**
- Hybrid cloud connectivity
- Extending on-prem AD and applications to Azure
- Backup and DR environments
- Secure migration to Azure

---

## Architecture Overview

- **On-premises Network**
  - VPN device (Firewall / Router)
- **Azure Virtual Network**
- **Virtual Network Gateway**
- **Local Network Gateway**
- **IPsec/IKE Tunnel**

Traffic between on-prem and Azure flows securely through the VPN tunnel.

---

## Azure VPN Gateway Concepts

### Gateway Types
- **VPN Gateway** – Used for S2S and P2S VPN
- **ExpressRoute Gateway** – Used for private MPLS connectivity

This project focuses on **VPN Gateway**.

---

### VPN Types
- **Route-based (Recommended)**
- Policy-based (Legacy – not recommended)

Route-based VPN supports:
- Multiple tunnels
- IKEv2
- BGP
- Active-Active configuration

---

### SKU Selection

| SKU | Use Case |
|----|---------|
| VpnGw1 | Small workloads |
| VpnGw2 | Medium workloads |
| VpnGw3 | High throughput |
| VpnGw5 | Enterprise-scale |

---

## Routing Models

### 1. Static Routing
- Manual address prefixes
- Simple to configure
- Suitable for small environments

**Limitation:** No dynamic route updates

---

### 2. BGP (Dynamic Routing)
- Uses BGP ASN and peer IPs
- Automatically exchanges routes
- Required for complex and scalable networks

**Recommended for production**

---

## High Availability & Redundancy

### Active-Standby (Default)
- Single VPN tunnel
- Automatic failover managed by Azure

### Active-Active
- Two VPN gateway instances
- Two tunnels per on-prem device
- Higher availability and throughput

---

## Authentication & Encryption

- **IKEv1 / IKEv2**
- **IPsec encryption**
- Pre-Shared Key (PSK)
- Industry-standard cryptographic algorithms

---

## Supported On-Prem VPN Devices

Azure supports most enterprise VPN devices including:
- Palo Alto
- FortiGate
- Cisco
- Check Point
- SonicWall

Configuration must match Azure IPsec/IKE parameters.

---

## Security Best Practices

- Use **route-based VPN with IKEv2**
- Enable **BGP** for scalability
- Rotate **pre-shared keys**
- Restrict traffic using **NSGs and UDRs**
- Monitor tunnel health and logs

---

## Monitoring & Troubleshooting

- Azure VPN Gateway metrics
- Connection status monitoring
- Diagnostic logs
- On-prem VPN device logs

---

## When to Use S2S VPN?

| Scenario | Recommended |
|--------|-------------|
| Hybrid connectivity | ✅ |
| Low to medium bandwidth | ✅ |
| Encrypted internet-based link | ✅ |
| High throughput / SLA | ❌ (Use ExpressRoute) |

---

## Project Status

🚧 **Work in Progress**

Planned enhancements:
- Step-by-step deployment guide
- BGP lab configuration
- Active-Active VPN setup
- Terraform / ARM templates
- Troubleshooting scenarios

---

## Author

**Virender Singh Rawat**  
Azure | Windows | Hybrid Infrastructure Architect  
