# Week 1 - Introduction and System Startup

## System Administrator Responsibilities

- Server installation and configuration
- User management
- Backup and recovery
- Security monitoring
- Troubleshooting
- System maintenance

---

## Linux Boot Process

Hardware
→ BIOS/UEFI
→ GRUB2 Boot Loader
→ Linux Kernel
→ systemd
→ System Services

---

## BIOS vs UEFI

### BIOS
- Traditional firmware
- Uses MBR

### UEFI
- Modern firmware
- Uses EFI System Partition (ESP)
- Supports multiple boot loaders

---

## GRUB2

Main functions:

- Load Linux kernel
- Support multiple operating systems
- Provide boot menu

---

## systemd

- First process started by Linux
- PID = 1
- Manages startup services

Common targets:

- graphical.target
- multi-user.target
- rescue.target
- emergency.target

---

## System Logs

Kernel logs:

```bash
dmesg
