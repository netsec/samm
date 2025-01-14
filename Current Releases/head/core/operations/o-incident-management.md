---
business_functions : Operations
title : Incident Management
assignedto       : Daniel (dan.kefer@gmail.com)
complete          : 90%
weight: 1
type: security_practice
---
# Short Description

Incident Management security practice describes activities carried to detect and respond to security incidents.

# Long Description

Once your applications become operational, you’re likely to face security incidents. For this document, we consider a security incident a breach or threat of an  imminent breach of at least one asset’s security goals due to malicious or negligent behaviour. Examples of a security incidents might include:

- successful DoS (Denial of Service) attack against a cloud application
- application user accessing private data of another one by abusing a security vulnerability
- attacker modifying the application source code

Sometimes, a security incident is detected only after months or even years when all damage has already been done. That's why the first stream called "Incident Detection" tackles the ability to reliably and timely detect security incidents.

Once you have identified that you're suffering from a security incident, it's essential to act in a well organized way in order to limit the damage as much as possible. Actitivies leading to this goal are described by the second stream called "Incident Response".


# Overview

| | A: Incident Detection | B: Incident Response |
|:---|:---|:---|
| Maturity 1 - Best-effort incident detection and handling | Best-effort incident detection with available log data | Defined high-level incident response strategy |
| Maturity 2 - Formal incident management process in place | Automated log evaluation driven by process | Root Cause Analysis with feedback loop |
| Maturity 3 - Mature incident management | Reliable timely incident detection | Proactive incident + emergency exercises |



# A: Incident Detection

This stream covers the time frame between a security-relevant event taking place and creation of a formal security incident, e.g. by creating a respective ticket and handing over to incident response process. With the increasing maturity, you want to shorten this time span and detect security incidents more reliably and efficiently.

## Maturity 1

### Benefit

Ability to detect the most obvious security incidents within a reasonable timeframe.

### Activity

The available log data (e.g. access logs, application logs, infrastructure logs) are analyzed to detect possible security incidents in accordance with known log data retention periods.

In small setups, you can do this manually with the help of common command line tools. With larger amounts of logs, employ automation techniques - even a simple script looking for suspicious events run periodically as a cron job is a step forward!

In case the logs from different sources are sent to a dedicated log system, it might be a good idea to analyze the logs here and also employ basic log correlation principles.

Even if you don’t have a 24/7 incident detection process, unavailability of the person in charge (vacation, illness) shouldn’t impact the detection speed and quality significantly.

You have a defined and generally known contact point for formal creation of security incidents.

### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time

### Quality Indicators

Typically, on this maturity level you have:

- defined and published the most probable incident scenarios
- assigned a person or role responsible for incident detection
- identified and evaluated some suspicious events
- documented the escalation process
- put reasonable effort into achieving log integrity

<!--
### Notes
- Should whether or not you do 24/7 detection be specified by maturity level? Maybe maturity should relate to risk rather than timing -> **Fourth paragraph reformulated**
- Log retention - risk-based decision on how long logs should be kept to aid -> **First paragraph edited**
- Log trustworthiness / integrity - have they been tampered with??? -> **Indicator added**
-->

## Maturity 2

### Benefit

Ability to timely detect expected security incidents.

### Activity

The incident detection process has a dedicated owner and clear documentation accessible to all process stakeholders, and is periodically checked to make sure it is up to date. You ensure employees responsible for incident detection follow this process (e.g. using training).

The process typically relies on a high degree of automation, collecting and correlating log data from different sources including application logs. You may collect the logs to a central place, if suitable. Explicit attention is periodically paid to integrity of the analyzed data. If you add a new application, you ensure that the process covers it within reasonable period of time.

You detect possible security incidents according to an available checklist. The checklist covers expected attack vectors, and known or expected kill chains. You evaluate it and update it regularly.

If you evaluate an event as a security incident with high level of confidence, the responsible staff is notified immediately, even outside business hours. You  perform further analysis and start the escalation process.

### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time


### Quality Indicators

Typically, on this maturity level, you:

- employ some automated measures for incident detection
- have up-to-date documentation for the incident detection process
- have documentation for the most probable incident scenarios
- integrate every new system taken to production into the process

<!--
### Notes
- Software-driven application-specific logs (whereas level 1 might be general logs) -> **Second paragraph**
- Look at known kill-chains / attacks and work backwards to select relevant logs - proactively checking that you are collecting the right data -> **third paragraph**
- Added value of the process -> **In the benefit now?**
- Centralized logging -> **2nd paragraph**
-->

## Maturity 3

### Benefit

Ability to timely detect unexpected security incidents.

### Activity

The process documentation includes measures for continuous process improvement. You check the continuity of process improvement, e.g. via tracking of changes.

The checklist for suspicious event detection is correlated at least from:

