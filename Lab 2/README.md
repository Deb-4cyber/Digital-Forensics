# 📌 Android App Repackaging Attack Lab

## 📝 Overview
This project explores the mechanics of a **Repackaging Attack** on the Android platform. The primary objective was to gain hands-on experience in reverse-engineering a legitimate application, injecting a malicious payload, and re-signing the application for deployment. This lab highlights the security risks associated with third-party app markets and the critical importance of code integrity in the mobile software supply chain.

## ⚙️ Methodology 
The investigation followed a systematic reverse-engineering and exploitation workflow:

- **Decompilation**: Disassembled the target APK to retrieve the human-readable Smali code and resource files.
- **Malicious Code Injection**: Integrated a specific Smali hook (`MaliciousCode.smali`) designed to trigger an unauthorized action (deleting system contacts).
- **Rebuilding & Optimization**: Reassembled the modified source files into a functional application package.
- **App Signing**: Generated a custom digital signature and signed the modified APK to bypass Android’s security verification for installation.
- **Deployment & Testing**: Hosted the malicious APK on a local server and executed the attack within a controlled SEED Android VM environment.

## 🛠️ Tools & Technologies
- **APKTool**: Primary tool for unpacking and rebuilding the Android application.
- **Smali/Baksmali**: For editing and assembling the underlying dex code.
- **Keytool & Jarsigner**: Used for creating a custom keystore and applying a digital signature to the modified APK.
- **SEED Ubuntu 16.04 VM**: The attack environment for reverse engineering.
- **Android 7.1 VM**: The target environment for deploying and testing the repackaged app.

## 💻 Implementation 
1. **Unpacking**: Used `apktool d RepackagingLab.apk` to extract the app's internal resources and Smali code.
2. **Identifying the Entry Point**: Analyzed the Smali files to find a suitable location (hook) to trigger the malicious logic.
3. **Payload Injection**: Inserted the `MaliciousCode.smali` logic into the app directory and added the necessary `invoke` command to the target class.
4. **Reassembling**: Package the modified folders back into a new APK format using `apktool b`.
5. **Signing**: 
   - Created a unique developer key using `keytool -genkey`.
   - Signed the modified APK using `jarsigner` to make it installable on the Android OS.
6. **Execution**: Installed the signed APK on the Android VM and triggered the payload to verify successful contact deletion.

## 📊 Results / Findings
- **Seamless Integration**: The repackaged application maintained the original UI and user experience, making the malicious modifications invisible to a standard user.
- **Payload Success**: Upon triggering the injected code, the application successfully performed the unauthorized deletion of contacts within the isolated VM.
- **Detection Gap**: Demonstrated that without verifying the developer's original certificate, it is nearly impossible for an end-user to distinguish between a legitimate and a weaponized application.

## 🖼️ Screenshots / Diagrams
> *Note: All screenshots and findings detailed below were captured during the exploitation phase in the SEED Lab environment.*

### Evidence Figure 1: Decompilation of the target APK using APKTool.
<img width="500" height="400" alt="2a" src="https://github.com/user-attachments/assets/a4797ccc-7996-4351-94b1-0db9759a4a9f" />

### Evidence Figure 2: The injected Smali code hook within the application logic.
<img width="500" height="400" alt="3b" src="https://github.com/user-attachments/assets/46d184a0-e1fb-43fe-a128-d5f5d9d482ec" />

### Evidence Figure 3: Verification of the signed malicious APK.
<img width="500" height="400" alt="4d" src="https://github.com/user-attachments/assets/7e483951-8f70-4275-969e-cfe5107bb4b4" />

### Evidence Figure 4: The repackaged app running on the Android VM.
<img width="500" height="400" alt="5c" src="https://github.com/user-attachments/assets/0134589d-bbc8-4cd5-8e43-86e91c3cdf02" />

## 💡 Challenges & Lessons Learned
- **Code Integrity**: Gained a deep understanding of Android’s signature requirement and how it can be bypassed if users download from untrusted sources.
- **Supply Chain Risk**: Witnessed how easily popular applications can be weaponized to perform background attacks.
- **Evidence Collection**: Practiced documenting the full lifecycle of an exploit, from reverse engineering to execution.

## 📂 Repository Structure
```text
├── Tools/
│   └── setup_commands.sh            # ☁️🔐 Commands for APKTool and Signing
├── Repackaging_Documentation/       # Technical notes and Smali logic
│   ├── injection_point.txt          # Details on the code hook location
│   └── malicious_logic_summary.md   # Explanation of payload behavior
├── Screenshots/                     # Exploitation visuals
└── README.md                        # Investigation summary 🕵️
