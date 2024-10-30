# Intelligence-Driven Computer Network Defense – Kill Chain – Summary
  * The conventional methods and tools of Intrusion detection systems (IDS) and anti-virus zero in on vulnerabilities.
  *	Malicious users and actors have existed since the inception of the computer network systems. Advancement of anti-virus software meant that propagating malicious code reduced.
  * Advance Persistent Threat (APT) a new class of threat with focus to compromise data for economic gain or military advancement has come into play.
  * Traditional methods fail to respond to APT appropriately because the response is done after the incident has occurred and the compromise centres from a fixable flaw.
  * The kill chain analyses the intrusions and the defensive courses of action at each chain.
  * One mitigation at one chain means a break in the chain and thus thwards the adversary or malicious actors.
  * The indicator is a piece of information that properly describes an intrusion. Three kinds of indicators: atomic, computed and behavioral indicators.
  *	Atomic indicators cannot be broken down further and still retain their meaning.
  *	Computed indicators are those made from data in an incident.
  *	Behavioural indicators are collections of atomic and computed indicators.
  *	These indicators are uncovered through analysis and collaborations by analysts.
  *	The kill chain purpose is to target and engage an adversary with the intention to arrive at a desired effect.
  *	The kill chain consists of 
      * Reconnaissance: gathering data through research, identifitying and selecting a target.
      *	Weaponization: embedding a remote access program through a paylod that is deliverable and contains an exploit point.
      *	Delivery: This involves the transmission of the weapon to the targeted environment.
      *	Exploitation: Once the weapon is delivered to the victim environment, the exploitation triggers the intruders malicious code.
      *	Installation: The actual installation of a remote access trojan or backdoor on the victims environment. Allowing the adversary to have persistent presence inside the trusted environment.
      *	Command and Control (C2): The compromised host or environment now has an established connection to the control servers of the intruders.
      *	Actions and objectives: The intruder now takes the action to achieve their original intent and objectives.
  *	At each level of phase of the kill chain there is an appropriate course of action to thwart the threat. Actions at each phase include the how-to detect, deny, disrupt, degrade, deceive or destroy.
  *	When the attacker is forced to make difficult and comprehensive adjustments to achieve their intent, the defender increases the attackers costs of executing a successful intrusion. This is a proper outcome.
  *	Intrusion reconstructions make the analysis complete that is by analysis of prior phases of what happened, can then actions be taken at those prior phases to mitigate future intrusions.
  *	For the intrusion to be economically viable, the attackers have to re-use tools and infrastructure, so when we have a complete analysis of each phase, we understand grasp and have a proper view of the approach and perspective of the attacker, thus we can mitigate at these levels and force the attacker to change tools and infrastructure thus driving up their costs. An outcome that is desired.
  *	Infact, the thorough analysis of numerous intrusion kill chains will reveal commonalities and overlapping indicators. Thus we are able to uncover the intruders patterns, behaviours, tactics, techniques and procedures. We get to understand how the really operate and not just what they do. We also get to understand the intruder or attackers intent and their mission objectives.
