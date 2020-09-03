# **Exercise 7: Load Balancing methods**


### **Task 1: Understand the Load balancing methods in Host Pools**


While configuring  a hostpool, we can select load balancing methods as per the needs.

There are two types of load balancing methods:

 **1. Breadth first**: Breadth-first load balancing distributes new user sessions across all available session hosts in the host pool. 

 **2. Depth first**:  Depth-first load balancing distributes new user sessions to an available session host with the highest number of connections but has not reached its maximum session limit threshold.


### **Task 2: Add new users to Azure Active Directory**

1. On Azure Portal page, click on **Show portals menu** button and select **Azure Active Directory**.

   ![ws name.](media/lb1.png)

2. Click on **Users** under **Manage** blade.

   ![ws name.](media/lb6.png)

3. Click on **+ New user** to add a new user.

   ![ws name.](media/lb5.png)

4. Add following configurations and leave rest to default:

   - User name: **WVDUser01**
   - Name: **WVDUser01**
   - Click on **Create**

   ![ws name.](media/lb8.png)

5. Now again click on **+ New user**, then add following configurations and leave rest to default.

   - User name: **WVDUser02**
   - Name: **WVDUser02**
   - Click on **Create**
   
   ![ws name.](media/lb7.png)

6. Both the newly created users will show up similarly as shown below. Copy the **user principal name** of both users and keep in a text editor.

   ![ws name.](media/lb11.png)

7. Click on **WVDUser01** to open it. Then click on **Groups** under *Manage* blade and select **+ Add memberships**.

   ![ws name.](media/lb12.png)

8. Click on **AAD DC Administrators** group and then click on **Select**.

   ![ws name.](media/lb13.png)

9. Once done, open **Profile** under **Manange** blade. Click on **Reset password** and then click on **Reset password** button.

   ![ws name.](media/lb3.png)

10. Copy the temporary password and paste it in a text editor.

   ![ws name.](media/lb4.png)

11. Repeat *Step 7* to *Step 10* for **WVDUser02**.


### **Task 3: Change and experience Load Balancing methods**


#### **A**. While creating WVD-HP-01 host pool we selected load blalancing method as *Breadth first*, now we are going to log into both the the session hosts created inside the WVD-HP-01 host pool and see the user distribution.


>**Note:** You are already logged into WVD-HP-01-DAG using WVDUser01 when you performed ***Exercise 11, Task 2, Step 20***, if that session is closed then visit `aka.ms/wvdarmweb` and click on WVD-HP-01-DAG and login with *WVDUser-01* credentials.

1. In your local machine go to **Start** and search for **Remote desktop** and open the application with exact icon as shown below.

   ![ws name.](media/137.png)
   

2. Click on the *ellipses* and select **Unsubscribe**.

   ![ws name.](media/lb16.png)

3. Click on **Subscribe** and enter you user credentials.

   - Username: Put the username of **WVD User-02** you copied earlier (for example: **WVDUser-02@azurehol1055.onmicrosoft.com**).
   
   ![ws name.](media/lb17.png)
   
   - Password: *Paste the temporary password you copied earlier*

   ![ws name.](media/lb17.png)

4. Portal will ask you to set a permanent password. For that just paste your temporary password under *Current Password* and add new password for the user.

   ![ws name.](media/lb15.png)

5. Now in the WVD client double click on the **WVD-HP-01-DAG** Desktop to access it. 

   ![ws name.](media/lb14.png)

3. Enter your **credentials** to access the application and click on **Submit**.

   - Username: Put the username of **WVD User-02** (for example: **WVDUser-02@azurehol1055.onmicrosoft.com**).
   - Password: *Paste the permanent password*
   
   ![ws name.](media/a52.png)
  

4. The virtual Desktop will launch as shown below. 

   ![ws name.](media/a54.png) 


5. Return back to azure portal on your browser and search for host pool and click on it.

   ![ws name.](media/w5.png)
   
   
6. Now click on **WVD-HP-01** hostpool to access it.

   ![ws name.](media/w7.png)
   
   
7. Under Manage blade, click on **Session hosts**.

   ![ws name.](media/w8.png)
   
   
8. Now as you can see two session host have one Active sessions each.

   ![ws name.](media/lb2.png)
   
>**Note:** This shows how users are divided into 2 different session host under *Breath first load balancing methods*.
   
9. Click on first session with one active session host and verify which user has been assigned to the particular session host and click on **Log off all active users**, then click on the **X** icon on the top right corner to return back to the session host page.

   ![ws name.](media/lb20.png)
    
>**Note:** We need to log off users from session hosts so that when the users login back to the session host, they are divided based on the depth first load balancing method.
   

#### **B**. Now we will change the load balanching method of WVD-HP-01 host pool to *Depth first* and see how users are divided between session hosts.

1. In *WVD-HP-01* host pool, click on **Properties** under *Settings* blade .

   ![ws name.](media/w14.png)
   
   
2. Change the load balancing algorithm to **Depth-first** then click on **Save icon**.

   ![ws name.](media/w15.png)
   
3. Now paste this link ```aka.ms/wvdarmweb``` in your browser and enter your **credentials** to login. 

   - Username: Put username **WVD User-01** which you copied earlier and then click on **Next**.
   
   ![ws name.](media/wvd42.png)

   - Password: *Paste the temporary password you copied earlier* and click on **Sign in**.

   ![ws name.](media/wvd43.png)
      
 5. Portal will ask you to set a permanent password. For that just paste your temporary password under *Current Password* and add new password for the user.

   ![ws name.](media/lb15.png)

6. Now in the WVD client double click on the **WVD-HP-01-DAG** Desktop to access it. 

   ![ws name.](media/lb14.png)

7. Select **Allow** on the prompt asking permission to *Access local resources*.

   ![ws name.](media/133.png)

8. Enter your **credentials** to access the application and click on **Submit**.

   - Username: *Put the username of **WVD User-01** which you copied earlier (for example: **WVDUser-01@azurehol1055.onmicrosoft.com**)*
   
   - Password: *Paste the Permanent password that you created.*
   
   ![ws name.](media/a47.png)


9. The virtual Desktop will launch as shown below. 

   ![ws name.](media/wvd39.png)
   
   
10. In your local machine go to **Start** and search for **Remote desktop** and open the application with exact icon as shown below.

   ![ws name.](media/137.png)
   

11. Now in the WVD client double click on the **WVD-HP-01-DAG** Desktop to access it. 

   ![ws name.](media/w6.png)

12. Enter your **credentials** to access the desktop and click on **Submit**.

   - Username: Put the username of **WVD User-02** which you copied in previous task (for example: **WVDUser-02@azurehol1055.onmicrosoft.com**)
   - Password: **Azure1234567**
   
   ![ws name.](media/a52.png)
   

13. The virtual Desktop will launch as shown below. 

   ![ws name.](media/a54.png) 


14. Return back to azure portal and navigate to **WVD-HP-01** host pool.

   ![ws name.](media/w8.png)
   
   
15. Now as you can any one of the session host from  *WVD-HP01-SH-0* or *WVD-HP01-SH-1* will have 2 Active sessions, click on it.

   ![ws name.](media/lb21.png)
   
>**Note:** This shows how both users are asigned into the same session host as *maximum limit per session was set to 5* under *Depth first load balancing method*
 that means first 5 users will be assigned to the the same session host, then the sixth user will be assigned to another session host.
 
   
16. Verify that both users have been assigned to the particular session host. 

   ![ws name.](media/lb22.png)

17. Click on the **Next** button present in the bottom-right corner of this lab guide.

