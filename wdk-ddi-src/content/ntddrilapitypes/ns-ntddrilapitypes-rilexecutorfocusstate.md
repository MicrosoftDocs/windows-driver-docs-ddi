---
UID: NS:ntddrilapitypes.RILEXECUTORFOCUSSTATE
title: RILEXECUTORFOCUSSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorfocusstate.htm
old-project: netvista
ms.assetid: 74fc88c0-3edf-4831-a03b-4ace6ca2ec04
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILEXECUTORFOCUSSTATE, *LPRILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE
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
req.alt-api: RILEXECUTORFOCUSSTATE
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
req.typenames: *LPRILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE
---

# RILEXECUTORFOCUSSTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILEXECUTORFOCUSSTATE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwNumberOfExecutors;
  BOOL [2] fFocusStates;
} RILEXECUTORFOCUSSTATE, RILEXECUTORFOCUSSTATE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwNumberOfExecutors


### -field fFocusStates


## -remarks
