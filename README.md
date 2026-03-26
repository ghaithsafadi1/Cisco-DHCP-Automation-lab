# ⚡DHCP Automation & Connectivity (Cisco Packet Tracer)

## 📖 Project Overview
This lab demonstrates the transition from a manual, static IP environment to an automated **Dynamic Host Configuration Protocol (DHCP)** infrastructure. Using Cisco Packet Tracer, I configured a wireless router to act as a DHCP server, providing seamless "Plug and Play" connectivity for multiple end-devices while eliminating the risk of manual entry errors.

## 🛠️ Implementation Details
The core of this lab involves moving away from the "Static" assignment method and allowing the network to manage itself through automated leasing.

### 1. Router Configuration (The Gateway)
The router was configured with the following parameters to manage the local network:
* **LAN IP (Gateway):** `172.16.0.1`
* **Subnet Mask:** `255.255.255.0`
* **DHCP Pool Start:** `172.16.0.100`
* **Maximum Users:** 50

### 2. The DORA Process
By monitoring the simulation, I verified the four-step handshake that occurs when a PC joins the network:
1. **Discover:** The PC broadcasts to find a DHCP server.
2. **Offer:** The Router offers an available IP (`.100`).
3. **Request:** The PC requests to use that specific IP.
4. **Acknowledgment (ACK):** The Router confirms the lease.

### 3. Verification & Testing
To ensure the network was fully functional, I performed the following tests:
* **IP Verification:** Checked that PC0, PC1, and PC2 received sequential IPs (`.100`, `.101`, `.102`).
* **Connectivity Test:** Executed `ping` commands between workstations to verify that dynamically assigned hosts can communicate across the LAN.

```bash
# Example verification from PC0 Command Prompt
ping 172.16.0.101  # Success
ping 172.16.0.102  # Success
