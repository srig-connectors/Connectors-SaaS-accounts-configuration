# Register Dynamics CRM App with Azure for OAuth 2.0 Authentication <br/>

## Summary <br/>

  This article describes the step-by-step process of registering Microsoft Dynamics CRM application with Azure Active Directory and generating the    Access token and configuring the account in webMethods.io Integration. <br/>

## Prerequisites <br/>

The user needs to have a working Microsoft Azure Active Directory and a Microsoft Dynamics CRM License to access the API. <br/>
Working webMethods.io Integration cloud tenant.

## Contents <br/>

1. Create and Configure the App in Microsoft Azure Active Directory. <br/>
2. Generate the Access_token and Resfresh_token using the REST Client. <br/>
3. Configuring the Microsoft Dynamics CRM ACcount in webMethods.io Integration. <br/>

## Steps <br/>

  1. Login to [Azure Portal](https://portal.azure.com/) (Use the same credentials as your dynamics CRM, if it asks you to sign up and set up a trial, you can do that)
  <br/>

  2. Once you have logged in, navigate to the option “Azure Active Directory” and click on “**App registration**”. <br/>

  ![\MicrosoftDynamicsCRM](images/1.png) <br/>