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

**KNOW TERM**
----
Likelihood of Occurrence - Weighted risk factor based on an analysis of the probability that a given threat is capable of exploiting a given vulnerability. 

Risk Assessment - Process of Id'ing, estimating, and prioritizing info sec risks. Carefully exam of threats and vulnerability info to determine the extent to which circumstances or events could have on an org.

Risk Assessment Methodology - Typically includes --
  - Risk Assessment process
  - An explicit risk model, defining key terms and assessable risk factors and the relationships among the factors.
  - An assessment approach ( quantitative, qualitative, or semi-qualitative), specifying the range of values those risk factors can assume during the risk assessment and how combinations of risk factors are id'ed/ analyzed so that values of those factors can be functionally combined to eval risk
  - An analysis approach ( threat-oriented, asset/impact-oriented, or vulnerability-oriented) describes how combinations of risk factors are id'd / analyzed to ensure adequate coverage of the problem space at a consistent level of detail. 

Risk Model - Defines that risk factors to be assessed and the relationships among those factors. Risk factors are characteristics used in risk models as inputs to determining levels of risk in risk assesments.

Threat Impact level - This is the magnitude of harm that can be expected to result from the consequences of unauthorized disclosure of info, unauthorized mods of info, unauthorized destruction of info, or loss of info or info system availability. 



----
NIST 800-37
Risk Management Framework (RMF)

RMF Promotes the concepts of near real-time risk management and ongoing system authorization through the implementation of robust continuous monitoring processes

6 Steps to RMF

![](Meta/Pasted%20image%2020241026220822.png)

1) Categorize - Categorize the system and information processed, stored, and tx based on an impact analysis
2) Security Control Selection - Select the set of NIST SP 800-53 controls to protect the system based on risk assessment(s)
3) Security Control Implementation - Implement the controls and docs how controls are deployed
4) Security Control Assessment - Assess to determine if the controls are in place, operating as intended, and producing the desired results.
5) System Authorization - Senior official makes a risk-based decision to authorize the system (to operate).
6) Security Control Monitoring - Continuously monitor control implementation and risk to the system 

    The Purpose of the 6 steps in the RMF is 
    - To respond to risk and frame risk wthin organization

# IS Policy
----

NIST 800-12 
3 Types of Policy
- Program Policy
- Issue-Specific Policy
- System-Specific Policy

Program Policy
  - Purpose - Sets the foundation of the entire policy document. Clearly articulate the main obj / goals of the policy
  - Scope - Define the boundaries and applicability of the policy within the organization. Specify which individuals, dept, systems, assets are covered by the policy and any exclusions or limitation. 
  - Responsibilities - Define the specific duties, obligation and expectation of various stakeholders in maintaining the orgs information security posture. 
  - Compliance - Outlines the orgs commitment to relevant laws, regulations, industry standards, and contractual obligation related to Info Sec. May also detail consequences of non-compliance for the orgs and its employees. 

Issue-Specific Policy
  Basic Components
  - Issue statement
  - Statements of the orgs position
  - Applicability
  - Roles and Responsibilities
  - Compliance
  - Points of Contact and supplementary info

System-Specific Policy
  Basic Components
  - Security Obj
  - Operational Security Rules
  - System-Specific Policy Implementation

