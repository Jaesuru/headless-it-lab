# Headless IT Lab Setup
This project documents how I built a fully headless home lab for practicing IT principles, designed in a way to help simulate a small help desk or sysadmin environment. 

It includes:
- A Windows 10/11 desktop running headlessly with a remote desktop software like AnyDesk (for ease of access, and because I didn't have much space in my room)
- Automated startup and network configurations
- Virtual machines running in VirtualBox on the remote desktop

---

## Reason For Why I Built This
I wanted to create a realistic environment for practicing IT troubleshooting, network setup, and remote management and configuration while studying for the CompTIA A+ certification. 
Because I didn't have access to enterprise-level equipment, creating a homelab with this setup was quick, easy, and great for learning things that would actually happen in a real-world IT environment. 

---

### What's Inside This Repository
| Section | Description |
|----------|-------------|
| [01 - AnyDesk Setup](docs/01-setup-anydesk.md) | Installing and configuring AnyDesk as a system service |
| [02 - VirtualBox Server Domain Controller Setup](docs/02-server-dc-vm.md) | Installing and configuring a server for handling services | 

--- 

## Key Skills Learned
- Remote desktop configuration and administration (AnyDesk, RDP)
- Windows service configuration
- Virtualization (VirtualBox)
- Networking fundamentals
- Hardware and software simulations
- Active directory management

---

## Screenshots / References

---

## Tools Used
- Windows 10 Home Edition (Headless system & choice of OS for VMs)
- AnyDesk (RDP)
- PowerShell & Bash (w/ macOS)
- HDMI Dummy Plug (most computers won't display anything when it isn't connected to a output source)

---

## Author
**Jason Jiang**
<br>
jiang.jason03@gmail.com
<br>
[LinkedIn Profile](https://wwww.linkedin.com/in/jasonjiangexperience)
