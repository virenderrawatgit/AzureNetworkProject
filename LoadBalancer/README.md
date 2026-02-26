# Azure Load Balancing Services – Architecture Guide

This repository provides a structured overview of **Azure load-balancing and traffic-distribution services**, focusing on **when, why, and how** each service is used in real-world cloud architectures.

Azure offers multiple load-balancing solutions designed for **different OSI layers, traffic patterns, and scopes (regional vs global)**.

---

## Azure Load Balancing Portfolio

| Service | OSI Layer | Scope | Primary Use |
|------|----------|------|-------------|
| Azure Load Balancer | Layer 4 | Regional | TCP/UDP workloads |
| Application Gateway | Layer 7 | Regional | Web applications |
| Azure Front Door | Layer 7 | Global | Global web acceleration |
| Traffic Manager | DNS | Global | DNS-based routing |

---

## Key Design Considerations

- **Layer 4 vs Layer 7 load balancing**
- **Regional vs Global traffic**
- **HTTP/S vs non-HTTP workloads**
- **Security (WAF, TLS termination)**
- **Latency, availability, and failover**

Each subfolder deep-dives into one service with architecture concepts and use cases.

---

## Repository Structure

- `/azure-load-balancer` – Layer 4 load balancing
- `/application-gateway` – Layer 7 reverse proxy
- `/azure-front-door` – Global edge load balancer
- `/traffic-manager` – DNS-based traffic routing

---

## Author

**Virender Singh Rawat**  
Azure | Cloud Architecture | Networking & Security  
