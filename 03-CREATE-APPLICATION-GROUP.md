# **Exercise 4: Create Application Groups and assign to users** 

As explained in the General Hierarchy section, Application Group is a logical grouping of applications installed on session hosts in the host pool. They are of two types: 

1. Remote Application 
2. Desktop 

## **Task 1: Create Application Group**

An application group of type ‘Desktop’ was created automatically while creating the Session Host in previous exercise. Now in this task, we will create a new application group of ‘Remote application’ type named *WVD-AG-01* and then assigning your user account to it. Then we will publish two applications i.e. *Word* and *Excel* in the application group.

1. Navigate to Azure portal, then search for *Windows virtual* in search bar and select **Windows Virtual Desktop** from the suggestions.

   ![ws name.](media/a109.png)


2. You will be directed towards the Windows Virtual Desktop management window.  

   ![ws name.](media/64.png)


3. Click on the **Application Group** tab. You will see the default Application Group there. Note that the type is ‘Desktop’. Also, it is associated with the Host Pool **WVD-HP-01** we created before and to the workspace **WVD-WS-01**. 

   ![ws name.](media/23.png)
   
   
4. Click on **WVD-HP-01-DAG** application group.

   ![ws name.](media/91.png)
      
5. Under **Manage** blade, open **Assignments** and then click on **+ Add**. 

   ![ws name.](media/w4.png)   
 
6. Now in the search bar, copy and paste your username **<inject key="AzureAdUserEmail" />**. Then under the search bar, click on your username to select it.

   ![ws name.](media/w7.png)
   
7. At last click on **Select** button. 
 
   ![ws name.](media/w6.png) 
 
8. Once done then create a new Application Group of type ‘Remote Application’. For this navigate back to the **Application groups** and click on the **+ Add** button. 

   ![ws name.](media/a18.png)

9. Under the *Basics* section, fill the parameters as mentioned below: 

      - Subscription: *Select the default subscription*.
      - Resource Group: *Select **WVD-RG** from the drop down*.
      - Host Pool: **WVD-HP-01** (*this application group will be created under WVD-HP-01 hostpool*)
      - Location: **East US**, *this should be same as the region of your resource group*.
      - Application Group Type: **RemoteApp** 
      - Application Group Name: **WVD-AG-01**
      - Click on **Next:Assignments**

   ![ws name.](media/72.png)

10. In the assignments section, you can add the user whom should be given access to WVD solution on this application group. 

11. Click on the **+Add Azure AD users or user groups**, then copy and paste your username **<inject key="AzureAdUserEmail" />** in the search bar. When your username appears under the search bar, select it and then click on **Select** button.

   ![ws name.](media/88.png)

12. Now click on **Next:Applications**. 

   ![ws name.](media/110.png)


13. On the **Applications** section, click on **Add Applications** to publish applications in the Session Host. 

   ![ws name.](media/76.png)


14. In this window, choose the parameters as mentioned below: 

   - Application Source: **Start Menu**    
   - Application: **Excel**
   - Leave rest of the parameters to be on default settings and click on **Save**.
   
   ![ws name.](media/a34.png)
 
15. Click on **Add Application** again. 

   ![ws name.](media/31.png)

16. Choose the parameters as mentioned below: 

   - Application Source: **Start Menu**    
   - Application: **Word**   
   - Leave rest of the parameters to be on default settings and click on **Save**.

   ![ws name.](media/77.png)

17. Now click on **Next:Workspace**. 

   ![ws name.](media/78.png)

18. In the Workspace section, you choose if the Application Group should be registered now or later.  

   - Register Application Group: **Yes**
   - **WVD-WS-01** workspace will be selected by default, since the default ‘Desktop’ type application group on the same Session Host *(WVD-HP01-SH-01)* is registered to this workspace.

   ![ws name.](media/79.png)

19. Click on **Review + Create**

   ![ws name.](media/35.png)


20. You will get a provision to validate the settings in the validation page. If everything looks correct, click on **Create**. 

   ![ws name.](media/80.png)


21. Once the deployment is complete, open notifications and click on **Go to Resource**. 

   ![ws name.](media/81.png)


22. Now in the Application Group Window that comes up, click on **Applications** present under **Manage** and you will see that the applications are published in the application Group. 

   ![ws name.](media/82.png)

23. Click on the **Next** button.
