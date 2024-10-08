
## Overview

Alexis is a fictional cybersecurity company with a large employee base. A security incident has occurred where an attacker gained unauthorized access to the company's internal networks by connecting their laptop to an unused port on a network switch. The attacker is now attempting to collect SSH credentials to access the central server containing critical proprietary data.

## Incident Details

### 1. Attacker's MAC Address

- **MAC Address:** 08:00:27:3d:27:5d
- **Analysis:** The MAC address of the attacker was identified using Wireshark.
![AttackerMAC](https://github.com/user-attachments/assets/373c7b9a-8cd3-4f1a-bc45-4d78ac7da466)


### 2. Type of Attack

- **Attack Type:** Man-in-the-Middle (MitM) Attack
- **Description:** The attacker is using a Man-in-the-Middle attack to intercept and listen to communications between the central server and other network hosts.

### 3. File Downloaded from the Central Server

- **File Name:** Alevis_Employee_Information_Chart.csv
- **Analysis:** The file was identified through an analysis of FTP packets and following the data stream.
![FTPfiletransfer](https://github.com/user-attachments/assets/edbea310-07bf-45ce-8860-31c7b65bdf3c)


### 4. Department of Borden Danilevich

- **Department:** Sales
- **Analysis:** By examining the downloaded CSV file, specifically entry 292, it was determined that Borden Danilevich is part of the Sales department.
![csvdownload](https://github.com/user-attachments/assets/30405c4f-c992-484a-bb0e-06f46095c93b)

![BordenDanilevich](https://github.com/user-attachments/assets/ff4e41af-2dce-472e-8417-ea82628467af)

### 5. SSH Password of the Domain Administrator

- **Password:** gMR<4eXf]e6W
- **Analysis:** The SSH password for the Domain Administrator was discovered in entry 478 of the CSV file.

![admin](https://github.com/user-attachments/assets/e84839e6-5ccb-472b-a141-513eb7ee6f53)

## Summary

The attacker was able to successfully perform a Man-in-the-Middle attack to intercept data transmitted between the central server and other network hosts. Key information obtained includes the MAC address of the attacker, details of a downloaded file (Alevis_Employee_Information_Chart.csv), and sensitive credentials including the SSH password of the Domain Administrator.

---

**Note:** All findings and analyses are based on the provided capture files and should be handled according to the Security Blue Team's guidelines. Redistribution of these findings without permission is prohibited.
