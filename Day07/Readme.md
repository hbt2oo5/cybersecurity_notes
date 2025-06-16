
# 📅 Day 7 – Nmap Implementation, Ports, Exploit Search & Vulnerability Tools 


## ⚙️ Nmap Implementation – Step-by-Step

### 1. Navigate to Nmap Working Directory
```bash
cd nmap
```

### 2. Create Target List File
Use `nano` to create a file containing domain(s) or IP(s) to scan:
```bash
nano dns.txt
```
📄 Paste your target URLs or IP addresses (one per line) into this file and save.

---

## 🧪 Running Nmap Scans

### 1. Basic Scan Using a List
```bash
nmap -iL dns.txt -oN test1.txt -vv
```
- `-iL dns.txt`: Input file with list of targets
- `-oN test1.txt`: Save output in normal format
- `-vv`: Increase verbosity

---

### 2. Full Port Scan
```bash
nmap -Pn -p- -vv -oN test2-p--vv.txt -iL dns.txt
```
- `-Pn`: Skip host discovery (treat all hosts as online)
- `-p-`: Scan all 65535 ports
- `-vv`: Verbose output

---

### 3. Targeted Service and Version Scan
```bash
nmap -Pn -T4 -p80,443,8080 -sV -vv -oN test-p-sv-vv.txt -iL dns.txt
```
- `-T4`: Faster timing
- `-p80,443,8080`: Scan selected ports
- `-sV`: Detect service/version
- `-oN`: Output result to file
- `-iL`: Input list of targets

📂 To open the saved result:
```bash
mousepad test-p-sv-vv.txt
```

---

## 💣 Exploit Enumeration with SearchSploit

`searchsploit` is a command-line tool to search the Exploit-DB database.

🔍 Example:
```bash
searchsploit apache tomcat
```

---

## 🌐 Understanding Ports

Ports are logical communication endpoints that allow systems to differentiate multiple services running on the same IP address.

- **Total Ports**: 0 to 65535
- **TCP (Transmission Control Protocol)**: A connection-oriented protocol that ensures reliable data delivery.
- **UDP (User Datagram Protocol)**: A connectionless protocol that is faster but doesn't guarantee delivery or order.

📌 Common Ports:
- **80** – HTTP
- **443** – HTTPS
- **8080** – Apache Tomcat (Alternate HTTP)
- **22** – SSH (Secure Shell)

🧠 You can find a full list of TCP/UDP ports here:  
[Wikipedia - List of TCP and UDP port numbers](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)

---

## 🛠️ Tools and Platforms

### 🗂️ Jira
Jira is a **project management and issue tracking tool** widely used by software teams to manage agile workflows, track bugs, and organize development tasks.

### 🔐 SSH (Secure Shell)
SSH is a secure protocol used to **remotely access and manage servers** over a network. It encrypts traffic to prevent eavesdropping and attacks.
- **Default Port**: 22

---

## 🕵️ Vulnerability Finding Platforms

### 1. [Shodan.io](https://www.shodan.io)
A powerful search engine that helps identify internet-connected devices like webcams, servers, routers, and IoT devices. It can also reveal open ports, running services, and software vulnerabilities.

### 2. [ZoomEye.ai](https://www.zoomeye.ai)
Similar to Shodan, ZoomEye scans the internet to identify open ports, services, and vulnerabilities. It is commonly used in **cyber threat intelligence** to analyze exposed attack surfaces.

---


