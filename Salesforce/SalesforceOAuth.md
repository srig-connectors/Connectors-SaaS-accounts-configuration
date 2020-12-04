---
title: "Setting up Salesforce OAuth"
metaTitle: "Setting up Salesforce OAuth account | webMethods.io Integration Workflow"
metaDescription: "Setting up Salesforce OAuth account | webMethods.io Integration Workflow"
---

# Summary:
   
This article describes how to configure an OAuth account to Salesforce using webMethods.io workflow<br/> 

# Prerequisites:
•	User must have working tenant of SaaS application, in this case Salesforce<br/> 
•	Working webMethods.io tenant<br/> 

# Contents:

Section 1: Configure a SaaS application in Salesforce <br/> 
Section 2: Set up a Salesforce account in webMethods.io tenant<br/> 

### Section 1. Configure a SaaS application in Salesforce 
Steps 

 1. Login to [Salesforce.com](https://login.salesforce.com)<br/> 
 2. Click on account setup page and hit **switch to classic** and hit **setup**<br/>

![Salesforce](images/1.png)<br/>

 3. Search for **apps** in quick find box<br/>

![Salesforce](images/2.png)<br/>

 4. Add new connected app, name the app and fill in all necessary details like app name, email, callback url and add all scopes<br/>
 5. Check in **Enable OAuth Settings** option<br/>

![Salesforce](images/3.png)<br/>

![Salesforce](images/4.png)<br/>

![Salesforce](images/5.png)<br/>

 6. **Save** the application and click on **Next**. Allow the app to 10-20 mins for registration<br/>
 7. Note the **Client Id** and **Client Secret** generated<br/>

![Salesforce](images/6.png)<br/>

 8. Get authorization code using the url below in browser and **allow** the browser to login to your salesforce account<br/>
    https://ap16.salesforce.com/services/oauth2/authorize?client_id=<client_id> &redirect_uri=https://www.softwareag.com&<br/>
    response_type=code<br/>
    
    *Note :- Instance can be found from login url. Ex: ap15, ap16 etc.*<br/>

 9. To get access token and refresh token use the below url in any REST client <br/>
      *Note :- POSTMAN REST client is used here. Link to download [POSTMAN](https://www.postman.com/downloads/).*<br/>
     
      Url     : https://ap16.salesforce.com/services/oauth2/token<br/>
      Method  : POST<br/>
      Params  : code, client_id, client_secret,redirect_uri and grant_type<br/>
      Example : https://ap16.salesforce.com/services/oauth2/token?code=aPrx5xrKPFq2PGQVvFWARb6q3ZqTJaA%3D%3D&client_id=33AXP7P1Xg2UhM5WtAkS6FWoLnL27hKEnL_fBw8L5XxzU3gDuBGw_jbaBCQ_IRH7m4HPcWTh&client_secret=0FEA3069044194F115C8C2C24CD3F1DF24BB08F27043699A9AC67&redirect_uri=https://www.softwareag.com&grant_type=authorization_code<br/>

![Salesforce](images/r.png)<br/>

 ### Section 2. Set up an account in webMethods.io

 Steps

 10. Login to **webMethods.io** Integration tenant<br/>
 11. Choose your project or click on **"+"** to create new project<br/>

![Salesforce](images/c.png)<br/>

 12. Choose your workflow or click on **"+"** to create new workflow<br/>

![Salesforce](images/8.png)<br/>
 
 13. Name your workflow and then Drag and drop **Salesforce CRM** from the connector pallet and double click on 
     **Salesforce CRM**  connector to configure or hover over connector and click the settings icon<br/>

![Salesforce](images/9.png)<br/>

 14. Select Action and for **Add Custom Action** option click on **"+"** add<br/>

![Salesforce](images/10.png)<br/>

 15. Choose existing account or to create new account click on **"+"** add button<br/>

![Salesforce](images/11.png)<br/>

 16. Fill in details like **Client Id**, **Client Secret**, **Access Token**, **Refresh Token** obtained in previous steps<br/>  
     (Step 7 & Step 9 respectively) and also Grant Type, Refresh URL, Server URL and Instance URL<br/>
     
     *NOTE:- Server URL is different for SOAP and REST services. SOAP connector is used here.*<br/>

      Server URL        : https://ap16.salesforce.com/services/Soap/u/44.0 {SOAP}<br/> 
      Server URL        : https://ap16.salesforce.com {REST}<br/> 
      Grant Type        : refresh_token<br/> 
      Refresh URL       : https://login.salesforce.com/services/oauth2/token<br/> 
      Instance URL      : https://ap16.salesforce.com<br/> 

![Salesforce](images/12.png)<br/> 

![Salesforce](images/13.png)<br/> 

17. Hit **Add** to save the connection<br/> 



