# University-Networking-Project
A full-scale University Network Design project in Cisco Packet Tracer!A large university which has two campuses situated 20kms apart. The university's students and staff are distributed in 4 faculties, these include the faculties of Health and Sciences, Business, Engineering/computing and Art/design

# 🌐 University Campus Network Design & Planning

This project outlines the network infrastructure design for a university with **two campuses**. It includes VLAN segmentation, dynamic IP assignment using **DHCP**, and inter-campus routing with **RIPv2**, along with a secure and scalable topology suitable for academic and administrative needs.

---

## 🏫 Campus Overview

### 🏢 Main Campus

#### 🧱 Building A
- **Departments**: Management, HR, Finance (Admin Staff)
- **Faculty**: Business
- **VLANs**:
  - VLAN 10: Management  
  - VLAN 20: HR  
  - VLAN 30: Finance  
  - VLAN 40: Faculty of Business
- **DHCP**: Centralized, router-based DHCP for all VLANs in Building A

#### 🧱 Building B
- **Faculties**:
  - VLAN 50: Engineering/Computing  
  - VLAN 60: Art & Design

#### 🧱 Building C
- **Usage**: Students' Labs + IT Department
- **VLANs**:
  - VLAN 70: Student Labs  
  - VLAN 80: IT Department
- **Servers**:
  - Web Server  
  - FTP Server  
  - DNS Server (optional)

---

### 🏥 Smaller Campus – Faculty of Health and Sciences

- **VLAN 90**: Staff  
- **VLAN 100**: Student Labs  
- **DHCP**: Router-based DHCP for VLAN 90 and VLAN 100

---

## 🔧 Configuration Requirements

### 🛠️ Core Devices

| Device Type | Location        | Role                             |
|-------------|------------------|----------------------------------|
| Router 1    | Main Campus      | RIPv2 Routing + DHCP             |
| Router 2    | Smaller Campus   | RIPv2 Routing + DHCP             |
| L3 Switch   | Building A       | Inter-VLAN Routing, Trunk Setup  |
| L2 Switches | All other blocks | VLAN access layer, port mapping  |

---

### 🔄 Routing & DHCP

- **Routing**: RIPv2 enabled between both routers
- **Static Routing**: To connect with external **cloud email server**
- **DHCP**:
  - Building A: VLANs 10–40
  - Building B/C: VLANs 50–80
  - Smaller Campus: VLANs 90–100

---

## 🔐 Security & VLAN Setup

- Assign **specific ports to VLANs** based on departments
- Configure **802.1Q trunk links** between switches
- Use a consistent **native VLAN** across the network
- (Optional) Implement **Port Security** for endpoint restrictions

---

## 🛰️ Cloud Connectivity

- Email Server hosted externally
- Reachable via static route on main campus router

---

## 🧩 Future Enhancements

- Add **Spanning Tree Protocol (STP)** for loop prevention
- Implement **ACLs** for VLAN traffic segmentation
- Integrate **Syslog/SNMP monitoring** for real-time diagnostics
- Backup DHCP using HSRP or VRRP

---


