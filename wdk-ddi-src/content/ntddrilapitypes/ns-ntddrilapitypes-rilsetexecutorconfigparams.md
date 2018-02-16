---
UID: NS:ntddrilapitypes.RILSETEXECUTORCONFIGPARAMS
title: RILSETEXECUTORCONFIGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorconfigparams.htm
old-project: netvista
ms.assetid: de392c8c-3153-48e8-85ad-dc1a5ed2812c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSETEXECUTORCONFIGPARAMS, netvista.rilsetexecutorconfigparams, *LPRILSETEXECUTORCONFIGPARAMS, ntddrilapitypes/RILSETEXECUTORCONFIGPARAMS, RILSETEXECUTORCONFIGPARAMS structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILSETEXECUTORCONFIGPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETEXECUTORCONFIGPARAMS, RILSETEXECUTORCONFIGPARAMS"
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

