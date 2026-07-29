# Week 1 – Introduction and System Startup

## Overview

This week introduced the role of a system administrator and the Linux startup process, including firmware, boot loaders, the kernel, and systemd.

---

## System Administrator Responsibilities

Typical system administration tasks include:

- Server installation and configuration
- User account management
- Backup and recovery
- Security monitoring
- Performance monitoring
- Troubleshooting and maintenance
- Applying updates and security patches

---

## Linux Boot Process

The Linux startup sequence follows these stages:

```text
Hardware
→ BIOS/UEFI
→ Boot Loader (GRUB2)
→ Kernel
→ systemd/init
→ Services
```

### BIOS / UEFI

- Performs hardware initialization
- Runs POST (Power-On Self-Test)
- Locates a bootable device

### Boot Loader

- Loads the operating system kernel
- GRUB2 is the most common Linux boot loader

### Kernel

- Loads into memory
- Mounts the root filesystem
- Starts systemd

### systemd

- First userspace process started by Linux
- Always runs with PID 1
- Starts and manages system services

---

## BIOS vs UEFI

### BIOS

- Traditional firmware
- Uses MBR partitioning

### UEFI

- Modern firmware standard
- Uses EFI System Partition (ESP)
- Supports multiple boot loaders

---

## GRUB2

GRUB2 is the default Linux boot loader.

Key functions:

- Load Linux kernels
- Provide boot menus
- Support multiple operating systems

Common configuration file:

```text
/boot/grub2/grub.cfg
```

---

## systemd Service Management

Useful commands:

```bash
systemctl status
systemctl start
systemctl stop
systemctl enable
systemctl disable
```

Common targets:

- graphical.target
- multi-user.target
- rescue.target
- emergency.target
- reboot.target

---

## Log Management

Important commands:

```bash
dmesg
journalctl
journalctl -k
```

Important log location:

```text
/var/log/messages
```

Logs are useful when diagnosing startup and system issues.

---

## Key Takeaways

- Linux startup follows a structured boot process.
- BIOS/UEFI initializes hardware before booting.
- GRUB2 loads the Linux kernel.
- systemd manages services and startup targets.
- Log files are essential for troubleshooting.
