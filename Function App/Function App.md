# Function App Deployment Manual
## Objective :
In this lab, you will create an Azure Function App using the Azure Portal. This hands-on exercise guides you through the essential steps to deploy a serverless compute resource in Azure. By the end of the lab, you will understand how to configure a Function App, deploy and test a simple function, and manage basic settings. You will also gain foundational knowledge of Azure’s serverless architecture and its event-driven execution model.

## Tasks :
1. Creating an Azure Storage Account via the Azure Portal — this storage account will be used to support the function app's infrastructure.

2. Creating an Azure Function App from within Visual Studio Code, including configuring the runtime and environment.

3. Developing a Blob Trigger function locally in VS Code.

4. Deploying the function to Azure directly from Visual Studio Code, validating successful integration with the storage account.

### Task 1 : Create an Azure Storage Account
 1. Go to [Azure Portal](https://login.microsoftonline.com/organizations/oauth2/v2.0/authorize?redirect_uri=https%3A%2F%2Fportal.azure.com%2Fsignin%2Findex%2F&response_type=code%20id_token&scope=https%3A%2F%2Fmanagement.core.windows.net%2F%2Fuser_impersonation%20openid%20email%20profile&state=OpenIdConnect.AuthenticationProperties%3DqsxJ_h_KR0vAGL38j_E6NEOfPT89BBzyfiaJd0o_aZu89ZU2BfV4d-NjF3ckuwbcbNd9ZSmbNrLyTPsB0rWUflEMhXiSYwxIx3zGyeejW01DZjYmyLhfxqeDyW8DpNNkB0jaNXoEnvqCG4atochKbS-G-SCu7pXezUSIJyPQfYzAj3el_P5qyHPEM5WTTmnA&response_mode=form_post&nonce=638816784146084860.NGNhODI3MmUtOTc2ZS00NTA5LTkwM2YtMGVjZjg2ZmMxMDYwMjc0YmJmNTktMWJmZS00NzczLWE5MjItNTM3OTNkZTBmNmI0&client_id=c44b4083-3bb0-49c1-b47d-974e53cbdf3c&site_id=501430&prompt=select_account&client-request-id=90700cc0-64fe-4d3d-8694-5c55fe4ca558&x-client-SKU=ID_NET472&x-client-ver=8.3.0.0).  

 2. Enter your Azure **Email Address (1)**, Click on **Next (2)** to Sign in.

    ![login](task1-1.png)  

 3. On the Azure portal, click on search bar, search for **Storage Account (1)**, and select **Storage Account (2)**.  

    ![sa](task1-2.png)  

 4. Click on **Create (1)** to create a storage account.  
  
    ![sa1](task1-3.png)  
 
 5. Fill the following details:  
    | Type | Value |
    |:---:|:---:| 
    | Resource Group | **anand.shekhawat02 (1)**|  
    |Storage account name | **anandlabs147 (2)**|
    |Region|**Canada Central (3)**|

    ![sa2](task1-4.png)  

6. |Type | Value|  
    |:---:|:---:|
    |Primary Service|**Azure Blob Storage (4)**|
    |Performance|**Standard (5)**|
    |Redundancy|**LRS (6)**|
    
    Click **Review + Create (7)**.
    ![sa3](task1-5.png)

7. Click on **Create (8)** to create the storage account.

    ![sa4](task1-6.png)

8. After the deployment, Click on **Go to resource (9)**, to go to storage account.  

    ![sa5](task1-7.png)

9. From the left panel, use Drop-down of **Data Storage (1)**, Click on **Container (2)**.
    
    ![sa6](task1-8.png)

10. To create Container click on **Container (3)**.  

    ![sa7](task1-9.png)

11. Provide the name of container as **Container (1)**. Click on **Create (2)**.  

    ![sa8](task1-10.png)

### Task 2 : Create and Deploy Function App  
1. From the desktop, open **Visual Studio Code (1)**.
    
    ![fa1](vscode1.png)  

2. From the Activity Bar on the left, select **Extensions(1)** and using the Search Bar, look for the **Azure Functions (2)** extension and click on **Install (3)**.

    ![fa2](task2-1.png)

3. In the same manner, click on **Install (5)** for **Azure Resources (4)** extension as well.

    ![fa3](task2-2.png)

4. From the Activity Bar on the left side, select **Azure (1)**.

    ![fa4](task2-3.png)  

5. Select **Sign in to Azure (2)** from the Resources drop-down to sign in to your Azure account.  

    ![fa5](task2-4.png)

6. From the Pop-up windows, Select **Allow (1)** to sign in using Microsoft.  
 
    ![fa6](task2-5.png)

7. Enter your Azure **Email Address (1)**, Click on **Next (2)** to Sign in.

    ![fa7](task2-6.png)  

8. In Resources, right-click on **Function App (1)**, select **Create Function App in Azure (2)**.

    ![fa8](task2-7.png)

9. Enter name as **blobtriggeredfunctionapp (3)** for the new Function app.

    ![fa9](task2-8.png)

10. Select the location **Sweden Central (4)** for the Function app.

    ![fa10](task2-9.png)

11. Select the runtime stack as **Python 3.11 (5)**.

    ![fa11](task2-10.png)

12. Select **2048 (6)** as the instance memory size for function app.

    ![fa12](task2-11.png)

13. Enter **100 (7)** as the maximum instance count.

    ![fa13](task2-12.png)

### Task 3 : Create and Deploy Function 

1. In the VS Code, Press **F1** and search **Create Function (1)**, and select **Azure Functions: Create Function (2)**.

    ![f1](task3-1.png)

2. Select the folder **blob function (3)**, this folder will contain the function.

    ![f2](task3-2.png)

3. Select **Python (4)** as a language. 

    ![f3](task3-3.png)

4. Select **Skip Virtual environment (5)**.

    ![f4](task3-4.png)

5. Select **Blob trigger (6)** as the template for the function.

    ![f5](task3-5.png)

6. Give this function name as **blobtriggerfunc (7)**.

    ![f6](task3-6.png)

7. Provide **Container/{name}.png (8)** as the path in the storage account that trigger will monitor.

    ![f7](task3-7.png)

8. Click on **Create new local app setting (9)**.
    
    ![f8](task3-8.png)

9. Select **Innova8 Training (10)** as the subscription.

    ![f9](task3-9.png)

10. Select **Azurite emulator for local storage (11)**.

    ![f10](task3-10.png)

11. Open Azure Portal, and storage account. In drop-down of **Security + Networking (1)**, select **Access keys (2)**.

    ![f11](task3-11.png)

12. Copy the **Connection String (3)**.

    ![f12](task3-12.png)

13. Go back to VS code and local.settings.json, Paste the connection string in **AzureWebJobsStorage (1)**.

    ![f13](task3-13(1).png)

14. From the Activity bar on the left, go to **Azure (1)**.

    ![f14](task3-14(1).png)

15. From the workspace, right click on **Local Project (2)**, and select **Deploy to Azure (3)**.

    ![f15](task3-15(1).png)

16. Select **Innova8 Training (1)** as a subscription.

    ![f16](task3-16(1).png)

17. Select the Function app which we created earlier **blobtriggeredfunctionapp147 (2)** to deploy our function.

    ![f17](task3-17.png)

18. From the Pop-up window, click on **Deploy (1)**.

    ![f18](task3-18.png)

19. Function Deployed Successfully.

    ![f19](task3-19.png)

### Task 4 : Testing the Function App

1. Go to Azure Portal, and search for **Function App (1)**, click on **Fucntion App (2)**.

    ![t1](task4-1.png)

2. From the list of Function Apps, select **blobtriggeredfunctionapp (1)**.

    ![t2](task4-2.png)

3. In the new Tab, open Storage Account and **upload (1)** a .png file to the blob container.

    ![t3](task4-3.png)

4. From the pop-up window, click on **Browse for files**.

    ![t4](task4-4.png)

5. From the Pop-up windows, **select (1)** the .png file you want to upload and click on **Open (2)**.

    ![t5](task4-5.png)

6. Click on the **Upload (1)**.

    ![t6](task4-6.png)

7. From the Left tab in Azure Function App go to the Settings and click on **Environment Variable (1)**.
    
    ![t7](task4-7.png)

8. Click on **Add (2)**, to add an environment variable.

    ![t7](task4-8.png)

9. Click on **Add (2)**. 

    ![t9](task4-9.png)

10. In the Add/Edit application setting window, add name **AzureWebJobsStorage (1)**, in the value add **Connection String (2)** we copied from storage account, click on **Apply (3)**.  

    ![t12](task4-10.png)    

10. Go to the Azure Function App tab in the browser, in the Overview tab, go to Function **blobtriggerfunc (1)**.

    ![t10](task4-7.png)

11. In the logs, we can see the function getting triggered.
    
    ![t11](task4-11.jpg)