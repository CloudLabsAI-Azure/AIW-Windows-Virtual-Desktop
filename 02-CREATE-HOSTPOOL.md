# **Exercise 3: Create Host Pool from Azure Portal** 

 
Host pools are a collection of one or more identical virtual machines within Windows Virtual Desktop environments. Each host pool can contain an app group that users can interact with as they would on a physical desktop. 
 
### **Task 1: Create Host pool**

In this exercise we will be creating a host pool named *WVD-HP-01* of pooled type and add two session hosts (virtual machines) i.e. *WVD-HP01-SH-0* and *WVD-HP01-SH-01*  then register them under a new workspace named *WVD-WS-01*.

1. On **Azure portal** search for *Windows virtual* in the search bar and select **Windows Virtual Desktop** from the suggestions.

   ![ws name.](media/a109.png)
 

2. You will be directed towards the Windows Virtual Desktop (hereafter referred as WVD) management window.  

   ![ws name.](media/64.png)


3. Now select **Host pools** under **Manage** blade and then click on **+ Add** to add new Host Pool.

   ![ws name.](media/z.png)


4. Creating a Host Pool is divided into multiple sections. The first one is the Basic section. All the fields in this section are explained below along with the values: 

 **A.** **Project Details –** Defines the environment 

   - Subscription: *Choose the default subscription*.
   - Resource Group: *Select **WVD-RG** from the drop down*.
   - Host Pool Name: **WVD-HP-01**
   - Location: **East US**, *basically this should be same as the region of your resource group*.      
   - Validation environmet: **No**
      
   >**Note:** Validation host pools let you monitor service updates before rolling them out to your production environment.
            
            
 **B.** **Host Pool Type –** Defines the type of host pool. 

   - Host pool type: **Pooled** 
      
   >**Note:** Host Pools are of 2 types: Pooled and Personal.  
   > **Pooled** is used to share the same Session Host (Virtual Machine) resources among multiple users.
   > **Personal** uses a dedicated Session host of individual user.

   - Max session Limit: **5**
      
   >**Note:** Max session Limit limits the simultaneous number of users on the same session host.
     
   - Load Balancing Algorithm: **Breadth First**
      
   >**Note:** Load Balancing Algorithm are of 2 types: *Breadth-first* and *Depth-first*. 
   > - **Breadth-first** load balancing distributes new user sessions across all available session hosts in the host pool. 
   > - **Depth-first** load balancing distributes new user sessions to an available session host with the highest number of connections but has not reached its maximum session limit threshold.
     
   - Then click on **Next:Virtual Machines**.
          
   ![ws name.](media/a1.png)  

5. In the Virtual machines tab, select **Yes** against **Add virtual machines**. By doing this, we are stepping towards adding Virtual machines to the host pool. 

   ![ws name.](media/66.png)

6. Now a long list of parameter appears, here add following configurations respective to their fields. 

  **A**. Session Host Specifications: In this section, we provide the details of the VMs to be created as session Hosts.    

   - Resource Group: *Select **WVD-RG** from the drop down*.
   - Virtual machine location: **East US**, *location should be same as location of your resource group*.
   - Virtual machine size: **Standard D1_v2**. *Click on **Change Size**, then select **D1_v2** and click on **Select** as shown below*
   
   ![ws name.](media/65.png)

   - Number of VMs: **2**   
   - Name prefix: **WVD-HP01-SH** 
   - Image type: **Gallery**
   - Image: **Windows 10 Enterprise multi-session, version 1909 + Office 365 ProPlus** *(choose from dropdown)* 
   - OS disk type: **Standard SSD**
   - Use managed disks: **Yes**
   
   ![ws name.](media/a8.png)
   
   
  **B**. Network and Security 
  
   - Subnet: **sessionhosts-subnet(10.0.1.0/24)** *(Choose from drop down)*
   - Specify Domain or Unit: **No**
   - Leave all other values on default.
  
 
  **C**. Domain and Administrator account  
  
   - AD domain join UPN: *Paste your username* **<inject key="AzureAdUserEmail" />**
   - Password: *Paste the password* **<inject key="AzureAdUserPassword" />**
   - Confirm Password: *Enter the password again.*

   ![ws name.](media/87.png)
   
7. Click on **Next:Workspace** to proceed. 

8. In the Workspace section, we need to specify if we need to register the default application group with a workspace. 

   - Register desktop app group: *Choose* **Yes** 
   - To this workspace: *Click on* **Create new**

   ![ws name.](media/67.png)
   
9. Once you click the **Create new**, a small window pops up, where you can specify the Workspace name you are going to create.  

   - Workspace name: **WVD-WS-01** 
   - Click on **OK**
     
   ![ws name.](media/68.png) 

10. Once we fill up all the parameters, click on the  **Review + create** button on the bottom left corner. 

    ![ws name.](media/69.png)


11. The last window helps us verify if the parameters we filled are correct. Wait for validation to pass, then click on **Create** to initiate the deployment. 

    ![ws name.](media/70.png)


12. Once the deployment gets succeededed, open notifications and click on **Go to Resource**.  

    ![ws name.](media/71.png)

13. You will see that the host pool **WVD-HP-01** is created with 2 session hosts in it, and a default application group (of type Desktop).  

    ![ws name.](media/85.png)


14. Click on **Session Hosts**. Notice the Session Hosts created, with a name concatenating the Name Prefix and increment number. 

    ![ws name.](media/86.png)

15. Click on the **Next** button.  
