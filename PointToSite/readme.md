# Azure Point-to-Site (P2S) VPN – Implementation Guide

This repository documents the design and configuration of **Azure Point-to-Site (P2S) VPN**, which enables secure remote access for individual clients to Azure Virtual Networks over an encrypted tunnel.

The project covers **all three supported P2S authentication methods**:
- Azure Certificate Authentication
- RADIUS (NPS) Authentication
- Azure Active Directory (Azure AD) Authentication

---
## What is Point-to-Site VPN?

Point-to-Site VPN allows individual client devices (Windows, macOS, Linux) to connect securely to an Azure VNet without requiring a site-to-site VPN device.

**Common use cases**
- Admin access to Azure VMs
- Secure access for remote users
- Lab, dev, and test environments
- Hybrid identity-based access

---

## Architecture Overview

- **Azure Virtual Network**
- **VPN Gateway (Route-based)**
- **Client Devices**
- Authentication depends on the selected method:
  - Certificates
  - RADIUS (NPS)
  - Azure AD

---

## Authentication Methods

### 1. Azure Certificate Authentication
**Best for:** Labs, small teams, non-production setups

**How it works**
- A root certificate is uploaded to Azure
- Client certificates are generated from the root
- VPN clients authenticate using certificates

**Pros**
- Simple to configure
- No dependency on Active Directory or RADIUS

**Cons**
- Manual certificate management
- Not scalable for large enterprises

---

### 2. RADIUS Authentication (NPS)
**Best for:** Enterprise environments with on-prem or hybrid AD

**How it works**
- Azure VPN Gateway forwards auth requests to a RADIUS server
- RADIUS is typically hosted on Windows Server with NPS
- Supports AD credentials, MFA, and policies

**Pros**
- Centralized authentication
- Supports MFA and conditional access
- Enterprise-grade control

**Cons**
- Requires NPS and connectivity to Azure
- Higher operational complexity

---

### 3. Azure Active Directory Authentication
**Best for:** Cloud-first and modern identity environments

**How it works**
- Users authenticate using Azure AD identities
- Uses OpenVPN protocol
- Supports Conditional Access and MFA

**Pros**
- No certificates or RADIUS required
- Seamless integration with Azure AD
- Best user experience

**Cons**
- Requires Azure AD P1/P2 features for advanced controls
- OpenVPN clients only

---

## VPN Client Support

| OS        | Certificate | RADIUS | Azure AD |
|----------|-------------|--------|----------|
| Windows  | ✅ | ✅ | ✅ |
| macOS    | ✅ | ❌ | ✅ |
| Linux    | ❌ | ❌ | ✅ |

---

## Security Considerations

- Always use **MFA** (RADIUS or Azure AD)
- Restrict address pools carefully
- Apply **NSGs** to limit lateral movement
- Monitor VPN logs and connection metrics

---

## When to Use Which Method?

| Scenario | Recommended Method |
|--------|--------------------|
| Lab / PoC | Certificate |
| Hybrid AD environment | RADIUS (NPS) |
| Cloud-first / Zero Trust | Azure AD |

---

## Project Status

🚧 **Work in Progress**  
Upcoming additions:
- Step-by-step deployment guides
- Terraform / ARM templates
- Troubleshooting scenarios
- Real-world enterprise architecture

---

## Author

**Virender Singh Rawat**  
Azure | Windows | Hybrid Infrastructure  
