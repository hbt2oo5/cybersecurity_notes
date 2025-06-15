# Day 6 – Nmap, Docker in Kali Linux, Geolocation with MaxMind, and WAF Detection

---

### 🌐 What is Nmap?

**Nmap** (Network Mapper) is a free and open-source tool used for network discovery and security auditing. It can rapidly scan large networks and determine hosts that are up, what services they are offering, operating systems, types of firewalls, and more.

Nmap is widely used by ethical hackers and security professionals for:
- Identifying open ports on a host
- Detecting service versions
- Mapping the network
- Running NSE (Nmap Scripting Engine) scripts

#### 📁 Step 1: Create a Working Directory

```bash
mkdir nmap
cd nmap
```


---

### 🔍 Nmap Command Breakdown (L1-L2-L3)

1. **TARGET SPECIFICATION**:
   ```
   -iL <inputfilename>   # Input from list of hosts/networks
   ```

2. **HOST DISCOVERY**:
   ```
   -sL     # List Scan - simply list targets to scan
   -sn     # Ping Scan - disable port scan
   -Pn     # Treat all hosts as online -- skip host discovery
   ```

3. **SCAN TECHNIQUES**:
   ```
   -sS/-sT/-sA/-sW/-sM    # TCP SYN/Connect()/ACK/Window/Maimon scans
   -sU                   # UDP Scan
   ```

4. **PORT SPECIFICATION AND SCAN ORDER**:
   ```
   -p <port ranges>             # Only scan specified ports
   -p-                          # Scan all ports (1–65535)
   --exclude-ports <ranges>    # Exclude specified ports from scanning
   -F                           # Fast mode - Scan fewer ports than default
   -r                           # Scan ports sequentially
   ```

5. **SERVICE/VERSION DETECTION**:
   ```
   -sV                         # Probe open ports to determine service/version info
   --version-intensity <0–9>   # Intensity level (0 = light, 9 = try all probes)
   --version-light             # Limit to most likely probes (intensity 2)
   --version-all               # Try every single probe (intensity 9)
   --version-trace             # Show detailed version scan activity
   ```

6. **SCRIPT SCAN**:
   ```
   -sC                           # Equivalent to --script=default
   --script=<Lua scripts>        # Comma-separated list of directories, script-files or script-categories
   ```

7. **OS DETECTION**:
   ```
   -O    # Enable OS detection
   ```

8. **TIMING AND PERFORMANCE**:
   ```
   -T<0-5>   # Set timing template (higher is faster)
   ```

9. **OUTPUT OPTIONS**:
   ```
   -oN/-oX/-oS/-oG <file>   # Output scan in normal, XML, s| grepable or JSON
   -v                      # Increase verbosity (-vv for more, -vvv for highest)
   ```

10. **MISC (Miscellaneous Scans)**:
   ```
   -A    # Enable OS detection, version detection, script scanning, and traceroute
   ```

---

#### 🔎 Nmap Command Levels

| Level | Command Example | Description |
|-------|------------------|-------------|
| **L1** | `nmap <target_ip>` | Basic ping and port scan. |
| **L2** | `nmap -sS <target_ip>` | TCP SYN scan (stealth scan). |
| **L3** | `nmap -A <target_ip>` | Aggressive scan with OS detection, version detection, script scanning, and traceroute. |

---

### 🐳 Introduction to Docker

**Docker** is a platform that enables developers and security professionals to build, deploy, and manage applications inside containers. Containers are lightweight, isolated environments that run applications with all their dependencies.

#### 📦 Installing Docker on Kali Linux

```bash
sudo apt install -y docker.io
```

---

### 🐧 Using Ubuntu Docker Image in Kali

1. **Pull Ubuntu Image**  
   ```bash
   sudo docker pull ubuntu
   ```

2. **Check Available Docker Images**  
   ```bash
   sudo docker images
   ```

3. **Run Ubuntu Container**  
   ```bash
   sudo docker run -it ubuntu:latest /bin/bash
   ```

4. **Check Container Info**  
   ```bash
   sudo docker ps -a
   ```

5. **Exit the Container**  
   ```bash
   exit
   ```

6. **Remove a Container**  
   ```bash
   sudo docker rm <container_id>
   ```

---

### 🧪 Using Kali Linux Docker Image

Follow the same steps as Ubuntu, just replace the image name:

1. **Pull Kali Image**  
   ```bash
   sudo docker pull kalilinux/kali-rolling
   ```

2. **Run Kali Container**  
   ```bash
   sudo docker run -it kalilinux/kali-rolling /bin/bash
   ```

3. **Check, Exit, and Remove**  
   Use `docker ps -a`, `exit`, and `docker rm <container_id>` as before.

---

### ⏱️ Uptime Kuma

**Uptime Kuma** is a self-hosted monitoring tool used to track website and service uptime. It runs in a Docker container and provides a user-friendly web interface.

- Official Site: [https://uptime.kuma.pet](https://uptime.kuma.pet)
- You can deploy it via Docker and access the UI from your browser.

---

### 🌐 OpenWebUI

**OpenWebUI** provides a graphical user interface to interact with web-based tools and scripts.

- Official Site: [https://openwebui.com](https://openwebui.com)
- Can be run in Docker inside Kali for easier access and automation.

---

### 🧾 Script Scanning

Nmap allows **script-based scanning** using the NSE (Nmap Scripting Engine). These scans can be IP-based or service-specific.

```bash
nmap -sC <target_ip>
```

This command runs default scripts against the target to detect vulnerabilities, services, and configurations.

---

### 🧭 Roadmap.sh

[https://roadmap.sh](https://roadmap.sh) is a helpful resource that provides curated paths for learning web development, cybersecurity, DevOps, etc.

- Use it to visualize what skills to focus on in your cybersecurity journey.

---

### 🌍 Geolocation with MaxMind

**MaxMind** provides IP geolocation and ASN (Autonomous System Number) databases that allow identifying an IP's geographical location and ISP information.

#### 🔎 What is MaxMind?

MaxMind is a data service provider offering:
- **ASN Database**: Identifies the ISP and autonomous system of an IP address.
- **City Database**: Provides location details like city, state, and postal code.
- **Country Database**: Provides country-level geolocation info.

#### 🧾 Steps to Use MaxMind

1. **Create a MaxMind Account**  
   - Go to [https://www.maxmind.com](https://www.maxmind.com) and register.

2. **Download the Databases**  
   - ASN: `GeoLite2-ASN.mmdb`  
   - City: `GeoLite2-City.mmdb`  
   - Country: `GeoLite2-Country.mmdb`

These `.mmdb` files are used with tools or scripts to identify and report geolocation details of IP addresses.

---

### 🛡️ WAFW00F (WAF Detection Tool)

**WAFW00F** is a tool used to detect if a website is protected by a Web Application Firewall (WAF).

#### 🔍 Example Command

```bash
wafw00f https://example.com
```

This command analyzes the URL and reports the type of WAF (if any) that is in place.
