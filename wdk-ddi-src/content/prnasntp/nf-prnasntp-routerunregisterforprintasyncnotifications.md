---
UID: NF:prnasntp.RouterUnregisterForPrintAsyncNotifications
title: RouterUnregisterForPrintAsyncNotifications function (prnasntp.h)
description: The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server.
old-location: print\routerunregisterforprintasyncnotifications.htm
tech.root: print
ms.assetid: 67909e35-fae2-40b7-b39f-58576e932332
ms.date: 04/20/2018
keywords: ["RouterUnregisterForPrintAsyncNotifications function"]
ms.keywords: RouterUnregisterForPrintAsyncNotifications, RouterUnregisterForPrintAsyncNotifications function [Print Devices], print.routerunregisterforprintasyncnotifications, prnasntp/RouterUnregisterForPrintAsyncNotifications, spoolfnc_3c629be8-f1d8-43fb-b225-582e4bb76c51.xml
f1_keywords:
 - "prnasntp/RouterUnregisterForPrintAsyncNotifications"
 - "RouterUnregisterForPrintAsyncNotifications"
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Spoolss.dll
api_name:
- RouterUnregisterForPrintAsyncNotifications
targetos: Windows
req.typenames: 
---

# RouterUnregisterForPrintAsyncNotifications function


## -description


The <code>RouterUnregisterForPrintAsyncNotifications</code> function unregisters for receiving asynchronous notifications associated with a printer or print server.


## -parameters




### -param hNotify [in]

The registration handle returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prnasntp/nf-prnasntp-routerregisterforprintasyncnotifications">RouterRegisterForPrintAsyncNotifications</a> function.


## -returns



This function returns S_OK on success, and a standard COM error code otherwise.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prnasntp/nf-prnasntp-routerregisterforprintasyncnotifications">RouterRegisterForPrintAsyncNotifications</a>
 

 

