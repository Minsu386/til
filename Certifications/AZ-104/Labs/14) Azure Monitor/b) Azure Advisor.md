## Azure Advisor Lab Notes (Updated Sep 2025)

### Prerequisites

-   Read access to an Azure subscription with deployed resources.

### Step 1: Open & Explore Azure Advisor

-   1.1
    
    Log in to Azure portal: [https://portal.azure.com/](https://portal.azure.com/)
    
    ✋
    
-   1.2
    
    Search for **Advisor** in the top search bar, select it.
    
    ✋
    
-   1.3
    
    On the **Advisor** overview/dashboard, ensure the categories are visible: **Cost**, **Security**, **Reliability**, **Performance**, **Operational Excellence**.
    
    ✋
    
-   1.4
    
    If you have multiple subscriptions, use the **Directory + subscription** filter (top right) to select the subscription(s) of interest.
    
    ✋
    

### Step 2: Explore Reliability & Workbook

-   2.1
    
    Select the **Reliability** tab (or tile) to view current reliability recommendations.
    
    ✋
    
-   2.2
    
    Notice the new **Reliability workbook template** (left menu under Advisor → Workbooks). Open it. Use its filters (subscription, resource group, tag) to focus on areas you care about. This gives a consolidated best-practice and risk checklist.
    
    ✋
    

### Step 3: Review Individual Recommendation

-   3.1
    
    From Reliability (or any category), click a recommendation (e.g. “Create an Azure Service Health alert” or similar).
    
    ✋
    
-   3.2
    
    On the **Recommendation details**, review:
    
    ✋
    
-   Description / what is being recommended
-   Why it exists (the risk / reliability goal)
-   Impact (High / Medium / Low)
-   Impacted resources (e.g. “1 subscription”, or specific resources)
-   Whether this recommendation contributes to improving your Advisor Score.

### Step 4: New Alerts & Notifications

-   4.1
    
    Instead of (or in addition to) creating a specific alert for a recommendation, note that you can **create alerts for any new Advisor recommendations** to proactively monitor when new items appear. This uses the activity log.
    
    ✋
    
-   4.2
    
    Also, look for **Advisor notifications / reminders** on the dashboard, often surfaced when there are outstanding recommendations or upcoming events (maintenance, outages).
    
    ✋
    

### Step 5: Apply / Postpone / Dismiss

-   5.1
    
    For a selected recommendation:
    
    ✋
    
-   Apply it (e.g. configure the service health alert, adjust configuration, etc.)
-   Or **Postpone/Snooze** (if available)
-   Or **Dismiss** if it's not relevant.
-   5.2
    
    After applying, wait a bit and then check that the recommendation status has changed (often to _Resolved_ or _Completed_). Also ensure that whatever you configured (e.g. alert, service) is operational.
    
    ✋
    

### Step 6: Verify & Clean Up

-   6.1
    
    Back in the Advisor Reliability (or relevant) category, verify that the status reflects your action (resolved/dismissed/postponed).
    
    ✋
    
-   6.2
    
    Go to **Monitor → Alerts** (if you created any) to ensure alerts are active.
    
    ✋
    
-   6.3
    
    If you created test resources/workbooks/alerts not needed afterward, delete them to avoid cost or noise.
    
    ✋
    

#### Section 7: Optional – Cost / Performance etc.

-   Explore other categories (Cost, Performance, Security, Operational Excellence) similarly.
-   In Cost, check what savings Advisor suggests; in Performance, see optimizations; etc.
-   Check **Advisor Score** (if available) to see how much you can improve by implementing recommendations.

### Reference

-   [Introduction to Azure Advisor](https://learn.microsoft.com/en-us/azure/advisor/advisor-overview)
-   [Reduce service costs by using Azure Advisor](https://learn.microsoft.com/en-us/azure/advisor/advisor-cost-recommendations)
-   [Advisor score](https://learn.microsoft.com/azure/advisor/advisor-score)