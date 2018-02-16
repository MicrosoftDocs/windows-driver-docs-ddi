---
UID: NF:rilapi.RIL_SetExecutorConfig
title: RIL_SetExecutorConfig function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setexecutorconfig.htm
old-project: netvista
ms.assetid: 528f5bfb-a84d-48e5-a74d-8f7bcee6d4cb
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_SetExecutorConfig, RIL_SetExecutorConfig method [Network Drivers Starting with Windows Vista], RIL_SetExecutorConfig, netvista.ril_setexecutorconfig
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
-	RIL_SetExecutorConfig
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetExecutorConfig function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetExecutorConfig(
   HRIL                     hRil,
   LPVOID                   lpContext,
   DWORD                    dwExecutor,
   const RILEXECUTORCONFIG  lpRilExecutorConfig
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwExecutor


### -param lpRilExecutorConfig


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



