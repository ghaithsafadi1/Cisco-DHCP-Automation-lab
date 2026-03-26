# ⚡ Lab: Customizing DHCP Services on a Wireless Router

## 📖 Scenario
In this lab, I transitioned a standard home-office setup from its default "out-of-the-box" configuration to a custom IP schema. The project focuses on changing the management IP of the router and redefining the client address pool for better network control.

## 🛠️ Implementation Steps

### 1. Gateway & Pool Modification
* **Original Gateway:** 192.168.0.1
* **New Management IP:** `192.168.5.1`
* **Custom DHCP Range:** Set to start at `.126` with a maximum of `75` users.

### 2. The "Lease Renewal" Challenge
Changing the router's IP mid-session causes a "Request Timeout" in the browser. I solved this by:
1. Toggling the client PC from **DHCP** to **Static** and back to **DHCP**.
2. This forced a new **DORA** handshake, allowing the PC to receive the updated Gateway info (`192.168.5.1`) and a new IP from the updated pool.

### 3. Verification Table
| Device | Assigned IP | Gateway | Result |
| :--- | :--- | :--- | :--- |
| **PC0** | 192.168.5.126 | 192.168.5.1 | ✅ Success |
| **PC1** | 192.168.5.127 | 192.168.5.1 | ✅ Success |
| **PC2** | 192.168.5.128 | 192.168.5.1 | ✅ Success |

## 🏁 Key Technical Takeaway
Understanding that the **Default Gateway** is the "door" out of the network. If the door moves (changing the Router IP), every client must be updated or "renewed" to find the new exit.

---
