---
description: "dbo.syscategories (Transact-SQL)"
title: "dbo.syscategories (Transact-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/04/2017"
ms.prod: sql
ms.prod_service: "database-engine"
ms.reviewer: ""
ms.technology: system-objects
ms.topic: "reference"
f1_keywords: 
  - "dbo.syscategories_TSQL"
  - "syscategories"
  - "syscategories_TSQL"
  - "dbo.syscategories"
dev_langs: 
  - "TSQL"
helpviewer_keywords: 
  - "syscategories system table"
ms.assetid: eb2cb75c-dc58-4a5b-b329-664e9fe20ce0
author: rothja
ms.author: jroth
---
# dbo.syscategories (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contains the categories used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to organize jobs, alerts, and operators. This table is stored in the **msdb** database.  
  
|Column name|Data type|Description|  
|-----------------|---------------|-----------------|  
|**category_id**|**int**|ID of the category|  
|**category_class**|**int**|Type of item in the category:<br /><br /> **1** = Job<br /><br /> **2** = Alert<br /><br /> **3** = Operator|  
|**category_type**|**tinyint**|Type of category:<br /><br /> **1** = Local<br /><br /> **2** = Multiserver<br /><br /> **3** = None|  
|**name**|**sysname**|Name of the category|  
  
  
