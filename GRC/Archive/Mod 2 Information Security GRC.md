# NIST AI 100-1
----
Artificial Intelligence Risk Management Framework (AI RMF 1.0)


# Part 1: Foundational Information
----

## 1. Framing Risk
----
- AI risk management minimizes potential negative impacts of AI systems.  Such as Threats to Civil Liberties  and rights. 
 
**1.1 Understanding & Addressing Risk, Impacts, and Harms**
- *Risk* - The composite measure of an event's probability of occurring and the magnitude or degree of the consequences of the corresponding event. 
- Neg Impact of event Risk is a Fn of 1) neg impact, or magnitude of harm, that would arise if the circumstance or even occurs 2) the likelihood of occurrence

**1.2 Challenges for AI Risk Management**

*Risk Measurement*
- Challenges:
  - Risk related to 3rd party software, hardware and data: Can accelerate R&D and facilitate tech transition. Can not control the 3rd party, They may not be using the same Risk Metrics that align with your org. 
  - Tracking emergent risks: Id'ing and tracking emergent risks and considering techniques for measure them. This can help AI Actors understand potential impacts or harms within specific context
  - Availability of reliable metrics:  Lack of consensus measurement methods. Measurement can be oversimplified, gamed, lack critical nuance, fail to account for differences in affected groups and contexts

*Risk Tolerance*
- Definition: Refers to the org's or AI actor's readiness to bear the risk in order to achieve its objectives. 
- Risk tolerance can be influence by legal or regulatory requirements
- New knowledge and methods to better inform harm/cost-benefits tradeoff will con't to be developed. So much that challenges for specifying AI risk tolerances remain unresolved; and that a framework is not yet readily applicable for mitigating negative AI risks. 

*Risk Prioritization*
- Not all incidents and failures can be eliminated.
- Policies and resources should be prioritized based on the assessed risk level and potential impact of an AI system.
- Prioritization may differ between AI systems that are designed to interact w/ humans vs system that are not. 
- *Residual Risk* - defined as risk remaining after risk treatment directly impacts end users or affected individuals and communities. 

*Organizational Integration and Management of Risk*
- Management should be integrated and incorporated into broad enterprise strategies and process.
- Examples of Overlapping risk include:
  - Privacy Concerns
  - Energy and environment implication associated w/ resource-heavy computing demands
  - security concerns related to CIA
  - General security of the underlying software and hardware for AI system
- Effective Risk Management is through commitment at senior levels and may require cultural change

## 2. Audience
----
NIST AI life cycle Activities
- Application Context
- Data & Input
- AI Model
- Task and Output

![](Meta/Pasted%20image%2020241103200910.png)

The two Inner circles show AI Systems' key dimensions and the Outer circle shows AI lifecycle stages.
Risk Management efforts start w/ the *Plan and Design* fn in the application context and are performed throughout the AI system lifecycle

![](Meta/Capture.png)

Start 
  Application Context
  - Plan & Design - Articulate and documents the system's concepts and obj., underlying assumptions and context in light of legal and regulatory requirements and ethical considerations
  Data & Input
  - Collect and Process Data  - Gather and validate, and clean data and document the metadata and characteristics of the dataset, in light of obj., legal and ethical consideration
  AI Model
  - Build and Use Model - Create or select algorithm; train models
  - Verify and Validate - Verify and validate, calibrate, and interpret model output
  Task and Output
  - Deploy and Use - Pilot, check compatibility with legacy systems, verify regulatory compliance, manage organizational change, and evaluate user experience. 
  Application Context
  - Operate and Monitor - Operate the AI system and continuously assess its recommendations and impacts (both intended and unintended) in light of obj., legal and regulatory requirements, and ethical considerations
  People and Planet
  - Use or Impacted by - Use system/technology; monitor & assess impacts; seek mitigation of impacts, advocate for rights

## 3.0 AI Risk and Trustworthiness
----
Characteristics of trustworthy AI systems include:
- Valid and reliable,
- Safe
- Secure and Resilient
- Accountable and transparent
- Explainable and interpretable
- Privacy-enhanced
- Fair with harmful bias managed

![](Meta/Pasted%20image%2020241103203641.png)

### 3.1 Valid and Reliable
----
*Validation* is the "confirmation, through the provision of obj. evidence, that the requirements for a specific intended use or application have been fulfilled"

- If AI systems are inaccurate, unreliable, or poorly generalized to data and settings it will increase negative AI risk and reduces trustworthiness

*Reliability* is the same standard as the the "ability of an item to perform as required, without failure, for a given time interval, under given condition."

- Accuracy and Robustness contribute to validity and trustworthiness of AI. And be in tension w/ one another in AI system.

*Accuracy* is the "Closeness of results of observation, computations, or estimates to the true values or the values accepted as being true."

*Robustness* or *Generalizability* is defined as the "ability of a system to maintain its level of performance under a variety of circumstances. "


### 3.2 Safe
----
AI System #1 rule: Do not harm human life, health, property, or the environment. 

Safe Operation of AI system is improved through:
- Responsible design, development, and deployment practices;
- Clear information to deployers on responsible use of the system;
- responsible decision-making by deployers and end users;
- explanations and documentation of risk based on empirical evidence of incidents. 

- Rigorous simulation and in-domain testing, real-monitoring, ability to shut down, modify, or have human intervention into systems that deviate from intended or expected fn.


### 3.3 Secure and Resilient
----
*Resilient* - System that can withstand unexpected adverse events or unexpected changes in their environment or use -- or if they can maintain their fn and structure in the face of internal and external changes and degrade safely and gracefully when this is necessary. 

