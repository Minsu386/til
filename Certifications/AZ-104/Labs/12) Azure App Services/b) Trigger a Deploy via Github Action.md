## Trigger a Deploy via Github Actions

Note: At ~5:30, Andrew accidentally names the file `staratup.txt`. The correct file name is supposed to be `startup.txt`

-   1.1
    
    References: [https://docs.microsoft.com/en-us/azure/app-service/quickstart-python?tabs=bash&pivots=python-framework-flask](https://docs.microsoft.com/en-us/azure/app-service/quickstart-python?tabs=bash&pivots=python-framework-flask)
    
    ✋
    

[https://docs.microsoft.com/en-us/azure/app-service/configure-language-python#container-startup-process?appservice=startup](https://docs.microsoft.com/en-us/azure/app-service/configure-language-python#container-startup-process?appservice=startup)

The steps from the previous video should be able to take you to the webpage. If you press **Browse**, you should be able to see a webpage with the text "Hello, World!"

![](https://images2.imgbox.com/96/a9/FhyzLTRP_o.png)

-   You should be able to see a webpage with the text "Hello, World!"

![](https://images2.imgbox.com/f6/52/bo1I6Sx0_o.png)

-   1.2
    
    You can go to the GitHub repo and click on **app.py**, to experiment with App Services, you can change the text to "Hello, Azure App Service!" (or any text you'd like)
    
    ✋
    

![](https://images2.imgbox.com/ec/07/ZJjlHnkK_o.png)

-   After changing the text and committing, it will deploy and update! (Which will take a moment ~2mins)

![](https://images2.imgbox.com/c5/31/aEMWS7dq_o.png)

-   1.3
    
    You can view the workflow in the "Actions" tab as well as the Deployment Center "Logs"
    
    ✋
    

![](https://images2.imgbox.com/4b/f2/GqsMm8v9_o.png)

-   1.4
    
    Click on "Browse" to see the newly updated website with "Hello, Azure App Service!"