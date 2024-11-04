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
![](Meta/Pasted%20image%2020241103203620.png)

