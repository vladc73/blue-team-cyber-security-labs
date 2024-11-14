# Packet Detective Lab

## Objective
Analyze network traffic to detect evasion, lateral movement, and Command and Control (C&C) activity.

### Category: 
Network Forensics
### Tactics: 
Execution, Defense Evasion, Command and Control
### Tools: 
Wireshark

### Scenario:
In September 2020, your SOC detected suspicious activity from a user device, flagged by unusual SMB protocol usage. Initial analysis indicates a possible compromise of a privileged account and remote access tool usage by an attacker.

Your task is to examine network traffic in the provided PCAP files to identify key indicators of compromise (IOCs) and gain insights into the attacker’s methods, persistence tactics, and goals. Construct a timeline to better understand the progression of the attack by addressing the following questions.

### Steps:
1.  (File => Traffic-1) What is the amount of bandwidth being used by the SMB protocol in bytes? 4406
	
 *You can find the answer by going to Statistics > Protocol Hierarchy and you would find the answer rightaway.
![bandwith](https://github.com/user-attachments/assets/46a55429-d0be-42a5-ba85-831e6f419222)

2. (File => Traffic-1) Which username was utilized for authentication via SMB? Administrator
	*To hunt for the username which was utilized for authenticating to the SMB service, there are several ways to achieve this. For me, I take a look at the info column which provides details about each packet, but before we are going to investigate each packet, make sure to filter just only the interested ones. In this case, SMB protocol. To filter it, just click on filter box below the main toolbar and search for smb.
	*After filter the packet protocol, you would see a lot of the information appears there which communicated using SMB protocol. By looking at the info column, you would directly see an interested username which used by malicious actor to authenticate to the SMB service.
![username](https://github.com/user-attachments/assets/cf8af9b3-48e8-47a9-a60f-e6510af1960b)

3. (File => Traffic-1) What is the name of the file that was opened? eventLog
	*On the same with previous filtering string, if we carefully look through each packet, you would see that the user have opened a file rightaway.
![nameoffile](https://github.com/user-attachments/assets/dd5d93aa-7e4c-4724-9e50-61625dfc9c2f)

4. (File => Traffic-1) What is the timestamp of the attempt to clear the event log? (24H-UTC) 2020-09-23 16:50:16.731550
	*By default, wireshark uses the time format which counts in a second since the packet first captured. Therefore, we have to change the time format first to achieve what we are looking for. To do this, we can go to View > Time Display Format and then choose for UTC time format.
	*By following the packet info, there is one packet info tells us about clearing eventlog and we just look at the timestamp and submit the answer.
![timestamp](https://github.com/user-attachments/assets/f2f601c7-cb69-4e94-869d-bbb3656ad4f5)

5. (File => Traffic-2) An attacker used a named pipe for communication to blend in and evade detection. What is the name of the service that utilized this pipe for communication? atsvc
	*By looking at the DCERPC protocol, I was hit by one interested protocol called “ISystemActivator” where it tells us a crucial message Remote Create Intance and it spots me to investigate it. By looking at the response, we would see the answer rightaway, but keep looking carefully.
![pipe](https://github.com/user-attachments/assets/ac33fdeb-8334-4ccd-97c4-820bf82543d6)

6. (File => Traffic-2) What was the duration of communication between 172.16.66.1 and 172.16.66.36? 11.7247
	*By navigating to Statistics > Conversations, on the TCP tap, you would see the information which describes the duration of communicating between those IPs.
![duration](https://github.com/user-attachments/assets/807f9219-4633-4135-af0b-bf1dc79c64aa)
 7. (File => Traffic-3) Which username is used to set up requests that may be considered suspicious? backdoor
	*On the third pcap, by looking through the packet info, there is a suspicious session setup requested to set up an username which I definitely sure that it was performed by malicious actor.
![username](https://github.com/user-attachments/assets/5b95423b-d355-45b9-a359-a433f30188ba)

8. (File => Traffic-3) What is the name of the executable file utilized to execute processes remotely? PSEXESVC.exe
	*from File menu > Export Object > SMB the only executable file is ..
![executable](https://github.com/user-attachments/assets/4dbb62ef-6643-4ad9-b7d3-f339abf39838)







