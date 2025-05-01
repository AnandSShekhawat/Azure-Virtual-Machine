# App Service Deployment Manual

## Objective
Deploy a simple Flask web application with HTML templates to Azure App Service directly from Visual Studio Code using the Azure App Service extension. This guide helps developers set up the project structure, and deploy the app, ensuring it runs smoothly as a publicly accessible web service on Azure.

## Task 1: Deployment through VS Code
In this Exercise we will be first configuring the VS code and then deploy our Web App using the VS Code.  

1. From the Desktop, open **Visual Studio Code (1)**.    
   ![0th](vscode1.png)


2. From the Activity Bar on the left, select **Extensions(1)** and using the **Search Bar**, look for the **Azure App Service (2)**       extension and click on **Install (3)**.
   
   ![1st](vs-code1.png)


3. In the same manner, click on **Install (4)** for **Azure Resources** extension as well.    

   ![3nd](vs-code3.png)


4. From the Activity Bar on the left side, select **Azure (1)**.  

   ![4th](vs-code4.png)


5. Select **Sign in to Azure (2)** from the Resources drop-down to sign in to your Azure account.  

   ![5th](vs-code5.png)


6. From the Pop-up windows, Select **Allow (1)** to sign in using Microsoft.   

   ![6th](vs-code6.png)


7. Enter your Azure **Email Address (1)**, Click on **Next (2)** to Sign in.  

   ![7th](vs-code7.png)


8. After Sign in to Azure Account, Select **App Services (1)** from the Resources and click on **Create New Web App (2)**.  

   ![8th](vs-code8.png)


9. Select a location for your app service as **Southeast East (3)**.  

   ![9th](vs-code9.png)


10. Provide a unique name for your Web App, **myapp-latest (4)**.  

   ![10th](vs-code10.png)


11. Select a runtime stack for your web app as **Python 3.9 (5)**.  

   ![11th](vs-code11.png)


12. Select the Pricing Tier as **Basic (B1) (6)**.  

   ![12th](vs-code12.png)


13. From the Pop-up window, click on **Deploy (1)** to deploy your web app on azure.  

   ![13th](vs-code13.png)


14. Navigate to the folder which contains the code and other required files i.e., **myapp (1)**.  

   ![14th](vs-code14.png)


15. In the Pop-up window, click on **Deploy (1)**.  

   ![15th](vs-code15.png)


16. After the deployment has completed, Click on **Browse Website (1)** from the Pop-up window.  

   ![16th](vs-code16.png)


17. Your Web App will open in a new tab on the browser.    
 ![17th](app-webpage3.png)  


