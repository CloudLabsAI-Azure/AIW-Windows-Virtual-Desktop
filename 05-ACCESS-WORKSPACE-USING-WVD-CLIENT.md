# **Exercise 6: Access the Published Applications/ Desktop using WVD Client**

WVD-Client is a remote desktop application through which we can connect to our windows virtual desktop environment.

## **Task 1: Access the Published Applications using WVD Client**

Now as we have published remote apps in previous exercises, now we will be accessing them using wvd-client.

1. Download the **WVD Client** on your local machine from the following [**Link**](https://docs.microsoft.com/en-us/azure/virtual-desktop/connect-windows-7-and-10) and install **Windows 64-bit** version by clicking on it.
   
   ![ws name.](media/a48.png)
   
   
2. Then open the setup and click **Next** on the Welcome page of setup.

3. Check the agreement box and click on **Next**.

4. On **Installation scope** window select **Install just for you** and then click on **Install**.

   ![ws name.](media/wvd41.png)

5. After installation, in your local machine go to **Start** and search for **Remote desktop** and open the application with exact icon as shown below.

   ![ws name.](media/137.png)
   
   
6. After the application opens click on **Subscribe**.

   ![ws name.](media/a49.png)
  
  
7. Enter your **credentials** to access the workspace.

   - Username: **<inject key="AzureAdUserEmail" />** *and then click on **Next**.*
   
   ![ws name.](media/95.png)

   - Password: **<inject key="AzureAdUserPassword" />** *and click on **Sign in**.*

   ![ws name.](media/96.png)
   
   
8. Make sure to uncheck **Allow my organization to manage my device** and click on **This app only**.

   ![ws name.](media/55.png)
   
   
9. Now click on any of the applications you want to access. Here we are selecting **Excel**. 

   ![ws name.](media/97.png)
   

10. Enter your **credentials** to access the Application.

   - Username: **<inject key="AzureAdUserEmail" />** 
   - Password: **<inject key="AzureAdUserPassword" />**
   
   ![ws name.](media/89.png)
   

11. Wait for your application to connect.

   ![ws name.](media/58.png)
   

12. Your Application will launch and will be ready to use.

    ![ws name.](media/59.png)
    
    
13. You can close this session now.


## **Task 2: Access the Workspace Desktop using WVD Client**

In this task we will be accessing the desktop type application named *WVD-HP-01-DAG* created by default when we created *WVD-HP-01* host pool using wvd-client.

1. In your local machine go to **start** and search for **Remote desktop** and open the Application with exact exact Icon as shown below.

   ![ws name.](media/51.png)

   
   
2. Now Click on **WVD-HP-01-DAG** Desktop to access it.

   ![ws name.](media/100.png)
   

3. Enter your **credentials** to access the Desktop.

   - Username: **<inject key="AzureAdUserEmail" />** 
   - Password: **<inject key="AzureAdUserPassword" />**
   
   ![ws name.](media/89.png)
   

4. Wait for your Desktop to connect.

   ![ws name.](media/62.png)
   

5. Your virtual Desktop will launch and it should be ready to use.
        
    ![ws name.](media/63.png)   
    
     
6. Click on the **Next** button.   
