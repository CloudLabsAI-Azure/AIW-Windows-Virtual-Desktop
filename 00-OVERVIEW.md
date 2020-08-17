# **Exercise 1: Overview** 

Windows Virtual Desktop is a multi-tenant service hosted by Microsoft that manages connections between Remote Desktop clients and isolated Windows Virtual Desktop tenant environments. Each Windows Virtual Desktop tenant environment consists of one or more host pools. Each host pool consists of one or more identical session hosts. The session hosts are virtual machines (VMs) running Windows 10 Enterprise multi-session, Windows Server 2019, Windows Server 2016, Windows 7, and Windows 10 Enterprise. 

 

Each host pool may have one or more application groups. There are two types of application groups: Remote Desktop and Remote Application. Remote desktop application group offers access to a full desktop and provides immersive user experience and full interaction with the operating system running on the session host. A Remote Application group publishes one or more Remote Application that display on the Remote Desktop client as the application window on the local Remote Desktop client's desktop. 

## **General Hierarchy**

### **Hostpools**

A host pool is a collection of Azure virtual machines that register to Windows Virtual Desktop as session hosts when you run the Windows Virtual Desktop agent. All session host virtual machines in a host pool should be sourced from the same image for consistent user experience. 

A host pool can be one of two types: 

1. **Personal**, where each session host is assigned to individual users. 

2. **Pooled**, where session hosts can accept connections from any user authorized to an application group within the host pool. 

You can set additional properties on the host pool to change its load-balancing behavior, how many sessions each session host can take, and what the user can do to session hosts in the host pool while signed in to their Windows Virtual Desktop sessions. You control the resources published to users through application groups. 

### **Application Groups**

 

An Application group is a logical grouping of applications installed on session hosts in the host pool. An application group can be one of two types: 

 

1. **RemoteApp**, where users access the RemoteApps you individually select and publish to the application group .

2. **Desktop**, where users access the full desktop 

By default, a desktop application group (named "Desktop Application Group") is automatically created whenever you create a host pool. You can remove this application group at any time. However, you can't create another desktop application group in the host pool while a desktop application group exists. To publish RemoteApps, you must create a RemoteApp application group. You can create multiple RemoteApp application groups to accommodate different worker scenarios. Different RemoteApp application groups can also contain overlapping RemoteApps. 

 

To publish resources to users, you must assign them to application groups. When assigning users to application groups, consider the following things: 

 

1. A user can be assigned to both - a desktop application group and a RemoteApp application group in the same host pool. However, users can only launch one type of application group per session. Users can't launch both types of application groups at the same time in a single session. 

2. A user can be assigned to multiple application groups within the same host pool, and their feed will be an accumulation of both application groups. 

### **Workspaces** 

A workspace is a logical grouping of application groups in the Windows Virtual Desktop. Each Windows Virtual Desktop application group must be associated with a workspace for users to see the remote applications and desktops published to them. 

### **End Users**

After you've assigned users to their application groups, they can connect to a Windows Virtual Desktop deployment with any of the Windows Virtual Desktop clients. 

Click on the **Next** button.  
