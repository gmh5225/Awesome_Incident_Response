# Awesome Incident Response [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
<img align="right" src="./images/awesome-incident-response.png" width="200" alt="Awesome Incident Response" title="Awesome Incident Response">
Welcome to "Awesome Incident Response" the ultimate open-source repository designed to simplify and guide you through the intricate world of incident response! Whether you're a seasoned cybersecurity professional or an aspiring enthusiast, this comprehensive collection of resources and tutorials will equip you with the knowledge and skills to effectively handle and mitigate security incidents. These strategies were developed with several decades of incident response experience and should guide you well through any type of cyber security incident, and pulls text and images from multiple sources that will be cited. 
<br /><br />

**Using this Guide:**

The main page (this page) should be considered the consolidated aka the "For Dummies" version of the Awesome Incident Response guide. Each phase of Awesome Incident Response is described and gives you the best practices needed for an effecient and effective response.  But if you want more detail, or need additional guidance, each section will have a [Read More] that will go more in depth.

This curated list of tools and resources is aimed to help security leaders, analysts, and [DFIR](http://www.acronymfinder.com/Digital-Forensics%2c-Incident-Response-%28DFIR%29.html) teams, and is always a work in progress. I hope you find this valuable, and as always Pull requests are encouraged and appreciated!

**Awesome Incident Response Percentage Complete:**

![06](https://progress-bar.dev/06/?title=Completeness) 

[-Bill (hevnsnt)](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/author.md)

---
**FUNDING:** 

If you believe that a community driven, open-sourced, and validated "Awesome Incident Response" resource is valuable for the internet to reference, please consider supporting this project. You can find more information for supporting the project in the right-sidebar.  Anything you contribute is greatly appreciated and goes 100% to supporting this project!

---
<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./images/Awesome-Incident-Response-Logo-Darkmode.png">
  <img alt="Text changing depending on mode. Light: 'Awesome Incident Response Logo' Dark: 'Awesome Incident Response Logo'" src="./images/Awesome-Incident-Response-Logo.png">
</picture>
</p>

## Contents
- [Preparation](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#preparation)
- [Identification](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#Identifcation)
- [Containment](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#containment)
- [Eradication](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#eradication)
- [Recovery](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#recovery)
- [Lessions Learned](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#lessons-learned)
- [Tools Index](https://github.com/hevnsnt/Awesome_Incident_Response/blob/main/README.md#tools-index)

---
### Preparation
Oh preparation, the most likely of all steps to be skipped, and only gets attention after the company suffered substantial losses and had to hire external consultants.

**DO NOT SKIP THIS STEP**
**Please, do it now. You will thank me later when you do not need to hire me to help you respond to an incident.**

Effective Incident Response happens _BEFORE_ an incident occurs. Preparation is EASY AND FUN. By preparing before a crisis occurs, you can minimize the damage and ensure a quick response when faced with an attack. 
Also, you will look like a hero! Awesome Incident Response requires a collaboration across multiple teams, and !surprise! not all of them are IT & Security. 
This section describes how to ensure that you have the right people, capbabilities, authorities, and processes in place in order to effectively respond to a crisis. 
Then we will discuss how to test your IR capablity to validate that everything is working as expected.

Do these 7 things now to greatly improve your ability to respond to any cyber crisis:

**1. Develop an Incident Response Plan and exercise it:** 

Your company should have a comprehensive plan in place that outlines the steps to be taken in the event of a cyber attack or breach. This plan should include clear roles and responsibilities for responding to an incident, as well as contact information for key stakeholders and outside experts.


**2. Ensure you are logging the correct events:**

I have worked thousands of incidents, and I have never seen an organization that is logging all the data sources that would have been extremely helpful for the detection and/or response. Often this is because they simply do not know what to log, or the expense of logging is something hey have not tackled (or received approval for) yet. Having a logging plan is essential, as a security leader, you can’t keep going back to get more budget as new applications, services, networks, or assets are introduced to your environment.  These costs need to be built into the project BEFORE it was implemented. At the very basic level, you need to be logging the the most critical areas of your environment, and these logs should be located on a separate system and retained for at least 90 days. For a indepth discussion about logging, see the [Identification Chapter](./chapters/2%20-%20Identification/identification.md)

**3. Regularly update software and systems:** 

Keeping all software and systems up-to-date with the latest security patches and upgrades is essential. This includes not just operating systems, but also any applications and devices connected to the network.

[Brian Krebs](https://krebsonsecurity.com/2011/05/krebss-3-basic-rules-for-online-safety/) Wrote "Krebs’s 3 Basic Rules for Online Safety" in 2011 and it still remains true today:

* If you didn’t go looking for it, don’t install it.
* If you installed it, update it.
* If you no longer need it, remove it.


**4. Conduct regular security assessments:** 

Regular security assessments can help identify vulnerabilities in your systems before they are exploited. This can include regular penetration testing, vulnerability scans, and security audits.


**5. Train employees:** 

Regular training for all employees on cybersecurity best practices and the importance of data privacy is crucial. This will not only raise awareness about potential risks, but also help prevent incidents from happening in the first place.


**6. Establish partnerships:** 

Establishing partnerships with outside experts, such as cybersecurity firms or incident response teams, can provide additional support and expertise in the event of a crisis. Having these relationships in place before an incident occurs can help ensure a rapid and effective response.


**7. Understand what your Cyber Insurance Covers (and does not cover):**


Read More on the [Preparation Chapter](./chapters/1%20-%20Preparation/preparation.md)

---

## Identifcation
Before we _Declare_ an incident, we need to identify the severity and impact of a security _event_. This section describes the best practices for building an effective Cyber Defense team, to ensure you are correctly monitoring the _correct things_ in your environment to quickly detect events as they occur in your environment.

Being able to fully understand the scope of a security incidenty, we need evidence to review. When did this happen? How long ago? How many systems are impacted? Was anything exfiltrated/destroyed? Who did this?.  All of these can be answered with an Awesome Logging strategy.  The following is a good starting point of systems that should be logged, and logs should be located on a separate system and retained for at least 90 days.

* Authentication (Active Directory, Identity Providers, Application, CASB, etc.) If a user logs into it, you should have that log.
* Firewalls
* Proxy / Webfiltering Solutions (DNS)
* Security Tools (IDS/IPS, DLP, Zeek, etc.)
* VPN Connections
* Anti-Malware / EDR
* Endpoint Command Line (Often overlooked, but is a GOLDMINE for Awesome Incident Response)
* DHCP
* Email Filtering / Spam Filtering
* Webservers / Application servers
* Servers (Cloud and On-prem)

Read More on the [Identification Chapter](./chapters/2%20-%20Identification/identification.md)

---

## Containment
The "containment" phase of incident response refers to the stage in which the primary objective is to limit the impact and scope of a security incident or breach. During this phase, the incident response team works swiftly to prevent further damage, isolate affected systems or areas, and mitigate the immediate risks associated with the incident. The containment phase is crucial in minimizing the potential harm caused by the incident and laying the foundation for subsequent recovery and remediation efforts.

Read More on the [Containment Chapter](./chapters/3%20-%20Containment/containment.md)

---

## Eradication
The "eradication" phase of incident response is the stage where the incident response team focuses on completely removing the cause of the security incident or breach from the affected systems and infrastructure. The objective is to eliminate any remnants of the attacker's presence and ensure that the environment is secure and free from vulnerabilities that could be exploited in the future. The eradication phase typically follows the containment phase and precedes the recovery and lessons learned phases.

Read More on the [Eradication Chapter](./chapters/4%20-%20Eradication/eradication.md)

---

## Recovery
The "recovery" phase of incident response refers to the stage where the focus shifts towards restoring normal business operations and returning the affected systems, networks, and data to a fully functional and secure state. The recovery phase follows the containment and eradication phases and involves activities aimed at recovering from the impact of the incident and minimizing any disruption caused to the organization. Often companies move to the recovery phase before Containment and Eradication are complete, leading to ineffective incient response and delaying a normal operating state. Do not make this mistake.

Read More on the [Recovery Chapter](./chapters/5%20-%20Recovery/recovery.md)

---

## Lessons Learned
The "lessons learned" phase of incident response is a crucial step that occurs after the incident has been resolved and normal operations have been restored. This phase focuses on reflecting on the incident response process and identifying valuable insights, improvements, and best practices to enhance future incident response efforts. The primary goal is to learn from the incident, prevent similar incidents from occurring in the future, and strengthen the overall security posture of the organization.

Read More on the [Lessons Learned Chapter](./chapters/6%20-%20Lessons%20Learned/lessonslearned.md)

---

## Tools Index
An amazing list of resources for an incident responder.
[Tools Index](./tools.md)
