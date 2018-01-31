---
UID: NF:rilapi.RIL_Initialize
title: RIL_Initialize function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_initialize.htm
old-project: netvista
ms.assetid: 7287281b-8c7b-4842-b312-1fff130a5de6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_initialize, rilapi/RIL_Initialize, RIL_Initialize method [Network Drivers Starting with Windows Vista], RIL_Initialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapi.h
apiname:
-	RIL_Initialize
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_Initialize function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_Initialize(
   DWORD             dwIndex,
   RILRESULTCALLBACK pfnResult,
   RILNOTIFYCALLBACK pfnNotify,
   DWORD             lpdwNotifications,
   DWORD             dwNotificationCount,
   LPVOID            lpParam,
   WCHAR             pwszClientName,
   HRIL              lphRil
);
````


## -parameters




#### - dwIndex



#### - pfnResult



#### - pfnNotify



#### - lpdwNotifications



#### - dwNotificationCount



#### - lpParam



#### - pwszClientName



#### - lphRil



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


