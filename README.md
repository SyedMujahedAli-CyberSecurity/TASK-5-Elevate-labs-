# TASK-5-Elevate-labs-
# Task 5 — Capture and Analyze Network Traffic using Wireshark

**Student:** Syed Mujahed Ali  
**Project:** Task 5 — Capture and Analyze Network Traffic  
**Date:**11-08-2025
**Tools Used:** Windows 11, Wireshark, Command Prompt, Web Browser

---

## Objective
Capture live network traffic over a Wi-Fi interface using Wireshark, apply filters to identify multiple protocols, and analyze their details to understand how they operate.

---

## Activities and Implementation

### 1. Selecting the Wi-Fi Interface
Opened Wireshark and selected the **Wi-Fi** interface to capture packets from the active wireless connection.

---

### 2. Starting Capture and Generating Traffic
While capturing was in progress, I generated different types of traffic:
- Opened `http://example.com` and `https://wikipedia.org` in the browser.
- Used `ping google.com` in Command Prompt to send ICMP packets.
- Used `nslookup google.com` to trigger DNS lookups.

**Evidence:**  
![Ping with capture running](screenshots/Screenshot_50.png)

---

### 3. Applying Filters and Analyzing Protocols

#### DNS (Domain Name System)
**Filter:** `dns`  
**Purpose:** Resolves domain names to IP addresses.  
**Observation:** Captured DNS queries and responses for domains like `self.events.data.microsoft.com`.  
**Details:** UDP over port 53, IPv6 addresses returned in AAAA records.  
![DNS traffic](screenshots/Screenshot_51.png)

---

#### TLS (Transport Layer Security)
**Filter:** `tls`  
**Purpose:** Encrypts communication for secure data transfer over HTTPS.  
**Observation:** Multiple TLSv1.2 and TLSv1.3 sessions captured, showing Application Data and Encrypted Alerts.  
**Details:** TCP over port 443; payload content encrypted.  
![TLS traffic](screenshots/Screenshot_52.png)

---

#### ICMP (Internet Control Message Protocol)
**Filter:** `icmpv6`  
**Purpose:** Used for network diagnostics like `ping`.  
**Observation:** Echo Request and Echo Reply packets matched the `ping google.com` test.  
**Details:** Showed round-trip request/reply between my machine and the destination.  
![ICMP traffic](screenshots/Screenshot_53.png)

---

## Results / Observations
- Successfully identified and analyzed DNS, TLS, and ICMP traffic.
- DNS packets revealed queried domains and IP addresses.
- TLS traffic confirmed secure, encrypted web sessions.
- ICMP traffic verified connectivity and response times.

---

## Conclusion
The exercise demonstrated how to:
1. Capture live traffic using Wireshark.
2. Apply display filters to isolate specific protocols.
3. Interpret packet details for DNS, TLS, and ICMP.

This built familiarity with Wireshark’s interface and the structure of common network protocols.

---

## Repository Contents
- `README.md` — This report.
- `screenshots/` — Folder containing:
  - `Screenshot_50.png` — Ping with Wireshark capture running.
  - `Screenshot_51.png` — DNS traffic filter view.
  - `Screenshot_52.png` — TLS traffic filter view.
  - `Screenshot_53.png` — ICMP traffic filter view.
- `task5_capture.pcapng` — Saved packet capture file.
