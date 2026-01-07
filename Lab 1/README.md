# 📌 Digital Forensic Investigation: The "Lone Wolf" Scenario

## 📝 Overview
This project demonstrates a comprehensive digital forensic analysis conducted as part of an academic lab exercise. The investigation centers on the "Lone Wolf" training scenario, where the primary objective was to analyze a suspect's digital artifacts to uncover plans for a potential mass shooting event. By utilizing industry-standard tools, the investigation successfully recovered deleted files, search history, and logistical planning documents that established the suspect's intent and escape routes.

## ⚙️ Methodology / Approach
The investigation followed a rigorous forensic workflow to ensure data integrity and legal admissibility:
- **Data Acquisition**: Captured a complete forensic disk image (`img_LoneWolf.E01`) of the suspect's laptop using FTK Imager.
- **Integrity Verification**: Utilized cryptographic hashing (MD5/SHA1) to verify that the forensic images remained untampered throughout the analysis.
- **Partition & File System Analysis**: Analyzed the hard drive architecture, total disk space, and user account structures, specifically focusing on the `jcloudy` user profile.
- **Artifact Extraction**: Systematically explored the root tree to identify and recover incriminating documents and web artifacts.
- **Reporting**: Documented the forensic process to ensure transparency and accountability, simulating the preparation of evidence for legal proceedings.

## 🛠️ Tools & Technologies
- **Autopsy (Version 4.0)**: Used as the primary digital forensics platform for deep-dive analysis and evidence categorization.
- **FTK Imager**: Employed for secure data acquisition, forensic imaging, and hashing.
- **Forensic File Formats**: Worked with `.E01` (Expert Witness Format) disk images.
- **Write Blocker**: Utilized during initial data capture to prevent accidental modification of evidence.

## 💻 Implementation / Steps
1.  **Environment Setup**: Installed the Autopsy forensic suite and prepared the Lone Wolf scenario data source.
2.  **Ingestion & Mapping**: Loaded the disk images into Autopsy and mapped out the various partitions and file systems.
3.  **Targeted Desktop Analysis**: Navigated to the directory `/img_LoneWolf.E01/Vol_vol7/Users/jcloudy/Desktop` to retrieve primary evidence.
4.  **Document Recovery**: Identified key evidence files including `The Cloudy Manifesto.docx`, `Planning.docx`, and `Cloudy thoughts.docx`.
5.  **Web Artifact Analysis**: Used the Data Artifacts section to analyze web searches related to weapon purchases and airport smuggling.
6.  **Timeline Reconstruction**: Correlated screenshots of flight bookings and hotel reservations to determine the suspect's planned operation date and escape timeline.

## 📊 Results / Findings
- **Operational Details**: The suspect planned to execute the operation on **April 7, 2018**, between **12:30 and 2:00 PM** at the "Town Hall Project" located at 21030 Whitfield Place.
- **Logistical Planning**: Evidence was found of round-trip airline tickets from Dulles International Airport to Bali, Indonesia, with a planned departure on the same day as the event.
- **Reconnaissance**: Recovered Google Maps screenshots detailing escape routes from the event location to the airport.
- **Evidence of Intent**: The "Cloudy Manifesto" and browser searches for "where to buy guns" and "smuggling cash" provided clear evidence of premeditation.
- **Mental State**: Analysis of the suspect's desktop showed a preoccupation with mental health quotes and firearms in the days leading up to the event.

## 🖼️ Screenshots / Diagrams
> *Note: All screenshots and findings detailed below are captured from the Autopsy Forensic Tool.*

### Evidence Figure 1: Proof of airline ticket purchase for Washington to Bali.
  <img width="500" height="250" alt="3a" src="https://github.com/user-attachments/assets/de8d79e2-f801-4c9c-93ba-bfece072281d" />

### Evidence Figure 2: The "Town Hall For Our Lives" event details at Sterling, VA.
  <img width="500" height="200" alt="3b" src="https://github.com/user-attachments/assets/b0a6d902-73e3-46e1-ae84-2796d2796077" />

### Evidence Figure 3: Google Maps escape route from Whitfield Place to Dulles Airport.
  <img width="500" height="200" alt="3e" src="https://github.com/user-attachments/assets/51872402-f9e6-4cbe-8a19-9f0330b29c2d" />

### Evidence Figure 4: Snippet from "The Cloudy Manifesto" detailing the suspect's ideology.
  <img width="500" height="200" alt="Screenshot (104)" src="https://github.com/user-attachments/assets/d76146ce-726d-4078-97be-d4f1a46b8536" />

### System View: Forensic view of the partition structure and deleted file recovery in Autopsy.
  <img width="500" height="300" alt="5a" src="https://github.com/user-attachments/assets/7414393a-9ed3-48d6-9208-f7bd76ef78fe" />
  <img width="500" height="300" alt="5f" src="https://github.com/user-attachments/assets/728df9e7-7e45-4c26-a3df-eb7cdcf1af5c" />

## 💡 Challenges & Lessons Learned
- **Data Recovery**: Gained proficiency in using FTK Imager to recover deleted or hidden files that a suspect might try to conceal.
- **Forensics Evidence Collection**: Learned the value of combining digital evidence (search history) with physical evidence (travel logs) to build a complete case profile.
- **Chain of Custody**: Understanding the critical importance of hashing and write-blocking to maintain a valid chain of custody for legal environments.
  
