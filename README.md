# The Crime Lab

## Objective
Uncover the events leading up to a murder by analyzing the victim's phone and witness statments.

### Category: 
Endpoint Forensics

### Tools: 
ALEAPP (Autopsy 4.2.0)

### Scenario:
We're currently in the midst of a murder investigation, and we've obtained the victim's phone as a key piece of evidence. After conducting interviews with witnesses and those in the victim's inner circle, your objective is to meticulously analyze the information we've gathered and diligently trace the evidence to piece together the sequence of events leading up to the incident.

Resources: Android-Forensics-References

### Steps:
1. Based on the accounts of the witnesses and individuals close to the victim, it has become clear that the victim was interested in trading. This has led him to invest all of his money and acquire debt.  Can you identify which trading application the victim primarily used on his phone? Olymp Trade
	
 *In Autopsy, I went to the installed programs and saw that olmptrade was installed

![olymptrade](https://github.com/user-attachments/assets/8d34d577-91fc-4d0b-ab33-a11d12a65d42)

2. According to the testimony of the victim’s best friend, he said, “While we were together, my friend got several calls he avoided. He said he owed the caller a lot of money but couldn’t repay now”.  How much does the victim owe this person? 250,000 EGP
	
 *Under messages, I click on the first and saw that the person owned 250,000 EGP

![owned](https://github.com/user-attachments/assets/cc4813ef-17ab-4d59-a95b-71b0810d8d1e)

3. What is the name of the person to whom the victim owes money? Shady Wahab
	
 *I check the number from the messages, check his contacts, and the number belong to Shady Wahab

 ![shady](https://github.com/user-attachments/assets/24f08b3a-9f85-4c29-a511-ed68098d2a03)

4. Based on the statement from the victim’s family, they said that on September 20, 2023, he departed from his residence without informing anyone of his destination. Where was the victim located at that moment?  The Nile Ritz-Carlton, Cairo
	
 *Let’s find out the recent activity of the victim, under By Extension, Images, and click on Modified Time to look for recent activity.
	
 *In the Google maps image and the blue spot is the victims last location

 ![last activity](https://github.com/user-attachments/assets/36d0e8ef-ac64-4298-92dc-569c8586186b)

5. The detective continued his investigation by questioning the hotel lobby. She informed him that the victim had reserved the room for 10 days and had a flight scheduled thereafter. The investigator believes that the victim may have stored his ticket information on his phone. Look for where the victim intended to travel.
	
 *Under By Extension, Images, and click on plane ticket image.

 ![ticket](https://github.com/user-attachments/assets/c8dc7f9e-58d7-493a-994f-fa6dde6cecc8)

6. After examining the victim’s Discord conversations, we discovered he had arranged to meet a friend at a specific location. Can you determine where this meeting was supposed to occur? The Mob Museum
	
 *Under By Extension, Documents, Plain Text and searched for the discord messages.
 
 ![mob museum](https://github.com/user-attachments/assets/0511b783-71af-4deb-b17f-0746333e8a5b)
