---
description: "Execute Statements Against Multiple Servers Simultaneously"
title: Execute Statements Against Multiple Servers Simultaneously
ms.service: sql
ms.subservice: ssms
ms.topic: conceptual
helpviewer_keywords: 
  - "multiserver queries"
  - "executing queries against multiple servers"
  - "queries [SQL Server], multiserver"
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.reviewer: ""
ms.custom: seo-lt-2019
ms.date: 07/18/2016
---

# Execute Statements Against Multiple Servers Simultaneously

[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

This topic describes how to query multiple servers at the same time in [!INCLUDE[ssnoversion](../../includes/ssnoversion-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group. 

The results returned by the query can be combined into a single results pane, or can be returned in separate results panes. The results set can include additional columns for the server name and the login used by the query on each server. Central Management Servers and subordinate servers can be registered by using only Windows Authentication. Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.  
  
> [!NOTE]  
> Before you execute the following procedures, create a Central Management Server and server group. For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](./create-a-central-management-server-and-server-group.md).  

  
##  <a name="Permissions"></a> Permissions  
 Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary. For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.  
  
 ## Execute statements against multiple configuration targets simultaneously  

1.  In SQL Server Management Studio, on the **View** menu, click **Registered Servers**.  
  
2.  Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.  
  
3.  In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     By default, the results pane will combine the query results from all the servers in the server group.  
  
#### To change the multiserver results options  
  
1.  In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.  
  
2.  Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.  
  
3.  On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.  
  
## See Also  
 [Administer Multiple Servers Using Central Management Servers](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
