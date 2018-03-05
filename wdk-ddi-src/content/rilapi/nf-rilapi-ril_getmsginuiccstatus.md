---
UID: NF:rilapi.RIL_GetMsgInUiccStatus
title: RIL_GetMsgInUiccStatus function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getmsginuiccstatus.htm
old-project: netvista
ms.assetid: 9cf60a9b-cb1e-46a5-b8d8-c7fc2c6f2cf3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL_GetMsgInUiccStatus, RIL_GetMsgInUiccStatus method [Network Drivers Starting with Windows Vista], netvista.ril_getmsginuiccstatus, rilapi/RIL_GetMsgInUiccStatus
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
-	RIL_GetMsgInUiccStatus
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetMsgInUiccStatus function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetMsgInUiccStatus(
   HRIL     hRil,
   LPVOID   lpContext,
   HUICCAPP hUiccApp,
   DWORD    dwIndex
);
````


## -parameters




### -param hRil


### -param lpContext


### -param hUiccApp


### -param dwIndex


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



