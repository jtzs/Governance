# IT Security

The goal of this document it to capture at a very high level broad security concepts that people should be aware when considering management of IT departments and IT Infrastructure.

## Contents
1. [Introduction](#What-is-cyber-security)
2. [Data Management](#data-management)
3. [Personal Data Protection Act (PDPA)](#personal-data-protection-act)
4. [Scams, Social Engineering and Phishing](#scams-social-engineering-and-phishing)
5. [Malware](#malware)
6. [Accounts & Passwords](#accounts--passwords)
7. [Physical cyber security](#physical-cyber-security)
8. [Application security](#application-security)
9. [Server security](#server-security)
10. [Supply Chain Risk management](#supply-chain-risk-management)
11. [Email security](#email-security)
12. [Misinformation/ Disinformation](#misinformation-disinformation)
13. [Risk Management](#risk-management)

## What is cyber security
The goal of Cyber security is the protection of an Organisation's IT assets. There are many threats to an organisation's IT assets, and attackers often do not need a reason to cause damage to an organisation's IT assets. Even the most well prepared organisations, multi-billion companies and first-world governments have difficulties when facing advanced persistent threats that specifically target them. The goal of cyber security is to deter the majority of attackers from causing damage to IT assets, minimising impact when there is damage and reducing downtime with a fast recovery.

A free resource for learning about cyber security is [IBM Skills build](https://skillsbuild.org/adult-learners/explore-learning/cybersecurity-analyst)

### Primary Security Concepts (CIA, AAA Triads)

| Term | Definition |
| ---- | ---------- |
| Confidentiality | The concept that information should only be revealed to those which you intend to reveal it to. <br/> i.e. Public information should be public and private information should remain private. |
| Integrity       | The concept that information shown should be consistent and accurate. <br/> i.e. Information should be correct and not changed unintentionally. |
| Availability    | The concept that information should be accessible when required. <br/> i.e. Information should be available when required. |
| Authentication  | The concept that information should only be revealed or actions allowed after a person's identity has been verified through one or more methods. <br/> E.g. Username and Password, Time-based one-time password (TOTP) |
| Authorization   | The concept that information should only be revealed or actions allowed for people with sufficient or correct rights or entitlements. <br/> E.g. Only Managers should be allowed to approve leave request, Auditors should not be allowed to change information. |
| Auditability (Non-Repudiation) | The concept that any action should be recorded and logged as evidence. <br/>  | 

## Data Management

The purpose of proper data management is to ensure organisational knowledge is protected and maintained to ensure it's availability and continuity. The main areas for consideration here are typically data storage and backup and data recovery. The data management strategy chosen should always depend on the data and value of the data that is being stored. Next consider any applicable regulations that might apply to the data PDPA, GDPR or HIPPA are just some examples of regulations that might apply to data that you store and will need to comply to. The Data management strategy should always depend on the data being protected, it does not make sense to spend millions protecting data that is only worth thousands and vice versa. 

### Data storage and backup

One of the most common maxims for data storage and backup is the 3-2-1 rule. 3 copies of the data in 2 locations and 1 off-site. This usually comes in the form of the original data, and 2 copies of backup. One backup would be a 'hot' backup (e.g. Network Attached Storage, cloud attached storage), which would be accessible at all times, and a 'cold' backup that can typically take ~1 hour to access (e.g. Hard Drives, Tape, AWS, Azure). This also meets the requirements for off-site storage as well.

This is a good rule of thumb but can generally be costly. A more cost effective option would be to use a cloud storage service with further snapshots of the data taken at regular intervals as required. These snapshots can be further encrypted for added protection.

Backups and by extension snapshots taken should always be stored with the same or more protection as the original data itself. Cloud service providers typically provide encryption services with key rotation for backups that can be utilised.

### Data recovery

Data recovery is a critical part of data management. it is too late when trying to recover important data only to realise that the backups are corrupted or not properly included in the backup strategy. As such it is important to include regular data restoration exercises to ensure the viability of the backups and to ensure that key data is not missed out.

The general recommended practice is to carry out data restoration exercises at least once a year.

## Personal Data Protection Act

Definition from Singapore PDPA Website: 
- Personal data refers to data about an individual who can be identified from that data, or from that data and other information to which the organisation has or is likely to have access.
- The Personal Data Protection Act (PDPA) provides a baseline standard of protection for personal data in Singapore.

It is important to note that while individual pieces of data may not constitute Personal Identifiable Data (PII) it is sometimes trivial to bring them together to form PII data. e.g. Names when combined with previous schools and date of birth is usually more than enough to identify a person.

[Data Protection Obligations under the PDPA](https://www.pdpc.gov.sg/-/media/files/pdpc/pdf-files/resource-for-organisation/data-protection-obligations-under-the-pdpa.pdf):
- Collection of Personal Data
  - Notification
  - Consent
  - Purpose Limitation
- Care of Personal Data
  - Accuracy
  - Protection
  - Retention Limitation
  - Transfer Limitation
- Individual's Autonomy over Personal Data
  - Access and Correction
  - Data Breach Notification
  - Data Portability 

[Key Reference](https://www.pdpc.gov.sg/overview-of-pdpa/the-legislation/personal-data-protection-act)

## Scams, Social Engineering and Phishing

Scams are a deceptive technique with the goal of tricking someone into providing information or funds to the scammer. Scams are typically identified by the use of generic greeting followed by a generic urgent request for information or funds. It can come many different forms including emails, SMS, letters and other messaging services. Social Engineering is a technique where attackers use social skills and psychological manipulation to trick people or [organisations](https://www.youtube.com/watch?v=lc7scxvKQOo) into revealing sensitive information.

Phishing is a specific form of social engineering where attackers deceive people into revealing sensitive information or installing malware by pretending to be from a trusted entity e.g. Governments or Banks. General phishing can be relatively easier to detect but can also make users think they are safe, susceptible to more advanced forms of phishing.  

Spear or Whale phishing is a more dangerous targetted form of phishing where the attacker will first carry out advanced reconnaissance of the target's background and existing relations. Spear phishing is usually towards specific executives for their corporate knowledge or entitlements while whale phishing is more specific towards High valued targets. The phishing will usually include specific references to the target's background or relations to make it more realistic. E.g. School Alumni, Banking or other Financial institutions.

One concerning trend with the creation of deepfake and the rise of easily accessible AI is to use a combination of these capabilities to accurately create [videos of people](https://www.channelnewsasia.com/singapore/deepfake-video-pm-lee-investment-scam-4012946) that have a relationship with the target. These can even come in the form of [video calls or conference calls](https://edition.cnn.com/2024/02/04/asia/deepfake-cfo-scam-hong-kong-intl-hnk/index.html) and used to trick the target into giving information or transferring funds to the attacker.

## Malware

Malware is a combination of the words malicious and software and defines a wide range of software that can be used to attack an organization. The earliest malware started in the form of spambots and viruses which primarily served to spread and spam other users on the network or to cause the device to be difficult to use.

- Keyloggers are a type of malware that can record keystrokes and send them to the attacker.
- Rootkits are a type of malware that would allow attackers to gain access to systems without the knowledge of the system owner.
- Ransomware is a type of malware that encrypts files and demands payment to decrypt or to prevent the system release of sensitive information on the public internet.
- Bots are a type of malware that are used by attackers for various purposes, including spamming, phishing, and other malicious activities.
- Spyware is a type of malware that collects information about users' online activity without their knowledge or consent, often used in blackmail or extortion purposes.
- Miners are a specific type of bot that utilise system resources to mine cryptocurrency for attackers.

Modern malware however can be much more dangerous, they typically use a combination of techniques to breach and fully exploit system. One of the most prominent malware attacks in recent times is [stuxnet](https://en.wikipedia.org/wiki/Stuxnet) in which an Iranian Nuclear Reactor with an isolated network was attacked for over a period of many months. Modern malware can be deployed using a variety of methods including clicking links, opening attachments and running scripts.

Modern Anti-Malware software is quite capable of facing most threats and do not have to be expensive. [Microsoft Defender](https://en.wikipedia.org/wiki/Microsoft_Defender_Antivirus) is a free solution that comes with Windows that should be able to meet most users needs. But even the most powerful anti-malware software will be ineffective with users that are unaware of the potential threats and does not keep their system up to date. When interacting with people do confirm their identity through multiple means if possible before revealing sensitive information as attackers are even [posing as anti-scam police](https://www.police.gov.sg/media-room/news/20241120_police_advisory_on_scam_involving_the_impersonation_of_the_anti_scam_centre)

## Accounts & Passwords

Passwords have an ancient history dating back to beyond the roman empire with the caesar cipher. As important as passwords are it is still unfortunately common for weak passwords to be chosen, reused in multiple places and left exposed for in public. The typical standard for Passwords and identity management is from [United States National Institute of Standards and Technology (NIST)](https://pages.nist.gov/800-63-3/sp800-63b.html). Shorter complex passwords with regular rotation is no longer recommended in the latest update in favour of longer, more secure passwords as summarised in [NIST Password Updates](https://blog.1password.com/nist-password-guidelines-update/). Finally Passwords should not be shared with anyone, if users are required to login to assist with supporting cases or other troubleshooting issues, the password should be changed once the issue is resolved.

### Account Management

Accounts should be tied to individual users as far as possible and [Multi Factor Authentication](https://en.wikipedia.org/wiki/Multi-factor_authentication) enabled where possible. 

Factors of authentication typically come in 3 categories:
- Something the user knows (e.g. Passwords, [Passphrase](https://en.wikipedia.org/wiki/Passphrase))
- Something the user has (e.g. Security Token, Digital certificate)
- Something the user is (e.g Fingerprint, Iris scanner, Facial recognition)

When an account is no longer required, the administrator should remove the account as soon as possible to prevent dormant accounts being an avenue of attack.

If sharing accounts is required, it is recommended to use a password manager to facilitate the sharing (e.g. [Google Password Manager](https://passwords.google.com/), [1Password](https://1password.com/)), use a complex password of more than 20 characters and not allow the password to be revealed to users.

### Secure Passwords

Do see the following recommendations for secure passwords.
1. At least 10 Characters long
2. Contain a mix of uppercase, lower case Characters, numbers and special characters
3. As far as possible [passphrases](https://en.wikipedia.org/wiki/Passphrase) should be used e.g. 3LongRedCars!, 5BlackCrowsOutside?, Romans12:1Therefore
4. Password complexity can be checked using online tools [CSA Password Checker](https://ihp.csa.gov.sg/password-checker) [HaveIBeenPwned](https://haveibeenpwned.com/Passwords). These should only be used as an estimate of what a secure password should be.

## Physical cyber security

The physical security of digital devices is often overlooked and many people underestimate the potential damage that can be caused by stolen devices or even USB ports that are left unsecured and unattended in public spaces. From [USB Killers](https://en.wikipedia.org/wiki/USB_killer) that are able to destroy devices upon plugged in to [USB Rubber Ducky](https://www.sciencedirect.com/science/article/pii/S2666281721000986) that deploys a host of malware when plugged in are just some examples of the damages that can be caused by unsecured devices. In addition, once stolen devices should be assumed to be breached and measures taken against any data that is stored on them, such as changing of passwords and remotely logging out of accounts.

Physical Cyber Security extends beyond computers and mobile phones, in an increasingly digital world the number of potential vectors for cyber attacks increases exponentially. One unexpected example is [wireless car thefts](https://www.straitstimes.com/asia/se-asia/car-thieves-in-malaysia-have-gone-high-tech-using-device-to-unlock-car-with-keyless) where attackers [record the signal](https://gizmodo.com/why-your-cars-key-fob-is-so-hackable-1851455426) used to unlock the car and then repeat it to unlock the car once you have left the vicinity. Near Field Communications (NFC) Cards are increasingly used for access to buildings and payment but have [numerous attack vectors](https://media.defcon.org/DEF%20CON%2031/DEF%20CON%2031%20presentations/Josep%20Pi%20Rodriguez%20-%20Contactless%20Overflow%20Code%20execution%20in%20payment%20terminals%20and%20ATM%E2%80%99s%20over%20NFC.pdf) that can be exploited. As technology advances the lives of people who embrace it are increasingly made easier, but also more vulnerable and so even more precautions have to be taken.

## Application security

Secure coding is a key part of application security. One of the most common references for secure coding is [OWASP](https://owasp.org/www-project-top-ten/) which has a large amount of resources for secure coding practices. 

## Server security

Servers should be considered as they typically contain important organisational applications and data. They can potentially be used maliciously by attackers to attack the organisation and organisational partners, typically causing more damage than possible with an average end user's device.

Important aspects of server security include:
- Ensure that the server and the applications on the server are up to date with all patches and updates.
- Reduce the exposure of the server's network through the usage of firewalls and network segregation.
- Reduce the exposure of the server through removing unnecessary services, closing unused ports and minimising the number of accounts with access to the server.
- Be aware of the latest vulnerabilities in the operating system and applications running on the server and take steps to mitigate them.
- Consider the usage of an Endpoint protection solution for the server. [Gartner for EPP](https://www.gartner.com/reviews/market/endpoint-protection-platforms)
- As far as possible use a Privilege Access Management solution for server access with Multi Factor Authentication enabled. Passwords should be replaced with Access Keys or Certificate based Authentication where possible.
- Instead of direct access to the server via RDP or SSH, do consider the use of a VPN, VPN Gateway, proxies or bastion hosts.

## Supply Chain Risk management

No Organisation is an island, and partners and suppliers often serve as multipliers for an organisation's effectiveness. However, as the network of partners and suppliers expands, it forms a [critical supply chain](https://en.wikipedia.org/wiki/Supply_chain_security) on which the organisation relies. This interdependence brings risks, as vulnerabilities in the supply chain can have far-reaching consequences. As such organisations should be aware of the risks that can arise from their supply chains and take steps to mitigate them.

Some recent examples of supply chain risks:
- [CrowdStrike outage in 2024](https://www.forbes.com/sites/sap/2024/07/25/crowdstrike-outage-creates-ripple-across-global-supply-chain/)
- [Solarwinds Supply chain attack in 2020](https://www.aquasec.com/cloud-native-academy/supply-chain-security/solarwinds-attack/)
- [Singapore Banks printing vendor ransomware](https://www.channelnewsasia.com/singapore/dbs-bank-china-ransomware-customer-data-printing-vendor-toppan-next-tech-5049616)
- [Elections Department uses the same printing vendor](https://www.channelnewsasia.com/singapore/eld-print-poll-cards-ballot-papers-toppan-ransomware-attack-5052191)

## Email security

In the age of digital communication, organisations are increasingly reliant on email for business operations. And as email becomes a trusted form of communication with partners and suppliers, it is important to ensure that email communications are secure and protected from potential threats. Some key things to look out for are:
- Constantly be aware of who you are sending emails to in all the email fields (To, CC, BCC)
- Always check the sender's address to ensure it is legitimate.
   - Be aware of domain spoofing attacks such as [homograph attacks](https://en.wikipedia.org/wiki/IDN_homograph_attack), [typosquatting](https://en.wikipedia.org/wiki/Typosquatting) and [subdomain takeovers](https://www.paloaltonetworks.com/blog/cloud-security/subdomain-takeover/)
- The reputation of your email is closely tied with your organisations' domain. Do ensure there is nothing illegal hosted on your domain.
- Ensure your email server or provider has proper email security measures in place [Email Security Reference](https://www.cloudflare.com/en-gb/learning/email-security/dmarc-dkim-spf/)
  - Sender Policy Framework (SPF)
  - DomainKeys Identified Mail (DKIM)
  - Domain-based Message Authentication Reporting and Conformance (DMARC)

## Misinformation/ Disinformation

Misinformation and Disinformation are two terms that can refer to the same false information but the intent and purpose of the information is different. Misinformation refers to false or misleading information that is shared without malicious intent, while disinformation refers to intentionally and often maliciously distribution of false or misleading information. While misinformation can be unintentional the impact of the information can be equally damaging.

In order to prevent the spread of such false information it is important to verify the source of the information before sharing or using it.  
In addition, important aspects of the information to consider:
- Source of the information
- Primary Source or Secondary Source
- Reliability of the source
- Peer reviews of the source
- Tone of the information/content
- Goal or intent of the information

Examples include
- Dihydrogen Monoxide
- [British Medical Journal Parachute Research](https://www.bmj.com/content/363/bmj.k5094)
  - Conclusion: Parachute use did not reduce death or major traumatic injury when jumping from aircraft in the first randomized evaluation of this intervention.

[Misinformation vs. Disinformation Reference 1](https://www.bbc.co.uk/bitesize/articles/z3hhvj6)  
[Misinformation vs. Disinformation Reference 2](https://guides.library.pdx.edu/fakenews) 
[Singapore fight against Misinformation](https://www.gov.sg/explainers/singapore-fight-against-misinformation)
[MHA - DISINFORMATION AND INFLUENCE CAMPAIGNS](https://www.mha.gov.sg/docs/default-source/default-document-library/03_22-ne-insights-on-disinformation-and-influence-campaigns.pdf)
[Halimah Yacob Deepfakes](https://www.channelnewsasia.com/singapore/halimah-yacob-deepfake-video-criticisng-government-ge2025-police-report-5066581)

## Risk Management

Risk management is the process of identifying, managing and accepting risks in an organisation. Risk management is a foundational element of sustainable and responsible business operations, helping the organisation to identify and plan strategies for facing risks, reducing disruptions when they occur.  

The risk management process typically follows the following steps
1. Identification of risks.
   - What are the organisation's data and activities.
   - What are the risks associated with those activities, especially referencing the CIA Triad.
   - Risks should be recorded in a risk register and prioritised based on their criticality, likelihood and impact.
2. Management of risks.
   - Risks are typically mitigated through avoidance, reduction, transference or acceptance.
   - Risks management activities should be recorded as part of risk management and reviewed regularly (annually).
3. Acceptance of risks.
   - When risks cannot be cannot further mitigated, the residual risks need to be accepted.
   - The residual risks should be escalated to the organisational leadership (typically the board) for awareness and acceptance.
   - Residual Risk acceptance should also be carried out regularly (annually).

[Reference 1](https://www.ibm.com/think/topics/risk-mitigation)
