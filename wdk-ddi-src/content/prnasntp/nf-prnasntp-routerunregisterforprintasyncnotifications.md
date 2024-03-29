---
UID: NF:prnasntp.RouterUnregisterForPrintAsyncNotifications
title: RouterUnregisterForPrintAsyncNotifications function (prnasntp.h)
description: The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server.
old-location: print\routerunregisterforprintasyncnotifications.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["RouterUnregisterForPrintAsyncNotifications function"]
ms.keywords: RouterUnregisterForPrintAsyncNotifications, RouterUnregisterForPrintAsyncNotifications function [Print Devices], print.routerunregisterforprintasyncnotifications, prnasntp/RouterUnregisterForPrintAsyncNotifications, spoolfnc_3c629be8-f1d8-43fb-b225-582e4bb76c51.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RouterUnregisterForPrintAsyncNotifications
 - prnasntp/RouterUnregisterForPrintAsyncNotifications
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - RouterUnregisterForPrintAsyncNotifications
---

# RouterUnregisterForPrintAsyncNotifications function


## -description

The <code>RouterUnregisterForPrintAsyncNotifications</code> function unregisters for receiving asynchronous notifications associated with a printer or print server.

## -parameters

### -param hNotify [in]


The registration handle returned by the <a href="/windows-hardware/drivers/ddi/prnasntp/nf-prnasntp-routerregisterforprintasyncnotifications">RouterRegisterForPrintAsyncNotifications</a> function.

## -returns

This function returns S_OK on success, and a standard COM error code otherwise.

## -see-also

<a href="/windows-hardware/drivers/ddi/prnasntp/nf-prnasntp-routerregisterforprintasyncnotifications">RouterRegisterForPrintAsyncNotifications</a>
