# 🔐 Brute Force Detection using Wazuh SIEM

## 📌 Project Overview

This project demonstrates the detection of **SSH brute-force attacks** using **Wazuh SIEM** in a controlled lab environment.

An attack is simulated using **Hydra** from Kali Linux, while logs are collected from an Ubuntu machine and analyzed by the Wazuh server to generate real-time alerts.

---

## 🧱 Architecture

Kali Linux (Attacker) → Ubuntu (Target + Wazuh Agent) → Wazuh Server (SIEM + Dashboard)

---

## 🖥️ Lab Setup

| Machine      | Role              | Tools Installed          |
| ------------ | ----------------- | ------------------------ |
| Kali Linux   | Attacker          | Hydra, Nmap              |
| Ubuntu       | Victim            | SSH, Wazuh Agent         |
| Wazuh Server | SIEM & Monitoring | Wazuh Manager, Dashboard |

---

## ⚙️ Tools & Technologies

* Hydra (Brute-force attack simulation)
* Nmap (Network scanning)
* Wazuh SIEM (Detection & monitoring)
* SSH Service (Target service)
* Linux (Ubuntu & Kali)

---

## 🚀 Attack Simulation

### 1️⃣ Port Scanning

```bash
nmap -p 22 <target-ip>
```

### 2️⃣ Brute-force Attack

```bash
hydra -l <username> -P passwords.txt ssh://<target-ip>
```

### 3️⃣ Result

* Multiple failed SSH login attempts generated
* Logs recorded in `/var/log/auth.log`

---

## 🔍 Detection Workflow

1. Wazuh Agent monitors system logs on Ubuntu
2. Logs are forwarded to Wazuh Server
3. Wazuh rules detect:

   * Multiple failed login attempts
   * Brute-force attack patterns
4. Alerts generated in Wazuh Dashboard

---

## 📊 Results

* 🚨 Real-time brute-force attack alerts detected
* 📈 Log correlation and analysis performed
* 🔐 Improved visibility into authentication attempts

---

## 📸 Screenshots

> Add screenshots of:

* Hydra attack running
* Wazuh dashboard alerts
* SSH logs (`auth.log`)

---

## 📚 Key Learnings

* Brute-force attack techniques
* SIEM-based detection mechanisms
* Log analysis and correlation
* SOC workflow fundamentals

---

## 🔮 Future Improvements

* 🔒 Implement Active Response (auto-block attacker IP)
* 🔥 Integrate firewall rules (iptables / ufw)
* 📧 Enable email alerting
* 📊 Add visualization dashboards

---

## 👤 Author

**Your Name**
Cybersecurity Enthusiast | SOC Analyst Aspirant

---
