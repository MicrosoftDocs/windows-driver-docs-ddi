---
UID: NF:rilapi.RIL_GetPersoDeactivationState
title: RIL_GetPersoDeactivationState function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getpersodeactivationstate.htm
old-project: netvista
ms.assetid: c82cfde4-f214-4722-8f59-d727ad5bfe7e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_GetPersoDeactivationState method [Network Drivers Starting with Windows Vista], netvista.ril_getpersodeactivationstate, RIL_GetPersoDeactivationState, rilapi/RIL_GetPersoDeactivationState
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
-	RIL_GetPersoDeactivationState
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_GetPersoDeactivationState function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetPersoDeactivationState(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwPersoFeature
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwPersoFeature



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


