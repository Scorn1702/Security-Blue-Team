## Overview

This report details the process of using Redline to detect Indicators of Compromise (IOCs) based on a simulated malware investigation. The primary objective was to identify potential malware files within a system using Mandiant IOCs, collected from provided malware samples.

## IOC Collection Setup

### Configuring Redline IOC Collector

Before exporting the Redline IOC Collector, it was essential to configure it correctly to search for specific indicators:

- **Enable String and SHA-1 Hash Searches**:  
    This can be done by selecting the **“Edit your script”** option during the export process. Navigate to the **Disk** tab and ensure that both **Strings** and **SHA-1** options are enabled.

### IOC Types Collected

The IOCs targeted in this investigation include:

- **MD5 Hashes**
- **SHA-1 Hashes**
- **File Size**
- **File Names**
- **Strings**

### Pre-Analysis Preparation

To ensure comprehensive coverage, I carefully reviewed the notes provided by the Threat Intelligence analysts. This step was crucial for identifying all potential malware traces in the system.

## Collecting IOC Data

### Extracting Malware Information

Using PowerShell, I gathered the necessary information (file names, file sizes, MD5 hashes, and SHA-1 hashes) from the malware samples provided. The following steps outline the process:

1. **Analyze File: 03....**  
    Collected relevant IOC data using PowerShell. ![Pasted image 20240903225634](https://github.com/user-attachments/assets/c0fe969e-8fe5-40f9-9aeb-8a34e7ca5115)
![Pasted image 20240903225714](https://github.com/user-attachments/assets/59f3762a-570c-4c7e-a7cf-28a425d27586)
![Pasted image 20240903225837](https://github.com/user-attachments/assets/d99851d7-ef62-4d3c-82ef-9afd2de091c6)

2. **Repeat for Additional Files**  
    The same method was applied to collect IOC data for other files. 

3. **Store IOCs in Mandiant**  
    The extracted information was then input into Mandiant IOCs. 
![Pasted image 20240903225941](https://github.com/user-attachments/assets/f7e316a6-2f2a-4c08-98b5-1dce26b47300)
![Pasted image 20240903230705](https://github.com/user-attachments/assets/77508ed9-9bf5-4a05-a685-358a979fafaf)

## Redline Analysis

### Setting Up for Analysis

With the IOCs generated, the next step was to import them into Redline for analysis:

1. **Add IOC Location**  
    Imported the newly created IOCs into Redline. 
    ![Pasted image 20240903231441](https://github.com/user-attachments/assets/9ff8cd35-1b66-40fd-811d-ca31ce641007)

2. **Specify Scan Path**  
    Configured Redline to scan the `DaveS\` directory. 
    ![Pasted image 20240903231321](https://github.com/user-attachments/assets/0f0f80a5-043d-4f8d-9d24-0db57699b73a)


### Running the Redline Audit

Executed the Redline audit to begin the analysis. 
![Pasted image 20240903231700](https://github.com/user-attachments/assets/80232a8c-7bc5-4ca8-8430-db114475ab86)
![Pasted image 20240903231738](https://github.com/user-attachments/assets/8eca1340-592b-40d3-beea-005ed30b41dd)

### Analyzing the Results

Opened the analysis session to review the findings. The results indicated that IOCs were detected in the `DaveS\` directory.
![Pasted image 20240903232224](https://github.com/user-attachments/assets/646204bd-a86b-4cdd-99c0-32a27c1141c6)

## Key Findings

Upon completing the analysis, the following information was uncovered:

1. **Number of Malware Files Detected**:  
    A total of **4** pieces of malware were identified using the IOCs generated from the samples.
    
2. **File Name Starting with "w"**:  
    The file named **`wallpaperHD.exe`** was identified.
    
3. **Malware in `/DaveS/Pictures`**:  
    It was confirmed that there is malware in this location (**True**).
    
4. **Recurring MD5 Hash**:  
    The MD5 hash **`0c4374d72e166f15acdfe44e9398d026`** appeared in two different files.
