# IT Security

The goal of this document it to capture at a very high level broad security concepts that people should be aware when considering management of IT departments and IT Infrastructure.

## Contents
- [Introduction](#What-is-cyber-security)
- [Data management](#Data-management)
- [Personal Data Protection Act (PDPA)](#personal-data-protection-act)
- [Scams, Social Engineering and Phishing](#scams-social-engineering-and-phishing)
- [Malware](#malware)
- [Accounts & Passwords](#accounts--passwords)
- [Physical cyber security](#physical-cyber-security)
- [Application security](#application-security)
- [Server security](#server-security)
- [Supply Chain Risk management](#supply-chain-risk-management)
- [Email security](#email-security)
- [Information/Disinformation](#information-disinformation)

## What is cyber security
The goal of Cyber security is the protection of an Organisation's IT assets. There are many threats to an organisation's IT assets, and attackers often do not need a reason to cause damage to an organisation's IT assets. Even the most well prepared organisations, multi-billion companies and first-world governments have difficulties when facing advanced persistent threats that specifically target them. The goal of cyber security is to deter the majority of attackers from causing damage to IT assets, minimising impact when there is damage and reducing downtime with a fast recovery.

### Primary Security Concepts (CIA, AAA Triads)
| Term | Definition |
| ---- | ---------- |
| Confidentiality | The concept that information should only be revealed to those which you intend to reveal it to. <br/> i.e. Public information should be public and private information should remain private. |
| Integrity       | The concept that information shown should be consistent and accurate. <br/> i.e. Information should be correct and not changed unintentionally. |
| Availability    | The concept that information should be accessible when required. <br/> i.e. Information should be available when required. |
| Authentication  | The concept that information should only be revealed or actions allowed after a person's identity has been verified through one or more methods. <br/> E.g. Username and Password, Time-based one-time password (TOTP) |
| Authorization   | The concept that information should only be revealed or actions allowed for people with sufficient or correct rights or entitlements. <br/> E.g. Only Managers should be allowed to approve leave request, Auditors should not be allowed to change information. |
| Auditing        | THe concept that any action should be recorded and logged as evidence. <br/>  | 

## Data management

The purpose of proper data management is to ensure organisational knowledge is protected and maintained to ensure it's availability and continuity. The main areas for consideration here are typically data storage and backup and data recovery. The data management strategy chosen should always first consider the data that is being stored as different types of data will require different management strategies.

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

[Data Protection Obligations under the PDPA](./references/links.md#PDPA-Infographic):
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

[Key Reference](./references/links.md#Singapore-PDPA)

## Scams, Social Engineering and Phishing

Scams are a deceptive technique with the goal of tricking someone into providing information or funds to the scammer. Scams are typically identified by the use of generic greeting followed by a generic urgent request for information or funds. It can come many different forms including emails, SMS, letters and other messaging services. Social Engineering is a technique where attackers use social skills and psychological manipulation to trick people or [organisations](./references/links.md#youtube-of-defcon-phishing) into revealing sensitive information.

Phishing is a specific form of social engineering where attackers deceive people into revealing sensitive information or installing malware by pretending to be from a trusted entity e.g. Governments or Banks. General phishing can be relatively easier to detect but can also make users think they are safe, susceptible to more advanced forms of phishing.  

Spear or Whale phishing is a more dangerous targetted form of phishing where the attacker will first carry out advanced reconnaissance of the target's background and existing relations. Spear phishing is usually towards specific executives for their corporate knowledge or entitlements while whale phishing is more specific towards High valued targets. The phishing will usually include specific references to the target's background or relations to make it more realistic. E.g. School Alumni, Banking or other Financial institutions.

One concerning trend with the creation of deepfake and the rise of easily accessible AI is to use a combination of these capabilities to accurately create [videos of people](./references/links.md#scam-using-lee-hsien-loong-deepfake) that have a relationship with the target. These can even come in the form of [video calls or conference calls](./references/links.md#phishiing-using-deepfake-video-call) and used to trick the target into giving information or transferring funds to the attacker.

## Malware

Malware is a combination of the words malicious and software and defines a wide range of software that can be used to attack an organization. The earliest malware started in the form of spambots and viruses which primarily served to spread and spam other users on the network or to cause the device to be difficult to use.

- Keyloggers are a type of malware that can record keystrokes and send them to the attacker.
- Rootkits are a type of malware that would allow attackers to gain access to systems without the knowledge of the system owner.
- Ransomware is a type of malware that encrypts files and demands payment to decrypt or to prevent the system release of sensitive information on the public internet.
- Bots are a type of malware that are used by attackers for various purposes, including spamming, phishing, and other malicious activities.
- Spyware is a type of malware that collects information about users' online activity without their knowledge or consent, often used in blackmail or extortion purposes.
- Miners are a specific type of bot that utilise system resources to mine cryptocurrency for attackers.

Modern malware however can be much more dangerous, they typically use a combination of techniques to breach and fully exploit system. One of the most prominent malware attacks in recent times is [stuxnet](./references/links.md#stuxnet) in which an Iranian Nuclear Reactor with an isolated network was attacked for over a period of many months. Modern malware can be deployed using a variety of methods including clicking links, opening attachments and running scripts.

Modern Anti-Malware software is quite capable of facing most threats and do not have to be expensive. [Microsoft Defender](./references/links.md#microsoft-defender) is a free solution that comes with Windows that should be able to meet most users needs. But even the most powerful anti-malware software will be ineffective with users that are unaware of the potential threats and does not keep their system up to date. When interacting with people do confirm their identity through multiple means if possible before revealing sensitive information as attackers are even [posing as anti-scam police](./references/links.md#scammers-as-anti-scam-police)

## Accounts & Passwords

Passwords have an ancient history dating back to beyond the roman empire with the caesar cipher. As important as passwords are it is still unfortunately common for weak passwords to be chosen, reused in multiple places and left exposed for in public. The typical standard for Passwords and identity management is from [United States National Institute of Standards and Technology (NIST)](./references/links.md#nist-for-passwords). Shorter complex passwords with regular rotation is no longer recommended in the latest update in favour of longer, more secure passwords as summarised in [NIST Password Updates](./references/links.md#1password-blog-on-nist-changes). Finally Passwords should not be shared with anyone, if users are required to login to assist with supporting cases or other troubleshooting issues, the password should be changed once the issue is resolved.

### Account Management

Accounts should be tied to individual users as far as possible and [Multi Factor Authentication](./references/links.md#multi-factor-authentication) enabled where possible. 

Factors of authentication typically come in 3 categories:
- Something the user knows (e.g. Passwords, Passphrase)
- Something the user has (e.g. Security Token, Digital certificate)
- Something the user is (e.g Fingerprint, Iris scanner, Facial recognition)

When an account is no longer required, the administrator should remove the account as soon as possible to prevent dormant accounts being an avenue of attack.

If sharing accounts is required, it is recommended to use a password manager to facilitate the sharing (e.g. [Google Password Manager](./references/links.md#google-password-manager), [1Password](./references/links.md#1password)), use a complex password of more than 20 characters and not allow the password to be revealed to users.

### Secure Passwords

Do see the following recommendations for secure passwords.
1. At least 10 Characters long
2. Contain a mix of uppercase, lower case Characters, numbers and special characters
3. As far as possible passphrases should be used e.g. 3LongRedCars!, 5BlackCrowsOutside?, Romans12:1Therefore
4. Password complexity can be checked using online tools [CSA Password Checker](https://ihp.csa.gov.sg/password-checker) [HaveIBeenPwned](https://haveibeenpwned.com/Passwords). These should only be used as an estimate of what a secure password should be.

## Physical cyber security

The physical security of digital devices is often overlooked and many people underestimate the potential damage that can be caused by stolen devices or even USB ports that are left unsecured and unattended in public spaces. From [USB Killers](./references/links.md#usb-killers) that are able to destroy devices upon plugged in to [USB Rubber Ducky](./references/links.md#usb-rubber-duck) that deploys a host of malware when plugged in are just some examples of the damages that can be caused by unsecured devices. In addition, once stolen devices should be assumed to be breached and measures taken against any data that is stored on them, such as changing of passwords and remotely logging out of accounts.

Physical Cyber Security extends beyond computers and mobile phones, in an increasingly digital world the number of potential vectors for cyber attacks increases exponentially. One unexpected example is [wireless car thefts](./references/links.md#wireless-car-theft) where attackers [record the signal](./references/links.md#stealing-a-car-with-technology) used to unlock the car and then repeat it to unlock the car once you have left the vicinity. Near Field Communications (NFC) Cards are increasingly used for access to buildings and payment but have [numerous attack vectors](./references/links.md#defcon-nfc) that can be exploited. As technology advances the lives of people who embrace it are increasingly made easier, but also more vulnerable and so even more precautions have to be taken.

## Application security

Secure coding is a key part of application security. One of the most common references for secure coding is [OWASP](./references/links.md#owasp-top-ten) which has a large amount of resources for secure coding practices. 

## Server security
## Supply Chain Risk management
## Email security
## Information/Disinformation
