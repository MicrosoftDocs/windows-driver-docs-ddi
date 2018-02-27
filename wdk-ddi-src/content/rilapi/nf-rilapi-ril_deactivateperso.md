---
UID: NF:rilapi.RIL_DeactivatePerso
title: RIL_DeactivatePerso function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_deactivateperso.htm
old-project: netvista
ms.assetid: 3116482a-aa56-4a1d-98ef-da06c5c1b789
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RIL_DeactivatePerso, RIL_DeactivatePerso method [Network Drivers Starting with Windows Vista], netvista.ril_deactivateperso, rilapi/RIL_DeactivatePerso
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
-	RIL_DeactivatePerso
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_DeactivatePerso function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_DeactivatePerso(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwPersoFeature,
   LPCSTR lpszPassword
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwPersoFeature


### -param lpszPassword


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



