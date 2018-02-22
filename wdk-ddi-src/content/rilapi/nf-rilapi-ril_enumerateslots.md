---
UID: NF:rilapi.RIL_EnumerateSlots
title: RIL_EnumerateSlots function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_enumerateslots.htm
old-project: netvista
ms.assetid: 58df87d5-1e7b-4ec8-8e88-631bbd78757a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapi/RIL_EnumerateSlots, RIL_EnumerateSlots method [Network Drivers Starting with Windows Vista], RIL_EnumerateSlots, netvista.ril_enumerateslots
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
-	RIL_EnumerateSlots
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_EnumerateSlots function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_EnumerateSlots(
   HRIL   hRil,
   LPVOID lpContext
);
````


## -parameters




### -param hRil


### -param lpContext


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



