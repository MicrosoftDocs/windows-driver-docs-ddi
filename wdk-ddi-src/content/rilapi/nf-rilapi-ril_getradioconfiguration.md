---
UID: NF:rilapi.RIL_GetRadioConfiguration
title: RIL_GetRadioConfiguration function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getradioconfiguration.htm
old-project: netvista
ms.assetid: 8e450e58-41e0-4df2-83d9-8975d437cdcb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, G, I, L, R, RIL_GetRadioConfiguration, RIL_GetRadioConfiguration method [Network Drivers Starting with Windows Vista], _, a, d, e, f, g, i, n, netvista.ril_getradioconfiguration, o, r, rilapi/RIL_GetRadioConfiguration, t, u"
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
-	RIL_GetRadioConfiguration
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetRadioConfiguration function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetRadioConfiguration(
   HRIL   hRil,
   LPVOID lpContext
);
````


## -parameters




### -param hRil


### -param lpContext


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



