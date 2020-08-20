# **Exercise 3: Create Host Pool from Azure Portal** 

 
Host pools are a collection of one or more identical virtual machines within Windows Virtual Desktop environment. Each host pool contains Application groups that users can interact with, as they would be on a physical desktop. 
 
### **Task 1: Create Host pool**

In this exercise, we will be creating a host pool named *WVD-HP-01* of pooled type, then adding two session hosts (virtual machines) i.e. *WVD-HP01-SH-0* and *WVD-HP01-SH-01*  and registering them under a new workspace named *WVD-WS-01*.

1. On **Azure portal** search for *Windows Virtual Desktop* in the search bar and select **Windows Virtual Desktop** from the suggestions.

   ![ws name.](media/w1.png)
 

2. You will get directed towards the Windows Virtual Desktop (hereafter referred to as WVD) management window.  

   ![ws name.](media/64.png)

3. Now select **Host pools** under **Manage** blade and then click on **+ Add** to add new Host Pool.

   ![ws name.](media/z.png)

4. In this step, we will provide the details required to create a Host Pool. For your convenience, this step is divided into two sections as follows:

 **A.** **Project Details –** Defines the environment 

   - Subscription: *Choose the default subscription*.
   - Resource Group: *Select **WVD-RG** from the drop down*.
   - Host Pool Name: **WVD-HP-01**
   - Location: **East US**, *basically this should be same as the region of your resource group*.      
   - Validation environmet: **No**
      
   >**Note:** Validation host pools let you monitor service updates before rolling them out to your production environment.
            
   ![ws name.](media/w9.png)
   
 **B.** **Host Pool Type –** Defines the type of host pool. 

   - Host pool type: **Pooled** 
      
   >**Note:** Host Pools are of 2 types: Pooled and Personal.  
   > - **Pooled** is used to share the same Session Host (Virtual Machine) resources among multiple users.
   > - **Personal** uses a dedicated Session host of individual users.

   - Max session Limit: **5**
      
   >**Note:** Max session Limit limits the simultaneous number of users on the same session host.
     
   - Load Balancing Algorithm: **Breadth First**
      
   >**Note:** Load Balancing Algorithm is of two types: *Breadth-first* and *Depth-first*. 
   > - **Breadth-first** load balancing distributes new user sessions across all available session hosts in the host pool. 
   > - **Depth-first** load balancing distributes new user sessions to an available session host with the highest number of connections but has not reached its maximum session limit threshold.
     
   - Then click on **Next:Virtual Machines**.
          
   ![ws name.](media/w10.png)  

5. In the Virtual machines tab, select **Yes** against **Add virtual machines**. By doing this, we are stepping towards adding Virtual machines to the host pool. 

   ![ws name.](media/66.png)

6. In this step, we will provide the details of the VMs to be created as session Hosts. For your convenience, this step is divided into three sections as follows:

  **A**. Session Host Specifications:     

   - Resource Group: *Select **WVD-RG** from the drop down*.
   - Virtual machine location: **East US**, *location should be same as location of your resource group*.
   - Virtual machine size: **Standard D1_v2**. *Click on **Change Size**, then select **D1_v2** and click on **Select** as shown below*
   
   ![ws name.](media/65.png)

   - Number of VMs: **2**   
   - Name prefix: **WVD-HP01-SH** 
   - Image type: **Gallery**
   - Image: **Windows 10 Enterprise multi-session, version 1909 + Microsoft 365 Apps** *(choose from dropdown)* 
   - OS disk type: **Standard SSD**
   - Use managed disks: *Leave to default*
   
   ![ws name.](media/ex3.png)
   
   
  **B**. Network and Security:
    Leave all values on default except:
    
   - Subnet: **sessionhosts-subnet(10.0.1.0/24)** *(choose from dropdown)*
   - Specify Domain or Unit: **No**
 
   ![ws name.](media/w3.png)
 
 **C**. Domain and Administrator account:
  
   - AD domain join UPN: *Paste your username* **<inject key="AzureAdUserEmail" />**
   - Password: *Paste the password* **<inject key="AzureAdUserPassword" />**
   - Confirm Password: *Paste the password* **<inject key="AzureAdUserPassword" />** *again.*
   
   ![ws name.](media/w2.png)
   
7. Click on **Next:Workspace** to proceed. 

8. In the Workspace section, we need to specify if we need to register the default application group to a workspace. 

   - Register desktop app group: *Choose* **Yes** 
   - To this workspace: *Click on* **Create new**

   ![ws name.](media/67.png)
   
9. Once you click on **Create new**, a small window pops up, where you can specify the Workspace name you are going to create.  

   - Workspace name: **WVD-WS-01** 
   - Click on **OK**
     
   ![ws name.](media/68.png) 

10. Now click on **Review + create** on the bottom left corner. 

    ![ws name.](media/69.png)


11. The last window helps us to verify if the parameters we filled are correct. Wait for validation to pass, then click on **Create** to initiate the deployment. 

    ![ws name.](media/70.png)

> **Note:** The deployment will take about 30 minutes to succeed.

12. Once the deployment gets succeeded, open notifications and click on **Go to Resource**.  

    ![ws name.](media/71.png)

> **Note:** In case you face deployment failure regarding Virtual Machine or any other resources under Host Pool, then follow the steps given below:

13. Go to your **WVD-RG** resource group.

    ![ws name.](media/w15.png)
 
14. Select the resources highlighted in the image below, then click on ellipsis in the top-right corner and click on delete.

    ![ws name.](media/w16.png)

15. Now under *Confirm delete* type **yes** in the bar and click on **Delete**.
 
    ![ws name.](media/w17.png)

16. Once the resources get deleted,then perform Task 1 from Step 1 to Step 11 to create the Host Pool again.

17. Now wait for the deployment to succeed. When it gets succeeded, open the notifications and click on **Go to Resource**.  

    ![ws name.](media/71.png) 

18. You will see that the host pool **WVD-HP-01** is created with two session hosts in it and a default application group (of type Desktop).  

    ![ws name.](media/85.png)


19. Click on **Session Hosts**. Notice the Session Hosts created, with a name concatenating the Name Prefix and increment number. 

    ![ws name.](media/86.png)

20. Click on the **Next** button present in the bottom-right corner of this lab guide.  
