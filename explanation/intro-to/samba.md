(introduction-to-samba)=
# Introduction to Samba

[Samba](https://www.samba.org), a suite of open-source tools, enables Unix-like operating systems, such as Ubuntu, to interact interact with Microsoft Windows networks.  Jeremy Allison(1) noted that he and Andrew Tridgell originally developed Samba in the early 1990s. Allison, a British programmer known for his contributions to the free software community, reverse-engineered the SMB protocol [reference to the SMB protocol] and implemented it in Samba (2). Andrew Tridgell an Australian computer scientist and open-source software developer, analyzed the SMB protocol in the Samba development process. Together, they created it to enable file and printer sharing between these disparate systems, laying the foundation for Samba and making it possible for Unix-like systems to communicate seamlessly with Windows networks.

## How Samba Enables Interoperability Between Ubuntu and Windows 
Samba achieves this interoperability via implementation of the Server Message Block (SMB) protocol [insert link to SMB documentation] used by Windows for network communication. This allows users to access files and printers hosted on servers with Ubuntu server or other Unix-like operating systems (OSs) from Windows clients, and vice versā. In effect, it facilitates resource sharing in mixed-OS environments.  

# Why Developers and System Operators Use Samba
Because organizations build networks from diverse operating systems, developers and system operators commonly deploy Samba in scenarios requiring cross-platform file and print services, Active Directory integration, and centralized network management. Many network environments require both Ubuntu and Microsoft Windows systems working together in harmony. Samba provides developers and network operators with various tools to configure an Ubuntu/Unix-type server to share network resources with Windows clients. Here, we'll look at ... 

1. some of the key principles related to Samba and its functionality
2. how to install and configure its tools available
3. some common Samba use cases

## Samba Functionality

To bridge the Windows-Ubuntu/Unix gap, system designers need several common Windows environment services to share device and user data and configuration details. These services fall under one of three main categories of functionality: file and printer sharing services, directory services, and authentication and access. Let´s take a look at each: 

### Samba File and Printer Sharing Services

File and printer sharing services use Samba´s ???improved??? Server Message Block (SMB) protocol [link to SMB reference] to facilitate file, folder, volume, and printer sharing of printers throughout the network. 

- **File Server**

With Samba, system developers can can {ref}`configure as a file server <samba-file-server>` to share files with Windows clients [link to walk-through guide].

- **Print Server**

Developers can also use Samba to {ref}`configure as a print server <samba-print-server>, sharing printer access with Windows clients [link to walk-through guide]. 

### Samba Directory Services

Samba directory services share vital information about the computers using both operating systems and the users of the network. They use technologies like the Lightweight Directory Access Protocol (LDAP) [link to this resource] and Microsoft Active Directory [link to this resource]. 

- **Microsoft Active Directory**
A collection of users, groups, or hardware components within a Microsoft Active Directory, a Microsoft Active Directory centralizes IT resource management. It stores user and device information, controls access, and simplifies administration. Administrators use the Active Directory to manage permissions. It ensures secure resource access and improves productivity across the network. [Link to guide that shows how to set up a server as a {ref}`member of an Active Directory domain <member-server-in-an-ad-domain>]

NOTE: Prior to the release of Active Directory support, Samba used NT4 Domain Controller emulation and the OpenLDAP backend for directory services. However, both of these legacy methods have been deprecated due to security risks and improved Active Directory integration. For more information, older Samba documentation on Samba.org Archives (www.samba.org) and the Wayback Machine (archive.org) are good starting places for this subject.

### Samba Authentication and Access

Samba Authentication and Access services establish computer or network user identity. They determine the level of access that should be granted to either via principles and technologies including file permissions, group policies, and the Kerberos authentication service [link to Kerberos authentication service reference] .

- ** Samba Share Access Controls**This article provides more details on {ref}`controlling access to shared directories <share-access-controls>`.

- **AppArmor Profile for Samba**
[link to guide on how to {ref}`set up a profile for Samba <samba-apparmor-profile>` using the Ubuntu security module, AppArmor]

- **Mounting CIFS Shares Permanently with Samba**
[link to guide on  {ref}`how to set up Common Internet File System (CIFS) shares <mount-cifs-shares-permanently>` to automatically provide access to network files and resources]

  (1) Allison, J. 2005. A tale of two standards. In News.samba.org (https://www.samba.org/samba/news/articles/low_point/tale_two_stds_os2.html), reviewed 7 February 2024.
  (2) Blair, J. 1998. Virtual Interview with Jeremy Allison and Andrew Tridgell. In Linux Journal (https://www.linuxjournal.com/article/2900), reviewed 7 February 2024.
