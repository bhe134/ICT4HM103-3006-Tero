## Introduction
HelSec is a community founded in 2018 for cybersecurity meetups. It is a non-profit for like minded cybersecurity individuals and the community meetups mostly in Helsinki and Espoo.

## Topic: Industrial Cyber Security
Speaker: Jos Helmich

* The background of the presenter is he has worked as a software developer for the brake monitoring unit, remote operating station, electronic crane unit in          Konecranes. He is currently a product security architect in Konecranes.
* The speaker is also a member of the ENISA advisory group.
* The General EU laws & directives  include GDPR, NIS 2, CRA, AIA (Artificial Intellgence Act)
* The US legislative  is predominantly an executive order from the acting president that can be retracted by a future president.
* Suppliers to the US government MUST fullfill a CISA attestation forms for their products.
* Manufacturing or industrial has also office cloud applications for Finance, HRM, travel etc.
* Manufacturing or industrial also has the cloud applications that the industrials sell to their customers. 
* The network diagram below shows the consideration points on how to implement the connection for the industrial cloud applications i.e. should the connection go     via the firewall of the office network, the DMZ or via the industrial zone? This needs careful considerations interms of security.

![image](https://github.com/user-attachments/assets/224eef8a-5ea3-42d2-a0d4-a39c649c1126)

* NIS-2 is about keeping your house in order while the CRA is done so that the products that are sold do not mess up someone else house.
* The NIS-2 has supply chain consequences e.g. questions to suppliers such as what is your minimum password length, are you cyber secure?. CRA has also supply        chain consequences.
* The 62443 family provides good advice or guidance for the industrial cybersecurity. Topics such as secure software development, the system requirement and the      component requirements.
* The security levels in 62443 family include the accidental tourist, normal users, hackers and nations state.
* AIA – EU legislation – new AI legislative framework that has a modular approach in covering the product safety, data requirements topics of GDPR and the cyber      resilience act.
* According to the current status, there is no clear directive process to enforce the NIS-2 or CRA to organisations.

## Topic: State of Union
Speaker: Heikki Juva

* The regulation includes RED (radio equipment directive) and CRA.
* RED (Radio equipment directive in 3 parts such as network security, financial etc
* CRA covers the technical security aspects and the vulnerability handling or reporting.
* The diagram below shows the timeline for RED and CRA. As can be seen the RED standard work started in 2022 in Traficom while the CRA standard started in Q2 2024. 
  The RED is to be enforced in 01/2025:

![image](https://github.com/user-attachments/assets/e7d44f7c-1f30-4271-a6d7-af6a6ecb905c)

* Therefore, RED is a practical framework for radio products devices.
* The device classification include topics such as: is the device connected to the internet (If the device is connected then the RED part 1 applies), Does the 
  device contain or process any personal information (If it does then the RED part 2 applies), and lastly does the device process any monetary transactions or 
  money (If so, then RED part 3 is applicable).
* The problematic requirements include topics of compatibility, outsourcing security (for example, external devices ensure the radio product security), reliance on 
  solely paper-based evaluation i.e. not evaluating the radio device itself.
* A practical example discussed in the presentation is a company named eagle. This company makes IP cameras devices for child movement or audio, and it also makes 
  devices or products for the purpose of health monitoring (e.g. measuring the heart rate). These products or devices are connected to the internet. These devices 
  do not process any monetary transactions and are thus classified as RED part 1 and 2 applicable.
* A few example topics that can be covered to evaluate the RED part 1 applicability for radio devices include: are software updates are enforced? Is the device 
  storage secure? are there exploitable vulnerabilities (running a CVE check)? are the passwords good? 
* In addition, other example topics that can covered how to evaluate the device for RED part 2 include: does the radio product affect the user privacy? e.g. taking 
  videos, pictures, audio etc. Is personal information gathered and shared with third parties e.g. cloud systems?
* It is extremely important to read carefully the legal text for the terms and conditions of the radio devices or product.
* For example, in the legal text, is there a provision for the right to be forgotten? For example, how to delete the device information from the cloud? What about 
  your personal data? What about the device internal information if it is wiped? are the IP addresses or passwords still stored in the device upon cleanup or reset?
* The statistics revealed the following for the 10 best selling health products: the largest amount of data usually within the EU, 90% of these products use TLS 
  and cert pinning, 80% are implemented on baremetal (there is no OS), 66% use wifi communication, 90% online temporarily.
* The most common issues uncovered with these products include: data is not completely removed (cleanup of one device revealed user data such as wifi SSID, wifi ip 
  address etc), these devices also share private or personal information with 3rd parties, the products have complex manufacturing such as outsourcing of R&D 
  activities etc.
* During the testing, the speaker wanted to find the actual manufacture of the device. Hence, dumping the firmware revealed you could get original manufacturers, 
  supply chain information, and digging deeper with information from the dump one could track the name of Head of R&D, financials details of the company etc.
* It is expensive to implement more secure means to such radio products, such as secure boot on these kinds of devices.

## References
https://www.twitch.tv/helsec, Meetup 2024-11-21

https://helsec.fi/events/2024-11-21_helsec_november_2024_meetup/
 
