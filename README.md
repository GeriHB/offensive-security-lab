# Offensive Security Lab

This repository documents the setup, exploitation, and reporting of my **self-buil pentesting lab**,

The lab is designed tot simulate real-world environments (Active Directtory, Linux, and web applications) and prepare for certtificattions like **PNPT, OSCP, and CRTP**, as well as practical job scenarios in offensive security.

---

## Objectives
- Build and document a complete pentesting lab
- Practice enumeration, exploiation, privilege escalation, and lateral movement.
- Develop professional reporting skills
- Share structured writetups for future reference and as a portfolio

## Lab Overview
The lab uses **VirtualBox** with bot **NAT** and **Host-Only networks**.
Main subnet: `192.168.56.0/24`

### Current Topology
- dc01.corp.local (Windows Server 2022 Core, Domain Controller - 192.168.56.102)
- win10-ws01 (Windows 10 Workstaion, domain joined - 192.168.56.101)
- kali-attacker (Kali Linux, attacker machine - 192.168.56.10)

### Planned Expansions
- **Linux victims** (Mettasploitable2, Kioptrix)
- **Web applications** (DVWA, Juice Shop)
- **Attack chains** (AS-REP roastting, Kerberoasting, BloodHound, privilege escalattion)

## Disclaimer
This project is for **educational purposes only**.
All vulnerable machines are contained in an **isolated lab environmend** and must never be exposed to the public internet. Use responsibly.
