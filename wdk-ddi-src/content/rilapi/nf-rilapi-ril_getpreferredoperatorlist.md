---
UID: NF:rilapi.RIL_GetPreferredOperatorList
title: RIL_GetPreferredOperatorList function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getpreferredoperatorlist.htm
old-project: netvista
ms.assetid: bee76337-8349-4e61-9b0c-e525ed001850
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RIL_GetPreferredOperatorList, RIL_GetPreferredOperatorList method [Network Drivers Starting with Windows Vista], netvista.ril_getpreferredoperatorlist, rilapi/RIL_GetPreferredOperatorList
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
-	RIL_GetPreferredOperatorList
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetPreferredOperatorList function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetPreferredOperatorList(
   HRIL                                hRil,
   LPVOID                              lpContext,
   HUICCAPP                            hUiccApp,
   RILGETPREFERENCEDOPERATORLISTFORMAT dwFormat
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwFormat


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



