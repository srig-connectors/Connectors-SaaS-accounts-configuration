---
title: "Setting up Google OAuth"
metaTitle: "Setting up Google OAuth account | webMethods.io Integration Workflow"
metaDescription: "Setting up Google OAuth account | webMethods.io Integration Workflow"
---

This tutorial describes configuring an OAuth account to google pubsub in webMethods.io Workflow<br/>

# Setting up Google OAuth 2.0<br/>

1.  Login to [Google Console](https://console.cloud.google.com) with the username and password<br/>
2.  From the projects list, select a project from the dropdown or create a new one if required<br/>

![Google PubSub](images/p.png)<br/>

3.  If the APIs & services page isn't already open, open the console left side menu and select **APIs & Services**<br/>
4.  On the left, click **Credentials**<br/>
5.  Click **+ Create Credentials**, then select **OAuth client ID**<br/>

![Google PubSub](images/1.png)<br/>

6.  Select the appropriate application type (In this case application type is **web application**) for your project and enter any
    additional information required<br/>
7.  Select **Authorized redirect URI** and add the redirect URI as https://developers.google.com/oauthplayground and hit
    **Create**<br/>

![PubSub](images/2.png)<br/>

8.  Note down the **Client Id** and **Client Secret** created<br/>
9.  Open the browser and point the browser to [Google Oauth Playground](https://developers.google.com/oauthplayground)<br/>
10. On the right corner of the page, click on gear icon and fill in OAuth Client ID and OAuth Client Secret generated
    (from Step 8) and click on close<br/>

![PubSub](images/3.png)<br/>

11. On left side panel, select the scopes required<br/>

![PubSub](images/4.png)<br/>

12. Hit on **Authorize API's**<br/>

![PubSub](images/5.png)<br/>

13. Click on **Exchange authorization code for tokens**<br/>

![PubSub](images/6.png)<br/>

14. Note down **Access Token** and **Refresh Token**<br/>

![PubSub](images/a.png)<br/>

# Setting up Google OAuth account in webMethods.io Integration Workflow<br/>

15. Login to **wM.io** Integration tenant and choose your project or click on **“+”** to create new project<br/>

![PubSub](images/c.png)<br/>

16. Choose your workflow or click on **“+”** to create new workflow<br/>

![PubSub](images/7.png)<br/>

17. From the right-hand panel of connectors list. Drag and drop a **Google Cloud PubSub Connector**<br/>

![PubSub](images/8.png)<br/>

18. Click on gear icon on the connector and choose any predefined operation (Example: listTopics) and click on **+** to add account<br/>

![PubSub](images/9.png)<br/>

19. Fill in the Client Id, Client Secret obtained from Step 8 and Access Token,Refresh Token  obtained from Step 14<br/>
    Refresh URL:  https://www.googleapis.com/oauth2/v4/token <br/>
    Grant_type :  refresh_token <br/>

![PubSub](images/10.png)<br/>

20. Click on **Add** and Hit **Next** and pass the required inputs (In this case “listTopics” requires projectId to be passed)<br/>

![PubSub](images/11.png)

21. Click on **Save** and **Run** the workflow<br/>

![PubSub](images/12.png)<br/>
![PubSub](images/13.png)<br/>
      

  
