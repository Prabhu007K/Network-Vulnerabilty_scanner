# Network Vulnerability Scanner & Real-Time Tracking

A Python-based Network Vulnerability Scanner that detects open ports, identifies vulnerable network services, and generates detailed vulnerability reports with risk assessment and mitigation recommendations. The tool includes real-time scanning visualization using Matplotlib.

---

## Features

- Multi-threaded fast port scanning  
- Real-time visualization of scanning progress  
- Detection of commonly vulnerable ports (FTP, SSH, SMB, RDP)  
- Automated reporting with risk levels and mitigation steps  
- Simulation mode for demonstration and testing  
- Clean terminal output with color coding  
- Cross-platform support (Windows, Linux, macOS)

---

## Technologies Used

| Component       | Description                                           |
|----------------|-------------------------------------------------------|
| Language        | Python                                                |
| Libraries       | socket, threading, matplotlib, argparse, datetime, colorama |
| Scan Type       | TCP Connect Scan                                      |
| Visualization   | Matplotlib (FuncAnimation)                            |
| Reporting       | Text-based, structured output                         |

---

## Installation

### Step 1: Clone the Repository
```bash
git clone https://github.com/Prabhu007K/Network-Vulnerabilty_scanner.git
cd Network-Vulnerabilty_scanner
````

### Step 2: Install Dependencies

```bash
pip install colorama matplotlib
```

---

## Usage

### Basic Scan

```bash
python3 scanner.py -t 192.168.1.1 -p 1-1024 -n 200 --timeout 0.5
```

### Simulation Mode (For Demonstration)

```bash
python3 scanner.py -t 192.168.1.1 -p 1-1024 -n 200 --timeout 0.5 --simulate
```

| Flag         | Description                              |
| ------------ | ---------------------------------------- |
| `-t`         | Target IP address                        |
| `-p`         | Port range (e.g., 1-1024)                |
| `-n`         | Number of threads                        |
| `--timeout`  | Socket connection timeout                |
| `--simulate` | Enable simulated vulnerability detection |

---

## Sample Output

```
╔══════════════════════════════════════════════════════════════╗
║                   NETWORK VULNERABILITY REPORT               ║
╚══════════════════════════════════════════════════════════════╝

Target IP: 192.168.1.1
Scan completed in: 2.45 seconds
Total ports scanned: 1024
Open ports found: 4
Vulnerabilities detected: 2

[+] Port 80 (HTTP) is open
[+] Port 22 (SSH) is open and vulnerable

[VULNERABILITY] SSH on port 22 - Weak encryption allowed (Risk: Medium)
Mitigation: Update SSH configuration and disable legacy ciphers
```

---

## Supported Vulnerability Checks

| Port | Service | Risk Level | Recommendation                                     |
| ---- | ------- | ---------- | -------------------------------------------------- |
| 21   | FTP     | High       | Disable anonymous access or use SFTP               |
| 22   | SSH     | Medium     | Use strong encryption and disable legacy protocols |
| 23   | Telnet  | Critical   | Replace with SSH                                   |
| 445  | SMB     | Critical   | Disable SMBv1 and update SMB configuration         |
| 3306 | MySQL   | High       | Restrict remote access or use VPN                  |
| 3389 | RDP     | High       | Enable NLA and use VPN                             |

---

## Internal Workflow

1. Uses TCP socket connection to detect open and closed ports
2. Fetches service information using `socket.getservbyport()`
3. Matches open ports with pre-defined vulnerability database
4. Displays real-time scanning progress using Matplotlib animation
5. Generates final vulnerability report with mitigation guidelines

---

## Future Enhancements

* Export reports as PDF/HTML
* CVE database integration
* Web interface using Flask/Django
* GUI implementation with PyQt or Tkinter
* Email-based vulnerability report automation

---

## Contribution

Contributions are welcome. Fork the repository, create a feature branch, and submit a pull request.

---

## License

This project is licensed under the MIT License.

---

## Contact

---
Email: [prabhuku004@gmail.com](mailto:prabhuku004@gmail.com)
---
LinkedIn: linkedin.com/in/k-prabhu-1869b8275/
---
GitHub: github.com/Prabhu007K
---


If you find this project helpful, consider starring the repository.
