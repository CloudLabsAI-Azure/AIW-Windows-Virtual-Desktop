# **Exercise 2: Pre-requisites to deploy Windows Virtual Desktop**

### **Pre-requisites**

To deploy Windows Virtual Desktop environment, we need a pre-created windows domain (for example: microsoft.com). This can be achieved using one of the following ways:

1. Azure Active Directory Domain Services(AADDS)
2. Windows Active Directory

In this lab, we have used AADDS and it is pre-provisioned. The domain name will be the suffix of your lab user account (for example: If your lab user account is ***odl_user_189588@azurehol1057.onmicrosoft.com***, the domain will be ***azurehol1057.onmicrosoft.com***.) Your lab user account is given ‘AAD DC Administrator’ privilege, hence can be used to domain join machines later. 
