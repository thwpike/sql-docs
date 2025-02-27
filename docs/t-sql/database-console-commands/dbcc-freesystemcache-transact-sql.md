---
description: "DBCC FREESYSTEMCACHE (Transact-SQL)"
title: "DBCC FREESYSTEMCACHE (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "02/25/2020"
ms.prod: sql
ms.prod_service: "sql-database"
ms.reviewer: ""
ms.technology: t-sql
ms.topic: "language-reference"
f1_keywords: 
  - "FREESYSTEMCACHE_TSQL"
  - "DBCC_FREESYSTEMCACHE_TSQL"
  - "DBCC FREESYSTEMCACHE"
  - "FREESYSTEMCACHE"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "clearing unused cache entries"
  - "DBCC FREESYSTEMCACHE statement"
  - "unused cache entries"
  - "releasing unused cache entries"
  - "freeing unused cache entries"
  - "cleaning unused cache entries"
ms.assetid: 4b5c460b-e4ad-404a-b4ca-d65aba38ebbb
author: rwestMSFT
ms.author: umajay
---
# DBCC FREESYSTEMCACHE (Transact-SQL)
[!INCLUDE [SQL Server SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/sql-asdb-asdbmi.md)]

Releases all unused cache entries from all caches. The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] proactively cleans up unused cache entries in the background to make memory available for current entries. However, you can use this command to manually remove unused entries from every cache or from a specified Resource Governor pool cache.
  
![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## Syntax  
```syntaxsql
DBCC FREESYSTEMCACHE   
    ( 'ALL' [, pool_name ] )   
    [WITH   
    { [ MARK_IN_USE_FOR_REMOVAL ] , [ NO_INFOMSGS ]  }  
    ]  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## Arguments
( 'ALL' [,_pool\_name_ ] )  
ALL specifies all supported caches.  
_pool\_name_ specifies a resource governor pool cache. Only entries associated with this pool are freed. To list the available pool names run:

```sql
SELECT name FROM sys.dm_os_memory_clerks
```

Most, but not all, caches can be individually freed using this command.
  
MARK_IN_USE_FOR_REMOVAL  
Asynchronously frees currently used entries from their respective caches after they're unused. After the DBCC FREESYSTEMCACHE WITH MARK_IN_USE_FOR_REMOVAL runs, new entries created in the cache aren't affected.  
  
NO_INFOMSGS  
Suppresses all informational messages.  
  
## Remarks  
Running DBCC FREESYSTEMCACHE clears the plan cache for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Clearing the plan cache causes a recompilation of all upcoming execution plans and can cause a sudden, temporary reduction in query performance. For each cleared cache store in the plan cache, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log contains the following informational message:

>`SQL Server has encountered %d occurrence(s) of cachestore flush for the '%s' cachestore (part of plan cache) due to 'DBCC FREEPROCCACHE' or 'DBCC FREESYSTEMCACHE' operations.`

 This message is logged every five minutes as long as the cache is flushed within that time interval.

## Result sets  
DBCC FREESYSTEMCACHE returns:
"DBCC execution completed. If DBCC printed error messages, contact your system administrator."
  
## Permissions  
Requires ALTER SERVER STATE permission on the server.
  
## Examples  
  
### A. Releasing unused cache entries from a Resource Governor pool cache  
The following example illustrates how to clean caches that are dedicated to a specified Resource Governor resource pool.
  
```sql
-- Clean all the caches with entries specific to the resource pool named "default".  
DBCC FREESYSTEMCACHE ('ALL', default);  
```  
  
### B. Releasing entries from their respective caches after they become unused  
The following example uses the MARK_IN_USE_FOR_REMOVAL clause to release entries from all current caches once the entries become unused.
  
```sql
DBCC FREESYSTEMCACHE ('ALL') WITH MARK_IN_USE_FOR_REMOVAL;  
```  
  
## See Also  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-freeproccache-transact-sql.md)  
[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-freesessioncache-transact-sql.md)  
[Resource Governor](../../relational-databases/resource-governor/resource-governor.md)
  
  
