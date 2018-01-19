---
UID: NS:ntddrilapitypes.RILSETEXECUTORFOCUSPARAMS
title: RILSETEXECUTORFOCUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetexecutorfocusparams.htm
old-project: netvista
ms.assetid: 5e9f9ef1-e86e-49a7-be76-a31595da28e6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETEXECUTORFOCUSPARAMS, *LPRILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS
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
req.alt-api: RILSETEXECUTORFOCUSPARAMS
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS
---

# RILSETEXECUTORFOCUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETEXECUTORFOCUSPARAMS {
  DWORD    dwNumberOfExecutors;
  BOOL [2] fFocusStates;
} RILSETEXECUTORFOCUSPARAMS, RILSETEXECUTORFOCUSPARAMS;
````


## -struct-fields

### -field dwNumberOfExecutors


### -field fFocusStates


## -remarks
