---
UID: NF:rilapi.RIL_SetCallForwardingStatus
title: RIL_SetCallForwardingStatus function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setcallforwardingstatus.htm
old-project: netvista
ms.assetid: c73e3b75-e11d-44b8-9a4a-c98ccfe1c820
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_SetCallForwardingStatus, RIL_SetCallForwardingStatus method [Network Drivers Starting with Windows Vista], netvista.ril_setcallforwardingstatus, RIL_SetCallForwardingStatus
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
-	RIL_SetCallForwardingStatus
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_SetCallForwardingStatus function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetCallForwardingStatus(
   HRIL                            hRil,
   LPVOID                          lpContext,
   DWORD                           dwExecutor,
   RILCALLFORWARDINGSETTINGSREASON dwReason,
   BOOL                            fAllClasses,
   DWORD                           dwInfoClasses,
   RILSERVICESETTINGSSTATUS        dwStatus
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwExecutor



### -param dwReason



### -param fAllClasses



### -param dwInfoClasses



### -param dwStatus



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


