---
UID: NF:rilapi.RIL_ResetModem_V2
title: RIL_ResetModem_V2 function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_resetmodem_v2.htm
old-project: netvista
ms.assetid: 3ee0ac02-6473-4f1d-9ac7-28f72140cc61
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL_ResetModem_V2, RIL_ResetModem_V2 method [Network Drivers Starting with Windows Vista], netvista.ril_resetmodem_v2, rilapi/RIL_ResetModem_V2
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
-	RIL_ResetModem_V2
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_ResetModem_V2 function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_ResetModem_V2(
   HRIL                       hRil,
   LPVOID                     lpContext,
   const RILRESETMODEMPARAMS  params
);
````


## -parameters




### -param hRil


### -param lpContext


### -param params


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



