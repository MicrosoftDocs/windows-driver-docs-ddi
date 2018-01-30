---
UID: NF:rilapi.RIL_GetMsgServiceOptions
title: RIL_GetMsgServiceOptions function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getmsgserviceoptions.htm
old-project: netvista
ms.assetid: 53e8be7b-dad2-4060-99b1-eca7b7fdb8ff
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ril_getmsgserviceoptions, RIL_GetMsgServiceOptions method [Network Drivers Starting with Windows Vista], RIL_GetMsgServiceOptions, rilapi/RIL_GetMsgServiceOptions
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
-	RIL_GetMsgServiceOptions
product: Windows
targetos: Windows
req.typenames: "*PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER"
req.product: Windows 10 or later.
---

# RIL_GetMsgServiceOptions function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetMsgServiceOptions(
   HRIL     hRil,
   LPVOID   lpContext,
   HUICCAPP hUiccApp
);
````


## -parameters




### -param hRil



### -param lpContext



### -param hUiccApp



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


