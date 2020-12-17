
# Configuring Google OAuth account in webMethods.io Integration Workflow <br/>

## Summary:

This article describes configuring an OAuth account to **Google Pub/Sub** in **webMethods.io Workflow**<br/>

## Pre-requisites:
•	User needs to have a **Google** account<br/> 
•	Working **webMethods.io Integration** tenant<br/> 

## Contents:

Section 1: [Configure a **Google** OAuth](./Configure a **Google** OAuth) <br/> 
Section 2: Setting up a **Google** OAuth account in **webMethods.io Integration** tenant<br/> 

### Section 1. Configure a Google OAuth <br/>

1.  Login to [Google Console](https://console.cloud.google.com) with the username and password<br/>

2.  From the projects list, select a project from the dropdown or create a new one if required<br/>

![Google PubSub](images/21.png)<br/>

3. To use **Google Cloud API**, user must enable an **Google Cloud Pub/Sub API** for a project using console <br/>

    i. On the left, click on **Navigation Menu**<br/>
         
    ![Google PubSub](images/22.png)<br/>

    ii. Under **APIs & Services** choose **Library**, select the API and **enable** it.<br/>

    ![Google PubSub](images/18.png)<br/>


    ![Google PubSub](images/19.png)<br/>


    ![Google PubSub](images/20.png)<br/>

4.  If the APIs & services page isn't already open, open the console left side menu and select **APIs & Services**<br/>

5.  On the left, click **Credentials**<br/>

6.  Click **+ Create Credentials**, then select **OAuth client ID**<br/>

![Google PubSub](images/1.png)<br/>

7.  Select the appropriate application type (In this case application type is **web application**) for your project and enter any
    additional information required<br/>

![Google PubSub](images/23.png)<br/>

8.  Select **Authorized redirect URI's** and add the redirect URI as https://developers.google.com/oauthplayground and hit
    **Create**<br/>

![PubSub](images/24.png)<br/>

9.  Note down the **Client Id** and **Client Secret** created<br/>

10. Open the browser and point the browser to [Google Oauth Playground](https://developers.google.com/oauthplayground)<br/>

11. On the right corner of the page, click on gear icon and fill in OAuth Client ID and OAuth Client Secret generated
    (from Step 8) and click on Close<br/>

![PubSub](images/3.png)<br/>

12. On left side panel, select the scopes required<br/>

![PubSub](images/4.png)<br/>

13. Hit on **Authorize APIs**<br/>

![PubSub](images/5.png)<br/>

14. Click on **Exchange authorization code for tokens**<br/>

![PubSub](images/6.png)<br/>

15. Note down **Access Token** and **Refresh Token**<br/>

![PubSub](images/15.png)<br/>

### Section 2: Setting up Google OAuth account in webMethods.io Integration Workflow<br/>

16. Login to **webMethods.io Integration** tenant and choose your project or click on **"+"** to create new project<br/>

![PubSub](images/16.png)<br/>

17. Choose your workflow or click on **"+"** to create new workflow<br/>

![PubSub](images/7.png)<br/>

18. From the right-hand panel of connectors list. Drag and drop a **Google Cloud PubSub Connector**<br/>

![PubSub](images/8.png)<br/>

19. Click on gear icon on the connector and choose any predefined operation (Example: listTopics) and click on **"+"** to 
    add account<br/>

![PubSub](images/9.png)<br/>

20. Fill in the **Client Id**, **Client Secret** obtained from Step 8 and **Access Token**,**Refresh Token**  obtained from Step 14<br/>

    Refresh URL:  https://www.googleapis.com/oauth2/v4/token <br/>
    Grant_type :  refresh_token <br/>

![PubSub](images/10.png)<br/>

21. Click on **Add** and Hit **Next** and pass the required inputs (In this case “listTopics” requires projectId to be passed)<br/>

![PubSub](images/11.png)

22. Click on **Save** and **Run** the workflow<br/>

![PubSub](images/12.png)<br/>

![PubSub](images/13.png)<br/>
      

  
