---
title: "Log In to an Instance of SQL Server (Command Prompt) | Microsoft Docs"
description: 'Learn about the "sqlcmd" utility. See how to use it in a command prompt to test connectivity to an instance of SQL Server.'
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ""
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords: 
  - "logins [SQL Server], named instance of SQL Server"
  - "log ins [SQL Server]"
  - "logins [SQL Server], default instance of SQL Server"
  - "command prompt [SQL Server], logins"
  - "logging in [SQL Server]"
ms.assetid: f67c11e3-c519-40c9-82c1-07efa9d9985e
author: rwestMSFT
ms.author: randolphwest
---
# Log In to an Instance of SQL Server (Command Prompt)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  This topic describes how to test connectivity to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the **sqlcmd** utility.  
  
##  <a name="SSMSProcedure"></a>  
  
#### To log in to the default instance of SQL Server  
  
1.  From a command prompt, enter the following command to connect by using Windows Authentication:  
  
    ```  
    sqlcmd [ /E ] [ /S servername ]  
  
    ```  
  
#### To log in to a named instance of SQL Server  
  
1.  From a command prompt, enter the following command to connect by using Windows Authentication:  
  
    ```  
    sqlcmd [ /E ] /S servername\instancename  
  
    ```  
  
## See Also  
 [sqlcmd Utility](../../tools/sqlcmd-utility.md)   
 [osql Utility](../../tools/osql-utility.md)  
  
  
