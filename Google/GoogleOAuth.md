---
title: "Setting up Google OAuth"
metaTitle: "Setting up Google OAuth account | webMethods.io Integration Workflow"
metaDescription: "Setting up Google OAuth account | webMethods.io Integration Workflow"
---

This tutorial describes configuring an oauth account to google pubsub in webMethods.io Workflow

# Setting up Google OAuth 2.0

1.  Login to [Google Console](https://console.cloud.google.com) with the username and password<br/>
2.  From the projects list, select a project or create a new one<br/>
3.  If the APIs & services page isn't already open, open the console left side menu and select "APIs & services"<br/>
4.  On the left, click Credentials<br/>
5.  Click New Credentials, then select OAuth client ID<br/>
![Google PubSub](images/1.png)
6.  Select the appropriate application type (In this case application type is “web application”) for your project and enter any
    additional information required<br/>
7.  Select “Authorized redirect URI’s” and add the redirect Uri as https://developers.google.com/oauthplayground<br/>
![PubSub](images/2.png)
8.  Hit “Create” the application. And note down the Client Id and Client Secret created<br/>
9.  Open the browser and point the browser to [Google Oauth Playground](https://developers.google.com/oauthplayground)<br/>
10. On the right corner of the page, click on gear icon and fill in OAuth Client ID and OAuth Client Secret and close<br/>
![PubSub](images/3.png)
11. On left side panel, select the scopes required<br/>
![PubSub](images/4.png)
12. Hit on “Authorize API’s”<br/>
![PubSub](images/5.png)
13. Select “Exchange authorization code for tokens”<br/>
![PubSub](images/6.png)
14. Note down “Access Token” and “Refresh Token”<br/>
![PubSub](images/14.png)

# Setting up Google OAuth account in webMethods.io Integration Workflow

15. Login to wMio Integration tenant and choose your project or click on “+” to create new project<br/>
![PubSub](images/7.png)
16. Select “Create New WorkFlow”
17. From the right-hand panel of connectors list. Drag and drop a “Google PubSub Connector”<br/>
![PubSub](images/8.png)
18. Click on gear icon on the connector and choose any predefined operation (Ex: listTopics) and click on "+" to add account<br/>
![PubSub](images/9.png)
19. Fill in the Client Id, Client Secret obtained from Step 8 and Access Token ,Refresh Token  obtained from Step 14<br/>
    Refresh URL:  https://www.googleapis.com/oauth2/v4/token <br/>
    Grant_type :  refresh_token <br/>
![PubSub](images/10.png)
20. Click on “Add” and Hit “Next” and pass the required inputs (In this case “listTopics” requires projectId to be passed)<br/>
![PubSub](images/11.png)
21. Click on “Save” to run the workflow<br/>
![PubSub](images/12.png)
![PubSub](images/13.png)
      

  
