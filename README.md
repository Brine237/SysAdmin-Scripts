# ⚙️ Basic System Administration Scripts

A lightweight collection of Windows batch and PowerShell scripts designed to streamline routine IT maintenance and network diagnostics.

---

## 📜 Included Scripts

### 1. Daily Maintenance & Cleanup (`cleanup.bat`)
Automates the process of clearing user temporary files and flushing the DNS resolver cache in a single run.

```batch
@echo off
echo Running basic system maintenance...
ipconfig /flushdns
del /q /f /s %temp%\*
echo Maintenance complete!
pause
# Display active IPv4 network interfaces
Get-NetIPAddress -AddressFamily IPv4 | Select-Object InterfaceAlias, IPAddress

# Test DNS and gateway connectivity
Test-NetConnection -ComputerName "8.8.8.8" -Port 53
