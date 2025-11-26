<h1 align="center">🏠 Homelab Architecture & Infrastructure</h1>

<p align="center">
  <strong>R&D • High Availability • Virtualization • Storage • Automation</strong><br>
  Dokumentacja mojego środowiska badawczo-rozwojowego (homelab) zaprojektowanego 
  do testowania architektur produkcyjnych, automatyzacji oraz technologii DevOps / SRE.
</p>

---

## 🇵🇱 **Opis (PL)**

Mój homelab pełni funkcję **profesjonalnego środowiska testowego**, w którym weryfikuję
architektury wysokiej dostępności, platformy wirtualizacji, rozwiązania storage,
narzędzia DevOps oraz automatyzację.

Środowisko jest zbudowane w oparciu o **Proxmox VE, Ceph, TrueNAS, Docker, Traefik, OIDC**
i rozbudowaną segmentację sieciową. Służy jako:

- platforma do testowania przed produkcją,  
- laboratorium HA (compute / storage / network),  
- środowisko CI/CD, skryptów i automatyzacji,  
- repozytorium dokumentacji technicznej i diagramów,  
- poligon do wdrażania rozwiązań klasy enterprise.  

---

## 🇬🇧 **Overview (EN)**

This homelab is a **professional R&D environment** used for validating high-availability
architectures, virtualization stacks, storage systems, container platforms, automation
and DevOps/SRE tooling.

It is built on **Proxmox VE, Ceph, TrueNAS, Docker, Traefik, OIDC** with a fully segmented network.
The purpose of the lab:

- pre-production testing,  
- HA validation (compute / storage / networking),  
- CI/CD, scripting and automation development,  
- infrastructure documentation and diagrams,  
- experimentation with enterprise-grade architecture designs.  

---

# 🏗 **Główne elementy architektury / Key Architecture Components**

### **🖥 Compute – Proxmox VE Cluster**
- 2-node cluster with HA  
- external quorum node  
- VMs + LXC workloads  
- integrated with Ceph & TrueNAS  

### **💾 Storage – Ceph + TrueNAS + ZFS**
- Ceph for VM volumes & high-availability storage  
- TrueNAS for NAS, backup & replication  
- ZFS snapshots, multi-tier: NVMe/SSD/HDD  

### **🌐 Networking – VLAN, routing, firewalls**
- MGMT / STORAGE / SERVERS / DMZ / LAB VLANs  
- MikroTik / OPNsense/pfSense routing  
- dedicated storage networks  
- WireGuard / IPsec VPN  

### **🐳 Container Platform – Docker**
- Traefik reverse proxy (TLS + OIDC)  
- structured stacks per service  
- monitoring/log integration  
- secure, isolated environments  

### **📈 Monitoring & Observability**
- Prometheus + Alertmanager  
- Grafana dashboards  
- Zabbix / Wazuh  
- central logging (ELK/Graylog/Wazuh)  

---

# 📁 **Struktura repozytorium / Repository structure**

```text
homelab/
│
├── README.md                 → główny opis
├── diagrams/
│   ├── homelab-overview.png
│   └── ceph-topology.png
│
├── infra/
│   ├── proxmox/
│   ├── ceph/
│   ├── truenas/
│   └── network/
│
├── ansible/                  → playbooki automatyzacji (w przyszłości)
│
├── docker/
│   ├── traefik/
│   ├── autentic/
│   └── stacks/
│
└── docs/
    ├── hardware.md
    ├── network.md
    ├── storage.md
    └── services.md
