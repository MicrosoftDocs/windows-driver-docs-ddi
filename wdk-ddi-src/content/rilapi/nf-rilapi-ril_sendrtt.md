---
UID: NF:rilapi.RIL_SendRTT
title: RIL_SendRTT function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendrtt.htm
old-project: netvista
ms.assetid: d655aa2e-ec58-4f9b-a349-a19e7c78469a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_sendrtt, RIL_SendRTT method [Network Drivers Starting with Windows Vista], RIL_SendRTT, rilapi/RIL_SendRTT
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
-	RIL_SendRTT
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_SendRTT function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SendRTT(
   HRIL         hRil,
   LPVOID       lpContext,
   DWORD        dwID,
   DWORD        dwExecutor,
   const WCHAR  lpwszRTTText
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwID



### -param dwExecutor



### -param lpwszRTTText



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


