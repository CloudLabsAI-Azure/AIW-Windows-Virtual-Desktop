# **Overview** 
   
Windows Virtual Desktop (WVD) is a desktop and app virtualization service that runs on the cloud. It is a multi-tenant service hosted by Microsoft Azure and manages connections between Remote Desktop clients and isolated Windows Virtual Desktop environments. Since it is on the cloud, it’s always up to date, secure, and highly scalable. You can connect to the Virtual Desktop running on Azure from anywhere in the world on any device. Also, it leverages the capability to control and monitor the resources needed for the users. Remote Desktop and App Virtualization provides access to an environment that is customized for user's needs, whether that is an app or desktop environment.


WVD offers support for a lot of Azure VM sizes. One of the interesting features is the support for Windows 7, on top of support for Windows 10 Enterprise multi-session, Windows Server 2019, Windows Server 2016, and Windows 10 Enterprise. WVD is optimized for Office 365 services, with full Teams video & audio functionality and fast, reliable experience for OneDrive. Windows Virtual Desktop is an appealing option to users as it is easy to implement, provide cost and time savings, enhanced security, and increase employee efficiency.

## **General Hierarchy**

### **Host Pools**

A Host pool is a collection of Azure virtual machines that register to Windows Virtual Desktop as session hosts when you run the Windows Virtual Desktop agent. All session host virtual machines in a host pool should be sourced from the same image for consistent user experience. 

Host Pools can be one of two types: 

1. **Personal**, where each session host is assigned to individual users. 

2. **Pooled**, where session hosts can accept connections from any user authorized to an application group within the host pool. 

You can set additional properties on the host pool to change its load-balancing behavior, how many sessions each session host can take, and what the user can do to session hosts in the host pool while signed in to their Windows Virtual Desktop sessions. You control the resources published to users through application groups. 

### **Application Groups**


An Application group is a logical grouping of applications installed on session hosts in the host pool. An application group can be one of two types: 

1. **RemoteApp**, where users access the RemoteApps you individually select and publish to the application group .

2. **Desktop**, where users access the full desktop 

By default, a desktop application group (named "Desktop Application Group") is automatically created whenever you create a host pool. You can remove this application group at any time. However, you can't create another desktop application group in the host pool while a desktop application group already exists. To publish RemoteApps, you must create a RemoteApp application group. You can create multiple RemoteApp application groups to accommodate different worker scenarios. Different RemoteApp application groups can also contain overlapping RemoteApps. 

 


### **Workspaces** 

A workspace is a logical grouping of application groups in Windows Virtual Desktop. Each Windows Virtual Desktop application group must be associated with a workspace for users to see the remote apps and desktops published to them. 

### **End users**

After you've assigned users to their application groups, they can connect to a Windows Virtual Desktop deployment with any of the Windows Virtual Desktop clients. 



Click on the **Next** button present in the bottom-right corner of this lab guide.  
