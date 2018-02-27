---
UID: NF:rilapi.RIL_StopModemLogs
title: RIL_StopModemLogs function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_stopmodemlogs.htm
old-project: netvista
ms.assetid: 1d1f092c-e867-49f7-8f17-90fbf73733fb
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_StopModemLogs, RIL_StopModemLogs method [Network Drivers Starting with Windows Vista], netvista.ril_stopmodemlogs, rilapi/RIL_StopModemLogs
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
-	RIL_StopModemLogs
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_StopModemLogs function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_StopModemLogs(
   HRIL   hRil,
   LPVOID lpContext
);
````


## -parameters




### -param hRil


### -param lpContext


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



