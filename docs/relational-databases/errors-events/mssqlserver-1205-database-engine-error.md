---
description: "MSSQLSERVER_1205"
title: "MSSQLSERVER_1205 | Microsoft Docs"
ms.custom: ""
ms.date: "04/04/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: supportability
ms.topic: "reference"
helpviewer_keywords: 
  - "1205 (Database Engine error)"
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
author: MashaMSFT
ms.author: mathoma
---
# MSSQLSERVER_1205
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## Details  
  
| Attribute | Value |  
| :-------- | :---- |  
|Product Name|SQL Server|  
|Event ID|1205|  
|Event Source|MSSQLSERVER|  
|Component|SQLEngine|  
|Symbolic Name|LK_VICTIM|  
|Message Text|Transaction (Process ID %d) was deadlocked on %.*ls resources with another process and has been chosen as the deadlock victim. Rerun the transaction.|  
  
## Explanation

Resources are accessed in conflicting order on separate transactions, causing a [deadlock](../sql-server-transaction-locking-and-row-versioning-guide.md?#deadlocks). For example:  
  
- Transaction1 updates **Table1.Row1**, while Transaction2 updates **Table2.Row2**
- Transaction1 tries to update **Table2.Row2** but is blocked because Transaction2 has not yet committed  
- Transaction2 now tries to update **Table1.Row1** but is blocked because Transaction1 has not committed
- A deadlock occurs because Transaction1 is waiting for Transaction2 to complete, but Transaction2 is waiting for Transaction1 to complete.  
  
The system will detect this deadlock and will choose one of the transactions involved as a 'victim'. It will then issue this error message, rolling back the victim's transaction.  For detailed information see [Deadlocks](../sql-server-transaction-locking-and-row-versioning-guide.md?#deadlocks).

## User Action  

Execute the transaction again. You can also revise the application to avoid deadlocks. The transaction that was chosen as a victim can be retried and will likely succeed, depending on what operations are being executed simultaneously.  
  
To prevent or avoid deadlocks from occurring, consider having all transactions access rows in the same order (**Table1**, then **Table2**). This way, although blocking might occur, a deadlock will be avoided.  
  
For further information, see [Handling Deadlocks](../sql-server-transaction-locking-and-row-versioning-guide.md?#handling-deadlocks) and [Minimizing Deadlocks](../sql-server-transaction-locking-and-row-versioning-guide.md#deadlock_minimizing).
