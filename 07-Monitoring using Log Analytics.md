# Exercise 6: Monitoring using Log Analytics

Windows Virtual Desktop uses Azure Monitor for monitoring and alerts like many other Azure services. This lets admins identify issues through a single interface. The service creates activity logs for both user and administrative actions.


### **Task 1: Create Log Analytics**

1. On the Azure portal, click on **Create a resource** given under *Azure services*.

   ![ws name.](media/wiw.png)

2. Type *Log Analytics Workspace* in the search bar and click on **Log Analytics Workspace** from the suggestions.

   ![ws name.](media/wiw1.png)

3. On the Log Analytics Workspace page, click on **Create**.

   ![ws name.](media/wiw2.png)

4. Now add the following configurations:

  - Subscription: *Choose the default subscription.*
  - Resource group: *Select **WVD-RG** from the drop down.*
  - Name: **wvd-monitoring-la-[uniqueid]** (*for example: wvd-monitoring-la-206533*)
  - Region: **East US**, *basically this should be same as the region of your resource group.*
  - Click on **Review + Create**

   ![ws name.](media/wiw3.png)

5. The last window helps us to verify if the parameters we filled are correct. Wait for validation to pass, then click on **Create** to initiate the deployment.

   ![ws name.](media/wiw18.png)

6. Once the deployment gets succeeded, go to **Windows Virtual Desktop**.

   ![ws name.](media/64.png)

7. Open **Host Pools** and then click on **WVD-HP-01**.

   ![ws name.](media/wiw12.png)

8. Now click on **Diagnostic settings** present under *Monitoring* blade, then click on **+Add diagnostic setting**.

   ![ws name.](media/wiw5.png)

9. Add the following configurations:

  - Diagnostic settings name: **HostPoolMonitoring**
  - Category details: *Check all the boxes present under logs i.e.,* **Checkpoint, Error, Management, Connection and HostRegistration.** 
  - Destination details: *Check the box for* **Send to Log Analytics**
  - Subscription: *Choose the default subscription.*
  - Log Analytics Workspace: *Select the log analytics workpsace(i.e.,**wvd-monitoring-la-[uniqueid]**) from the drop down, that we just created.*
  - At last, click on **Save**.

   ![ws name.](media/wiw6.png)

10. Navigate back to Windows Virtual Desktop and open **Application groups**.

   ![ws name.](media/wiw10.png)
   
11. Click on **WVD-HP-01-DAG**. Then select **Diagnostic settings** present under *Monitoring* blade and click on **+Add diagnostic setting**.

   ![ws name.](media/wiw20.png) 
   
12. Add the following configurations:

  - Diagnostic settings name: **ApplicationGroupMonitoring**
  - Category details: *Check all the boxes present under logs i.e.,* **Checkpoint, Error and Management.** 
  - Destination details: *Check the box for* **Send to Log Analytics**
  - Subscription: *Choose the default subscription.*
  - Log Analytics Workspace: *Select the log analytics workpsace(i.e.,**wvd-monitoring-la-[uniqueid]**) from the drop down, that we just created.*
  - At last, click on **Save**.

   ![ws name.](media/wiw8.png)
   
13. Navigate back to **Application groups** and click on **WVD-AG-01**.

   ![ws name.](media/wiw25.png)

14. Add the following configurations:

  - Diagnostic settings name: **ApplicationGroupMonitoring1**
  - Category details: *Check all the boxes present under logs i.e.,* **Checkpoint, Error and Management.** 
  - Destination details: *Check the box for* **Send to Log Analytics**
  - Subscription: *Choose the default subscription.*
  - Log Analytics Workspace: *Select the log analytics workpsace(i.e.,**wvd-monitoring-la-[uniqueid]**) from the drop down, that we just created.*
  - At last, click on **Save**.

   ![ws name.](media/wiw26.png)

15. Navigate back to Windows Virtual Desktop and open **Workspaces**.

   ![ws name.](media/wiw9.png)
   
16. Click on **WVD-WS-01**. Then select **Diagnostic settings** present under *Monitoring* blade and click on **+Add diagnostic setting**.    
   
   ![ws name.](media/wiw11.png)
 
17. Add the following configurations:

  - Diagnostic settings name: **WorkspaceMonitoring**
  - Category details: *Check all the boxes present under logs i.e.,* **Checkpoint, Error, Management and Feed.** 
  - Destination details: *Check the box for* **Send to Log Analytics**
  - Subscription: *Choose the default subscription.*
  - Log Analytics Workspace: *Select the log analytics workpsace(i.e.,**wvd-monitoring-la-[uniqueid]**) from the drop down, that we just created.*
  - At last, click on **Save**.  
   
   ![ws name.](media/wiw13.png)
   
18. Now navigate to *Log Analytics Workspace* and open your workpsace, then select **Logs** under *General* blade. 

   ![ws name.](media/wiw14.png)

19. Click on **Get Started** button and then close the *Example queries* window by clicking on **X** button.

   ![ws name.](media/wiw15.png)

20. In the *Query Explorer*, paste the following query and set the **Time Range** to **Last 30 minutes**, then click on **Run** button.

   ```
   WVDConnections 
   |sort by TimeGenerated asc, CorrelationId
   |summarize Connectcount = dcount(CorrelationId) by bin(TimeGenerated, 1d),UserName = toupper(trim_end("@.*",UserName))
   ```
   
   ![ws name.](media/wiw23.png)

21. In results, logs will appear similar to one shown below.

   ![ws name.](media/wiw17.png)

> **Note:** Logs may take upto 24 hours to appear in results.

22. Click on the **Next** button present in the bottom-right corner of this lab guide.





