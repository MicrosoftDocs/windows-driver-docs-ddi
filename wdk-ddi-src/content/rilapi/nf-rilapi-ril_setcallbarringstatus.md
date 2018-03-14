---
UID: NF:rilapi.RIL_SetCallBarringStatus
title: RIL_SetCallBarringStatus function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setcallbarringstatus.htm
old-project: netvista
ms.assetid: 2012944f-b889-4084-92c8-95c1340599f3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RIL_SetCallBarringStatus, RIL_SetCallBarringStatus method [Network Drivers Starting with Windows Vista], netvista.ril_setcallbarringstatus, rilapi/RIL_SetCallBarringStatus
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
req.lib: 
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
-	RIL_SetCallBarringStatus
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetCallBarringStatus function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetCallBarringStatus(
   HRIL                             hRil,
   LPVOID                           lpContext,
   DWORD                            dwExecutor,
   RILCALLBARRINGSTATUSPARAMSTYPE   dwType,
   BOOL                             fAllClasses,
   DWORD                            dwInfoClasses,
   LPCSTR                           lpszPassword,
   RILCALLBARRINGSTATUSPARAMSSTATUS dwStatus
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param dwType


### -param fAllClasses


### -param dwInfoClasses


### -param lpszPassword


### -param dwStatus


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



