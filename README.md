

---

# 🛡️ Basic Vulnerability Scan using OpenVAS (Full and Fast)

## 📌 Objective

Perform a basic vulnerability scan on a local machine using **OpenVAS (Greenbone Vulnerability Management)** in Kali Linux, following internship requirements.

---

## 1️⃣ Installation & Setup

### Update system packages

```bash
sudo apt update && sudo apt upgrade -y
```

### Install OpenVAS (GVM)

```bash
sudo apt install openvas -y
```

### Initial Setup

```bash
sudo gvm-setup
```

**Outcome:**

* Initializes the scanner database
* Downloads the vulnerability feed
* Creates the default **admin** user (save the username and password shown in the terminal)

### Start GVM Services

```bash
sudo gvm-start
```

**Outcome:**
Displays the web interface URL, e.g.:

```
https://127.0.0.1:9392
```

---

## 2️⃣ Access the Web Interface

* Open a browser in Kali Linux
* Navigate to:

```
https://127.0.0.1:9392
```

* Login with the **admin** credentials created during setup

---

## 3️⃣ Create Scan Target

1. Go to **Configuration → Targets → New Target**
2. **Name:** `Localhost Vulnerability Scan`
3. **Hosts:** `192.168.x.x` (replace with your local IP from `ip addr show`)
4. **Alive Test:** `Consider Alive`
5. **Port List:** `All IANA assigned TCP and UDP`
6. Save the target

---

## 4️⃣ Create Scan Task

1. Go to **Scans → Tasks → New Task**
2. **Name:** `Full Vulnerability Scan - Localhost`
3. **Target:** Select the target created above
4. **Scan Config:** `Full and Fast`
5. Save the task

---

## 5️⃣ Run the Scan

* On the **Tasks** page, click the ▶️ **Start** icon
* Wait for the scan to complete (typically 30–60 minutes for a local scan)

---

## 6️⃣ Results

**Outcome:**
The **Full and Fast** scan found only informational results (**Log** severity 0.0), meaning no exploitable vulnerabilities were detected.

**Key Findings:**

1. **OS Detection Consolidation and Reporting** – Detected OS: Linux Kernel
2. **Traceroute** – Determined network distance: 1 hop
3. **CPE Inventory** – Detected CPE: `cpe:/o:linux:kernel`
4. **Hostname Determination** – Hostname same as IP address

---

## 7️⃣ Conclusion

* **Severity:** No vulnerabilities found above **Log** level
* Only informational results were reported
* The system appeared secure at the time of scanning
* Recommendation: Keep the system updated and perform periodic scans for ongoing security assurance

---
