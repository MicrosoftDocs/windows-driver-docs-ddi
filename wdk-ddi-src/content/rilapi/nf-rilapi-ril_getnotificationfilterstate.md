---
UID: NF:rilapi.RIL_GetNotificationFilterState
title: RIL_GetNotificationFilterState function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getnotificationfilterstate.htm
old-project: netvista
ms.assetid: 143eca3c-fa20-4731-bdfe-c48b929febcb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_getnotificationfilterstate, RIL_GetNotificationFilterState method [Network Drivers Starting with Windows Vista], RIL_GetNotificationFilterState, rilapi/RIL_GetNotificationFilterState
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
-	RIL_GetNotificationFilterState
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetNotificationFilterState function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetNotificationFilterState(
   HRIL   hRil,
   LPVOID lpContext
);
````


## -parameters




### -param hRil



### -param lpContext



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


