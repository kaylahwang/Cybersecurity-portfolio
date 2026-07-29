# Week 1 Commands Reference

## User and Network

```bash
ifconfig
```

Display network interface configuration.

```bash
su
```

Switch to the root user.

---

## System Startup and Recovery

```bash
reboot
```

Restart the system.

```bash
shutdown -h now
```

Shut down the system immediately.

---

## GRUB2 Single-User Mode

Edit kernel boot parameters in GRUB2:

```text
rw init=/sysroot/bin/sh
```

Used to boot into a single-user maintenance shell.

---

## systemd Targets

```bash
systemctl get-default
```

Display the default startup target.

```bash
systemctl isolate multi-user.target
```

Switch to command-line mode.

```bash
systemctl isolate graphical.target
```

Return to graphical mode.

---

## Service Management

```bash
systemctl list-unit-files
```

List available services and targets.

```bash
systemctl is-enabled sshd
```

Check whether a service starts automatically.

```bash
systemctl is-active sshd
```

Check whether a service is currently running.

```bash
systemctl start sshd
```

Start a service.

```bash
systemctl stop sshd
```

Stop a service.

```bash
systemctl enable sshd
```

Enable a service at boot.

```bash
systemctl disable sshd
```

Disable a service at boot.

---

## Log Analysis

```bash
dmesg
```

View kernel boot messages.

```bash
journalctl
```

View system logs.

```bash
journalctl --since "10 minutes ago"
```

View recent log entries.

```bash
journalctl -u sshd.service
```

View logs for a specific service.

```bash
journalctl -p err
```

View error messages only.

---

## Important Log Files

```text
/var/log/messages
```

General system log messages.

```text
/var/log/secure
```

Authentication and security logs.
