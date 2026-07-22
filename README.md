This repository is designed for students, cybersecurity enthusiasts, SOC analysts, and defensive security professionals who want to learn the most commonly used Blue Team tools in a structured order. Each tool includes its primary use case, executable, and a simple example to help you get started.

> **⚠️ Disclaimer**
>
> This repository is intended **for educational and defensive security purposes only**. The tools listed here should be used only in environments where you have authorization to monitor, investigate, or secure systems.

---

# 🎯 Learning Order

The tools in this repository follow a typical Blue Team workflow. You'll start with foundational command-line utilities before progressing through monitoring, detection, investigation, incident response, and automation.


Commands & Utilities
        ↓
SIEM
        ↓
Security Onion
        ↓
Endpoint Detection & Response (EDR/XDR)
        ↓
Threat Intelligence
        ↓
Endpoint Telemetry & Logging
        ↓
Network Monitoring (IDS/IPS/NSM)
        ↓
Network Traffic Analysis
        ↓
Asset Discovery
        ↓
Vulnerability Management
        ↓
SOAR
        ↓
Detection Engineering
        ↓
Digital Forensics & Incident Response (DFIR)
        ↓
Incident & Case Management
        ↓
Analysis Utilities

---

# 🖥️ 1. Commands & Utilities

These foundational tools are used daily by SOC analysts, DFIR investigators, and detection engineers for automation, scripting, packet capture, and certificate inspection.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Bash | Shell scripting & SOC automation | `bash` | `bash script.sh` |
| Python | Automation, log parsing & scripting | `python3` | `python3 parser.py` |
| Git | Clone repositories & manage detection rules | `git` | `git clone https://github.com/SigmaHQ/sigma.git` |
| OpenSSL | Inspect certificates & TLS configuration | `openssl` | `openssl s_client -connect target.com:443` |
| tcpdump | Command-line packet capture | `tcpdump` | `tcpdump -i eth0` |

---

# 📊 2. SIEM (Security Information & Event Management)

SIEM platforms centralize logs from multiple sources, correlate events, generate alerts, and help analysts investigate security incidents efficiently.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Splunk | Enterprise log analysis & alert triage | `splunk` | `sudo /opt/splunk/bin/splunk start` |
| Elastic Stack (ELK) | Open-source SIEM & analytics platform | `elasticsearch`, `kibana` | `sudo systemctl start elasticsearch` |
| Wazuh | Open-source SIEM + XDR platform | `wazuh-manager` | `sudo systemctl start wazuh-manager` |
| Microsoft Sentinel | Cloud-native SIEM on Azure | Azure Portal | Managed via Azure Portal |

---

# 🧅 3. Security Onion (SOC Platform)

Security Onion is an integrated SOC platform that combines multiple open-source security tools into a single environment for monitoring, detection, and investigation.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Security Onion | SOC platform with Suricata, Zeek, Elastic, Fleet and more | `so-status` | `sudo so-status` |

---

# 🛡️ 4. Endpoint Detection & Response (EDR / XDR)

EDR and XDR platforms continuously monitor endpoints, detect malicious activity, support investigations, and help security teams respond to threats.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| CrowdStrike Falcon | Cloud-managed EDR & threat hunting | `falconctl` | `sudo falconctl -g --aid` |
| Microsoft Defender for Endpoint | Microsoft enterprise EDR | `mdatp` | `mdatp health` |
| SentinelOne | Independent EDR/XDR platform | Agent (background service) | Managed via Singularity Console |
| Microsoft Defender XDR | Unified Microsoft XDR platform | Web Portal | `https://security.microsoft.com` |

---

# 🌐 5. Threat Intelligence

Threat intelligence platforms help enrich investigations by checking file hashes, IP addresses, domains, URLs, and other indicators of compromise (IOCs).

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| VirusTotal | Reputation lookup for files, URLs & hashes | `vt` (optional CLI) | `vt file <hash>` |
| MISP | Threat intelligence sharing platform | `docker compose` | `docker compose up -d` |

---

# 📝 6. Endpoint Telemetry & Logging

These tools generate detailed endpoint logs that support threat hunting, incident investigations, and detection engineering.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Sysmon | Detailed endpoint logging (Windows-first) | `sysmon` | `sudo sysmon -i config.xml` *(Linux port)* |
| osquery | SQL-based endpoint visibility | `osqueryi` | `osqueryi` |

> **📝 Note**
>
> Sysmon is primarily deployed on Windows. Although a Linux port exists, it is significantly less common than the Windows implementation.

---

# 📡 7. Network Monitoring (IDS / IPS / NSM)

These tools monitor network traffic to detect malicious activity, analyze protocols, and generate alerts based on signatures or behavioral analysis.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Suricata | Multi-threaded IDS/IPS | `suricata` | `sudo suricata -i eth0 -c /etc/suricata/suricata.yaml` |
| Zeek | Network Security Monitoring (NSM) & protocol analysis | `zeek` | `sudo zeek -i eth0` |
| Snort | Signature-based IDS | `snort` | `sudo snort -i eth0 -c /etc/snort/snort.conf` |

---

# 📈 8. Network Traffic Analysis

