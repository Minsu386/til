# Explore the Enterprise Desktop

## Benefits of modern management

## Enterprise Desktop Lifecycle
----
![](Meta/Pasted%20image%2020240123211043.png)

**Planning**: Preparing defining a strategy for system management
**Purchasing**: Processing rand obtaining approval of invoices
**Deployment**: Installing an OS, enrolling devices, and deploying app to the device
**Operations**: Ensuring that system are functioning properly and are protected.
**Support**: Ensuring that the end users learn how to use their systems and application.  
**Upgrade and Retire**: Replacing devices, retiring obsolete hardware, or unenrolling a device from the org

## Planning and Purchasing

**Planning Stage**:
- **Computer strategy**: Policies such as image and hardware standardization, environment design, replacement frequency, mobile device vs desktop usage, and BYOD policies
- **Computer Selection**: Choosing hardware, software, and peripherals. Includes design config and app compatibility testing
- **Deployment Methods**: Different deployment methods have different cost that support that method. Can choose multiple types of deployments methods to accommodate different scenarios. 
- **Demand forecasting**: Predicting future computing resource requirements to determine the resources it needs to purchase
- **Design config**: Which new features you use and how to incorporate them into the overall plan. 

**Purchasing Stage** - includes negotiation, contracts, vendor management, shipping, and disposal of packaging material
- **Hardware**: Typically represents ~ 1/2 the cost in the purchase phase of the computer life cycle
- **Software**: productivity apps, antivirus software, and communication tools
- **Accessories**: cables, psu, keyboard , mice, bags, docking, secure-access cards
- **Deployment Process**: chosen deployment method will directly affect the overall deployment cost. additional cost - storage requirements of file servers, and hard disk drives, Flash drives, bandwidth
- **Hardware Staging**: securely and adequately storing, unpacking, inspecting, and inventorying the system. 

## Desktop Deployment
----

Critical phase Building & Deploying

### Building
Allows you to improve efficiencies when developing a strategy for abase OS config. Key steps include
- **Streamlining Deployment Process**: developing automated solution and procedures that you can use for deployment 
- **Developing deployment process**: Traditional you might create a baseline OS image. Using newer features such as Windows Autopilot might involve creating a base device configuration
- **testing**: VM to simulate deployment and validate configurations quickly and effectively; the testing plan should include physical devices to test before deployment
- **Configuration**: This step includes developing an automation solution, testing and config standardized images or device config, accounting for IT labor to config computers, and planning for network access configuration
- **Managing the logistics**: Storing Computers, deploying and setting up physical hardware, communicating to end users.  Also includes providing the HW vendor w/ configuration requirements to be done by the vendor before shipping the device to the organization

### Deployment

Usually takes place in phases throughout the networking environment. Use the early phases to validate scenarios such as device configuration profiles, image configurations, end-user experience, application deployment success, and so forth. 

### Data Migration
----

Some best practices
- Migrate Essential Data to cloud using tools such as "Known Folder Move" (KFM)...One drive selecting folder to keep up to date with backup to the cloud ( Desktop , Documents, Photos etc)
- Use in-place upgrades
- User State Migration Tool - USMT 10.0 - Captures user accounts, user files, os settings, and application settings and migrates them to a new Win installation. can use for PC replacement and PC refresh migrations.

## Plan App Deployment
----
Consist of three phases
1) Managing Application inventory & compatibility
2) Packaging applications.
3) providing life-cycle support

### Application Inventory and Compatibility
----
Gathering inventory of application is first step in understanding the fx of app compatibility changes in your environment
Tools to perform asset inventories such as **Intune**

### App Packaging
---
Creating automated installation involve using silent installation commands from vendor.  If silent installation is not available such as inhouse developed software, you will need to package or repackage the app.  You can create Windows Installer packages. Microsoft Application Virtualization (App-v) **will be depreciated April 2026**
Recommend Azure Virtual Desktop w/ MSIX app watch.

### App Life-cycle Support
----
- Deploying New App: Test new app for compatibility issues w/ existing app
- Installing new version of existing app: Ver upgrades are usually significantly more complex than updates, and comprehensive planning and testing are paramount. This is to ensure that the upgrade release occurs appropriately
- Updating applications: Updates are far more frequent and require less testing than version upgrades

### Application Delivery
----
auto - during deployment, based on user grp membership,  
On demand - through a portal


## Plan for upgrades and retirement
----
- Storage
- when / how to retrieve and replace assets
- wiping data Corp Own and BYOD
  - If BYOD if the app is managed, intune can selectively wipe data specific to that app. 


# Explore Windows Editions
----

## Windows client editions and capabilities
----
|**Windows 10 / Windows 11 Edition**|**Audience**|**Availability**|
|---|---|---|
|Home|Individual home use|Everyone|
|Pro|Small and mid-sized businesses, advanced users|Everyone|
|Pro for Workstations|Users with advanced performance and storage requirements|Everyone|
|Enterprise|Large enterprise organizations|Available to Volume LicenseMicrosoft Volume Licensing, Microsoft Enterprise Agreement, Microsoft Store for Education or Microsoft Cloud Solution Provider program|
|Enterprise LTSC|Large enterprise organizations with restrictive change requirements|Microsoft Volume Licensing, Microsoft Enterprise Agreement, or Microsoft Cloud Solution Provider program|
|Pro Education|Comparable to Pro for school staff, administrators, teachers, and students|Available to academic Volume License customers|
|Education|Comparable to Enterprise for school staff, administrators, teachers, and students|Available to academic Volume License customers|
|IoT Core/Enterprise|Fixed purpose and appliance devices|Available through Windows IoT Distributors|


