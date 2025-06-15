
## Day 5 – Creating Custom Commands in Kali Linux & Introduction to Ethical Hacking

---

### 🛠️ Custom Command Creation in Kali Linux (`myip`)

We created a custom command named `myip` that displays the IP address of our PC and copies it to the clipboard.

#### Step-by-Step Guide

| Step | Command | Purpose |
|------|---------|---------|
| 1 | `ifconfig` | Displays network interfaces and IP info. |
| 2 | `ifconfig eth0` | Shows details for the `eth0` interface. |
| 3 | `ifconfig eth0 \| grep inet \| grep -v ":" \| awk '{print $2}'` | Filters out only the IP address. |
| 4 | `nano myip.sh` | Creates a shell script file. |
| 5 | (Add the command inside the file) | Example: <br>```bash<br>#!/bin/bash<br>ifconfig eth0 \| grep inet \| grep -v ":" \| awk '{print $2}'<br>``` |
| 6 | Save and exit `nano` | `CTRL + O`, `ENTER`, `CTRL + X` |
| 7 | `ls -lh` | Check file permissions. |
| 8 | `chmod +x myip.sh` | Add execute permission. |
| 9 | `mv myip.sh myip` | Rename the script to match the custom command name. |
| 10 | `sudo cp -r myip /bin` | Copy the command to `/bin` so it can run globally. |
| 11 | `myip` | Run the custom command to print your IP. |

#### 🧠 Key Concepts

- **`awk`**: A command-line utility used for pattern scanning and text processing. It reads input line-by-line, splits each line into fields, and performs actions based on patterns. In our use case, it extracts the IP address field from the output.
- **File Permissions (`ls -lh`)**:
  - **r** = read: permission to view file contents
  - **w** = write: permission to modify or edit the file
  - **x** = execute: permission to run the file as a program
  - **First rwx** → for **User**
  - **Second rwx** → for **Group**
  - **Third rwx** → for **Others**
  -  The permission string also includes a character at the beginning:
  - **d** = directory  
  - **l** = symbolic link  
  - **-** = regular file
  -  **`.sh` Files**: Files ending in `.sh` are shell script files, commonly used for Bash scripting.
- **`chmod +x`**: Grants execute permission to a file.

---

### 📋 Enhancing `myip` Command to Copy IP to Clipboard

We extended the functionality of `myip` to copy the IP address directly to the clipboard.

#### Additional Steps

| Step | Command | Purpose |
|------|---------|---------|
| 1 | `apt search clipboard` | Searches for clipboard-related packages. |
| 2 | (Choose) `xclip` | CLI tool to interface with the system clipboard. |
| 3 | `sudo apt install -y xclip` | Installs xclip. |
| 4 | Edit your script in `/bin` directly:<br>`sudo nano /bin/myip` | Modifies the existing `myip` command. |
| 5 | Update script:<br>```bash<br>#!/bin/bash<br>ip=$(ifconfig eth0 \| grep inet \| grep -v ":" \| awk '{print $2}')<br>echo $ip<br>echo $ip \| xclip -selection clipboard<br>``` | Now it prints and copies the IP address. |

---

## 🧑‍💻 Introduction to Ethical Hacking

### 🔍 What is Hacking?

**Hacking** refers to the act of exploiting vulnerabilities in a system or network to gain unauthorized access to data or control. While some hacking is used for malicious purposes (stealing data, causing damage), the term itself is neutral and simply means manipulating systems in unintended ways.

### 🛡️ What is Ethical Hacking?

**Ethical Hacking** is the practice of legally breaking into computers and devices to test an organization's defenses. It involves authorized attempts to bypass system security to identify potential vulnerabilities. Ethical hackers use the same tools and techniques as malicious hackers, but with the goal of strengthening security rather than compromising it.

### 👨‍💼 Who is an Ethical Hacker?

An **Ethical Hacker** is a skilled cybersecurity professional hired by organizations to test systems and identify security flaws. They are often certified (e.g., CEH – Certified Ethical Hacker) and operate within legal and contractual boundaries. Their work helps prevent data breaches, cyberattacks, and ensures systems are secure from malicious threats.

---

### 🧑‍🎓 Types of Hackers

| Hacker Type | Description |
|-------------|-------------|
| **White Hat** | Ethical hackers who work legally to help organizations secure their systems. |
| **Black Hat** | Malicious hackers who exploit systems for personal or financial gain. |
| **Grey Hat** | Hackers who may violate laws but don't have malicious intentions; their actions may still be illegal. |
| **Red Hat** | Hackers who aggressively target black hat hackers using offensive methods. |
| **Hacktivist** | Individuals who hack to promote political or social causes. |
| **Script Kiddie** | Inexperienced hackers who use pre-written scripts or tools without deep understanding. |

---

### 🔐 CIA Triad (Core Principles of Information Security)

| Component | Description |
|-----------|-------------|
| **Confidentiality** | Ensures that sensitive data is only accessible to authorized users. It protects personal, financial, or proprietary data from exposure. Techniques include encryption, access controls, and authentication. |
| **Integrity** | Ensures that data remains accurate, consistent, and trustworthy throughout its lifecycle. It prevents unauthorized alterations to data. Hashing and digital signatures are common techniques used to maintain integrity. |
| **Availability** | Ensures that systems, networks, and data are available for authorized users when needed. It involves maintaining hardware, regularly updating software, and implementing redundancy to minimize downtime. |

The **CIA Triad** is a fundamental model in cybersecurity that guides the development of security policies, systems, and practices. It consists of three key components: **Confidentiality**, **Integrity**, and **Availability**. Each of these principles plays a vital role in protecting digital information and ensuring reliable system operations.

#### ✅ Confidentiality
Confidentiality is the principle of ensuring that sensitive data is accessible only to those who are authorized to view it. It protects information from being disclosed to unauthorized individuals, systems, or processes. Common methods to maintain confidentiality include data encryption, strong password policies, multi-factor authentication, and role-based access controls. Failing to ensure confidentiality can result in serious consequences, such as identity theft, corporate espionage, or national security threats.

#### ✅ Integrity
Integrity involves maintaining the accuracy, consistency, and trustworthiness of data throughout its lifecycle. This means that data should not be modified, deleted, or tampered with by unauthorized individuals. Ensuring integrity is critical because corrupted or manipulated data can lead to flawed decisions, financial loss, or safety hazards. Techniques such as cryptographic hashing, checksums, digital signatures, and version control systems help protect data integrity by detecting and preventing unauthorized alterations.

#### ✅ Availability
Availability ensures that authorized users have timely and reliable access to information and resources whenever needed. It involves maintaining system uptime, preventing service disruptions, and recovering quickly from failures. Availability is crucial for organizations that rely on real-time data and continuous services, such as healthcare, finance, or emergency systems. Strategies to improve availability include redundancy (backup systems), regular maintenance, load balancing, denial-of-service (DoS) protection, and disaster recovery planning.

Together, these three principles form the foundation of modern cybersecurity practices. A weakness in any one of them can expose an organization to threats, making the CIA Triad essential for designing and evaluating secure systems.


