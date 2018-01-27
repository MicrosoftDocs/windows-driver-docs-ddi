---
UID: NF:rilapi.RIL_Dial_V1
title: RIL_Dial_V1 function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_dial_v1.htm
old-project: netvista
ms.assetid: 8d4967fc-bcb7-4770-92a8-aac9ef13085b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_Dial_V1 method [Network Drivers Starting with Windows Vista], rilapi/RIL_Dial_V1, netvista.ril_dial_v1, RIL_Dial_V1
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
-	RIL_Dial_V1
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_Dial_V1 function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_Dial_V1(
   HRIL              hRil,
   LPVOID            lpContext,
   DWORD             dwExecutor,
   const RILADDRESS  lpraAddress,
   DWORD             dwOptions
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwExecutor



### -param lpraAddress



### -param dwOptions



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


