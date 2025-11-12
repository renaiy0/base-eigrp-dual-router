

````markdown
# 🛰️ EIGRP Simple Simulation

A minimal yet practical Cisco Packet Tracer project demonstrating **EIGRP (Enhanced Interior Gateway Routing Protocol)** configuration between multiple routers in a small network topology.

![Topology Preview](assets/topology.png)

---

## 📘 Project Overview

This project focuses on implementing **EIGRP** routing across multiple routers to enable dynamic routing between different networks.  
It’s a simplified example perfect for students or beginners learning about **EIGRP fundamentals** in a simulated environment.

### Key Concepts
- Basic **router interconnection**
- **EIGRP autonomous system** setup
- **Network advertisement**
- **Routing table verification**

---

## 🧩 Network Topology

| Device | Interface | IP Address | Connected To |
|--------|------------|-------------|---------------|
| Router0 | Fa0/0 | 192.168.10.1 | Switch0 |
| Router0 | Se0/0/0 | 10.10.10.1 | Router1 |
| Router1 | Se0/0/0 | 10.10.10.2 | Router0 |
| Router1 | Fa0/0 | 192.168.20.1 | Switch1 |
| PCs | DHCP / Static IP | - | Corresponding Router |

---

## ⚙️ Configuration Steps

### 🖥️ Router 0 Configuration
```bash
Router> enable
Router# configure terminal
Router(config)# interface fa0/0
Router(config-if)# ip address 192.168.10.1 255.255.255.0
Router(config-if)# no shutdown
Router(config)# interface se0/0/0
Router(config-if)# ip address 10.10.10.1 255.255.255.0
Router(config-if)# no shutdown
Router(config)# router eigrp 100
Router(config-router)# network 192.168.10.0
Router(config-router)# network 10.10.10.0
Router(config-router)# end
Router# write memory
````

### 🖥️ Router 1 Configuration

```bash
Router> enable
Router# configure terminal
Router(config)# interface fa0/0
Router(config-if)# ip address 192.168.20.1 255.255.255.0
Router(config-if)# no shutdown
Router(config)# interface se0/0/0
Router(config-if)# ip address 10.10.10.2 255.255.255.0
Router(config-if)# no shutdown
Router(config)# router eigrp 100
Router(config-router)# network 192.168.20.0
Router(config-router)# network 10.10.10.0
Router(config-router)# end
Router# write memory
```

---

## 🧠 EIGRP Verification

Check EIGRP neighbor relationships and routing tables using:

```bash
show ip route
show ip eigrp neighbors
show ip protocols
```

### Example Outputs

| Router      | CLI Output                      |
| ----------- | ------------------------------- |
| **Router0** | ![Router0 CLI](assets/CLI1.png) |
| **Router1** | ![Router1 CLI](assets/CLI2.png) |

---

## 🧪 Connectivity Test

After successful EIGRP configuration, test the connection between PCs in both networks.

Example successful ping:

![Ping Success](assets/Success.png)

---

## 📁 Folder Structure

```
/assets/
 ├── topology.png        # Network topology diagram
 ├── CLI1.png            # Router0 CLI output
 ├── CLI2.png            # Router1 CLI output
 ├── Success.png         # Successful ping result
 └── EIGRP-Simple.pkt    # Cisco Packet Tracer project file
```

---

## 🎯 Learning Goals

By completing this lab, you’ll understand how to:

* Configure **EIGRP** on Cisco routers
* Establish **neighbor adjacency**
* Verify routing using CLI commands
* Test connectivity across networks dynamically

---

## 🧰 Requirements

* **Cisco Packet Tracer** (v7.0+ recommended)
* Basic understanding of:

  * IP addressing
  * Router interfaces
  * EIGRP concepts

---

## 📝 Notes

* Ensure all interfaces are **up/up** before enabling EIGRP.
* Verify the **autonomous system number (AS 100)** matches on all routers.
* You can extend this project by adding another router or subnet for advanced EIGRP scenarios.

---

## 🚀 Quick Preview

> Full topology and configurations are provided in the `/assets/` folder.
> Just open the `.pkt` file in Cisco Packet Tracer and start exploring!

---

```

---

💡 Tinggal copy ke `README.md` kamu — GitHub bakal otomatis nampilin semua foto dari `/assets/`, lengkap dan profesional.  
Mau aku tambahkan **badge GitHub-style** (misal: Cisco Packet Tracer, EIGRP, Networking) di bagian atas biar tampil lebih keren lagi?
```
