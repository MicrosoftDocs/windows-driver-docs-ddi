---
UID: NF:rilapi.RIL_SendUiccToolkitCmdResponse
title: RIL_SendUiccToolkitCmdResponse function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_senduicctoolkitcmdresponse.htm
old-project: netvista
ms.assetid: 400e2172-803c-4b6c-a41e-3c322077ffa4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_SendUiccToolkitCmdResponse, netvista.ril_senduicctoolkitcmdresponse, RIL_SendUiccToolkitCmdResponse method [Network Drivers Starting with Windows Vista], rilapi/RIL_SendUiccToolkitCmdResponse
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
-	RIL_SendUiccToolkitCmdResponse
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_SendUiccToolkitCmdResponse function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SendUiccToolkitCmdResponse(
   HRIL         hRil,
   LPVOID       lpContext,
   DWORD        dwSlotIndex,
   const LPBYTE pbDetails,
   DWORD        dwDetailSize
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param pbDetails


### -param dwDetailSize


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



