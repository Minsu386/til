## Create Deployment Slots

**Section 1 - Create a Deployment Slot**

-   1.1
    
    Go to Deployment Slots, Click **Upgrade**, in the Productions Tab, Click on "See additional options" and Choose:
    
    ✋
    
-   **S1**
-   100 total ACU
-   1.75 GB memory
-   A-Series compute equivalent

Click **Apply**

-   1.2
    
    Click on Deployment Slots, Click +Add Slot
    
    ✋
    
-   Name: staging
-   Clone settings from: voyager-delta-flyer (name of your App Service), Click Add
-   1.3
    
    Click on voyager-delta-flyer-staging, if you click Browse, you will see nothing is deployed.
    
    ✋
    

**Section 2 - Create a new branch for staging and have two different deployments running ready for swap**

-   2.1
    
    At the GitHub repo, Create a new branch called **staging**
    
    ✋
    

![](https://images2.imgbox.com/2b/d9/piWCywW8_o.png)

-   2.2
    
    Go into the **app.py** file, and edit the text to "Hello, Klingons!", and Commit.
    
    ✋
    

![](https://images2.imgbox.com/b0/33/1aa9plHY_o.png)

-   2.3
    
    Go to your voyager-delta-flyer-staging, Enter in the settings of GitHub. Organization, Repository: **python-docs-hello-world**, Branch: **staging**. Build: **Python**, Click Save!
    
    ✋
    
-   You should now have two deployments running (or your own unique name) e.g.
-   [https://voyager-delta-flyer.azurewebsites.net/](https://voyager-delta-flyer.azurewebsites.net/)
-   [https://voyager-delta-flyer-staging.azurewebsites.net/](https://voyager-delta-flyer-staging.azurewebsites.net/)

![](https://images2.imgbox.com/c3/74/jwJDD5sa_o.png)

![](https://images2.imgbox.com/bf/95/1GRhQHpx_o.png)

**Section 3 - Swap**

-   3.1
    
    In your Deployment Slots - voyager-delta-flyer-staging, Click "Swap", **Source**: voyager-delta-flyer-staging, **Target**: voyager-delta-flyer, Click **Swap**
    
    ✋
    
-   Very useful in providing updates or making changes in different environments with a team or individually with no downtime!
-   3.2
    
    Go to Deployment Slots - voyager-delta-flyer, you can modify the Traffic by entering in 50 for staging, it will make the main also 50.
    
    ✋
    

![](https://images2.imgbox.com/4c/b7/LD2V20tO_o.png)