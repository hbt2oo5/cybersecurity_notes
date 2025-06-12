## 📅 Day 03: GitHub, Cloud Tools, and Linux Environment Setup

---

### 🐙 What is GitHub?

**GitHub** is a **cloud-based platform** and **version control system** that allows users to:

- 📦 Store and manage source code  
- 📜 Track changes in code using Git  
- 🤝 Collaborate with others on shared projects  
- 🕒 Roll back to previous versions when needed  

It helps developers organize, contribute, and maintain projects across teams or even entire communities.

---

### 📁 What is a Repository in GitHub?

A **repository** (or "repo") is like a folder that stores your project’s files, including:

- Code  
- Documentation  
- Images  
- Scripts  
- Configuration files  

Repositories can be **public** (visible to everyone) or **private** (visible only to invited collaborators).

---

### 🧱 Creating a Repository in GitHub

#### 🔧 Steps to Create a Repository:

1. Go to [https://github.com](https://github.com)  
2. Click on the ➕ icon and choose **"New repository"**  
3. Enter a **repository name**  
4. Add a **description** (optional but recommended)  
5. Choose between **Public** or **Private**  
6. ✅ Check **"Add a README file"** to initialize the repository with documentation  
7. Click **"Create repository"**

---

### 📘 What is a README.md File?

A `README.md` file is a **Markdown** file (`.md`) used to provide:

- 📄 Project description  
- 🛠️ Setup instructions  
- 📚 Usage guidelines  
- 🧑‍💻 Contributor info  

GitHub automatically displays `README.md` on the homepage of the repository. Markdown (`.md`) supports formatted text like **bold**, _italics_, lists, links, and more.

---

### 🍴 Forking a Repository on GitHub

**Forking** means creating your own copy of someone else’s repository under your GitHub account.

✅ Useful when:
- You want to contribute to an open-source project  
- You need to experiment without affecting the original repo  

🪜 Steps:
1. Open the desired GitHub repository  
2. Click on **"Fork"** (top-right corner)  
3. The forked repo will appear in your account for modifications  

---

### 🧠 MCP Server in AI

**MCP (Multi-Context Processor)** server in AI handles multiple contexts or tasks simultaneously, enabling:

- 🤖 Scalable parallel processing of AI models  
- 🧠 Real-time learning or decision-making  
- 🔁 Context switching in conversational systems or multitask agents  

It's used in distributed AI systems where multiple intelligent tasks are run in parallel.

---

### 🎧 What is Vibe Coding?

**Vibe Coding** is a casual or creatively immersive way to code—focused on **flow, collaboration, and creativity**.

🔗 Some platforms that support vibe coding:

| Platform     | Description                          |
|--------------|--------------------------------------|
| **Lovable**  | Collaborative creative coding space  |
| **Humana.AI**| AI-assisted coding with intuitive UX |
| **Replit**   | In-browser IDE with multiplayer mode |

These environments emphasize a “vibe” — music, themes, live collaboration — turning coding into an enjoyable experience.

---

### 🐧 Running Kali Linux as an Application on Windows Using WSL

We learned how to run **Kali Linux** as a native application on Windows using **WSL (Windows Subsystem for Linux)** — a compatibility layer that allows you to run Linux binaries directly on Windows without a virtual machine.

This allows users to:
- Launch Kali Linux just like any app  
- Use Linux tools side-by-side with Windows tools  
- Access the Linux kernel within the Windows environment  

---

### 💻 Basic Kali Linux Commands & Concepts

Here are the foundational Linux commands we practiced in Kali Linux:

| Command       | Description                          |
|---------------|--------------------------------------|
| `sudo`        | Super User Do – run commands as admin |
| `cd`          | Change directory                     |
| `ls`          | List directory contents              |
| `pwd`         | Print working directory              |
| `rm`          | Remove files or directories          |
| `mkdir`       | Make a new directory                 |
| `apt update`  | Refresh package list from servers    |
| `apt upgrade` | Install available software updates   |

📂 **Root Directory**  
In Linux systems:

- The **root directory** is represented as `/` and is the top-most directory in the file system hierarchy.  
- The **root user's home directory** is specifically located at `/root`.

---

### 🖥️ What is KVM?

**KVM (Kernel-based Virtual Machine)** is a virtualization module built into the Linux kernel.

- Converts Linux into a hypervisor  
- Allows running multiple virtual machines (VMs) with separate OSes  
- Used in cloud platforms like OpenStack and Proxmox  

🔧 Requires hardware virtualization support (Intel VT-x or AMD-V)

---

### 💥 What is a Buffer Overflow?

A **buffer overflow** is a software vulnerability where a program writes more data to a memory buffer than it can hold.

- This excess data can overwrite adjacent memory  
- Leads to **crashes**, **data leaks**, or **remote code execution**  
- Commonly exploited in hacking techniques  

📌 *Example:* An attacker inputs a large string in a login field that overflows memory and allows execution of their own code.
