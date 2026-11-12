# 🛡️ Penetration Testing Report – Footprinting & Network Scanning

**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

---

## 👤 Project Details

| Field | Details |
|---|---|
| Pentester Name | Ayush Bhardwaj |
| Program/Batch | B084 – Networkwalks |
| Date | 11 November 2026 |
| Modules Completed | W2-PM1 (Multiple Kali Tools) <br> W2-PM5 (Zenmap Scanning) |
| Client/Target | 1. Networkwalks (Written Permission Secured) <br> 2. My Own Local LAN Network |
| Permission Secured | Yes |
| Phases Covered | Phase 1: Reconnaissance & Footprinting <br> Phase 2: Scanning & Network Discovery <br> Phase 3–5: In Progress |

---

## 1. ⚠️ Liability Disclaimer

I have performed these activities only on systems and devices where I had secured written permission or on devices and systems that I own myself. All these materials are for educational and research purposes only.

Do not use anything from here to break the law. The instructor, authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility.

Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. Unauthorized access is a crime in most countries, even when nothing is damaged.

---

## 2. 📌 Introduction

This report covers footprinting the `networkwalks.com` domain using multiple Kali Linux tools (W2-PM1) and scanning my own local network with Zenmap (W2-PM5).

One module covers the footprinting phase and the other covers the scanning phase. Together, they demonstrate how an attacker moves from gathering publicly available information to identifying live hosts on a network.

This is Week 2 of my ongoing Cybersecurity and Ethical Hacking internship program at Networkwalks.

All activities were performed using Kali Linux for footprinting and a Windows PC with Zenmap installed for network scanning.

Each activity includes the commands used, observations, screenshots as evidence, and an explanation of why the findings matter from a cybersecurity perspective.

---

## 3. 🛠️ Tools Used

The following tools were used during the practical activities:

| Tool | Purpose |
|---|---|
| Kali Linux | Operating system used for reconnaissance activities |
| Windows | Operating system used for network scanning |
| WHOIS | Find domain registration details, ownership and name servers |
| WhatWeb | Identify website technologies, CMS and server information |
| Nslookup | Resolve domain names into IP addresses using DNS |
| Curl -I | Inspect HTTP response headers |
| Wafw00f | Detect Web Application Firewall protection |
| DNSRecon | Enumerate DNS records such as NS, MX, SPF and TXT |
| Zenmap (Nmap GUI) | Discover live hosts, IP addresses and MAC addresses |
| Windows CMD | Identify local IP and MAC address information |

---

## 4. 🔍 Activities Performed

### 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the `networkwalks.com` domain using Kali Linux tools.

The objective was to collect publicly available information about the target website and understand how different tools help during the footprinting phase.

**1. WhatWeb**

Used WhatWeb to identify the technologies used by the website.

- Identified WordPress 7.1.4.
- Detected WP Download Manager 3.3.76.
- Identified Apache, Bootstrap and jQuery.
- Collected website IP address information.

**2. Nslookup**

Used Nslookup to resolve the domain name into its corresponding IP address.

- Domain: `networkwalks.com`
- IP Address: `192.232.216.135`
- DNS Server: `1.1.1.1`

**3. Curl -I**

Used Curl with the `-I` option to inspect HTTP response headers.

- Received HTTP/2 200 response.
- Identified the Apache server.
- Observed the WordPress REST API endpoint `/wp-json/`.
- Collected additional HTTP header information.

**4. Wafw00f**

Used Wafw00f to identify whether a Web Application Firewall was protecting the website.

- Identified ModSecurity (SpiderLabs).
- Detection was completed using two HTTP requests.

These tools helped me understand how publicly available website information can be collected and analyzed during the footprinting phase.

### 4.2 Network Scanning with Zenmap

For the second activity, I used Zenmap to perform network discovery on my own local virtual network.

The objective was to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.

I entered my subnet into Zenmap and selected **Ping Scan** to identify active hosts.

**Network Details:**

| Parameter | Details |
|---|---|
| Network | 10.0.0.0/24 |
| Total IP Addresses Scanned | 256 |
| Live Hosts Found | 3 |
| Scan Time | 2.89 seconds |

**Discovered Hosts:**

| IP Address | MAC Address | Device |
|---|---|---|
| 10.0.0.1 | 52:54:00:12:35:00 | QEMU Virtual NIC |
| 10.0.0.2 | 08:00:27:1D:C8:FB | My Kali Linux Machine |
| 10.0.0.254 | 08:00:27:84:69:E4 | Oracle VirtualBox Virtual NIC |

After completing the scan, I opened the Topology section in Zenmap to view the discovered hosts and their connections to localhost.

I generated the network topology and saved the output in PDF format.

This activity helped me understand how Zenmap can be used to discover active devices and visually represent a local network.

---

## 5. ⚠️ Risk Analysis / Impact

