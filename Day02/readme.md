## 📅 Day 02: Cybersecurity Threats, Hacking OSes & Virtual Environments

#### ⚠️ Types of Cybersecurity Threats

1. **Phishing**
   - A social engineering attack that deceives users into clicking malicious links or entering sensitive information (like passwords or credit card numbers) on fake websites.
   - Phishing emails often look like they're from trusted sources (banks, companies, coworkers).
   - 📌 *Example:* An employee receives an email appearing to be from their boss requesting urgent access to financial documents.

2. **Ransomware**
   - A form of malware that uses **cryptography** to encrypt the victim's files and demands a ransom payment in exchange for the decryption key.
   - It can cripple hospitals, banks, or government agencies by locking critical data.
   - 📌 *Example:* A university's data is encrypted after a professor downloads a malicious attachment, and the attacker demands Bitcoin to unlock it.

3. **Malware**
   - A general term for any software intentionally designed to cause damage. This includes viruses, worms, spyware, Trojans, and more.
   - Malware can delete data, steal credentials, spy on activity, or hijack system resources (e.g., for crypto mining).
   - 📌 *Example:* A free browser extension installs adware that redirects all searches and shows unwanted ads.

4. **Social Engineering**
   - Psychological manipulation that tricks users into making security mistakes or giving up sensitive information.
   - Instead of attacking computers, attackers exploit human behavior and trust.
   - 📌 *Example:* Someone calls an employee pretending to be from IT support and asks for their login credentials.

5. **Man-in-the-Middle (MITM) Attack**
   - An attacker secretly intercepts and possibly alters communications between two systems.
   - Common in unsecured Wi-Fi environments where traffic isn’t encrypted.
   - 🔒 *Defense:* Using **SSL/TLS encryption** (HTTPS) helps prevent MITM by encrypting data end-to-end.
   - 📌 *Example:* A hacker captures login credentials transmitted over an unsecured network at a coffee shop.

6. **Zero-Day Attack**
   - Exploits previously unknown software vulnerabilities before the developer has a chance to fix them.
   - Zero-day exploits are especially dangerous because they are unexpected and typically not detectable by antivirus tools.
   - 📌 *Example:* An unpatched browser vulnerability is used to gain remote control of systems across thousands of computers.

---

#### 🌐 What is a Domain?
A **domain** is a readable name that maps to a server’s IP address, used to identify websites (e.g., `google.com` instead of `142.250.72.14`).

---

#### 🧠 USB Rubber Ducky (Keystroke Injection)

- A **USB Rubber Ducky** looks like a normal USB flash drive but functions as a keyboard when plugged into a system.
- It runs automated scripts by simulating rapid keyboard inputs — often used to inject commands and payloads.
  
📌 *Example:*  
An attacker plugs it into a victim's machine, and it opens a terminal, downloads a script from the internet, and executes it — all in under 5 seconds.

**Skills/Tools Required:**
- Ducky Script
- Command-line knowledge (PowerShell, Bash, CMD)
- Physical access to the machine

---

#### 🐧 Learning About Kali Linux

- **Kali Linux** is a Debian-based Linux distribution built specifically for penetration testing and digital forensics.
- It comes preloaded with hundreds of security tools such as Nmap, Metasploit, Burp Suite, Wireshark, and more.

#### 💾 Downloading & Installing Kali Linux

Steps:
1. Go to [https://www.kali.org](https://www.kali.org)
2. Download the ISO image for Kali Linux (Installer or Live)
3. Use a **virtual machine** or bootable USB to install the OS
4. Follow the guided installer to set username, password, disk size, and network settings

---

#### 🧰 Other Hacking Operating Systems Explored

We also explored different OS options used for ethical hacking, penetration testing, and cybersecurity analysis:

| OS Name        | Website                | Description |
|----------------|-------------------------|-------------|
| **Kali Linux** | [kali.org](https://www.kali.org) | Widely used OS for penetration testing |
| **Parrot OS**  | [parrotsec.org](https://www.parrotsec.org) | Privacy and security-focused distro |
| **BlackArch**  | [blackarch.org](https://www.blackarch.org) | Arch-based distro for advanced security users |
| **BackBox**    | [blackbox.org](https://www.backbox.org) | Ubuntu-based penetration testing OS |
| **Garuda Linux** | [garudalinux.org](https://www.garudalinux.org) | Performance-oriented Arch Linux with security tools |
| **Ubuntu**     | [ubuntu.com](https://www.ubuntu.com) | General-purpose Linux, can be customized for security work |

✅ **We will be using Kali Linux throughout this course.**

---

#### 🖥️ Virtual Machine Setup for Cybersecurity Labs

To safely run hacking OSes, we use **virtual machines** — isolated environments that simulate a full operating system inside your current OS.

**Tools we will use:**
- **VMware Workstation 17 Pro**
- **VirtualBox**

These platforms allow us to:
- Run Kali Linux without affecting the host OS
- Take snapshots and revert changes
- Practice attacks safely and legally in a sandbox environment