Security Concerns 
- data poisoning;
- exfiltration of models
- training data
- other intellectual property

you're secure if you can maintain CIA and prevent unauthorized access

Security and resilience are related but distinct
  - Resilience - the ability to return to normal fn after an unexpected adverse event.
  - Security - Includes resilience, but also encompasses protocols to avoid, protect against, respond to, or recover from attacks.

### 3.4 Accountable and Transparent
----
*Transparency* - Reflects the extent to which info about an AI sys and its outputs is available to individuals interacting w/ such a sys -- regardless of whether they are even aware that they are doing so.

Accountability presupposes transparency

Promoting higher lvls of understanding, transparency increases confidence in the AI sys

A transparent sys is not necessarily an accurate, privacy-enhanced, secure, or fair system.

### 3.5 Explainable and Interpretable 
----
*Explainability* - Representation of the mechanisms underlying AI systems' operations
*Interpretability* - The meaning of AI systems' output in the context of their designed functional purposes.

perception of negative risk is from lack of understanding

Risks to interpretability often can be addressed by communicating a description of why an AI system made a particular prediction or recommendation. 

Transparency, explainability, and interpretability support each other. 
  - Transparency - can answer the question "What Happened"
  - Explainability - can answer the question of "How" a decision was made in the system
  - Interpretability - can answer the question of "Why" a decision was made by the system and its meaning or context to the user.

### 3.6 Privacy-Enhanced
----
*Privacy* - refers generally to the norms and practices that help to safeguard human autonomy, identity, and dignity. 

Privacy should help guide choices for AI system design, development, and deployment

### 3.7 Fair -- With Harmful Bias Managed
----
NIST id'd 3 major categories of AI bias to be considered.
1) Systemic
2) Computational and Statistical
3) Human-cognitive

Systemic - Present in AI Datasets, the organizational norms, practices, and processes across the AI lifecycle
Computational - Data sets and algorithmic processes, often stem from systematic errors due to non-representatives names
Human-Cognitive - relates how society perceives AI systems information to make a decision or fill in missing info, or how human thinks about purposes and fn of an AI system. 

## 4.0 Effectiveness of the AI RMF
----
Orgs and user should periodically eval whether the AI RMF has improved their ability to manage risk. 
- Policies
- processes
- practices
- implementation plans
- indicators
- measurements
- expected outcomes

# Part 2: Core and Profiles
----

## 5.0 AI RMF Core
----
The core is composed of 4 fn.
  1) Govern
  2) Map
  3) Measure
  4) Manage

![](Meta/Pasted%20image%2020241106053453.png)

### 5.1 Govern
----
Governing Authorities can determine the overarching policies that direct an organization's mission, goals, values, culture, and risk tolerance. 

### 5.2 Map
---
*MAP* - fn establishes the context to frame risks related to an AI system. 

AI actors often do you not have full access of other parts and their associated contexts

The interdependencies between these activities amount different actors can make it difficult to reliably anticipate impacts of AI systems
- As a result, the best intentions w/in one dimension of the AI lifecycle can be undermined via interaction w/ decisions and conditions in other later activities. 

Outcomes become basis for Measure and Manage fn

The **MAP** fn is intended to enhance an org's ability to identify risks and broader contributing factors.

Fn is enhanced by incorporating perspectives from a diverse internal team 

Gathering such broad perspectives can help organizations proactively prevent negative risks and develop more trustworthy AI systems by:
  - improving their capacity for understanding contexts;
  - checking their assumptions about context of use;
  - enabling recognition of when systems are not fn w/in or out of their intended context;
  - Id'ing + and beneficial uses of their existing Ai systems;
  - improving understanding of limitations in AI and ML processes;
  - Iding constraints in real-world apps that may lead to - impacts;
  - id'ing known and foreseeable - impacts related to intended use of AI systems;
  - anticipating risks of use of AI systems beyond use

### 5.3 Measure
----
- Purpose: Focuses on assessing the performance and risk of AI systems, aiming to measure and evaluate AI risks
- Key Concepts:
  - **Risk Metrics and Indicators:** Define and use metrics to assess AI risks, including performance, fairness and robustness.
  - **Monitoring and Evaluation:** Set up continuous monitoring to detect deviation or emergent risks.
  - **Verification and Validation:** Test and validate that the AI systems meets the intended design requirements.
  - **Feedback Loops:** Implement systems to learn from issues and incorporate adjustments to improve risk management.
- **Key Actions:**
  - Regularly testing the AI model's performance to detect issues early. 
  - Creating mechanisms for real-time feedback to update the model as necessary.
### 5.4 Manage
----
- **Purpose:** Implement processes to address and reduce AI system risk continually. 
- **Key Concepts:**
  - **Risk Mitigations:** Implement strategies to minimize Identified risks, including bias reductions, security enhancements, and use education. 
  - **Incident Response:** Have plans in place to address incidents and mitigate impact if risks materialized. 
  - **Continuous Improvement:** Use feedback from the measure phase to improve the AI systems over time.
  - **Adaptability:** Ensure the system can evolve w/ changing risks and environments.
- **Key Actions:** 
  - Applying appropriate mitigation measures based on identified risks
  - Setting up a structured response plan for potential AI-related incidents.
  - Iterating on the AI system design, processes, and policies based on risk management outcomes. 

## AI RMF Profiles
----
These assist org's in deciding how they might best manage AI risk that is well-aligned w/ their goals, considers legal /regulatory requirements and best practices, and reflects risk management priorities.

