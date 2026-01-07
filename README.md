# 🕵️ Digital-Forensics

---

A high-performance suite of **Forensic Investigative Engines** designed to transform raw bit-stream images and volatile memory dumps into actionable security intelligence. This repository documents end-to-end workflows of 3 major labs including Autopsy, App Repackaging and Memory Forensics.

---

## 🎯 Project Spotlight

| Project | Role | Industrial Value |
| :--- | :--- | :--- |
| **[![Autopsy](https://img.shields.io/badge/Lab_1-Autopsy-red?style=flat-square)](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%201)** | **Artifact Triage** | Reconstructs the 'Chain of Events' and mitigates anti-forensic data deletion.|
| **[![Repackaging](https://img.shields.io/badge/Lab_2-App_Repackaging-blue?style=flat-square)](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%202)** | **Reverse Engineering** | Neutralizes mobile supply-chain threats through deep-code Smali injection analysis.  |
| **[![Memory](https://img.shields.io/badge/Lab_3-Memory_Forensics-green?style=flat-square)](https://github.com/Deb-4cyber/Digital-Forensics/tree/main/Lab%203)** | **Memory Triage** | Resolves "Fileless" adversarial persistence via VAD tree and process family reconstruction.|

---

## 🛠️ Industrial Forensic Strengths

- **Forensic Evidence Discovery:** Conducted deep-sector analysis using **Autopsy** to correlate non-volatile artifacts. Specialized in recovering system files and user activity artifacts bypassed by standard OS APIs.
- **Static Binary Analysis:** Executed reverse engineering on Android binaries. Utilized `apktool` for deconstruction and manual **Smali code modification** to identify logic vulnerabilities and validate application integrity.
- **Volatile Artifact Reconstruction:** Leveraged a hybrid **Volatility 2 & 3** workflow. Successfully navigated missing VMware metadata by performing automated **Symbol/PDB resolution** to identify 48 active process threads.
- **Malicious Persistence Analysis:** Utilized `pstree` to map hierarchical process family trees. Identified critical parent-child anomalies, tracing unauthorized service-spawning (e.g., verifying `sshd.exe` lineage to PID 184 and `mysqld-nt.exe` to the Service Control Manager).
- **Evidence Integrity Management:** Strict adherence to DFIR standards when handling `.vmem` and bit-stream images, ensuring accurate memory address space mapping even in the absence of original metadata.

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
