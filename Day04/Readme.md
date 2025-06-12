# 📅 Day_04 - Administrative Commands, Networking, and Kali Linux Services

---

## ⚙️ Administrative Commands in Kali Linux

**Administrative commands** are privileged system commands that allow users (typically superusers or system administrators) to manage system configurations, users, storage, processes, and network settings. These commands are essential for maintaining the proper functioning and security of the system.

| Command | Description |
|---------|-------------|
| `whoami` | Shows current user. |
| `hostname` | Displays system hostname. |
| `sudo su` | Switch to superuser (root). |
| `sudo username` | Execute command as another user. |
| `sudo passwd` | Change password for user. |
| `df -h` | Displays disk usage (human-readable). |
| `du -sh` | Shows total disk usage of current directory. |
| `htop` | Interactive process viewer (advanced task manager). |

---

## 👤 User Management

- **Create new user:**
```bash
sudo useradd <username>
sudo passwd <username>
```
- Used to add new users and set passwords for them.

---

## 🔥 Kali Linux Firewall (UFW)

- UFW (Uncomplicated Firewall) is used to manage firewall rules.
- It controls which network services are allowed or blocked through system ports.

---

## 🌐 DNS (Domain Name System)

- DNS servers store index pages that map domain names to IP addresses.
- **Google DNS:** `8.8.8.8` (widely used public DNS server).

### Testing DNS using ping:

```bash
ping 8.8.8.8 -c3
```

- `-c3` option sends 3 ping requests.

---

## 🔧 Services Running in Kali Linux

| Service | Purpose |
|---------|---------|
| Apache | Web server for HTTP/HTTPS hosting. |
| SSH | Secure remote access to the system. |
| FTP | File Transfer Protocol server for uploading/downloading files. |

---

## 🌐 Networking Commands

### `ifconfig` — Displays network interface configuration

- Shows various network adapters:
  - `docker0` — Docker adapter.
  - `nat` — Network Address Translation adapter.
  - `eth0` — Ethernet adapter.
  - `lo` — Loopback adapter (127.0.0.1).

---

## 🌍 IP Address Overview

**IP address (Internet Protocol address)** is a unique identifier assigned to each device connected to a network. It allows devices to locate and communicate with each other over the internet or local networks.

### Types of IP Address

| IP Version | Description |
|------------|-------------|
| IPv4 | Internet Protocol version 4 uses 32-bit addresses, written in dotted decimal notation (e.g., `192.168.1.1`). |
| IPv6 | Internet Protocol version 6 uses 128-bit addresses, written in hexadecimal format (e.g., `2001:0db8:85a3::8a2e:0370:7334`). |

### Key Differences:

- **IPv4:**
  - Limited address space (~4.3 billion addresses).
  - Still widely used.
  - Example: `192.168.0.1`

- **IPv6:**
  - Extremely large address space.
  - Designed to replace IPv4 due to exhaustion.
  - Supports advanced features like auto-configuration, better routing, and built-in security.
  - Example: `2001:0db8:85a3::8a2e:0370:7334`

---

