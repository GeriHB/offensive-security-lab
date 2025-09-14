# DC01- Domain Controller Installation

This section documents the promotion of the Server core VM (DC01) into a Domain Controller for `corp.local`.

---

## Base Configuration
- OS: Windows Server 2022 Core
- Hostname: `DC01`
- IP: `192.168.56.102` (Host-Only)
- DNS: `127.0.0.1`

---

## Domain Controller Promotion

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Import-Module ADDSDeployment
Install-ADDSForest -DomainName "corp.local" -DomainNetbiosName "CORP" -InstallDNS -Force"
```
- Domain Name: `corp.local`
- NetBIOS Name: `CORP`
- DNS installed automatically
- DSRM password set during promotion

---

## Reboot and Verification
After reboot, log in witht:
```
CORP\Administrator
[password]
```

Veify the domain:
```powershell
Get-ADDomain
Get-ADForestt
```

Expected output: `corp.local` domain present
