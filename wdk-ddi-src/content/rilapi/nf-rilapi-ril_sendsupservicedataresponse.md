---
UID: NF:rilapi.RIL_SendSupServiceDataResponse
title: RIL_SendSupServiceDataResponse function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendsupservicedataresponse.htm
old-project: netvista
ms.assetid: 28e8093e-6fcc-4abd-999a-5948e7062c43
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, I, L, R, RIL_SendSupServiceDataResponse, RIL_SendSupServiceDataResponse method [Network Drivers Starting with Windows Vista], S, _, a, c, d, e, i, n, netvista.ril_sendsupservicedataresponse, o, p, r, rilapi/RIL_SendSupServiceDataResponse, s, t, u, v"
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
-	RIL_SendSupServiceDataResponse
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SendSupServiceDataResponse function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SendSupServiceDataResponse(
   HRIL         hRil,
   LPVOID       lpContext,
   DWORD        dwExecutor,
   const WCHAR  lpwszData
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param lpwszData


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



