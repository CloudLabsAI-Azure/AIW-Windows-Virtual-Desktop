# **Exercise 13: Load Balancing methods**


### **Task 1: Understand the Load balancing methods in Host Pools**


While configuring  a hostpool, we can select load balancing methods as per the needs.

There are two types of load balancing methods:

 **1. Breath first**: Breadth-first load balancing distributes new user sessions across all available session hosts in the host pool. 

 **2. Depth first**:  Depth-first load balancing distributes new user sessions to an available session host with the highest number of connections but has not reached its maximum session limit threshold.


### **Task 2: Change and experience Load Balancing methods**


**A**. While creating WVD-HP-01 host pool we selected load blalancing method as *Breath first*, Now we are going to log into both the the session hosts created inside the WVD-HP-01 host pool and see the user distribution.


>**Note:** You are already logged into WVD-HP-01-DAG using WVDUser01 when you performed ***Exercise 11, Task 2, Step 20***, if that session is closed then visit `aka.ms/wvdarmweb` and click on WVD-HP-01-DAG and login with *WVDUser-01* credentials.

1. In your local machine go to **Start** and search for **Remote desktop** and open the application with exact icon as shown below.

   ![ws name.](media/137.png)
   

2. Now in the WVD client double click on the **WVD-HP-01-DAG** Desktop to access it. 

   ![ws name.](media/w6.png)

3. Enter your **credentials** to access the application and click on **Submit**.

   - Username: Put the username of **WVD User-02** (for example: **WVDUser-02@azurehol1055.onmicrosoft.com**).
   - Password: **Azure1234567**
   
   ![ws name.](media/a52.png)
   

4. Your virtual Desktop will launch. 

   ![ws name.](media/a54.png) 


5. Return back to azure portal on your browser and search for host pool and click on it.

   ![ws name.](media/w5.png)
   
   
6. Now click on **WVD-HP-01** hostpool to access it.

   ![ws name.](media/w7.png)
   
   
7. Under Manage blade, click on **Session hosts**.

   ![ws name.](media/w8.png)
   
   
8. Now as you can see two session host have one Active sessions each.

   ![ws name.](media/w11.png)
   
>**Note:** This shows how users are divided into 2 different session host under *Breath first load balancing methods*.
   
9. Click on first session with one active session host and verify which user has been assigned to the particular session host and click on **Log off all active users**, then click on the **X** icon on the top right corner to return back to the session host page.

   ![ws name.](media/w12.png)
   
10. Now click on second session hosts with a active session host and verify which user has been assigned to the particular session host and click on **Log off all active users**, then click on the **X** icon on the top right corner to return back to the session host page.

   ![ws name.](media/w16.png)
    
>**Note:** Wneed to log off users from session hosts so that when the users login back to the session host, they are divided based on the depth first load balancing method as shown in sub task *B*.
   
**B.** Now we will change the load balanching method of WVD-HP-01 host pool to *Depth first* and see how users are divided between session hosts.


1. In WVD-HP-01 page under Settings blade click on **Properties**.

   ![ws name.](media/w14.png)
   
   
2. Change the load balancing algorithm to **Depth-first** then click on **Save icon**.

   ![ws name.](media/w15.png)
   
3. Now paste this link ```aka.ms/wvdarmweb``` in your browser and enter your **credentials** to login. 

   - Username: Put username **WVD User-01** which you copied in previous step (for example: **WVDUser-01@azurehol1055.onmicrosoft.com**). Then click on **Next**.
   
   ![ws name.](media/wvd42.png)

   - Password: **Azure1234567** and click on **Sign in**.

   ![ws name.](media/wvd43.png)
      
      
4. Select **WVD-HP-01-DAG** Desktop.

   ![ws name.](media/wvd53.png)

5. Click on **Allow** for the Prompt.

   ![ws name.](media/133.png)


6. Enter your **credentials** to access the application and click on **Submit**.

   - Username: Put the username of **WVD User-01** which you copied in previous task (for example: **WVDUser-01@azurehol1055.onmicrosoft.com**)
   
   - Password: **Azure1234567**
   
   ![ws name.](media/a47.png)


7. Your virtual Desktop will launch.. 

   ![ws name.](media/wvd39.png)
   
   
8. In your local machine go to **Start** and search for **Remote desktop** and open the application with exact icon as shown below.

   ![ws name.](media/137.png)
   

9. Now in the WVD client double click on the **WVD-HP-01-DAG** Desktop to access it. 

   ![ws name.](media/w6.png)

10. Enter your **credentials** to access the desktop and click on **Submit**.

   - Username: Put the username of **WVD User-02** which you copied in previous task (for example: **WVDUser-02@azurehol1055.onmicrosoft.com**)
   - Password: **Azure1234567**
   
   ![ws name.](media/a52.png)
   

11. Your virtual desktop will launch. 

   ![ws name.](media/a54.png) 


12. Return back to azure portal on your browser and search for host pool and click on it.

   ![ws name.](media/w5.png)
   
   
13. Now click on **WVD-HP-01** hostpool to access it.

   ![ws name.](media/w7.png)
   
   
14. Under Manage blade, click on **Session hosts**.

   ![ws name.](media/w8.png)
   
   
15. Now as you can any one of the session host from  *WVD-HP01-SH-0* or *WVD-HP01-SH-1* will have 2 Active sessions, click on it.

   ![ws name.](media/w9.png)
   
>**Note:** This shows how both users are asigned into the same session host as *maximum limit per session was set to 5* under *Depth first load balancing method*
 that means first 5 users will be assigned to the the same session host, then the sixth user will be assigned to another session host.
 
   
16. Verify that both users have been assigned to the particular session host. 

   ![ws name.](media/w10.png)

17. Click on the **Next** button.
