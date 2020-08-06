# **Exercise 1: Overview** 

Windows Virtual Desktop is a multi-tenant service hosted by Microsoft that manages connections between RD clients and isolated Windows Virtual Desktop tenant environments. Each Windows Virtual Desktop tenant environment consists of one or more host pools. Each host pool consists of one or more identical session hosts. The session hosts are virtual machines (VMs) running Windows 10 Enterprise multi-session, Windows Server 2019, Windows Server 2016, Windows 7, and Windows 10 Enterprise. 

 

Each host pool may have one or more app groups. There are two types of app groups: Remote Desktop and Remote App. Remote desktop app group offers access to a full desktop and provides immersive user experience and full interaction with the operating system running on the session host. A Remote App group publishes one or more Remote Apps that display on the Remote Desktop client as the application window on the local Remote Desktop client's desktop. 

## **General Hierarchy**

### **Hostpools**

A host pool is a collection of Azure virtual machines that register to Windows Virtual Desktop as session hosts when you run the Windows Virtual Desktop agent. All session host virtual machines in a host pool should be sourced from the same image for a consistent user experience. 

A host pool can be one of two types: 

1. **Personal**, where each session host is assigned to individual users. 

2. **Pooled**, where session hosts can accept connections from any user authorized to an app group within the host pool. 

You can set additional properties on the host pool to change its load-balancing behavior, how many sessions each session host can take, and what the user can do to session hosts in the host pool while signed in to their Windows Virtual Desktop sessions. You control the resources published to users through app groups. 

### **App Groups**

 

An app group is a logical grouping of applications installed on session hosts in the host pool. An app group can be one of two types: 

 

1. **RemoteApp**, where users access the RemoteApps you individually select and publish to the app group 

2. **Desktop**, where users access the full desktop 

By default, a desktop app group (named "Desktop Application Group") is automatically created whenever you create a host pool. You can remove this app group at any time. However, you can't create another desktop app group in the host pool while a desktop app group exists. To publish RemoteApps, you must create a RemoteApp app group. You can create multiple RemoteApp app groups to accommodate different worker scenarios. Different RemoteApp app groups can also contain overlapping RemoteApps. 

 

To publish resources to users, you must assign them to app groups. When assigning users to app groups, consider the following things: 

 

1. A user can be assigned to both a desktop app group and a RemoteApp app group in the same host pool. However, users can only launch one type of app group per session. Users can't launch both types of app groups at the same time in a single session. 

2. A user can be assigned to multiple app groups within the same host pool, and their feed will be an accumulation of both app groups. 

### **Workspaces** 

A workspace is a logical grouping of application groups in Windows Virtual Desktop. Each Windows Virtual Desktop application group must be associated with a workspace for users to see the remote apps and desktops published to them. 

### **End Users**

After you've assigned users to their app groups, they can connect to a Windows Virtual Desktop deployment with any of the Windows Virtual Desktop clients. 

Click on the **Next** button.  
