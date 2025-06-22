
# 📅 Day 9 – Introduction to Wireshark, Analyzing packets in Wireshark, Configuring MaxMind Geolocation Database in Wireshark, Tools for IP Geolocation


## 🧪 What is Wireshark?

**Wireshark** is a powerful network protocol analyzer used to capture and inspect network traffic in real time. It is commonly used by security professionals to monitor and troubleshoot networks, and to identify malicious traffic.

- In **Kali Linux**, Wireshark is already pre-installed.
- In **Windows**, it needs to be downloaded and installed manually from [wireshark.org](https://www.wireshark.org/)
- For Windows analysis, Wireshark must be **run as Administrator** to access full network capabilities.
- It is best practice to **analyze packets in Windows** and perform **testing in a sandbox or Kali Linux environment**.

---

## 📶 Using Wireshark on Windows

1. Open Wireshark as **Administrator**.
2. You’ll see a list of **network adapters** (e.g., Ethernet, Wi-Fi, etc.).
3. Double-click on the **Wi-Fi adapter** to start capturing packets.
4. You'll see columns such as:
   - Time
   - Source
   - Destination
   - Protocol
   - Length
   - Info

---

## 🌍 Configuring MaxMind Geolocation Database in Wireshark

To enhance packet analysis with geolocation info:

### 🔧 Steps:
1. While packets are being captured, go to:
   - `Edit` → `Preferences` → `Name Resolution`
2. Under **MaxMind database directories**, click **Edit**.
3. Add the directory path containing your `.mmdb` files:
   - `GeoLite2-ASN.mmdb`
   - `GeoLite2-City.mmdb`
   - `GeoLite2-Country.mmdb`
4. Click **Apply** and refresh the interface.
5. Click any random packet → Expand `Internet Protocol Version 4`.
6. You'll see:
   - Source GeoIP (City, Country)
   - Destination GeoIP (City, Country)
7. Right-click on parameters to **add them as columns**.

---

## 📥 Downloading & Analyzing Packet Files

You can download `.pcap` files and analyze them in Wireshark.

- Go to: `Statistics` → `Endpoints`
- You can view:
  - IP Address
  - GeoIP City & Country (if MaxMind is configured)
- On the right panel, click on **Map**
  - Click **Browser** to open a world map view
  - Shows **heat signatures** based on packet density and activity

---

## 🌐 Tools for IP Geolocation

### 🔹 What is db-ip.com?

[db-ip.com](https://db-ip.com) provides geolocation data based on IP addresses.  
It offers a public API and downloadable databases for:
- Country
- City
- ISP
- ASN information

It is often considered more **accurate and up-to-date** than free alternatives.

---

### 🔹 What is ip-api?

[ip-api.com](https://ip-api.com) is another API-based IP geolocation service.

- Provides JSON-based data for:
  - City
  - Region
  - Country
  - ZIP
  - Latitude/Longitude
  - ISP and Organization
- Easy to integrate into security scripts or reconnaissance tools

---

📁 End of Day 9 Notes
