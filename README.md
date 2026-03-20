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

  <img width="1920" height="922" alt="VirtualBox_Kali Linux_20_03_2026_16_02_35" src="https://github.com/user-attachments/assets/d558201d-b9f5-42c7-a032-8e82607ef163" />
  <img width="1920" height="922" alt="VirtualBox_Kali Linux_20_03_2026_15_52_35" src="https://github.com/user-attachments/assets/fc7595e4-f3f0-46a1-aa60-56ec6c14bab2" />
  <img width="1920" height="922" alt="VirtualBox_Ubuntu_20_03_2026_15_14_42" src="https://github.com/user-attachments/assets/d593007c-f32e-4244-ae90-568caede85f9" />
  <img width="1920" height="922" alt="VirtualBox_Ubuntu_20_03_2026_15_55_01" src="https://github.com/user-attachments/assets/097654ee-a21a-4e2c-805f-b854905e14f2" />
  <img width="1920" height="922" alt="VirtualBox_Ubuntu_20_03_2026_15_43_26" src="https://github.com/user-attachments/assets/1f6b9387-d0c8-4f51-9e0f-629cc42de67b" />
  <img width="1920" height="922" alt="VirtualBox_Ubuntu_20_03_2026_15_55_19" src="https://github.com/user-attachments/assets/b67acd71-1795-43d5-ae3d-6822165b09a4" />


---

## 👤 Author

Yerramsetty Purandeshwar
Cybersecurity Enthusiast | SOC Analyst Aspirant

---
