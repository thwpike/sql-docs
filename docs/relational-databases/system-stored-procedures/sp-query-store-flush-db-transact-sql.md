---
description: "sp_query_store_flush_db (Transact-SQL)"
title: "sp_query_store_flush_db (Transact-SQL)"
ms.custom:
- event-tier1-build-2022
ms.date: "04/25/2022"
ms.prod: sql
ms.prod_service: "database-engine, sql-database"
ms.reviewer: ""
ms.technology: system-objects
ms.topic: "reference"
f1_keywords: 
  - "sp_query_store_flush_db_TSQL"
  - "sys.sp_query_store_flush_db_TSQL"
  - "sp_query_store_flush_db"
  - "sys.sp_query_store_flush_db"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "sys.sp_query_store_flush_db"
  - "sp_query_store_flush_db"
ms.assetid: 580c03ae-57fc-4562-a6bb-5ec89521e38c
author: markingmyname
ms.author: maghan
monikerRange: "=azuresqldb-current||>=sql-server-2016||>=sql-server-linux-2017||=azuresqldb-mi-current"
---
# sp_query_store_flush_db (Transact-SQL)

[!INCLUDE [sqlserver2016-asdb-asdbmi](../../includes/applies-to-version/sqlserver2016-asdb-asdbmi.md)]

Flushes the in-memory portion of the Query Store data to disk. If [Query Store for secondary replicas](../performance/monitoring-performance-by-using-the-query-store.md#query-store-for-secondary-replicas) is enabled, this only impacts the primary replica.
  
 ![Topic link icon](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## Syntax  
  
```syntaxsql
sp_query_store_flush_db [;]  
```  
  
## Return Code Values  
 0 (success) or 1 (failure)  
  
## Permissions  
 Requires the **ALTER** permission on the database.
  
## Examples  
 The following example flushes the in-memory portion of the Query Store data to disk.  
  
```sql
EXEC sp_query_store_flush_db;  
```  
  
## Next steps

Learn more about Query Store in the following articles:

- [Monitoring Performance By Using the Query Store](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md)  
- [sp_query_store_force_plan &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-force-plan-transact-sql.md)   
- [sp_query_store_remove_query &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-remove-query-transact-sql.md)   
- [sp_query_store_unforce_plan &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-unforce-plan-transact-sql.md)   
- [sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
- [sp_query_store_remove_plan &#40;Transct-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-remove-plan-transct-sql.md)   
- [sp_query_store_reset_exec_stats &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-query-store-reset-exec-stats-transact-sql.md)   
- [Query Store Catalog Views &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/query-store-catalog-views-transact-sql.md)   
  
  
