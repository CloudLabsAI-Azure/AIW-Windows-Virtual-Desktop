# **Exercise 2: Pre-requisites to deploy Windows Virtual Desktop**

### **Task 1**: **Review the Pre-requisites**

To deploy Windows Virtual Desktop environment, we need a pre-created windows domain (for example: contoso.com). This can be achieved using one of the following ways:

1. Azure Active Directory Domain Services(AADDS)
2. Windows Active Directory

In this lab, we have used AADDS and it is pre-provisioned. The domain name will be the suffix of your lab user account (for example: If your lab user account is ***odl_user_189588@azurehol1057.onmicrosoft.com***, the domain will be ***azurehol1057.onmicrosoft.com***.) Your lab user account is given ‘AAD DC Administrator’ privilege, hence can be used to domain join machines later. 


### **Task 2: Log in to Azure Portal**

1. Open **Azure Portal** (https://portal.azure.com) in your browser. 

2. Login to Azure with the username **<inject key="AzureAdUserEmail" />** and click on **Next**.

   ![](media/wvd1.png)

3. Enter password **<inject key="AzureAdUserPassword" />** and click on **Sign in**.

   ![](media/wvd2.png)

> **Note:** 
> - If there's a popup entitled **Stay signed in?** with buttons for **No** and **Yes** - Choose **No**.
>
>  ![](media/a102.png)
>   
> - If there's another popup entitled **Welcome to Microsoft Azure** with buttons for **Start Tour** and **Maybe Later** - Choose **Maybe Later**.
>
>  ![](media/wvd4.png)

4. Click on the **Next** button present in the bottom-right corner of this lab guide.  
 
