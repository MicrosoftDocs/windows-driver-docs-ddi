---
UID: NF:rilapi.RIL_GetUiccLockState
title: RIL_GetUiccLockState function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getuicclockstate.htm
old-project: netvista
ms.assetid: a831f49b-203e-4672-aced-679f0835dabb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_GetUiccLockState, RIL_GetUiccLockState method [Network Drivers Starting with Windows Vista], netvista.ril_getuicclockstate, rilapi/RIL_GetUiccLockState
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_GetUiccLockState
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetUiccLockState function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetUiccLockState(
   HRIL               hRil,
   LPVOID             lpContext,
   const RILUICCLOCK  lpRilUiccLock
);
````


## -parameters




### -param hRil


### -param lpContext


### -param lpRilUiccLock


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



