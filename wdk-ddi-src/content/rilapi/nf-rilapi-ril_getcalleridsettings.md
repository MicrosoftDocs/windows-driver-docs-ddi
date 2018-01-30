---
UID: NF:rilapi.RIL_GetCallerIdSettings
title: RIL_GetCallerIdSettings function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getcalleridsettings.htm
old-project: netvista
ms.assetid: c85590bb-6489-4675-9008-8c5606d0b889
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_GetCallerIdSettings, netvista.ril_getcalleridsettings, RIL_GetCallerIdSettings, RIL_GetCallerIdSettings method [Network Drivers Starting with Windows Vista]
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
-	RIL_GetCallerIdSettings
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_GetCallerIdSettings function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetCallerIdSettings(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwExecutor
);
````


## -parameters




### -param hRil



### -param lpContext



### -param dwExecutor



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


