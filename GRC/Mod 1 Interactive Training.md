# Elements of Info Security (IS)
----
8 Major elements for understanding how security req and controls support the org's overall ops
- Info Sec support the mission of the orgs
- Info Sec is an integral element of sound management
- Info Sec protections are tailored to the level of risk
- Info Sec roles and responsibilities are made explicit
- Info sec responsibilities for system owners go beyond their own orgs
- Info Sec requires a comprehensive and integrated approach
- Info Sec is assessed and monitored regularly
- Info Sec is constrained by societal and cultural factors

**The Key element of Info Sec is that it is regular assessment and monitoring.**
### Terms
---
Confidentiality - Preserving authorized restriction on info access and disclosure, including means for protecting personal privacy and proprietary info

Integrity - Guarding against improper info modification or destruction and ensuring info non-repudiation and authenticity. 
  There are two types of integrity
  1) Data Integrity - is the property that data has not been altered in an unauthorized manner. Covers data in storage, during processing, and while in transit
  2) System Integrity - Is the quality that a system has when it performs its intended function in an unimpaired manner, free from unauthorized manipulation of the system, whether intentional or accidental

Availability - Ensuring timely and reliable access to and use of information

Security Controls - The management, operational, and technical controls (i.e., safeguards or countermeasures) prescribed for a system to protect the confidentiality, availability, and integrity of the system and its information

### Data Types
----
Personally Identifiable Information (PII) - includes any information that can be used to distinguish or trace an individual's ID, alone or combined w/ other personal or identifying info
  Examples
    - Full name
    - SSN
    - Driver's license num
    - passport num
    - Email
    - Account numbers
    - phone number

Protected Health Information (PHI) - Includes any info about health status, provision of health care, or payment for health care created or collected by a Covered Entity ( or a Business Associate of a Covered Entity) that can be linked to a specific Individual 
  Examples
  - Medical records
  - Health Insurance information
  - Demographic Data (Age, gender, race, ethnicity) 
  - Medical test results
  - Prescription info
  - Treatment plans
  - Mental Health Records

Electronic Protected Health Information (ePHI) - Includes Protected Health Info that is stored, tx, or processed electronically
  Examples
  - Electronic Medical Records (EMRs)
  - Electronic Health Records (EHRs)
  - Personal Health Records (PHRs)
  - Electronic Prescriptions
  - Medical Device Data
  - Electronic Communications containing PHI (emails, text messages)

Sensitive Personal Information (SPI) - is a subset of PII that requires additional protection due to its sensitive nature and potential for harm if disclosed
  Examples
  - Financial Information
  - Medical info
  - Genetic data
  - Biometric data
  - Sexual Orientation
  - Religious beliefs
  - Political opinions

Educational Records - are directly related to a student and maintained by an educational agency or institution or a party acting for the agency or institution. 
  Examples
  - Grades
  - Transcripts
  - Disciplinary records
  - Attendance records
  - financial aid info

Employment Records - info related to an individual's employment, including hiring, performance, and termination
  Examples
  - Resume
  - Employment history
  - EPE
  - Disciplinary action
  - Salary and benefits info

Geolocation data - Id an personal physical location

Behavioral Data - Online activities, preferences, and interest

Controlled Unclassified Information (CUI) - info that requires controls pursuant to and consistent w/ applicable laws, regulation, and gov't wide policies, but is not classified under Executive Order 13526
  Examples
  - PII, PHI
  - Critical Infrastructure info
  - Defense info
  - Export control data
  - financial
  - intelligence data
  - + many other

International Traffic in Arms Regulations (ITAR) data - Related to defense articles, services, and related technical data as defined in the US Munitions List (USML). 


You must understand what info an org collects, processes, and stores to ensure appropriate measures are in place and the orgs complies w/ relevant regs, laws and contractual obligations


### Frameworks & Standard
----
Framework 
  - Provide a general set of guidelines, industry-accepted practices, and recommendations for managing and reducing security risks
  - Typically voluntary and flexible, allowing organizations to adapt and implement them based on their specific needs, goals, and risk appetite while providing a structured approach to security without (sometimes) including specific technical requirements or auditable criteria. 
Standards
  - Is often a more prescriptive set of requirements that orgs must follow to ensure minimum security
  - Can be mandatory and less flexible than frameworks, especially when tied to regulations or industry-specific requirements
  - Typically include specific technical controls, processes, and auditable criteria that orgs must implement and maintain.
  - Compliance w/ standards can/may be independently verified and certified through audits or assessments. 

- 
# IS Roles and Responsibilities
----
focuses on management controls

# IS Threats and Vulnerabilities
----

What is a vulnerability?
- It is a weakness in a system, system security procedure, internal controls, or implementation that could be exploited by a threat source or threat event. 

Two types of threat Sources
1) Adversarial - Are individuals, groups, orgs, or entities that seek to exploit an orgs dependence on cyber resources. Employees, privileged users, and trusted user have been known to defraud orgs system (insider threat)
2) Non-Adversarial - Refer to natural disasters or erroneous actions taken by individuals in the course of executing their everyday responsibilities. 


# IS Risk Management
----
NIST 800-39 Managing IS Risk

Divided into 4 process
  1) Framing Risk
  2) Assessing Risk
  3) Responding to Risk
  4) Monitoring Risk

Two type of risk
1) Inherent - Level of risk that exists in the absence of any controls or mitigating measures. Inherent risk is determined by considering the likelihood and impact of a risk event, assuming that no controls are implemented. 
   Ex: data breach in an org w/ no malware protection, incident response capabilities, and/or access controls would be very high
2) Residual - Level of risk that remains after implementing controls and mitigating measures. 