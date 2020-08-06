# **Exercise 2: Pre-requisites to deploy Windows Virtual Desktop**

### **Task 1**: **Review the Pre-requisites**

To deploy a Windows Virtual Desktop environment, we need a pre-created windows domain (e.g: contoso.com). This can be created one of the following:

1. Azure Active Directory Domain Services(AADDS)
2. Windows Active Directory

In this lab, we have used AADDS and it is pre-provisioned. The Domain name will be the suffix of your lab user account (Eg: If your lab user account is ***odl_user_189588@azurehol1057.onmicrosoft.com***, the domain will be ***azurehol1057.onmicrosoft.com***.) Your lab user account is given ‘AAD DC Administrator’ privilege, hence can be used to domain join machines later. 


### **Task 2: Login to Azure Portal**

1. Navigate **Azure Portal** (https://portal.azure.com) in your browser. 

2. Login to Azure with the username **<inject key="AzureAdUserEmail" />**

   ![](media/wvd1.png)

3. Enter password **<inject key="AzureAdUserPassword" />** and click on **Sign in**.

   ![](media/wvd2.png)
   
> **Note**: Refer the **Environment Details** tab for any other lab credentials/details.
  
   ![](media/wvd7.png)

4. There will be a pop-up entitled **Stay signed in?** with buttons for **No** and **Yes** - Choose **No**.

   ![](media/a102.png)

5. You may encounter a popup entitled **Welcome to Microsoft Azure** with buttons for **Start Tour** and **Maybe Later** - Choose **Maybe Later**.

   ![](media/wvd4.png)

6. Click on the **Next** button.  
