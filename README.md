🔐 Building a Brute-Force Detection Lab with Wazuh SIEM: A Detailed Guide
📌 Introduction

In today’s cybersecurity landscape, brute-force attacks remain one of the most common methods attackers use to gain unauthorized access to systems. Detecting such attacks in real time is a critical responsibility of a Security Operations Center (SOC).

This project demonstrates how to build a brute-force attack detection lab using Wazuh SIEM, simulating real-world attack scenarios and analyzing logs to generate alerts.

🎯 Objective

The goal of this project is to:

Simulate an SSH brute-force attack

Monitor authentication logs

Detect suspicious activity using Wazuh

Generate real-time alerts in a SIEM dashboard

🧱 Lab Architecture

Kali Linux (Attacker) → Ubuntu (Target + Wazuh Agent) → Wazuh Server (SIEM)

🖥️ Environment Setup
🔹 Attacker Machine

OS: Kali Linux

Tools:

Hydra

Nmap

🔹 Victim Machine

OS: Ubuntu

Services:

SSH enabled

Wazuh Agent installed

🔹 SIEM Server

Wazuh Server:

Wazuh Manager

Wazuh Dashboard

⚙️ Tools Used

Hydra → Password brute-force tool

Nmap → Network scanner

Wazuh → SIEM platform

SSH → Target service

🚀 Step-by-Step Attack Simulation
1️⃣ Scan for Open Ports

Before launching the attack, identify open services using Nmap:

nmap -p 22 <target-ip>

This confirms that the SSH port (22) is open.

2️⃣ Launch Brute-Force Attack

Use Hydra to perform the attack:

hydra -l <username> -P passwords.txt ssh://<target-ip>

👉 This command attempts multiple password combinations on the SSH service.

3️⃣ Attack Behavior

Multiple failed login attempts occur

Logs are generated in:

/var/log/auth.log
🔍 Detection Using Wazuh

Wazuh continuously monitors system logs and applies detection rules.

🔄 Detection Workflow

Wazuh Agent collects logs from Ubuntu

Logs are sent to Wazuh Server

Wazuh analyzes logs using built-in rules

Alerts are triggered for:

Multiple failed logins

Brute-force patterns

📊 Results and Observations

🚨 Real-time alerts generated in Wazuh Dashboard

🔍 Suspicious login activity detected

📁 Logs successfully collected and analyzed

📈 Clear visibility into attack behavior
