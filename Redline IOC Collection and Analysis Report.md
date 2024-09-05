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

    
2. **Store IOCs in Mandiant**  
    The extracted information was then input into Mandiant IOCs. ![[Pasted image 20240903225714.png]] ![[Pasted image 20240903225837.png]] ![[Pasted image 20240903225941.png]]
    
3. **Repeat for Additional Files**  
    The same method was applied to collect IOC data for other files. ![[Pasted image 20240903230705.png]]
    

## Redline Analysis

### Setting Up for Analysis

With the IOCs generated, the next step was to import them into Redline for analysis:

1. **Add IOC Location**  
    Imported the newly created IOCs into Redline. ![[Pasted image 20240903231441.png]]
    
2. **Specify Scan Path**  
    Configured Redline to scan the `DaveS\` directory. ![[Pasted image 20240903231321.png]]
    

### Running the Redline Audit

Executed the Redline audit to begin the analysis. ![[Pasted image 20240903231700.png]]

### Analyzing the Results

Opened the analysis session to review the findings. The results indicated that IOCs were detected in the `DaveS\` directory. ![[Pasted image 20240903231738.png]]

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
