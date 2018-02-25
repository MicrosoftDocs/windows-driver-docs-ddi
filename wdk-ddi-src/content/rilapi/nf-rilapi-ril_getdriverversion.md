---
UID: NF:rilapi.RIL_GetDriverVersion
title: RIL_GetDriverVersion function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getdriverversion.htm
old-project: netvista
ms.assetid: 7cf55a17-fbb9-4edc-ae12-23dce450a628
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , D, G, I, L, R, RIL_GetDriverVersion, RIL_GetDriverVersion method [Network Drivers Starting with Windows Vista], V, _, e, i, n, netvista.ril_getdriverversion, o, r, rilapi/RIL_GetDriverVersion, s, t, v"
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
-	RIL_GetDriverVersion
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetDriverVersion function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetDriverVersion(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwMinVersion,
   DWORD  dwMaxVersion
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwMinVersion


### -param dwMaxVersion


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



