## **README.md Content**

````markdown
# 🛡️ Basic Vulnerability Scan using OpenVAS (Full and Fast)

## 📌 Objective
Perform a basic vulnerability scan on my PC using OpenVAS Community Edition in Kali Linux, following the internship task requirements.

---

## 1️⃣ Installation & Setup

### Update system packages
```bash
sudo apt update && sudo apt upgrade -y
````

### Install OpenVAS (Greenbone Vulnerability Management)

```bash
sudo apt install openvas -y
```

### Setup OpenVAS

```bash
sudo gvm-setup
```

**Outcome:**

* Initializes scanner database
* Downloads vulnerability feed
* Creates admin user (save credentials shown in terminal)

### Start GVM services

```bash
sudo gvm-start
```

**Outcome:**
Shows the web interface URL (e.g., [https://127.0.0.1:9392](https://127.0.0.1:9392))

---

## 2️⃣ Access Web Interface

* Open browser in Kali and go to:

  ```
  https://127.0.0.1:9392
  ```
* Login with the admin credentials from setup.

---

## 3️⃣ Create Scan Target

* Go to **Configuration → Targets → New Target**
* **Name:** `Localhost Vulnerability Scan`
* **Hosts:** `192.168.x.x` (your local IP from `ip addr show`)
* **Alive Test:** `Consider Alive`
* **Port List:** `All IANA assigned TCP and UDP`
* Save target.

---

## 4️⃣ Create Scan Task

* Go to **Scans → Tasks → New Task**
* **Name:** `Full Vulnerability Scan - Localhost`
* **Target:** Select the one created above
* **Scan Config:** `Full and Fast`
* Save task.

---

## 5️⃣ Run the Scan

* On the **Tasks** page, click the ▶️ Start icon.
* Wait 30–60 mins for scan to finish.

---

## 6️⃣ Results

**Outcome:**
The Full and Fast scan found only informational results (Log severity 0.0), meaning no exploitable vulnerabilities were detected.

**Findings:**

1. **OS Detection Consolidation and Reporting** — Detected Linux Kernel OS.
2. **Traceroute** — Determined network distance (1 hop).
3. **CPE Inventory** — Detected system CPE: `cpe:/o:linux:kernel`.
4. **Hostname Determination** — Hostname same as IP address.

---

## 7️⃣ Conclusion

* **Severity:** No vulnerabilities found.
* Only informational logs were generated, indicating a clean system at the time of scanning.
* Recommended to keep system updated and rescan periodically.

---

