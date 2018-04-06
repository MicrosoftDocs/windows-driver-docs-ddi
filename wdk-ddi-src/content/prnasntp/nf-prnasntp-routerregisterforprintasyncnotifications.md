---
UID: NF:prnasntp.RouterRegisterForPrintAsyncNotifications
title: RouterRegisterForPrintAsyncNotifications function
author: windows-driver-content
description: The RouterRegisterForPrintAsyncNotifications function registers for asynchronous notifications associated with a printer or print server.
old-location: print\routerregisterforprintasyncnotifications.htm
old-project: print
ms.assetid: 87966827-72b2-4be7-859a-628c1accca48
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RouterRegisterForPrintAsyncNotifications, RouterRegisterForPrintAsyncNotifications function [Print Devices], print.routerregisterforprintasyncnotifications, prnasntp/RouterRegisterForPrintAsyncNotifications, spoolfnc_c39b58f9-b714-437d-86c0-89f2d922c920.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prnasntp.h
req.include-header: Prnasntp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	RouterRegisterForPrintAsyncNotifications
product:
- Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# RouterRegisterForPrintAsyncNotifications function


## -description


The <code>RouterRegisterForPrintAsyncNotifications</code> function registers for asynchronous notifications associated with a printer or print server.


## -parameters




### -param pName [in]

A pointer to a null-terminated string that specifies the name of the printer or print server.


### -param pNotificationType [in]

A pointer to the GUID that represents the type of notifications of interest to the caller.


### -param eNotifyFilter [in]

The filter for the session or user of interest to the caller when receiving notifications.


### -param eConversationStyle [in]

The type of communication: unidirectional or bidirectional.


### -param pCallback [in]

A pointer to the callback that is used deliver the notifications.


### -param phNotify [out]

A pointer to an opaque handle. The caller can use this handle to discontinue receiving notifications.


## -returns



This function returns S_OK on success, and a standard COM error code otherwise.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562028">RouterUnregisterForPrintAsyncNotifications</a>
 

 

