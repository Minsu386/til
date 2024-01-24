phillipchoi@aciplab0819.onmicrosoft.com


# Select Win Deployment Tool
----
Learning Objective: *Select the appropriate deployment tool, given a scenario*

answer file = unattend.xml

On-Prem Solution
- Windows Deployment Services (WDS) - is a feature in WIn Server that makes it easy for beginners to install Windows on multiple computers over the network simultaneously. It simplifies the setup process, allowing user to quickly and remotely deploy the Win OS without individual manual installations
- The Win ADK (Windows Assessment and Deployment Kit) is a collection of tools that help users customize and deploy Win OS on their computers. It simplifies the process of creating personalized Win Installations, making it easier to setup new systems and manage large-scale deployments efficiently. 
- SysPrep - Deprecated.  Allows orgs to create a customized image of the Win OS. 
- The Microsoft Deployment Toolkit (MDT) is a software tool that helps orgs automate and streamline the process of deploying Win OS on multiple computers
- The Microsoft System Center Configuration Manager  (SCCM) - is a management tool that helps orgs efficiently deploy and manage software apps, updates, and OS across their network

Cloud-Solutions
- Windows Autopilot - a collection of capabilities to deploy Win PCs
- Subscription Activation - allows orgs to install new ver of Win by changing SKUs
- Azure AD with Mobile Device Management - users can log into the PC with an organizationally-provisioned Azure AD. The device will be automatically enrolled into the Microsoft Intune MDM solution. All post-installation tasks are deployed, configured and controlled through centralized policies. 

