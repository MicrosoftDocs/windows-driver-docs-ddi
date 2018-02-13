---
UID: NF:rilapi.RIL_GetUiccATR
title: RIL_GetUiccATR function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getuiccatr.htm
old-project: netvista
ms.assetid: 7518f018-5ece-43e6-8aad-02038c0e94fc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_GetUiccATR, netvista.ril_getuiccatr, RIL_GetUiccATR method [Network Drivers Starting with Windows Vista], RIL_GetUiccATR
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
-	RIL_GetUiccATR
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetUiccATR function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetUiccATR(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwSlotIndex
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



