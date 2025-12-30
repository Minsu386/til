## How to Set Up and Activate the Microsoft Authenticator App

_Updated for Microsoft Entra ID – formerly Azure Active Directory_

### Step 1: Enable the Microsoft Authenticator App

- 1.1
    
    Access the Entra Admin Center  
    
- In your web browser, visit: [https://entra.microsoft.com](https://entra.microsoft.com) or go to [https://portal.azure.com](https://portal.azure.com) and search for **Microsoft Entra ID**.  
    
- Sign in with a **Global Administrator** or **Authentication Administrator** account.
- 1.2
    
    Locate User Settings  
    
- In the **Microsoft Entra admin center**, navigate to:  
    **Users → All Users**  
    
- Locate the user you want to enable for MFA (e.g., _Kevin Uxbridge_).  
    
- Click the **user’s name** to open the user profile.
- 1.3
    
    Enable Multi-Factor Authentication (MFA)  
    
- From the toolbar, select **Authentication methods → Require re-register MFA** if needed.  
    
- Alternatively, in the **Security → Authentication methods** page, you can **enforce registration** for all or selected users.  
    
- To configure the default method, open:  
    **Microsoft Entra ID → Protection → Authentication methods → Policies**  
    
- Ensure the **Microsoft Authenticator** method is **enabled** for users or groups.  
    
- You can choose **All users** or specific **groups**.
- 1.4
    
    Set User Settings (Optional)  
    
- Return to the user’s profile.  
    
- Under **Manage → Authentication methods**, click **Add authentication method**.  
    
- Choose **Microsoft Authenticator** from the dropdown list.  
    
- Click **Add**.  
    
- The user will be prompted to register the Microsoft Authenticator app during the next sign-in.
- 1.5
    
    User Registration  
    
- Download and install the **Microsoft Authenticator** app on their mobile device.  
    - Available from the **App Store (iOS)** or **Google Play Store (Android)**.  
        
- Open the app and sign in with their **work or school account**.  
    
- Follow the prompts to **scan the QR code** displayed during login at [https://aka.ms/mfasetup](https://aka.ms/mfasetup).  
    
- Approve the test notification to confirm setup.
- 1.6
    
    Confirm MFA Enforcement  
    
- After the user completes registration, go back to **Users → Multi-Factor Authentication**.  
    
- Verify that the user’s **MFA status** is set to **Enabled** or **Enforced**.

## Step 2: Bulk Update MFA Settings

- 2.1
    
    Download and Prepare the Bulk CSV Template  
    
- In the **Microsoft Entra admin center**, go to:  
    **Users → Multi-Factor Authentication → Bulk Operations**.  
    
- Click **Bulk update**.  
    
- Download the **CSV template** file.
- 2.2
    
    Populate the Template  
    
- Open the CSV file in Excel or another editor.  
    
- Enter each user’s **User Principal Name (UPN)** and **MFA status** (Enabled, Enforced, or Disabled).

Example:

```
UserPrincipalName, MFAStatus
kevin.uxbridge@contoso.com, Enabled
wanda.maximoff@contoso.com, Enabled
```

- 2.3
    
    Upload and Apply Bulk Changes  
    
- Return to the **Bulk update** page.  
    
- Click **Browse** and select your completed CSV file.  
    
- Click **Submit** or the **Next arrow** to apply the update.  
    
- Once processed, the listed users will be updated to the specified **MFA status**.
- 2.4
    
    Verify Bulk Update  
    
- Navigate back to **Users → Multi-Factor Authentication**.  
    
- Confirm that all users listed in your CSV file now show the intended MFA status.

## Step 3: Best Practices and Additional Notes

- **Microsoft Entra ID** is the new name for **Azure Active Directory (Azure AD)**. The functionality is unchanged.  
    
- Use **Conditional Access policies** under **Protection → Conditional Access** to require MFA based on sign-in risk, location, or device compliance.  
    
- Consider enabling **combined registration** for MFA and self-service password reset (SSPR) to streamline user onboarding:  
    [https://aka.ms/setupsecurityinfo](https://aka.ms/setupsecurityinfo)  
    
- Encourage users to configure a **backup authentication method** (e.g., phone number or email).  
    
- Regularly review **Sign-in logs → Security → Multi-Factor Auth status** to ensure compliance.

### Outcome:

MFA is successfully enabled for your users via Microsoft Entra ID, and users have registered the Microsoft Authenticator app for secure sign-ins.

[Mass Import](https://app.exampro.co/student/material/az-104/2483)

[Self-Service Rest Password](https://app.exampro.co/student/material/az-104/2485)