## Create a Tenant in Microsoft Entra ID Lab Notes

#### Goal

Learn how to create a new Microsoft Entra ID tenant (formerly known as Azure Active Directory tenant) to logically separate identities and manage access for different organizations or environments.

#### Prerequisites

- An active **Azure account** with permissions to create a Microsoft Entra tenant (typically a global administrator).
- Access to the [Azure portal](https://portal.azure.com/).

### Step 1: Sign in to the Azure Portal

- 1.1
    
     Visit: [https://portal.azure.com](https://portal.azure.com)
    
- 1.2
    
    Sign in using your Microsoft credentials.
    

### Step 2: Navigate to Microsoft Entra ID

- 2.1
    
    In the left-hand navigation menu (or use the search bar), type and click on **"Microsoft Entra ID"**.
    

### Step 3: Create a New Tenant

- 3.1
    
    From the Microsoft Entra overview page, select **"Manage tenants"** (top of the page).
    
- 3.2
    
    Click the **"+ Create"** button.
    

### Step 4: Choose Tenant Type

You will see two options:

- **Microsoft Entra ID** (Recommended) – For Business-to-Business (B2B) or internal organization use.
- **Microsoft Entra External ID** – For Business-to-Consumer (B2C) scenarios (e.g., customer-facing applications).
- 4.1
    
    **Select**: **Microsoft Entra ID**  
    
- 4.2
    
    Click **"Next: Configuration"**.
    

### Step 5: Configure Tenant Details

- 5.1
    
    Fill in the following fields:
    
- **Organization name**: e.g., `Starfleet`
- **Initial domain name**: Must be unique across Microsoft (e.g., `starfleet1984.onmicrosoft.com`)
- **Country or region**: Select your preferred location (e.g., `Canada`) > 🔍 _Note: This affects compliance and regulatory settings, not the data center region directly._
- 5.2
    
    Click **"Next: Review + Create"**.
    

### Step 6: Review and Create

- 6.1
    
    Review the configuration settings.
    
- 6.2
    
    Click **"Create"** to deploy the new tenant.
    
- 6.3
    
    Wait for the creation process to complete (takes less than a minute).
    

### Step 7: Switch to the New Tenant

- 7.1
    
    After creation:
    
- A banner will appear at the top with an option to **switch directories**.
- Click **"here"** in the banner or manually switch tenants by selecting your account in the top-right corner → **Switch directory** → choose your new tenant.

#### Result:

You have successfully created a new Microsoft Entra tenant (formerly Azure AD). You can now manage users, groups, roles, and integrate identity for your apps or organization.
 