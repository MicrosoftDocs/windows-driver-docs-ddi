---
UID: NF:rilapi.RIL_GetCallForwardingSettings
title: RIL_GetCallForwardingSettings function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getcallforwardingsettings.htm
old-project: netvista
ms.assetid: f9abb454-5fd1-4680-ab83-f24897c89193
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, G, I, L, R, RIL_GetCallForwardingSettings, RIL_GetCallForwardingSettings method [Network Drivers Starting with Windows Vista], S, _, a, d, e, g, i, l, n, netvista.ril_getcallforwardingsettings, o, r, rilapi/RIL_GetCallForwardingSettings, s, t, w"
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
-	RIL_GetCallForwardingSettings
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetCallForwardingSettings function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetCallForwardingSettings(
   HRIL                            hRil,
   LPVOID                          lpContext,
   DWORD                           dwExecutor,
   RILCALLFORWARDINGSETTINGSREASON dwReason,
   BOOL                            fAllClasses,
   DWORD                           dwInfoClasses
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param dwReason


### -param fAllClasses


### -param dwInfoClasses


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



