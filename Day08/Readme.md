
# 📅 Day 8 – Shodan, MaxMind Database, Vulnerability Scanning

---

## 🌐 Shodan – The Search Engine for Hackers

**What is Shodan?**  
Shodan is a specialized search engine that indexes internet-connected devices and their associated metadata. It allows cybersecurity professionals and hackers to identify open ports, services, and potential vulnerabilities across the internet.

### 🔐 Steps:
1. Create a free account at [https://www.shodan.io](https://www.shodan.io)
2. Log into your account to access full search capabilities.

### 🔍 Example Filter Query:
```sh
vuln:s17-010 country:"IN" city:"Pune"
```
This query finds systems in Pune, India, vulnerable to the `s17-010` vulnerability.

- Shodan reveals public IP addresses and performs global port scanning to gather:
  - Open ports
  - Service versions
  - Mapped vulnerabilities

---

## 🧪 Scanning Shodan IPs with Nmap in Kali

After identifying a public IP using Shodan, perform a full port scan using:

```bash
sudo nmap -Pn -T4 -p- -vv -oN sh-ip-port.txt <ip-address>
```

- `-Pn`: Treat all hosts as online
- `-T4`: Aggressive timing for faster scan
- `-p-`: Scan all 65535 ports
- `-vv`: Verbose mode
- `-oN`: Save output in normal format

---

## 🐝 What is Honey Port?

A **Honey Port** is a decoy network port set up to detect unauthorized access or exploitation attempts.  
- It functions like a **honeypot**, designed to attract attackers for observation, detection, and analysis.  
- It acts as a sandbox or controlled environment to capture and research malicious behavior.

---

## 🎥 What is Hikvision?

**Hikvision** is a major manufacturer of IP-based surveillance cameras and security systems.  
- Commonly used in both commercial and residential setups.
- Often targeted in security assessments due to default credentials and unpatched firmware vulnerabilities.

---

## 🌍 MaxMind Geolocation Databases

MaxMind offers geolocation data that can be used with tools like Nmap for IP enrichment.

### 🧾 Steps:
1. Create an account at [https://www.maxmind.com](https://www.maxmind.com)
2. Download the following **GeoLite2** databases (in `.tar.gz` format):
   - **GeoLite2-ASN**
   - **GeoLite2-City**
   - **GeoLite2-Country**

---

## 🗂️ Handling the GeoLite Databases in Kali Linux

### Step-by-Step:

1. Open the Nmap directory:
```bash
cd nmap
```

2. Go to Downloads:
```bash
cd Downloads
```

3. Paste/download the `.tar.gz` files into this directory.

4. Verify the file types:
```bash
file Geolite2-*
```

5. List with permissions and sizes:
```bash
ls -lh
```

6. Unzip the files:
```bash
gunzip Geolite2-ASN.tar.gz
gunzip Geolite2-City.tar.gz
gunzip Geolite2-Country.tar.gz
```

7. Extract the contents:
```bash
tar -xvf Geolite2-ASN.tar
tar -xvf Geolite2-City.tar
tar -xvf Geolite2-Country.tar
```

8. Use tree to view the directory structure:
```bash
tree
```

Expected output:
```
.
├── GeoLite2-City_YYYYMMDD
│   ├── LICENSE.txt
│   ├── GeoLite2-City.mmdb
│   └── README.txt
├── GeoLite2-ASN_YYYYMMDD
│   ├── LICENSE.txt
│   ├── GeoLite2-ASN.mmdb
│   └── README.txt
├── GeoLite2-Country_YYYYMMDD
│   ├── LICENSE.txt
│   ├── GeoLite2-Country.mmdb
│   └── README.txt
```


9. Move to `/opt` and create a new directory:
```bash
cd /opt
sudo mkdir mmdb
```

10. Copy `.mmdb` files to `/opt/mmdb`:
```bash
sudo cp ~/Downloads/*/*.mmdb /opt/mmdb
```

11. Confirm copy:
```bash
ls -lh /opt/mmdb
```

---

## 🛡️ Introduction to Vulnerability Scanning

**Vulnerability scanning** is a process used to identify, analyze, and report known security weaknesses in systems, networks, and applications.

- Often automated using tools like Nessus, OpenVAS, or Nmap scripts.
- A crucial step in proactive defense and part of penetration testing cycles.

---

📁 End of Day 8 Notes
