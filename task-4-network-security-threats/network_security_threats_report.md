**Common Network Security Threats**



**Oasis Infobyte Cybersecurity Internship**



**Name:** Letlhogonolo Molokwane  

**Task:** Research Report on Common Network Security Threats  

**Date:** July 2026



**Introduction**



Computer networks allow people and organisations to communicate, share information and access online services. Businesses depend on networks for activities such as sending emails, processing payments, storing customer information and communicating with employees. This makes network security important because a successful attack can interrupt business operations or expose sensitive information.



A network security threat is anything that can affect the confidentiality, integrity or availability of information and services. Confidentiality means that information is only seen by authorised people. Integrity means that information remains correct and is not changed without permission. Availability means that authorised users can access a service when they need it.



In this report, I discuss three common network security threats: Denial-of-Service attacks, Man-in-the-Middle attacks and spoofing. I explain how these attacks work, their possible impact and the measures that organisations can use to reduce the risk.



**1. Denial-of-Service attacks**



**What is a Denial-of-Service attack?**



A Denial-of-Service attack, also known as a DoS attack, is an attempt to make a computer system, website or network service unavailable to legitimate users.



According to the National Institute of Standards and Technology, a DoS attack prevents authorised access to a resource or delays important system operations. This means that the main purpose of the attack is to affect availability rather than directly steal information.



A Distributed Denial-of-Service attack, known as a DDoS attack, has the same goal. The difference is that a DDoS attack uses many devices or systems to send traffic to the target at the same time.



**How does it work?**



A web server and network connection can only handle a certain amount of traffic. During a DoS attack, the attacker sends more requests than the target can process. This may cause the system to become extremely slow, stop responding or crash.



In a DDoS attack, the traffic comes from many sources. Attackers often use a botnet, which is a group of compromised computers or Internet of Things devices controlled without the owners' knowledge. Because the traffic comes from many different addresses, it can be more difficult to block than traffic coming from one system.



**The Cybersecurity and Infrastructure Security Agency separates DDoS techniques into three broad groups:**



**1. Volumetric attacks:** These attempt to use all the available network bandwidth by sending a very large amount of traffic.

**2. Protocol attacks:** These target weaknesses in network protocols or use up resources on devices such as firewalls and servers.

**3. Application-layer attacks:** These target a particular application or service, such as repeatedly requesting pages from a website.



**Possible impact**



**A DoS or DDoS attack may cause:**



\- A website or application to become unavailable

\- Loss of sales while customers cannot use the service

\- Reduced employee productivity

\- Additional recovery and security costs

\- Customer complaints

\- Damage to the organisation's reputation

\- Loss of trust from customers and business partners



The attack may not directly steal information, but the interruption can still be expensive. It can also distract security teams while another attack is taking place.



**Real-world example:** Mirai and Dyn



A well-known DDoS incident happened on 21 October 2016. A Mirai-related botnet used compromised Internet of Things devices to carry out DDoS attacks that affected Dyn, a company that provided Domain Name System services.



The disruption caused several websites and online services to become unavailable or only work occasionally for several hours. The affected services included websites connected to companies such as Twitter, Amazon, PayPal and Netflix.



This case showed that devices such as internet-connected cameras and recorders can become part of a botnet when they are not properly secured. It also showed how an attack against one important service provider can affect many other organisations.



**Prevention and mitigation**



**Organisations can reduce the risk and effect of DoS and DDoS attacks by:**



\- Monitoring network traffic for unusual increases

\- Using firewalls and intrusion-prevention systems

\- Applying rate limits to control repeated requests

\- Using DDoS protection and traffic-filtering services

\- Distributing services across different servers and locations

\- Maintaining backup systems

\- Creating an incident-response plan

\- Working with internet service providers during large attacks

\- Keeping servers and network devices updated

\- Securing Internet of Things devices and changing default passwords



It may not always be possible to stop every packet sent during a large DDoS attack. The goal is to detect the attack early, filter harmful traffic and keep important services available.



**2. Man-in-the-Middle attacks**



**What is a Man-in-the-Middle attack?**



A Man-in-the-Middle attack, usually shortened to MITM, happens when an attacker secretly positions themselves between two parties that are communicating.



For example, a user may believe that they are communicating directly with a website. However, the attacker may be receiving the communication first and then forwarding it to the website. If the attack succeeds, the attacker could observe or change information travelling between the user and the service.



NIST describes MITM as an attack where someone is positioned between two communicating parties to intercept or alter the data travelling between them.



**How does it work?**



A MITM attack can happen when communication is not properly encrypted or when a user connects through an untrusted network. The attacker attempts to make both sides believe they are communicating directly with each other.



**Some methods connected to MITM attacks include:**



\- Creating a fake Wi-Fi access point