- Sources and knowledge bases external to the company (e.g. new vulnerability announcements affecting the used technologies)
- Past security incidents
- Threat model outcomes


You use correlation of logs for incident detection for all reasonable incident scenarios. If the log data for incident detection is not available, you document it  as a defect, triage and handle it according to the resulting priority / SLA.

The quality of the incident detection does not depend on the time or day of the event. If you do not act upon the security event within a defined time, it triggers further notifications according to a defined escalation path. The efficiency is of the incident is also checked by exercises with defined improvement action points.


### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time


### Quality Indicators

Typically, on this maturity level:

- there is evidence that you have improved the process within the last year
- you evaluate suspicious events in less than one hour from their  occurrence and  document the result
- the detection process has its own KPIs
- there are tickets in dev queues with requests for log data improvement

<!--
### Notes
- Tabletop exercises / simulation exercises -> **Last paragraph edited**
- Centralized logging -> **Covered in level 2**
-->

# B: Incident Response

Incident Response starts the moment you acknowledge and verify the existence of a security incident. Your goal is to act in a coordinated and efficient way so that further damage is limited as much as possible. If suitable, you want to identify the root cause and limit the probability of similar incidents happening in the future.

## Maturity 1

### Benefit

Ability to efficiently solve most common security incidents.

### Activity

The first step is to recognize the incident response competence as such and define an owner responsible for its continuous development. They keep up with current state of incident handling best practices and forensic tooling.

You usually don't go for dedicated incident response personnel on this maturity level, but you define  the participants of the process are defined (for instance, regular admins or developers helping in case of need). There is a know single point of contact for  the team And a conscious decision regarding reachability of the personnel.

When security incidents happen, you document the steps taken. Protect this information from unauthorized access if necessary.

### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time


### Quality Indicators

Typically, on this maturity level:

- the person responsible for the process is documented and generally known
- all security incidents are documented in a consistent way
- first KPIs for security incidents are collected

<!--
### Notes
- Define 'incident' -> **Defined in Practise Long Description**
-->

## Maturity 2

### Benefit

Understanding and efficient handling of most security incidents.

### Activity
Formally establish and document the security incident response process. The documentation includes information like:

- Most probable/common scenarios of security incidents and high-level instruction how to handle them. For such scenarios, also use public knowledge about possibly relevant 3rd-party incidents
- Rules for triaging the incident
- Rules for involvement of different stakeholders (including mandatory timeframe to do so, if needed), e.g. senior management, Public Relations, Legal, privacy, Human Resources, External (law enforcement) Authorities, Customers.

Knowledgeable and properly trained staff is available in and outside of business hours with defined time to act. Keep both hardware and software tools up to date and ready for use anytime. Define a war room.

The process includes a policy for carrying out root cause analysis and its expected outcomes.

### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time


### Quality Indicators

Typically, on this maturity level:

- You perform Root Case Analysis for the most severe security incidents
- Security playbooks are available for the most common incidents
- there is dedicated trainings for incident response staff
- forensic analysis tooling is available

<!--
### Notes
- Root cause analysis - should be about the incident in question (becomes more advanced at L3) -> **last paragraph reformulated**
- You have to communicate the incident (within a certain timeframe). Involve authorities if necessary. -> **Third bullet point adapted**
-->

## Maturity 3

### Benefit

Efficient incident response independent of time, location, or art of the incident.

### Activity

Establish a dedicated incident response team, continuously available and also in charge of the continuous process improvement with the help of regular RCAs. For distributed organizations, define and document logistics rules for all relevant locations if sensible.

Document detailed incident response procedures and keep them upd to date. Where sensible, automate procedures. Keep ll resources necessary for these procedures (e.g. separate communicating infrastructure or reliable external location) ready to use. Detect unavailability of these resources in a timely manner.  

Carry out incident and emergency exercises are regularly. Use the results for process improvement.

Define, gather, evaluate, and act upon metrics on the incident response process, including its continuous improvement.

### Maturity Questions
#### Q 1
Are ...?

*Answer Options*
- No
- Yes, some of the time
- Yes, approx. half the time
- Yes, most or all of the time


### Quality Indicators
Typically, on this maturity level:

- You perform Root Cause Analysis for all security incidents unless there is a specific reason not to do so
- You identify and document improvements in the RCAs and you have probably implemented them
- You have carried out some exercises in the last year.
- There is a roadmap for process improvement
- Process metrics are available (e.g. resolution speed, affected customers, ...)
- In most incidents, you use playbooks to a high degree

<!--
### Notes
- Root cause analysis - feedback loop - learning and improving beyond the incident at hand -> **first paragraph updated**
- Automated incident response (e.g. rasp [Runtime Application Self-Protection Security], phantom, demisto) -> **automation mentioned in the first paragraph**
- Not concrete - what are you going to do to concretely improve on L2 -> **Mentioned RCAs, Exercices, Metric evaluation...**
-->
