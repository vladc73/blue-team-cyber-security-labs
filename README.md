# PsExec Hunt Lab

## Objective
Investigate network traffic to respond to an IDS alert of suspicious PsExec lateral movement.

### Category: 
Wireshark
### Tactics: 
Tactics:Execution, Defense Evasion, Discovery, Lateral Movement
### Tools: 
Wireshark

### Scenario:
Our Intrusion Detection System (IDS) has raised an alert, indicating suspicious lateral movement activity involving the use of PsExec. To effectively respond to this incident, your role as a SOC Analyst is to analyze the captured network traffic stored in a PCAP file.

### Steps:
1. In order to effectively trace the attacker’s activities within our network, can you determine the IP address of the machine where the attacker initially gained access? 10.0.0.130
	
 *Here after PsExec was successfully written, The attacker immediately used it and .key file also be generated on HR-PC
	
 *PSEXECSVC was also created on\\10.0.0.130\IPC$ which mean the attacker also used this network share beside ADMIN$
![psexecsvcIP](https://github.com/user-attachments/assets/fafebe5b-b2cf-40e0-994c-d8c8d26dea1e)

2. To fully comprehend the extent of the breach, can you determine the machine’s hostname to which the attacker first pivoted? SALES-PC
	
 *I knew that the attacker already used PsExec but I didn’t know where to find the answer but in the end, Follow TCP Stream worked.
 ![targetname](https://github.com/user-attachments/assets/7122a44e-fe12-48c2-8c31-9762f6ef6ca1)

3. After identifying the initial entry point, it’s crucial to understand how far the attacker has moved laterally within our network. Knowing the username of the account the attacker used for authentication will give us insights into the extent of the breach. What is the username utilized by the attacker for authentication? ssales
	
 *On SMB2 packet, I saw that ssales user was the account of this session
![username](https://github.com/user-attachments/assets/a082b775-f7ef-4911-88d0-a8258abb8559)

4. After figuring out how the attacker moved within our network, we need to know what they did on the target machine. What’s the name of the service executable the attacker set up on the target? PSEXESVC.exe
![executable](https://github.com/user-attachments/assets/e8669653-3d06-4212-bcad-e4df05a1ce55)

5. We need to know how the attacker installed the service on the compromised machine to understand the attacker’s lateral movement tactics. This can help identify other affected systems. Which network share was used by PsExec to install the service on the target machine? ADMIN$

![networkshare](https://github.com/user-attachments/assets/56e13657-22c3-45b8-86f0-855c783beeb6)

6. We must identify the network share used to communicate between the two machines. Which network share did PsExec use for communication? IPC$
![communicate](https://github.com/user-attachments/assets/7af6e609-e792-44a9-a7a7-aefda9fd74f6)

7. Now that we have a clearer picture of the attacker’s activities on the compromised machine, it’s important to identify any further lateral movement. What is the machine’s hostname to which the attacker attempted to pivot within our network? SALES-PC or MARKETING-PC
![targetname](https://github.com/user-attachments/assets/30cd38a7-106b-4f4f-a64b-00dbb7b7f57e)