\- Redirecting network traffic

\- ARP spoofing on a local network

\- DNS manipulation

\- Stealing or misusing digital certificates

\- Taking control of an active user session



A successful attack may allow the attacker to see login information, payment information, private messages or other sensitive data. In some cases, information may also be changed before it reaches the intended recipient.



**Possible impact**



**A MITM attack may result in:**



\- Theft of usernames and passwords

\- Exposure of confidential information

\- Unauthorised access to accounts

\- Changes to data while it is being transmitted

\- Financial fraud

\- Loss of customer trust

\- Legal and regulatory consequences

\- Damage to the organisation's reputation



This type of attack is dangerous because the victim may not immediately notice that someone has interfered with the communication.



**Real-world example:** DigiNotar



DigiNotar was a company that issued digital certificates used to confirm the identity of websites. In 2011, the company was compromised and false certificates were created.



A report from the European Union Agency for Cybersecurity stated that false certificates connected to the incident appeared to have been used in a large-scale MITM attack against users in Iran.



Digital certificates are important because they help browsers verify that a user is communicating with the correct website. A false certificate can make a harmful connection appear trustworthy. The DigiNotar incident demonstrated the serious effect that a compromised certificate authority can have on internet security.



**Prevention and mitigation**



**Individuals and organisations can reduce the risk of MITM attacks by:**



\- Using HTTPS for websites and online services

\- Checking browser certificate warnings instead of ignoring them

\- Encrypting sensitive network communication

\- Avoiding sensitive transactions over unsecured public Wi-Fi

\- Using a trusted Virtual Private Network when appropriate

\- Using multi-factor authentication

\- Keeping browsers, operating systems and network devices updated

\- Using secure Wi-Fi encryption

\- Monitoring networks for unexpected ARP or DNS changes

\- Ending inactive user sessions

\- Training users to recognise suspicious login pages and certificate warnings



HTTPS is especially important because it encrypts information travelling between the browser and the website. It also allows the browser to check the website's digital certificate.



**3. Spoofing attacks**



**What is spoofing?**



Spoofing happens when an attacker pretends to be a trusted device, person or service. The attacker changes identifying information so that a communication appears to come from a legitimate source.



The word spoofing describes several related attacks. The exact method depends on what the attacker is pretending to be.



**Common types of spoofing**



**IP address spoofing**



Every device communicating over an IP network uses an IP address. In IP spoofing, an attacker changes the source address in a network packet so that the traffic appears to come from a different system.



IP spoofing is sometimes used in reflection and amplification DDoS attacks. The attacker places the victim's address in the source field of a request. Other servers then send their responses to the victim instead of the attacker.



**Email spoofing**



In email spoofing, an attacker makes an email appear to come from a trusted person or organisation. The message might look as if it was sent by a manager, bank, supplier or colleague.



The attacker may ask the recipient to open a harmful link, provide account details or make an urgent payment. The displayed sender information can look convincing even though the message did not come from the real sender.



**DNS spoofing**



The Domain Name System translates website names into IP addresses. During DNS spoofing, false DNS information may direct a user to the wrong system.



The harmful website may look similar to the real one. If the user does not notice the difference, they may enter private information into the fake website.



**ARP spoofing**



The Address Resolution Protocol helps devices on a local network connect IP addresses to physical network addresses. During ARP spoofing, an attacker sends false ARP information to devices on the network.



This may allow network traffic to pass through the attacker's system. ARP spoofing can therefore be used as part of a MITM attack.



**Possible impact**



**Spoofing attacks may cause:**



\- Theft of login details

\- Fraudulent payments

\- Redirection to fake websites

\- Unauthorised network access

\- Exposure of confidential information

\- Distribution of malware

\- Interruption of network communication

\- Damage to an organisation's reputation



Spoofing is effective because people and computer systems often make decisions based on the identity of the sender. If that identity is false, the victim may trust a harmful message or connection.



**Real-world impact:** Business Email Compromise



Business Email Compromise, or BEC, is a form of fraud where criminals impersonate or take control of trusted business email accounts. They may then ask employees or customers to transfer money or change payment details.



Not every BEC incident uses email spoofing. Some attackers compromise a real email account instead. However, these incidents demonstrate the financial danger of messages that appear to come from trusted business contacts.



The FBI's Internet Crime Complaint Center reported more than $55 billion in exposed losses connected with reported BEC incidents between October 2013 and December 2023. These incidents affected organisations of different sizes and were reported across many countries.



**Prevention and mitigation**



**Organisations can reduce spoofing risks by:**



\- Using SPF, DKIM and DMARC to protect email domains

\- Using DNSSEC to protect DNS information

\- Applying network filtering to reject packets with invalid source addresses

\- Using secure network switches and ARP inspection where available

