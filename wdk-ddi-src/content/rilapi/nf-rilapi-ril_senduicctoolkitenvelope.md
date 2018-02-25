---
UID: NF:rilapi.RIL_SendUiccToolkitEnvelope
title: RIL_SendUiccToolkitEnvelope function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_senduicctoolkitenvelope.htm
old-project: netvista
ms.assetid: 1e83f7ae-8d7b-4d06-a8f0-5b4c2f04f4a4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, I, L, R, RIL_SendUiccToolkitEnvelope, RIL_SendUiccToolkitEnvelope method [Network Drivers Starting with Windows Vista], S, T, U, _, c, d, e, i, k, l, n, netvista.ril_senduicctoolkitenvelope, o, p, rilapi/RIL_SendUiccToolkitEnvelope, t, v"
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
-	RIL_SendUiccToolkitEnvelope
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SendUiccToolkitEnvelope function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SendUiccToolkitEnvelope(
   HRIL         hRil,
   LPVOID       lpContext,
   DWORD        dwSlotIndex,
   const LPBYTE pbEnvelope,
   DWORD        dwEnvelopeSize
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param pbEnvelope


### -param dwEnvelopeSize


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



