# Grab The Phisher Lab

## Objective
Analyze a phishing kit mimicking a crypto exchange and uncover the malicious actors behind it.

### Category: 
Threat Intel
### Tactics: 
Initial Access, Discovery, Exfiltration

### Scenario:
An attacker compromised a server and impersonated https://pancakeswap.finance/, a decentralized exchange native to BNB Chain, to host a phishing kit at https://apankewk.soup.xyz/mainpage.php. The attacker set it as an open directory with the file name "pankewk.zip". 

Provided the phishing kit, you as a soc analyst are requested to analyze it and do your threat intel homework.
![inside-pankewk](https://github.com/user-attachments/assets/0227d507-2242-4595-971f-fab1d66cb432)


### Steps:
1. Which wallet is used for asking the seed phrase? metamask
	
 *After unzipping the file, we have a folder named pankewk. Inside the folder Pankewk, we can see a folder named metamask folder.
	
 *The wallet that is used for asking the seed phrase is metamask.
 ![inside-pankewk](https://github.com/user-attachments/assets/c4b1eb58-3857-4dbb-8f50-883e1c3b023a)
2. What is the file name that has the code for the phishing kit? metamask.php
	
 *Step 1: Inside the metamask folder, we have three files:
		a) .DS_Store
		b) index.html
		c) metamask.php
	
*The file name that has the code for the phishing kit is metamask.php.
 ![inside-metamask-folder](https://github.com/user-attachments/assets/747302fe-096f-452c-8dae-998523d2f5e4)

