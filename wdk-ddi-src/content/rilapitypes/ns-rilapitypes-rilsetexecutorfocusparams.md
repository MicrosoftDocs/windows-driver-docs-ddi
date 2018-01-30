---
UID: NS:rilapitypes.RILSETEXECUTORFOCUSPARAMS
title: RILSETEXECUTORFOCUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorfocusparams_2.htm
old-project: netvista
ms.assetid: 724df793-72cb-4460-bec8-0136b86ff82d
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsetexecutorfocusparams_2, RILSETEXECUTORFOCUSPARAMS, rilapitypes/RILSETEXECUTORFOCUSPARAMS, *LPRILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS structure [Network Drivers Starting with Windows Vista]
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
-	RILSETEXECUTORFOCUSPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETEXECUTORFOCUSPARAMS, *LPRILSETEXECUTORFOCUSPARAMS
req.product: Windows 10 or later.
---

# RILSETEXECUTORFOCUSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSETEXECUTORFOCUSPARAMS {
  DWORD                   dwNumberOfExecutors;
  BOOL [MAXNUM_EXECUTORS] fFocusStates;
} RILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS;
````


## -struct-fields




### -field dwNumberOfExecutors



### -field fFocusStates


