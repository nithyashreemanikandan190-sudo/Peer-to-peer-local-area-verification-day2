# Answer Key: Peer-to-Peer Local Area Network Verification

## 1. Aim

To establish a Peer-to-Peer Local Area Network (LAN) by connecting two workstations, PC0 and PC1, through a Cisco 2960 Layer 2 switch, configuring static IPv4 addresses, and verifying connectivity using the `ping` and `arp -a` commands.

## 2. Software and Devices Required

- Cisco Packet Tracer
- Two PCs (PC0 and PC1)
- One Cisco 2960 switch (Switch0)
- Two Copper Straight-Through cables

## 3. IP Address Configuration

| Device | Interface | IPv4 Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| PC0 | FastEthernet0 | 192.168.10.25 | 255.255.255.0 | 192.168.10.1 |
| PC1 | FastEthernet0 | 192.168.10.26 | 255.255.255.0 | 192.168.10.1 |

**Network Address:** `192.168.10.0/24`

## 4. Procedure

### Step 1: Place the Devices

1. Open Cisco Packet Tracer.
2. Keep the existing PC0 in the workspace.
3. Add another generic PC from **End Devices**. It will be named PC1.
4. Add a Cisco 2960 switch from **Network Devices → Switches**.

### Step 2: Connect the Devices

1. Click **Connections** (lightning bolt icon).
2. Select **Copper Straight-Through**.
3. Connect PC0 FastEthernet0 to Switch0 FastEthernet0/1.
4. Connect PC1 FastEthernet0 to Switch0 FastEthernet0/2.
5. Wait for the link indicators to turn green.

### Step 3: Configure PC0

1. Click PC0 → **Desktop** → **IP Configuration**.
2. Select **Static**.
3. Enter the following values:

   - IP Address: `192.168.10.25`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: `192.168.10.1`

4. Close the window.

### Step 4: Configure PC1

1. Click PC1 → **Desktop** → **IP Configuration**.
2. Select **Static**.
3. Enter the following values:

   - IP Address: `192.168.10.26`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: `192.168.10.1`

4. Close the window.

### Step 5: Verify IP Configuration

1. Open PC0 → **Desktop** → **Command Prompt**.
2. Enter:

   `ipconfig`

3. Press Enter.
4. Verify that PC0 has IP address `192.168.10.25` and subnet mask `255.255.255.0`.

### Step 6: Test Network Connectivity

1. In PC0's Command Prompt, enter:

   `ping 192.168.10.26`

2. Press Enter.
3. Observe the replies from PC1.
4. Successful replies indicate that PC0 can communicate with PC1.

**Expected Output:**

```text
Reply from 192.168.10.26: bytes=32 time<1ms TTL=128
Reply from 192.168.10.26: bytes=32 time<1ms TTL=128
Reply from 192.168.10.26: bytes=32 time<1ms TTL=128
Reply from 192.168.10.26: bytes=32 time<1ms TTL=128
```

*Note: The first ping may occasionally time out while ARP resolves the destination MAC address. If this happens, repeat the ping command.*

### Step 7: Inspect the ARP Table

1. In the same Command Prompt, enter:

   `arp -a`

2. Press Enter.
3. Look for an entry corresponding to `192.168.10.26`.
4. Verify that the entry contains a physical (MAC) address.

The ARP entry confirms that PC0 has resolved PC1's IPv4 address to its MAC address.
<img width="1312" height="1199" alt="image" src="https://github.com/user-attachments/assets/fe3bf054-2b1d-4863-a8d8-b4c1e98a9446" />


## 5. Testing Results

| Test | Expected Result |
|---|---|
| PC0 IP configuration | Correct |
| PC1 IP configuration | Correct |
| Physical connections | Link indicators green |
| Ping from PC0 to PC1 | Successful replies |
| ARP table inspection | PC1's IP-to-MAC mapping appears after communication |

## 6. Result

A Peer-to-Peer LAN was configured successfully using two PCs connected through a Cisco 2960 switch. Static IPv4 addresses were assigned to both PCs, and connectivity was verified using the `ping` command. The `arp -a` command was used to inspect the resolved IP-to-MAC address mapping.

## 7. Conclusion

This lab demonstrates basic LAN setup, static IPv4 configuration, connectivity testing, and ARP-based address resolution. Both PCs can communicate because they belong to the same subnet and are connected through the Layer 2 switch.
## 👩‍💻 Author

**Nithyashree**

**Course:** B.Tech – Computer Science and Business Systems

---

## ⭐ Project Status

**Completed**