\- Confirming unusual payment requests through another communication method

\- Training employees to inspect email addresses carefully

\- Using multi-factor authentication

\- Monitoring for unusual account activity

\- Keeping systems and network devices updated

\- Reporting suspicious messages

\- Using strong passwords and protecting email accounts



For example, an employee who receives an urgent request to change banking details should confirm it using a known telephone number instead of replying directly to the email.



**4. Comparison of the threats**



|**Threat**|**Main target**|**Main purpose**|**Common effect**|**Useful protection**|
|-|-|-|-|-|
|DoS or DDoS|Website, server or network service|Make a service unavailable|Downtime and loss of access|Traffic monitoring, rate limiting and DDoS protection|
|MITM|Communication between two parties|Intercept or change information|Data exposure and account compromise|HTTPS, encryption, secure Wi-Fi and certificate checking|
|Spoofing|Identity information in communication|Pretend to be a trusted source|Fraud, redirection or unauthorised access|Email authentication, DNSSEC, filtering and verification|



These attacks are different, but they can also be used together. For example, IP spoofing can be used during a DDoS attack, while ARP or DNS spoofing may help an attacker carry out a MITM attack.



**5. General network security measures**



Organisations should not depend on only one security control. A stronger approach uses several protective measures together.



**Important measures include:**



1\. Regular updates: Security updates should be applied to operating systems, applications, routers and other network devices.

2\. Firewalls: Firewall rules should only allow network traffic that is required.

3\. Encryption: Sensitive information should be encrypted while stored and while moving across a network.

4\. Multi-factor authentication: A stolen password should not be enough to access an important account.

5\. Network monitoring: Unusual traffic and account activity should be investigated.

6\. Backups: Important information should be backed up and tested regularly.

7\. User awareness: Employees should be trained to recognise suspicious emails, links and payment requests.

8\. Access control: Users should only receive the permissions required for their work.

9\. Incident response: Organisations should have a clear plan for reporting, containing and recovering from an attack.

10\. Regular assessments: Authorised security scans and reviews can identify unnecessary services and weak configurations.



Technology is important, but employees also play a major role in network security. A well-designed security system can still be affected if a user trusts a false message or ignores a security warning.



**Conclusion**



This research helped me understand that network attacks can affect systems in different ways. A DoS or DDoS attack mainly affects availability by preventing legitimate users from accessing a service. A MITM attack targets communication and may allow information to be observed or changed. Spoofing focuses on false identity information and can make harmful communication appear trustworthy.



The Mirai, DigiNotar and Business Email Compromise examples show that these threats can have serious real-world effects. They can interrupt popular online services, expose private communication and cause large financial losses.



There is no single security measure that can stop every network threat. Organisations need a combination of secure configurations, updates, encryption, monitoring, access controls and employee awareness. They also need a response plan so that they can act quickly when an incident takes place.



**References**



1\. National Institute of Standards and Technology. "Denial of Service." 

&#x20;  https://csrc.nist.gov/glossary/term/denial\_of\_service



2\. National Institute of Standards and Technology. "Distributed Denial of Service."  

&#x20;  https://csrc.nist.gov/glossary/term/distributed\_denial\_of\_service



3\. Cybersecurity and Infrastructure Security Agency. "Understanding and Responding to Distributed Denial-of-Service Attacks." 

&#x20;  https://www.cisa.gov/resources-tools/resources/understanding-and-responding-distributed-denial-service-attacks



4\. United States Department of Justice. "Individual Pleads Guilty to Participating in Internet-of-Things Cyberattack in 2016." 

&#x20;  https://www.justice.gov/archives/opa/pr/individual-pleads-guilty-participating-internet-things-cyberattack-2016



5\. National Institute of Standards and Technology. "Man-in-the-Middle Attack."  

&#x20;  https://csrc.nist.gov/glossary/term/man\_in\_the\_middle\_attack



6\. European Union Agency for Cybersecurity. "Operation Black Tulip: Certificate Authorities Lose Authorities."  

&#x20;  https://www.enisa.europa.eu/sites/default/files/all\_files/Operation\_Black\_Tulip\_v2.pdf



7\. National Institute of Standards and Technology. "Trustworthy Email." 

&#x20;  https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-177.pdf



8\. National Institute of Standards and Technology. "Advanced DDoS Mitigation Techniques."  

&#x20;  https://www.nist.gov/programs-projects/advanced-ddos-mitigation-techniques



9\. National Institute of Standards and Technology. "Secure Domain Name System Deployment Guide."  

&#x20;  https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-81r3.pdf



10\. Federal Bureau of Investigation Internet Crime Complaint Center. "Business Email Compromise: The $55 Billion Scam."  

&#x20;   https://www.ic3.gov/PSA/2024/PSA240911

