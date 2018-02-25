---
UID: NF:rilapi.RIL_DisableModemFilters
title: RIL_DisableModemFilters function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_disablemodemfilters.htm
old-project: netvista
ms.assetid: eb1ac5cc-f757-4aee-9a21-ed4b03d4b6a8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, F, I, L, M, R, RIL_DisableModemFilters, RIL_DisableModemFilters method [Network Drivers Starting with Windows Vista], _, a, b, d, e, i, l, m, netvista.ril_disablemodemfilters, o, r, rilapi/RIL_DisableModemFilters, s, t"
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
-	RIL_DisableModemFilters
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_DisableModemFilters function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_DisableModemFilters(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  filterID
);
````


## -parameters




### -param hRil


### -param lpContext


### -param filterID


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



