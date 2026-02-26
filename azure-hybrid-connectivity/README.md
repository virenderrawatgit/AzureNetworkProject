# Azure Hybrid Connectivity – Architecture Guide

This repository provides a structured overview of **Azure hybrid connectivity models**, focusing on how on-premises environments securely connect to Azure using different networking approaches.

The goal of this project is to explain **design concepts, use cases, and decision criteria** for each connectivity option, rather than only step-by-step configuration.

---

## Connectivity Models Covered

This repository includes the following Azure hybrid connectivity options:

### 1. Point-to-Site (P2S) VPN
- Client-to-Azure connectivity
- Designed for individual users or administrators
- Commonly used for remote access and lab environments

📁 Folder: `/point-to-site-vpn`

---

### 2. Site-to-Site (S2S) VPN
- Network-to-network connectivity
- Uses IPsec/IKE tunnels over the internet
- Suitable for small to medium hybrid deployments

📁 Folder: `/site-to-site-vpn`

---

### 3. ExpressRoute
- Private, dedicated connectivity to Azure
- Does not traverse the public internet
- Designed for enterprise-scale and mission-critical workloads

📁 Folder: `/expressroute`

---

## High-Level Comparison

| Feature | P2S VPN | S2S VPN | ExpressRoute |
|------|--------|--------|--------------|
| Connectivity Type | Client-based | Network-based | Private circuit |
| Internet Dependency | Yes | Yes | No |
| Bandwidth | Low | Medium | High |
| Latency | Variable | Variable | Low & predictable |
| SLA | No | No | Yes |
| Typical Use Case | Admin / Remote Access | Hybrid VPN | Enterprise Hybrid |

---

## Design Considerations

When choosing a connectivity model, consider:
- Business criticality
- Bandwidth and latency requirements
- Security and compliance needs
- Cost and operational complexity
- Scalability and future growth

---

## Project Objective

This repository is intended for:
- Azure architects and engineers
- Hybrid cloud design reference
- Interview and certification preparation
- Real-world enterprise architecture learning

---

## Author

**Virender Singh Rawat**  
Azure | Hybrid Connectivity | Cloud Architecture