# Comparison of Cyber Kill Chain and ATT&CK Enterprise matrix
The mitre attack enterprise matrix compromises of phases and in those phases are tactics for attacks alongside their techniques. This matrix is exhaustive interms of techniques that can be deployed in each phase. It really offers a comprehensive set of information for each phase. In comparison, the kill chain is a guide for the defenders to know what kind of information is available and the course of action that can be taken in each phase. In my opinion, the two are useful resources that complement each other quite well and should be used together. Users of this tools range from cyber security experts or professionals, security consultants, security forensic firms, security officers, and just anyone who is remotely interested to be security aware. Quite frankly, these resources are extremely interesting. 
# Security Incident
This security incident was described by a Technical lead for the forensic team at Trusec. A security company based in Sweden. In the summer 2016 the Swedish security services a government security agency contacted a major telecommunications organization in Swedne and informed them that one of their systems has been talking to a foreign command and control server. That is a foreign threat actor. The further gave 2 IP addresses of the foreign command and control servers and internal IP host IP address in the organization that has been communicating with the command and control server.
The internal host turned out to be a compromised host jump server belonging to a managed services provider (MSP) that manages the network servers for this telecommunications company. A perfect place to be for as threat actor. The investigation started by taking the Disk image and memory dump of the jump server. Further investigation revealed Malicious DLL was being loaded and this makes connection with the CC servers. 
Further investigation at the MSP revealed that more of their customers had been compromised with the same malware. This was planned and orchestrated such that they could compromise an MSP network, then compromise the jump hosts used by the MSP to access their customers network, install malicious malware for communication with CC, and then finally run scans to check open connections to the United State department of defence. The primary objective to gain access to US government systems and steal data. The cleanup at the telecommunication company was an arduous process which included installing active monitoring and EDR tooling. 
* Concept of threat actor: A foreign state threat actor (suspicion was China). 
* Exploit: User credential theft of a single user at the MSP. malware, anti root kit software
* Vulnerability: use of anti root kit software to execute malicious DLL software, windows storage of clear text passwords in memory
* Business impact: Data theft interms of company secrets and patents., Loss of customers for the MSP company.
## e) Voluntary bonus - fundamentals of security & theoretical foundations 
I think that users’ behaviours and mannerisms do contribute to security incidents. Therefore, user security awareness campaign is an area that must be over emphasized in organizations so that users can be kept alert and aware of such occurrences of security incidents and attempts. For example, sending mock-up email attachments and links that users shouldn’t open can be one form of constant reminder in this user security awareness campaigns. One fundamental of security is to run security awareness campaigns all year round in organizations i.e. from short security web trainings to such email attachment and link mock-ups
## f) Voluntary bonus - Cyber Kill Chain or MITRE ATT&CK
As a first time user of these two models, my position or argument is that these models are extensive in covering the phases. The mitre attack enterprise matrix is exhaustive with techniques and tactics for each phase. The kill chain offers the visibility of mapping the indicators to each phase for analysis. As I mentioned, these two are important and complement each other quite well. Maybe an addition to the model would be a separate phase for forensic analysis and reporting.
# Install Debian on Virtualbox
Installation steps for Debian.
![Step-1](https://github.com/user-attachments/assets/5727e30e-34b2-4641-b03b-cf3265d2d308)
![Step-2](https://github.com/user-attachments/assets/5fdc0d40-574c-49e3-a8fb-2d9c496d379b)
![Step-3](https://github.com/user-attachments/assets/67623bf1-482f-427b-8ce3-9c753b809cdf)
![Step-4](https://github.com/user-attachments/assets/8dbc43b1-1941-4866-a3e8-aff9ea8077bf)
![Step-5](https://github.com/user-attachments/assets/fabd980b-8242-436b-8143-ab6372c898b4)
![Step-6](https://github.com/user-attachments/assets/28cade55-a540-493e-b13f-4fbc2eb99eb8)
![Step-7](https://github.com/user-attachments/assets/a77605fc-b51c-42be-aa0f-4a7a435ebdfc)
![Step-8](https://github.com/user-attachments/assets/272d6451-04d4-4de3-a925-320f05cbb464)
![Step-9](https://github.com/user-attachments/assets/48b2c432-0185-4e3e-8650-1aa077aa7e1f)
![Step-10](https://github.com/user-attachments/assets/ba1a4877-702a-4600-9c38-612783ca5bcc)
![Step-11](https://github.com/user-attachments/assets/58620e8a-e55b-4de2-bbbf-ee320734069a)
![Step-12](https://github.com/user-attachments/assets/a87c9c44-a4f3-4c01-a67f-084a6ff4122b)
![Step-13](https://github.com/user-attachments/assets/81701b43-af09-4944-ac61-437c5c90abd2)
![Step-14](https://github.com/user-attachments/assets/a6d99500-0007-4cba-936f-a5bcb8d6bac8)
![Step-15](https://github.com/user-attachments/assets/09f9bc57-4725-44c1-a18b-90fe3bbadfa1)
![Step-16](https://github.com/user-attachments/assets/2629fae6-0773-46e9-9b71-3294ad967161)

## References
Eric M. Hutchins∗ , Michael J. Cloppert† , Rohan M. Amin, Ph.D. January 2011. Lockheed Martin Corporation. Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains.

Darknet Diaries 26 October 2021. EP 103: Cloud Hopper. Darknet Diaries podcast. URL: https://darknetdiaries.com/episode/103/. Accessed: 29 October 2024. 

MITRE ATT&CK 2024. Enterprise Matrix. URL: https://attack.mitre.org/matrices/enterprise/. Accessed 29 October 2024.
