# 🇵🇪 cisco-peru-network

Simulation of a 3-tier hierarchical national network covering all 24 departments of Peru, built in Cisco Packet Tracer. The project models how a government or enterprise could interconnect regional and departmental offices using static routing and serial WAN links.

---

## 📐 Architecture

The network follows a 3-tier hierarchical model:

```
TIER 1 — LIMA (core)
    └── TIER 2 — Regional Hubs (distribution)
            └── TIER 3 — Departments (access)
```

### Regional Hubs (Tier 2)

| Region | Hub | Departments covered | Network |
|---|---|---|---|
| North | La Libertad | Tumbes, Piura, Lambayeque, Cajamarca, Amazonas | 10.13.0.0/16 |
| Center-North | Huánuco | Áncash, Pasco, Junín, Huancavelica | 10.10.0.0/16 |
| South | Arequipa | Moquegua, Tacna, Ica, Ayacucho, Apurímac | 10.4.0.0/16 |
| East | Loreto | San Martín, Ucayali, Madre de Dios, Cusco, Puno | 10.16.0.0/16 |

---

## 🗺️ IP Address Map

| # | Department | LAN Network | Router IP | Server IP | PC IP |
|---|---|---|---|---|---|
| 1 | Lima (Capital) | 10.14.1.0/24 | 10.14.1.1 | 10.14.1.100 | 10.14.1.50 |
| 2 | La Libertad | 10.13.1.0/24 | 10.13.1.1 | 10.13.1.100 | 10.13.1.50 |
| 3 | Amazonas | 10.1.1.0/24 | 10.1.1.1 | 10.1.1.100 | 10.1.1.50 |
| 4 | Piura | 10.20.1.0/24 | 10.20.1.1 | 10.20.1.100 | 10.20.1.50 |
| 5 | Lambayeque | 10.17.1.0/24 | 10.17.1.1 | 10.17.1.100 | 10.17.1.50 |
| 6 | Tumbes | 10.23.1.0/24 | 10.23.1.1 | 10.23.1.100 | 10.23.1.50 |
| 7 | Cajamarca | 10.6.1.0/24 | 10.6.1.1 | 10.6.1.100 | 10.6.1.50 |
| 8 | Arequipa | 10.4.1.0/24 | 10.4.1.1 | 10.4.1.100 | 10.4.1.50 |
| 9 | Moquegua | 10.18.1.0/24 | 10.18.1.1 | 10.18.1.100 | 10.18.1.50 |
| 10 | Tacna | 10.22.1.0/24 | 10.22.1.1 | 10.22.1.100 | 10.22.1.50 |
| 11 | Ica | 10.11.1.0/24 | 10.11.1.1 | 10.11.1.100 | 10.11.1.50 |
| 12 | Ayacucho | 10.5.1.0/24 | 10.5.1.1 | 10.5.1.100 | 10.5.1.50 |
| 13 | Apurímac | 10.3.1.0/24 | 10.3.1.1 | 10.3.1.100 | 10.3.1.50 |
| 14 | Huánuco | 10.10.1.0/24 | 10.10.1.1 | 10.10.1.100 | 10.10.1.50 |
| 15 | Áncash | 10.2.1.0/24 | 10.2.1.1 | 10.2.1.100 | 10.2.1.50 |
| 16 | Pasco | 10.19.1.0/24 | 10.19.1.1 | 10.19.1.100 | 10.19.1.50 |
| 17 | Junín | 10.12.1.0/24 | 10.12.1.1 | 10.12.1.100 | 10.12.1.50 |
| 18 | Huancavelica | 10.9.1.0/24 | 10.9.1.1 | 10.9.1.100 | 10.9.1.50 |
| 19 | Loreto | 10.16.1.0/24 | 10.16.1.1 | 10.16.1.100 | 10.16.1.50 |
| 20 | San Martín | 10.15.1.0/24 | 10.15.1.1 | 10.15.1.100 | 10.15.1.50 |
| 21 | Ucayali | 10.24.1.0/24 | 10.24.1.1 | 10.24.1.100 | 10.24.1.50 |
| 22 | Madre de Dios | 10.25.1.0/24 | 10.25.1.1 | 10.25.1.100 | 10.25.1.50 |
| 23 | Cusco | 10.21.1.0/24 | 10.21.1.1 | 10.21.1.100 | 10.21.1.50 |
| 24 | Puno | 10.8.1.0/24 | 10.8.1.1 | 10.8.1.100 | 10.8.1.50 |

---

## 🔧 Equipment

| Tier | Device | Role |
|---|---|---|
| Core (Lima) | Cisco Router 2911 | Main core router |
| Regional Hubs | Cisco Router 2911 | Distribution routers |
| Departments | Cisco Router 1941 | Access routers |
| All | Cisco Switch 2960 | Layer 2 switching |
| All | Server-PT | Local server |
| All | PC-PT | End-user test client |

---

## 🔗 Link Types

- **LAN:** Straight-through cables (PC → Switch → Router)
- **WAN:** Serial DCE/DTE cables between routers (point-to-point /30 subnets)
- **Clock rate:** 64000 bps on DCE interfaces

---

## ✅ Connectivity Tests

Ping tests were performed between departments across different regions to validate end-to-end static routing. All nodes successfully communicate across multiple hierarchical hops.

Example path: `PC-Cajamarca → Libertad → Lima → Arequipa → PC-Arequipa`

---

## 🛠️ Technologies

- Cisco Packet Tracer 8.x
- Static routing (`ip route`)
- IPv4 addressing (Class A private space `10.0.0.0/8`)
- Subnetting — /24 for LANs, /30 for WAN point-to-point links
- Manual switch configuration (VLAN 1)

---

## 📁 Files

| File | Description |
|---|---|
|  [Descargar proyecto (.pkt)](Server.pkt)  | Full Cisco Packet Tracer simulation |
|  [Descargar proyecto (.pkt)](Server.pkt) | Project documentation with screenshots and configs |
 

---

## 👤 Author

**Arnoldo Aguilar de León**  
Computer Systems Engineering  
Instituto Tecnológico de Nuevo León  
Course: Computer Networks
