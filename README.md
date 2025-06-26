# 🛡️ Nessus Essentials Vulnerability Scan - Windows Localhost

## 📌 Objective
Perform a vulnerability scan on a local Windows machine using **Nessus Essentials** and identify potential security risks.

---

## 🖥️ Scan Information

- **Scanner**: Tenable Nessus Essentials
- **Target**: 127.0.0.1 (localhost)
- **Host OS**: Windows 11
- **Scan Date**: 26 June 2025
- **Nessus Version**: Essentials Free Edition

---

## 📊 Summary of Detected Issues

| Severity  | Count |
|-----------|-------|
| 🔴 Critical | 0     |
| 🟠 High     | 0     |
| 🟡 Medium   | 2     |
| 🟢 Low      | 1     |
| 🧪 Info     | Many (default info plugins)

---

## 🚨 Top Vulnerabilities Identified

### 1. ❗ **SSL Certificate Cannot Be Trusted**
- **Plugin ID**: 51192
- **Risk**: Medium
- **CVSS v3**: 6.5
- **Summary**: The SSL certificate on port 8834 (Nessus Web UI) is self-signed or not trusted.
- **Fix**: Use a certificate from a trusted Certificate Authority (CA).

---

### 2. ⚠️ **SMB Signing Not Required**
- **Plugin ID**: 57608
- **Risk**: Medium
- **CVSS v3**: 5.3
- **Summary**: SMB service on port 445 does not require message signing, making it vulnerable to MITM attacks.
- **Fix**: Enable message signing in Windows Local Security Policy:
  - `Local Policies > Security Options > Microsoft network server: Digitally sign communications (always)` → **Enable**

---

### 3. ℹ️ **UPnP Detection**
- **Plugin ID**: 35712
- **Risk**: Informational
- **Summary**: The system exposes detailed UPnP data over HTTP (port 2869), which may be useful to attackers for fingerprinting.
- **Fix**: Disable UPnP services if not needed via Services or Windows Features.

---

## 🩹 General Recommendations

- Apply all Windows updates and patch regularly.
- Use strong certificates for internal services (e.g., Nessus UI).
- Harden SMB by disabling legacy protocols and enforcing signing.
- Disable unused services like UPnP, NetBIOS, or remote access.

---

## 📸 Screenshots

> *(Add screenshots from your Nessus dashboard/report here)*

- ![img](https://github.com/Amish-C-K/Elevate-Labs--task3/blob/main/images/t3-1.png)
- ![img](https://github.com/Amish-C-K/Elevate-Labs--task3/blob/main/images/t3-1.png)
- ![img](https://github.com/Amish-C-K/Elevate-Labs--task3/blob/main/images/t3-1.png)

---

## 📁 Files in This Repo

| File                   | Description                        |
|------------------------|------------------------------------|
| `report.pdf`           | Full Nessus scan result            |
| `README.md`            | Report summary (this file)         |
| `screenshots/`         | Screenshots from Nessus Web UI     |

---

## 🗣️ Interview Takeaways

- **Q:** Why is SMB signing important?  
  **A:** It prevents tampering during SMB communication by enforcing integrity checks.

- **Q:** What does a self-signed certificate risk?  
  **A:** It can enable MITM attacks due to lack of trust verification.

- **Q:** Should UPnP be enabled?  
  **A:** Only if required. Otherwise, it's safer to disable due to exposure of internal service info.

---

## 👨‍💻 Author

**Amish Chandran Kasaragod (Ack)**  
Security Researcher | Cybersecurity Intern  
GitHub: [@Amish-C-K](https://github.com/Amish-C-K)

---

