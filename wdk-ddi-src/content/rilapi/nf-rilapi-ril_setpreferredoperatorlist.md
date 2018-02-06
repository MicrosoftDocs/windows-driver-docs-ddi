---
UID: NF:rilapi.RIL_SetPreferredOperatorList
title: RIL_SetPreferredOperatorList function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setpreferredoperatorlist.htm
old-project: netvista
ms.assetid: e61e9e3f-b70f-4b0a-8e64-4c7c4c086130
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SetPreferredOperatorList, RIL_SetPreferredOperatorList method [Network Drivers Starting with Windows Vista], netvista.ril_setpreferredoperatorlist, rilapi/RIL_SetPreferredOperatorList
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
-	RIL_SetPreferredOperatorList
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetPreferredOperatorList function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetPreferredOperatorList(
   HRIL              hRil,
   LPVOID            lpContext,
   HUICCAPP          hUiccApp,
   DWORD             dwPreferredListSize,
   RILOPERATORNAMES  lpPreferredList
);
````


## -parameters




### -param hRil



### -param lpContext



### -param hUiccApp



### -param dwPreferredListSize



### -param lpPreferredList



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


