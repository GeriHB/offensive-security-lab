# 01 - Environment Setup

This file documens the VirtualBox environment and networking for the offensive security lab.

---
## VirtualBox Networking

Two networks are used in the lab:
- **NAT** - Internet access (Kali only)
- **Host-only (vboxnet0)** - Internal lab subnet (`192.168.56.0/24`)

### Hos-only adapter (`vboxnet0`)
- Subnet: `192.168.56.0/24`
- Host machine: `192.168.56.1`

---

## Virtual Machines

|VM|Role|Adapter(s)|IP Address|Notes|
|--|----|----------|----------|-----|
|Kali Attacker|Pentest tools|NAT + Host Only|192.168.56.10|NAT for internet, Host-only for lab|
|DC01|Domain Controller|Host-only|192.168.56.102|Runs AD DS, DNS, corp.local|
|Win10-WS01|Workstation client|Host-only|192.168.56.101|Joined to corp.local domain|

---

## Verification

### From DC01 (Server Core)
```powershell
ipconfig
```

Expectetd output: IP `192.168.56.102`.

### From Win10-WS01
```powershell
ping 192.168.56.102
nslookup dc01.corp.local
```

Should resolve to the DC's IP.

### From Kali
```sh
ping 192.168.56.101
ping 192.168.56.102
```

