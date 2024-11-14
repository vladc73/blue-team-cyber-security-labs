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
3. In which language was the kit written? php
	
 *The metamask.php file is written in PHP language.

4. What service does the kit used to retrieve the victim’s machine information? Sypex Geo
	
 *After opening the file metamask.php, we can see that request is being made to “http://api.sypexgeo.net/json/" server to get the victim’s geo, city, and date.
	
 *The service that the kit used to retrieve the victim’s machine information is Spypex Geo.
![inside-metamask-file](https://github.com/user-attachments/assets/f63436fe-e124-428f-a623-bd6993649c0e)
5. How many seed phrases were already collected? 3
	
 *Metamask > metamask.php
	
 *Inside metamask.php file, this 2 lines of code takes user-submitted data from a form and appends it to a log file called “log.txt” in the “/log/” directory.
	
 *From this, we know that the log folder has seed phrases.
	
 *Step 4: Inside the folder log, we have 3 files.
		a) .DS_Store
		b) .htaccess
		c) log.txt
	
 *Inside the file log.txt, we have 3 phrases.
![inside-log-file](https://github.com/user-attachments/assets/45ff6b96-c2ad-48c4-81e0-78213cf2ed82)
6. Write down the seed phrase of the most recent phishing incident? father also recycle embody balance concert mechanic believe owner pair muffin hockey
	
 *First of all go through the folders. Inside the log folder, there we can see the log.txt file. There we can see the 3 phases.
	
 *The seed phrase of the most recent phishing incident is “father also recycle embody balance concert mechanic believe owner pair muffin hockey”.
 ![inside-log-file](https://github.com/user-attachments/assets/ab194732-3a90-4785-b9d9-e9000f7db3f0)
7. Which medium had been used for credential dumping? Telegram
	
 *Inside the metamask.php file, we can see that Telegram Bot API is used to send a message, including the access token, chat ID, message text, and parse mode for HTML formatting.
	
 *The medium that has been used for credential dumping is Telegram.
 ![telegram](https://github.com/user-attachments/assets/8d615522-62cb-4702-96f0-c76a2c49fd27)
8. What is the token for the channel? 5457463144:AAG8t4k7e2ew3tTi0IBShcWbSia0Irvxm10
	
 *Inside the metamask.php file, the $token variable is stated.
	
 *The token for the channel is “5457463144:AAG8t4k7e2ew3tTi0IBShcWbSia0Irvxm10”.
 ![token](https://github.com/user-attachments/assets/d4db734d-77dc-4496-8ac0-ecacc1954122)
9. What is the chat ID of the phisher’s channel? 5442785564
	
 *Inside the metamask.php file, the $id variable is stated
	
 *The chat ID of the phisher’s channel is “5442785564”.
 ![chatid](https://github.com/user-attachments/assets/b1427a00-258a-489c-84f2-2a260b5b02a3)
10. What are the allies of the phish kit developer? j1j1b1s@m3r0
	
 *Inside the metamask.php file, a username is stated while greeting.
	
 *The allies of the phish kit developer is “j1j1b1s@m3r0”
 ![allies](https://github.com/user-attachments/assets/6e36a403-a379-4be3-a320-36caa0ef183b)
11. What is the full name of the Phish Actor? Marcus Aurelius
	
 *Inside the metamask.php file, by executing a GET request on the URL“https://api.telegram.org/bot5457463144:AAG8t4k7e2ew3tTi0IBShcWbSia0Irvxm10/getChat?chat_id=  5442785564" using the provided token and chat ID, we receive a specific result from the Telegram Bot API. The exact content and details of the obtained result cannot be determined without the actual response.
	
 *The full name of the Phish Actor is Marcus Aurelius.
 ![q11-12](https://github.com/user-attachments/assets/026b6910-00d9-474e-a277-1b5c9af3768a)
12. What is the username of the Phish Actor? pumpkinboii
	
 *By executing a GET request on the URL “https://api.telegram.org/bot5457463144:AAG8t4k7e2ew3tTi0IBShcWbSia0Irvxm10/getChat?chat_id=5442785564" using the provided token and chat ID, we receive a specific result from the Telegram Bot API.
	
 *The username of the Phish Actor is pumpkinboii
 ![q11-12](https://github.com/user-attachments/assets/7f374bbe-7edc-4b6b-8322-78a443552596)
