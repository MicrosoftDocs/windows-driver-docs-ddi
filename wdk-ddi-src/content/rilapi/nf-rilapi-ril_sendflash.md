---
UID: NF:rilapi.RIL_SendFlash
title: RIL_SendFlash function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendflash.htm
old-project: netvista
ms.assetid: 9a23fae8-7142-48a1-871e-1fa3a6d8e112
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RIL_SendFlash
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
req.alt-api: RIL_SendFlash
req.alt-loc: rilapi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SendFlash function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_SendFlash(
   HRIL         hRil,
   LPVOID       lpContext,
   DWORD        dwExecutor,
   LPRILADDRESS lpraRilAddress
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwExecutor 


### -param lpraRilAddress 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
