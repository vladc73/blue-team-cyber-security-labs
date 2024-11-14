# Yellow RAT Lab

## Objective
Investigate malware behind abnormal network traffic at GlobalTech Industries

### Category: 
Threat Intel

### Tools: 
VirusTotal

### Scenario:
During a regular IT security check at GlobalTech Industries, abnormal network traffic was detected from multiple workstations. Upon initial investigation, it was discovered that certain employees' search queries were being redirected to unfamiliar websites. This discovery raised concerns and prompted a more thorough investigation. Your task is to investigate this incident and gather as much information as possible.

Known IOC : SHA256 hash:
30E527E45F50D2BA82865C5679A6FA998EE0A1755361AB01673950810D071C85

### Steps:
1. Understanding the adversary helps defend against attacks. What is the name of the malware family that causes abnormal network traffic? PoshC2 - S0378, Jupyter Loader, Jupyter Client, "Yellow Cockatoo RAT"

*In Virustotal, I enter the Hash into the search box

*Click the Relations tab and scrolled down to the graph summary

*In the graph summary, I click on the center icon to open the Virustotal graph

*I click on "Introducing The Jupyter Infostealer/Backdoor icon

*This is where the malware family is and source link
![source link](https://github.com/user-attachments/assets/17f519f5-440e-4af1-9978-ccd2f44fb246)

2. As part of our incident response, knowing common filenames the malware uses can help scan other workstations for potential infection. What is the common filename associated with the malware discovered on our workstations? 111bc461-1ca8-43c6-97ed-911e0e69fdf8.dll
	
 *Next to the Community score, the name is the second one down
	
 *Under Relations tab, scroll down to the Names section and first name is the answer
 ![filename](https://github.com/user-attachments/assets/59a11595-0e2a-4e38-a22d-a10e9bb127ff)

3. Determining the compilation timestamp of malware can reveal insights into its development and deployment timeline. What is the compilation timestamp of the malware that infected our network? 2020-09-24 18:26:47 UTC
	
*Under the Details tab, scroll to the Portable Executable info
![compliation timestamp](https://github.com/user-attachments/assets/65d26e71-c0a4-4e07-9aaf-640990987ecb)

4.  Understanding when the broader cybersecurity community first identified the malware could help determine how long the malware might have been in the environment before detection. When was the malware first submitted to VirusTotal? 2020-10-15 02:47:37 UTC
	
*Under the details tab, scroll down to the History section
 ![firstsubmitted](https://github.com/user-attachments/assets/f3cb6b16-2326-4f1a-93f6-733c8c8ba299)

5. To completely eradicate the threat from Industries’ systems, we need to identify all components dropped by the malware. What is the file name dropped by the malware in the Appdata folder? %APPDATA%\solarmarker.dat
	
 *This is under the community tab, one of the analysis of the file and follow the link to the dropper and check the behavior tab to determine the filename dropped by the malware.
	
 -https://www.virustotal.com/gui/file/a1a9137dea275aa805e5640f6450366dbf6e10be066e5c12c34904e45e469c4c/detection
![namedropped1](https://github.com/user-attachments/assets/8dbf4122-e553-4eef-86a2-1fa1e491fb44)
![namedropped2](https://github.com/user-attachments/assets/d02ca764-0f59-4cd2-b547-6b0d6386bea6)

6. It is crucial to identify the C2 servers with which the malware communicates to block its communication and prevent further data exfiltration. What is the C2 server that the malware is communicating with? gogohid.com
	
*Behavior tab > Activity Summary > Network Communications> Memory Pattern URLs
![C2 server](https://github.com/user-attachments/assets/dcb4d690-e81d-46ee-add0-35b54d8141ab)
