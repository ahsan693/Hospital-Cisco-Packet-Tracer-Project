# 🏥 Hospital Network Project (Cisco Packet Tracer)

## 📘 Overview

This Cisco Packet Tracer project simulates the internal computer network of a hospital. The network is designed with **multiple departments**, each assigned to a **separate VLAN**, using **DHCP for IP management**, **NAT for internet access**, and **Access Control Lists (ACLs)** for secure inter-departmental communication.

---

## 🏗️ Network Topology

- **3 Switches (Core + Access)**
- **1 Router (Handles Inter-VLAN Routing, NAT, ACL)**
- **1 Server (DHCP, DNS, FTP, Web, Email)**
- **Multiple End Devices per Department**
- **1 ISP Router (Internet Simulation)**

---

## 🏢 Departments and VLANs

| Department         | VLAN ID | IP Network       |
|--------------------|---------|------------------|
| Emergency          | 10      | 192.168.10.0/24  |
| ICU                | 20      | 192.168.20.0/24  |
| OPD                | 30      | 192.168.30.0/24  |
| Radiology          | 40      | 192.168.40.0/24  |
| Administration     | 50      | 192.168.50.0/24  |
| Pharmacy           | 60      | 192.168.60.0/24  |
| Lab                | 70      | 192.168.70.0/24  |
| Server Room (Mgmt) | 99      | 192.168.99.0/24  |

---

## 📡 Features Implemented

### ✅ VLANs
- Each department is segmented via VLAN.
- Inter-VLAN routing is handled by **Router-on-a-Stick** configuration.

### ✅ DHCP
- **Central DHCP server** provides IP addresses dynamically to all departments.
- DHCP scopes are configured for each VLAN.

### ✅ NAT (Network Address Translation)
- **Static and/or PAT (Port Address Translation)** is used to allow internal devices to access the internet using public IPs.

### ✅ ACL (Access Control Lists)
- ACLs are used to:
  - Restrict access between departments (e.g., only Admin can access Server Room).
  - Block unauthorized access to sensitive departments.
  - Permit only specific services (e.g., HTTP/HTTPS, DNS).

---

## 🌐 IP Addressing Plan

| VLAN | Subnet            | Gateway           |
|------|-------------------|-------------------|
| 10   | 192.168.10.0/24   | 192.168.10.1      |
| 20   | 192.168.20.0/24   | 192.168.20.1      |
| 30   | 192.168.30.0/24   | 192.168.30.1      |
| 40   | 192.168.40.0/24   | 192.168.40.1      |
| 50   | 192.168.50.0/24   | 192.168.50.1      |
| 60   | 192.168.60.0/24   | 192.168.60.1      |
| 70   | 192.168.70.0/24   | 192.168.70.1      |
| 99   | 192.168.99.0/24   | 192.168.99.1      |

**Public IP for NAT:** `203.0.113.2` (connected to ISP)

---

## ⚙️ Configuration Summary

### Router
- Sub-interfaces for each VLAN
- DHCP relay agents
- NAT inside/outside interfaces
- ACLs applied to VLAN interfaces or NAT access

### Switches
- VLAN configuration
- Trunk and access ports
- Inter-switch trunking

### Server
- DHCP Scopes for all VLANs
- DNS (optional)
- Web/FTP/Email services

---

## 🔐 Example ACL Rules

- Allow only Admin VLAN (50) to access the Server VLAN (99)
- Deny all other VLANs from accessing VLAN 99
- Allow Internet access for all departments except Lab (VLAN 70)
- Permit HTTP/HTTPS and DNS traffic only from Pharmacy

---

## 🚀 How to Run

1. Open the project in **Cisco Packet Tracer**
2. Start simulation mode to verify:
   - IP address assignment via DHCP
   - Inter-VLAN communication
   - ACL restrictions
   - NAT functionality (test internet access via web browser)
3. Use **`ipconfig`** on PCs and **`ping`**/`tracert` commands for testing

---

## 📂 Files Included

- `HospitalNetwork.pkt` – Cisco Packet Tracer Project File
- `README.md` – Documentation File
- `config_notes.txt` – Optional CLI configuration for router/switches

---

## 📌 Notes

- Project follows principles of **modular design**, **security**, and **scalability**
- VLAN separation improves **security** and **performance**
- DHCP + NAT + ACL ensure **efficient**, **secure**, and **automated** networking

---

## 👨‍⚕️ Project By

Your Name  
[Your Email]  
[Your University / Organization]  

---

## 📅 Date

July 2025

