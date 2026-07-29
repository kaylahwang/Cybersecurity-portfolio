# Week 1 Learning Journal

## Practical Activities

- Explored the CentOS and Windows Server environments.
- Examined network settings and server configurations.
- Observed the Linux boot process from GRUB2 to system startup.
- Booted Linux into single-user mode for maintenance and recovery.
- Managed system services using systemctl.
- Explored systemd targets and startup modes.
- Examined system logs using dmesg and journalctl.
- Explored Windows Server Manager and administrative tools.

---

## Key Learnings

### Linux Startup Process

The Linux startup process follows a structured sequence:

```text
BIOS/UEFI → GRUB2 → Linux Kernel → systemd → Services
```

Understanding this process is important when diagnosing boot failures and startup issues.

### systemd

systemd is the primary service manager in modern Linux distributions. It is responsible for starting and managing services, controlling startup targets, and maintaining system operation.

### System Logging

System logs provide valuable information for troubleshooting and monitoring.

Common tools:

```bash
dmesg
journalctl
```

Important log files:

```text
/var/log/messages
/var/log/secure
```

### Single-User Mode

Single-user mode provides a minimal environment for system maintenance and recovery tasks. It can also be used for troubleshooting startup problems and password recovery.

---

## Reflection

This week provided a solid introduction to Linux and Windows server administration. The practical activities helped me understand how operating systems start, how services are managed through systemd, and how system logs can be used to investigate issues. Learning the startup process has improved my understanding of troubleshooting and system recovery procedures.
