# DHCP-Server-Allocation-MAC-Filtering

## 🚀 Purpose
This project simulates dynamic IP address assignment using a DHCP server and Layer 2 access control through MAC address filtering. It's designed for IT students and network engineers learning foundational LAN services and basic security enforcement.

## 🖼️ Topology / Diagram
See `/assets/dhcp-mac-filter-topology.png`.

- 1 Router (DHCP Server enabled)
- 1 Switch
- 3 PCs (PC1, PC2, PC3)

## ⚙️ How It Works
- **Input:** Router DHCP configuration, switch with port security enabled, and PCs set to use DHCP.
- **Process:** 
  - DHCP server assigns IPs to clients within a defined pool.
  - Switch restricts access based on MAC addresses per port.
  - Violating devices trigger shutdown or restrict connectivity.
- **Output:** Approved devices receive IPs and connect to network; rogue devices are blocked.

## 🧪 Example Run
```bash
# In Packet Tracer:
1. Enable DHCP on router
2. Configure port security on switch (1 MAC per port)
3. Connect PC1 and verify IP via DHCP
4. Swap PC1 with PC3 on same port
```
```
Expected output:
- PC1 receives valid IP
- PC3 triggers port violation (shutdown or restrict)
```

## 🛠️ Setup Instructions
1. Configure the router with DHCP pool and excluded addresses.
2. Enable switch port security (sticky or static).
3. Connect PCs and observe behavior.
4. Use `show mac address-table` and `show port-security` for verification.

## ⚠️ Error Handling / Edge Cases
- PC not receiving IP: Check DHCP pool and exclusion range.
- Port shuts down: Ensure allowed MAC matches current device.
- No security violation: Verify port security settings (violation mode, max MACs, aging).

## 🔁 How to Extend
- Add more ports with different security modes (shutdown, restrict, protect).
- Test aging timers and sticky MAC persistence after reboot.
- Integrate a rogue DHCP server and observe conflicts.

## 🧾 Version History
- v1.0: DHCP + MAC filtering base scenario
- v1.1: Added port security violations and recovery tests

## 🧠 Author
John Felix  
GitHub: [https://github.com/Johnfednyfelix]  
LinkedIn: [https://www.linkedin.com/in/johnfelix/]