Based on the information collected during the footprinting and network scanning activities, I identified the following potential risks.

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Web technology information exposed | WordPress 7.1.4, WP Download Manager 3.3.76, Apache and jQuery identified | Attackers may identify software requiring further security review | 🟠 Medium |
| 2 | Server IP address identifiable | Domain resolved to 192.232.216.135 | Provides information about the network location of the web service | 🟢 Low |
| 3 | HTTP technical information exposed | Apache server and WordPress REST API endpoint identified | May assist technology fingerprinting and further enumeration | 🟢 Low |
| 4 | WAF technology identifiable | ModSecurity (SpiderLabs) detected | Reveals information about the web application's security architecture | 🟢 Low |
| 5 | Multiple live hosts visible on local network | Zenmap identified three live hosts | Unknown or unauthorized devices may potentially be present on a network | 🟠 Medium |

**Risk Level Key:**
- 🔴 Critical
- 🟠 Medium
- 🟢 Low

The risks listed above are observations from the footprinting and scanning exercises, not confirmed vulnerabilities.

No exploitation or vulnerability validation was performed as part of these two modules. Further authorized security testing would be required to confirm any actual vulnerability.

---

## 6. 💡 Recommendations

Based on the observations from these activities, I recommend the following security improvements:

**1. Review Publicly Exposed Technology Information**

Organizations should regularly review the information exposed about their web technologies, CMS platforms and plugins to reduce unnecessary information disclosure.

**2. Keep Software Updated**

WordPress, WP Download Manager, jQuery and other web technologies should be regularly updated to fix known security vulnerabilities.

**3. Secure HTTP Response Headers**

Review HTTP response headers and configure appropriate security headers to reduce unnecessary information exposure and improve web application security.

**4. Protect WordPress REST API**

Review access to the `/wp-json/` endpoint and ensure that sensitive information is not publicly accessible without proper authorization.

**5. Properly Configure and Monitor the WAF**

Keep ModSecurity enabled, updated and properly configured to detect and block suspicious web requests.

**6. Monitor Public-Facing Infrastructure**

Regularly review server IP addresses and publicly exposed services to identify unexpected changes or security issues.

**7. Perform Regular Internal Network Scanning**

Organizations should periodically use tools such as Zenmap to identify active devices and monitor their local networks.

**8. Investigate Unknown Network Devices**

Any unexpected devices discovered during network scanning should be investigated and verified to prevent unauthorized network access.

**9. Maintain Network Documentation**

Keep records of IP addresses, MAC addresses, network devices and topology diagrams to make network monitoring and troubleshooting easier.

**10. Perform Authorized Security Assessments**

Conduct regular security assessments to identify potential weaknesses in web applications and network infrastructure. All testing should be performed with proper authorization.

---

## 7. 🎯 Conclusion

During Week 2 of my Cybersecurity and Ethical Hacking internship, I completed practical activities covering footprinting, reconnaissance and network scanning.

In the footprinting activity, I used Kali Linux tools to collect information about the target domain. I learned how WhatWeb identifies web technologies, Nslookup resolves domain names, Curl inspects HTTP headers, and Wafw00f detects Web Application Firewalls.

In the network scanning activity, I used Zenmap to identify my local network configuration and discover active hosts. I also collected IP and MAC address information and created a network topology.

These exercises helped me understand that information gathering is an important part of cybersecurity. Even before attempting to exploit a system, a security professional can learn a significant amount about an environment by analyzing publicly available information and network responses.

I also learned that technical findings should be documented clearly, including the activities performed, observations, potential risks and recommended security improvements.

Finally, I understood that reconnaissance and scanning must always be performed within an authorized scope. All activities were completed as part of the assigned educational cybersecurity lab.

---

## 8. 📸 Evidences Collected

### Footprinting & Reconnaissance

**WhatWeb – Technology Identification**

<img width="422" height="80" alt="Screenshot 2026-11-11 183249" src="https://github.com/user-attachments/assets/5e4bceee-9eec-4277-9144-39c6891c2d1a" />

**Nslookup – DNS Resolution**

<img width="88" height="50" alt="Screenshot 2026-11-11 183316" src="https://github.com/user-attachments/assets/40b5011d-d946-4dfc-84a3-32d32d1e5808" />

**Curl – HTTP Response Headers**

<img width="421" height="86" alt="Screenshot 2026-11-11 183420" src="https://github.com/user-attachments/assets/4866e3ef-0d77-4ca5-9cbf-e8682a3b9bd9" />

**Wafw00f – WAF Detection**

<img width="229" height="115" alt="Screenshot 2026-11-11 183448" src="https://github.com/user-attachments/assets/8f2a7573-3bb1-49fb-b973-e9ba8516eff8" />

### Network Scanning – Zenmap

**Network Topology**

<img width="347" height="211" alt="Screenshot 2026-11-11 190026" src="https://github.com/user-attachments/assets/fc6d1c25-cbb4-48a8-8822-64c2351a90e2" />

---

## 👤 Author

**Ayush Bhardwaj**

Cybersecurity Intern – B084

LinkedIn: [Ayush Bhardwaj](https://www.linkedin.com/in/ayush-bhardwaj-82970832b/)

---

## 📌 Project Information

- **Program Name:** Cybersecurity Program at Networkwalks
- **Week:** 02
- **Modules:** W2-PM1 & W2-PM5
- **Repository:** [Ayush-Bhardwaj-cyber](https://github.com/Ayush-Bhardwaj-cyber)

---

**End of Report** 🛡️
