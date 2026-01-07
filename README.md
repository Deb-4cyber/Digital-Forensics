# 🕵️ Digital-Forensics

A high-performance suite of **Forensic Investigative Engines** designed to transform raw bit-stream images and volatile memory dumps into actionable security intelligence. This repository documents end-to-end workflows of 3 major labs including Autopsy, App Repackaging and Memory Forensics.

---

## 🎯 Project Spotlight

| Project | Role | Industrial Value |
| :--- | :--- | :--- |
| **[Autopsy](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%201)** | **Artifact Triage** | Resolves "Fileless" adversarial persistence via VAD tree and process family reconstruction. |
| **[App Repackaging](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%202)** | **Reverse Engineering** | Reconstructs the 'Chain of Events' and mitigates anti-forensic data deletion. |
| **[Memory Forensics](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%203)** | **Memory Triage** | Neutralizes mobile supply-chain threats through deep-code Smali injection analysis. |

---

## 🛠️ Industrial Forensic Strengths

* **Volatile Artifact Reconstruction:** Leveraged a hybrid **Volatility 2 & 3** workflow. Successfully navigated missing VMware metadata by performing automated **PDB symbol resolution** to identify 48 active process threads.
* **Adversarial Persistence Detection:** Utilized `pstree` to map hierarchical process family trees. Identified critical parent-child anomalies, tracing unauthorized service-spawning (e.g., verifying `sshd.exe` lineage to PID 184 and `mysqld-nt.exe` to the Service Control Manager).
* **Forensic Timeline Recovery:** Conducted deep-sector analysis using **Autopsy** to correlate non-volatile artifacts. Specialized in recovering evidence bypassed by standard OS APIs through forensic file carving and metadata analysis.
* **Static Binary Analysis:** Executed reverse engineering on Android binaries. Utilized `apktool` for deconstruction and manual **Smali code injection** to identify logic vulnerabilities and validate application integrity.
* **Evidence Integrity Management:** Strict adherence to DFIR standards when handling `.vmem` and `.E01` files. Proven capability in resolving kernel offsets and memory address spaces manually when automated metadata is unavailable.

---

### 🔧 Technical Stack

- **Forensic Tools:** Volatility 2.6.1, Volatility 3, Autopsy, The Sleuth Kit.

- **Reverse Engineering:** Apktool, Smali/Baksmali, Uber-APK-Signer, Keytool.

- **Environments:** Kali Linux (Forensic Environment), Windows Kernel Debugging.

- **Competencies:** PID Lineage Tracking, APK Repackaging, Artifact Triage and File Carving.

---

## 📁 Repository Structure
```text
.
├── Lab 1/    # Disk Forensics: Timeline Reconstruction & Evidence Recovery
├── Lab 2/    # Mobile App Security: Reverse Engineering & Smali Injection Analysis
├── Lab 3/    # Memory Forensics: Resolving Volatile family trees & PS Scanning
└── README.md # Portfolio Landing Page & DFIR Skills Matrix
