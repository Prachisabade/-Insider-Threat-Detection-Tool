# -Insider-Threat-Detection-Tool 

A Python-based security monitoring tool designed to detect and log potential insider threats. Events are logged to an SQLite database, logs are refreshed in real-time. This version features a **Modern GUI**, real-time pop-up alerts, and smart log management. It tracks sensitive file access, off-hour activity, USB insertions, and suspicious processes.

## 🚀 Features

### 🎨 Modern UI (CustomTkinter)
* **Dark/Light Mode:** Toggle between themes with a single click.
* **Sidebar Navigation:** A clean "panel" layout for controls.
* **Responsive Table:** A styled log viewer that adapts to the chosen theme.

### 🔔 Real-Time Alerts
The tool triggers pop-up warnings for critical events:
1.  **Off-Hours Login:** Detects activity outside of 9 AM – 6 PM.
2.  **Mass File Access:** Alerts if >3 sensitive files are accessed within a minute.
3.  **Suspicious Processes:** Alerts if >5 dangerous processes (e.g., `cmd.exe`, `powershell.exe`) are running.
4.  **Physical Security:** Immediate alert upon USB device insertion.

### ⚡ Performance & Management
* **Smart Deduplication:** Prevents log spam by grouping identical events occurring within 60 seconds.
* **Quick Refresh:** Live monitoring updates every **5 seconds**.
* **Clear Logs:** A dedicated button to wipe the database and reset the view.

---

## 🛠️ Technologies Used
* **Python 3**
* **CustomTkinter** (Modern GUI framework)
* **Psutil** (System monitoring)
* **SQLite3** (Local log storage)
* **Threading** (Non-blocking background monitoring)

---

## 📥 Installation & Usage

1.  **Clone this Repository**
    ```bash
5 days ago

Fix clone command formatting in README
    git clone https://github.com/Prachisabade/-Insider-Threat-Detection-Tool.git
5 days ago

Initialize README with project details and instructions
    ```
2.  **Install Dependencies**
    You must install `customtkinter` and `psutil` to run:
    ```bash
    pip install customtkinter psutil
    ```

3.  **Run the Tool**
    ```bash
    python INTD.py
    ```

---

## ⚙️ Configuration
Ensure Python 3 is installed.
Tested on Windows 11. Modify paths for compatibility with other operating systems.
Run with administrator privileges for full functionality.
You can customize the monitoring rules by editing the `CONFIG` section in `INTD.py`:
```python
SENSITIVE_DIRS = ["C:/Users/Public/Documents", "C:/ImportantData"]  # Directories to watch
WORK_HOURS = (9, 18)  # Working hours (24-hour format)
DB_FILE = "insider_threat_logs.db" # Database file name
