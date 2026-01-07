# 📌 Windows Memory Forensics (Volatility) 

## 📝 Overview
This lab analyzes a Windows memory dump (`evilprofessor.vmem`) to reconstruct system activity. I employed a hybrid workflow, using **Volatility 3** for initial process triage and **Volatility 2** for granular hierarchy mapping to identify service origins and parent-child relationships.

## 🛠️ Tools & Environment
- **Volatility 3**: Used for rapid process enumeration and symbol resolution.
- **Volatility 2 (v2.6.1)**: Used for detailed hierarchical process tree (`pstree`) analysis.
- **OS**: Kali Linux.

## ⚙️ Methodology
1.  **System Triage (Vol 3)**: Identified **48 active processes** and resolved kernel symbols despite missing VMware metadata.
2.  **Service Analysis**: Identified **3 active `cmd.exe` instances** and compared `pslist` vs `psscan` to find terminated processes.
3.  **Hierarchy Mapping (Vol 2)**: Visualized parent-child lineages to verify service legitimacy.

## 📊 Key Findings
- **sshd.exe Analysis**: Traced the origin of `sshd.exe` to parent process **PID 184**.
- **Service Validation**: Confirmed **mysqld-nt.exe** was spawned by **PID 740** (Service Control Manager), validating it as a legitimate system service.
- **Integrity**: Verified a consistent count of 48 active tasks across both forensic frameworks.

## 🖼️ Screenshots

### Evidence Figure 1: Volatility 3 pslist & Process Count
<img width="600" height="500" alt="1" src="https://github.com/user-attachments/assets/d60328b2-7bd1-4d12-81b1-64ab17d52930" />

### Evidence Figure 2: Volatility 2 pstree - Service Origins
Reconstructing the hierarchy to identify that PID 184 spawned sshd.exe.
<img width="600" height="500" alt="4 a" src="https://github.com/user-attachments/assets/036a4710-2170-44c7-a048-bc696728f09b" />

### Evidence Figure 3: Volatility 2 pstree - Extended View
<img width="600" height="500" alt="4 b" src="https://github.com/user-attachments/assets/efd66ea2-9c2a-4242-99fb-9fc0d3f930e3" />

### Evidence Figure 4: MySQL Service Validation
Final verification of mysqld-nt.exe originating from PID 740.
<img width="600" height="500" alt="5" src="https://github.com/user-attachments/assets/edfa2e92-bbcd-4076-a398-a261e1d6a8f4" />

## 💡 Lessons Learned
- Pivoted between Volatility versions to leverage specific plugin strengths (e.g., Vol 2's detailed `pstree` formatting).
- Mastered tracing background services back to their roots to distinguish legitimate operations from malicious activity.
