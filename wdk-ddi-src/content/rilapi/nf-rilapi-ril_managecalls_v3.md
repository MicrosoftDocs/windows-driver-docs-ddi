---
UID: NF:rilapi.RIL_ManageCalls_V3
title: RIL_ManageCalls_V3 function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_managecalls_v3.htm
old-project: netvista
ms.assetid: 4c301656-8918-46f2-8f8f-3ceff2af8e94
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 3, C, I, L, M, R, RIL_ManageCalls_V3, RIL_ManageCalls_V3 method [Network Drivers Starting with Windows Vista], V, _, a, e, g, l, n, netvista.ril_managecalls_v3, rilapi/RIL_ManageCalls_V3, s"
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
-	RIL_ManageCalls_V3
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_ManageCalls_V3 function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_ManageCalls_V3(
   HRIL                               hRil,
   LPVOID                             lpContext,
   DWORD                              dwExecutor,
   RILMANAGECALLPARAMSCOMMAND         dwCommand,
   DWORD                              dwID,
   const LPRILCALLMEDIAOFFERANSWERSET lprcmOfferAnswer,
   const LPRILADDRESS                 lpraAddress
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param dwCommand


### -param dwID


### -param lprcmOfferAnswer


### -param lpraAddress


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



