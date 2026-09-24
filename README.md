# 🌐 Laboratory Report: Router-on-a-Stick Inter-VLAN Routing
**Cisco Packet Tracer Network Configuration & Implementation**

---

## 📋 Student Metadata
* **Student Name:** Ayalkibet Abriham
* **Course:** Cybersecurity & Network Administration
* **Instructor:** Ruth Alemayehu
* **Date:** September 2026

---

## 🎯 1.0 Objective
The primary objective of this laboratory exercise was to configure and verify inter-VLAN routing using the **"Router-on-a-Stick"** architecture. This setup enables devices situated in isolated virtual local area networks (**VLAN 10** and **VLAN 30**) to communicate seamlessly through a single physical router interface (`G0/0`) connected to an 802.1Q trunk port (`G0/1`) on switch `S1`.

---

## 💡 2.0 Summary & Understanding
In this practical network engineering lab, I learned how to bridge communication between segregated network segments using a single router interface configured with IEEE 802.1Q subinterfaces. 

* **The Problem:** Initially, devices residing in separate VLANs—such as `PC1` (`172.17.10.10` in VLAN 10) and `PC3` (`172.17.30.10` in VLAN 30)—were completely isolated from one another. Because Layer 2 switches cannot route traffic across distinct subnet and VLAN barriers natively, traffic drops occurred.
* **The Solution:** By creating dedicated subinterfaces (`G0/0.10` and `G0/0.30`) on router `R1`, mapping them with appropriate encapsulation tags (`dot1Q 10` and `dot1Q 30`), assigning respective gateway IP addresses, and configuring the connecting switch port (`G0/1`) as an 802.1Q trunk port, inter-VLAN routing was successfully established.
* **Verification:** Comprehensive testing using end-to-end ICMP echo requests (`ping`) confirmed **100% successful packet delivery** (0% packet loss, `time < 1ms`), highlighting critical concepts of enterprise network segmentation, default gateway routing, and trunking.

---

## 📸 3.0 Screenshots & Verification Section

### Network Topology Layout
*(Placeholder for your Packet Tracer topology screenshot showing PC1, Switch S1, Router R1, and PC3)*

### Verification and Ping Results Output
```text
C:\>ping 172.17.30.10

Pinging 172.17.30.10 with 32 bytes of data:

Reply from 172.17.30.10: bytes=32 time<1ms TTL=127
Reply from 172.17.30.10: bytes=32 time<1ms TTL=127
Reply from 172.17.30.10: bytes=32 time<1ms TTL=127
Reply from 172.17.30.10: bytes=32 time<1ms TTL=127

Ping statistics for 172.17.30.10:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
```
<img width="953" height="445" alt="image" src="https://github.com/user-attachments/assets/8bf5630a-8e0e-455e-9c37-38a4ba85e462" />


---
*End of Report*
