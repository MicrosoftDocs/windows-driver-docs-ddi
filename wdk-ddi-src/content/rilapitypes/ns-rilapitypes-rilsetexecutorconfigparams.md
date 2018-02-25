---
UID: NS:rilapitypes.RILSETEXECUTORCONFIGPARAMS
title: RILSETEXECUTORCONFIGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorconfigparams_2.htm
old-project: netvista
ms.assetid: b8dcfd30-e7fc-45ab-b407-a0719f624c8e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSETEXECUTORCONFIGPARAMS, ,, A, C, E, F, G, I, L, M, N, O, P, R, RILSETEXECUTORCONFIGPARAMS, RILSETEXECUTORCONFIGPARAMS structure [Network Drivers Starting with Windows Vista], S, T, U, X, netvista.rilsetexecutorconfigparams_2, rilapitypes/RILSETEXECUTORCONFIGPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILSETEXECUTORCONFIGPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETEXECUTORCONFIGPARAMS, *LPRILSETEXECUTORCONFIGPARAMS
req.product: Windows 10 or later.
---

# RILSETEXECUTORCONFIGPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSETEXECUTORCONFIGPARAMS {
  DWORD              dwExecutor;
  RILEXECUTORCONFIG  rilExecutorConfig;
} RILSETEXECUTORCONFIGPARAMS, RILSETEXECUTORCONFIGPARAMS;
````


## -struct-fields




### -field dwExecutor


### -field rilExecutorConfig

