# 🛡️ Networkwalks – Week 2 Cybersecurity Labs

## 📌 Project Overview

This repository documents my hands-on cybersecurity activities completed during Week 2 of the Networkwalks Cybersecurity Internship Program – Batch B084.

The objective was to perform reconnaissance, gather information about a target domain, identify web technologies, inspect DNS records and HTTP responses, detect Web Application Firewall (WAF) technologies, and discover active hosts on a local network.

The activities covered two major phases of penetration testing: **Reconnaissance & Footprinting** and **Scanning & Network Discovery**.

## 🧰 Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux & windows | Cybersecurity testing environment |
| WhatWeb | Identifying website technologies and server details |
| Nslookup | Resolving domain names to IP addresses |
| cURL | Inspecting HTTP response headers |
| Wafw00f | Detecting Web Application Firewall technologies |
| Nmap | Discovering active hosts on a network |
| Zenmap | GUI-based network scanning and topology visualization |
| Terminal | Executing reconnaissance and scanning commands |

## 🏗️ Lab Configuration

| Component | Configuration |
|---|---|
| Operating System | Kali Linux & windows |
| Virtualization | Oracle VirtualBox |
| Network Interface | eth0 |
| Kali IP Address | `10.0.0.2` |
| Network Subnet | `10.0.0.0/24` |
| Subnet Mask | `255.255.255.0` |
| Target Domain | `networkwalks.com` |
| Target IP Address | `192.232.216.135` |
| Scanning Tool | Nmap / Zenmap 7.98 |
| Scan Type | Ping Scan |
| Network Range | `10.0.0.0/24` |

## ⚙️ Step-by-Step Implementation

### 1. Phase 1 – Reconnaissance & Footprinting

Performed passive and active information gathering against the authorized target domain `networkwalks.com`.

**Tasks performed:**

- Identified the technologies used by the target website.
- Retrieved the target domain's IP address using DNS lookup.
- Inspected HTTP response headers using cURL.
- Identified the Web Application Firewall using Wafw00f.
- Examined publicly exposed server and web application information.

**Commands Used:**

```bash
whatweb https://networkwalks.com

nslookup networkwalks.com

curl -I https://networkwalks.com

wafw00f https://networkwalks.com
```

**Key Findings:**

- Identified WordPress 7.1.4 and WP Download Manager 3.3.76.
- Detected Apache, jQuery 3.7.1 and Bootstrap.
- Resolved `networkwalks.com` to `192.232.216.135`.
- Observed an HTTP/2 200 response.
- Detected ModSecurity (SpiderLabs) as the WAF.

**Screenshots:** 
<img width="422" height="80" alt="Screenshot 2026-11-11 183249" src="https://github.com/user-attachments/assets/2f1a401e-88ef-49b8-9505-83fdd3a3ce12" />

<img width="88" height="50" alt="Screenshot 2026-11-11 183316" src="https://github.com/user-attachments/assets/106b05c6-3177-4ebf-8caf-ca85d90c64b1" />

<img width="421" height="86" alt="Screenshot 2026-11-11 183420" src="https://github.com/user-attachments/assets/2b8d8fea-01aa-451f-b09f-ca11e8394774" />

<img width="229" height="115" alt="Screenshot 2026-11-11 183448" src="https://github.com/user-attachments/assets/209126b8-3981-4290-8ea5-4a67a893c77d" />


### 2. Phase 2 – Scanning & Network Discovery

Performed network discovery using Nmap and Zenmap to identify active hosts within the local virtual network.

**Tasks performed:**

- Identified the local network subnet.
- Configured a ping scan for `10.0.0.0/24`.
- Identified active hosts on the network.
- Examined MAC addresses and vendor information.
- Generated a network topology diagram using Zenmap.

**Commands Used:**

```bash
ip a

nmap -sn 10.0.0.0/24
```

**Scan Results:**

- Total IP addresses scanned: 256
- Active hosts discovered: 3
- Scan duration: 2.89 seconds

**Discovered Hosts:**

| IP Address | MAC Address | Identification |
|---|---|---|
| `10.0.0.1` | `52:54:00:12:35:00` | QEMU virtual NIC |
| `10.0.0.2` | `08:00:27:1D:C8:FB` | Kali Linux |
| `10.0.0.254` | `08:00:27:84:69:E4` | Oracle VirtualBox virtual NIC |

**Screenshot:**
<img width="347" height="211" alt="Screenshot 2026-11-11 190026" src="https://github.com/user-attachments/assets/3306a7f2-491a-4772-bc52-9f97f773dc3f" />

<img width="122" height="175" alt="Screenshot 2026-11-11 193347" src="https://github.com/user-attachments/assets/030cfdfe-07ad-4d7f-ac8b-af1abbf9edda" />

## 🐛 Troubleshooting

### Website Information Gathering

Different tools provided different types of information about the target website.

Used WhatWeb, Nslookup, cURL and Wafw00f to gather and verify web technology, DNS, HTTP and WAF information.

### DNS Resolution

Verified that the target domain resolved successfully to its corresponding IP address using Nslookup.

### Network Discovery

Configured the correct network range and used the Nmap ping scan to identify active hosts within the local subnet.

### Network Topology Generation

Used Zenmap to visualize discovered devices and generate a network topology diagram for better understanding of the network structure.

## 📚 Learning Outcomes

- Learned the fundamentals of reconnaissance and footprinting.
- Identified website technologies using WhatWeb.
- Understood DNS resolution using Nslookup.
- Inspected HTTP response headers using cURL.
- Learned how to identify WAF technologies using Wafw00f.
- Understood host discovery using Nmap.
- Used Zenmap for graphical network scanning and topology visualization.
- Identified active devices and their MAC addresses.
- Improved practical knowledge of penetration testing methodology and network discovery.

## 🏆 Lab Completion

| Activity | Result |
|---|---|
| WhatWeb – Website Fingerprinting | Completed |
| Nslookup – DNS Resolution | Completed |
| cURL – HTTP Header Inspection | Completed |
| Wafw00f – WAF Detection | Completed |
| Nmap – Network Discovery | Completed |
| Zenmap – Network Topology | Completed |

## 👨‍💻 Author

**Ayush Bhardwaj**

Networkwalks Cybersecurity Internship Program – Batch B084

**Project:** Week 2 – Footprinting, Reconnaissance & Network Scanning

**LinkedIn Update:** [View LinkedIn Post](https://lnkd.in/p/gu9sfuby)