Traffic analysis tools inspect captured packets to understand network behavior, troubleshoot issues, and investigate security incidents.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Wireshark | GUI packet analysis | `wireshark` | `wireshark` |
| TShark | Command-line packet analysis | `tshark` | `tshark -i eth0` |
| Arkime ⭐ | Large-scale packet capture, indexing & search | `arkime` | `docker compose up -d` |

---

# 🖥️ 9. Asset Discovery

Asset discovery tools identify hosts, services, operating systems, and network assets to maintain an accurate inventory of the environment.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Nmap | Network discovery, service detection & asset inventory | `nmap` | `nmap -sV 192.168.1.0/24` |

---

# 🔍 10. Vulnerability Management

Vulnerability management solutions scan systems, identify known weaknesses, prioritize risks, and support remediation efforts.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Nessus | Enterprise vulnerability scanner | `nessusd` | `sudo systemctl start nessusd` |
| Greenbone Vulnerability Management (GVM / OpenVAS) | Open-source vulnerability scanning | `gvm-start` | `sudo gvm-start` |

> **📝 Note**
>
> **OpenVAS** now primarily refers to the scanning engine, while the complete platform is commonly known as **Greenbone Vulnerability Management (GVM)**.

---

# 🤖 11. SOAR (Security Orchestration, Automation & Response)

SOAR platforms automate repetitive security tasks, orchestrate responses across multiple security tools, and help analysts investigate and respond to incidents more efficiently.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Splunk SOAR (formerly Phantom) | Automate response playbooks for Splunk alerts | Web Console | Managed through Splunk SOAR |
| Cortex XSOAR (Palo Alto) | Enterprise SOAR platform | Web Console | Managed through Cortex XSOAR Portal |

> **📝 Note**
>
> SOAR platforms are typically deployed as appliances or cloud services and are managed through a web interface rather than a Linux command-line interface.

---

# 🎯 12. Detection Engineering

Detection engineering focuses on creating, testing, and maintaining detection rules that identify suspicious activity across endpoints, networks, and SIEM platforms.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| YARA | Malware identification using pattern-matching rules | `yara` | `yara rules.yar suspicious.exe` |
| Sigma | Vendor-neutral detection rule format | `sigma` | `sigma convert -t splunk rule.yml` |

---

# 🧪 13. Digital Forensics & Incident Response (DFIR)

DFIR tools help investigate security incidents by analyzing disk images, memory dumps, endpoint artifacts, and event logs to determine what happened and support recovery efforts.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| Autopsy | Disk forensics, timelines & deleted file recovery | `autopsy` | `autopsy` |
| Volatility 3 | Memory forensics & RAM analysis | `volatility3` | `volatility3 -f memory.raw windows.pslist` |
| Velociraptor | Enterprise DFIR & threat hunting | `velociraptor` | `sudo ./velociraptor gui` |
| Chainsaw ⭐ | Fast Windows Event Log hunting using Sigma rules | `chainsaw` | `chainsaw hunt logs/ --rules sigma/` |
| Hayabusa ⭐ | Windows Event Log analysis & threat detection | `hayabusa` | `hayabusa scan -d C:\Logs` *(Windows)* |

> **📝 Note**
>
> **Chainsaw** and **Hayabusa** are widely used during Windows-focused DFIR investigations because they provide fast and efficient Windows Event Log analysis.

---

# 📂 14. Incident & Case Management

These platforms help security teams organize investigations, manage evidence, track tasks, and collaborate throughout the incident response lifecycle.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| TheHive | Security incident & case management | `thehive` | `sudo systemctl start thehive` |
| Cortex (TheHive Project) | IOC enrichment & automated analyzers | `cortex` | `sudo systemctl start cortex` |

> **📝 Note**
>
> **Cortex** from **TheHive Project** is used for IOC enrichment and automated analyzers. It is **not** the same product as **Cortex XSOAR** from Palo Alto Networks.

---

# 🧰 15. Analysis Utilities

These utilities simplify decoding, transforming, hashing, and analyzing data during threat hunting, malware analysis, incident response, and digital forensics.

| Tool | Use Case | Executable | Example |
|------|----------|------------|---------|
| CyberChef | Decode, encode, hash, encrypt, decrypt, transform, and analyze data | Web Application | Open CyberChef in a browser |

---

# 📖 Recommended Learning Resources

- TryHackMe (SOC Level 1 & Blue Team Rooms)
- Blue Team Labs Online (BTLO)
- LetsDefend
- CyberDefenders
- Security Onion Documentation
- Splunk Documentation
- Elastic Documentation
- Wazuh Documentation
- SigmaHQ
- MITRE ATT&CK Framework
- MITRE D3FEND
- Malware Traffic Analysis
- DFIR Report
- SANS DFIR

---

# 🤝 Contributing

Contributions are welcome! If you'd like to add new defensive tools, improve descriptions, fix inaccuracies, or expand the repository, feel free to open an issue or submit a pull request.

---

# ⚖️ License

This project is licensed under the **MIT License**.

---

# ⭐ Support

If you find this repository useful, consider giving it a **⭐ Star**. It helps others discover the project and motivates future improvements.

---

# ⚠️ Disclaimer

This repository is intended **for educational and defensive security purposes only**. The tools listed here should only be used to monitor, investigate, detect, and defend systems where you have proper authorization. The author is not responsible for any misuse of the information provided in this repository.
