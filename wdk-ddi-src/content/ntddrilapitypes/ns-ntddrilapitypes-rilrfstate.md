---
UID: NS:ntddrilapitypes.RILRFSTATE
title: RILRFSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstate.htm
old-project: netvista
ms.assetid: 7eb78864-d20c-4993-8b33-63096bf971fa
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILRFSTATE, *LPRILRFSTATE, RILRFSTATE
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
req.alt-api: RILRFSTATE
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
req.typenames: *LPRILRFSTATE, RILRFSTATE
---

# RILRFSTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRFSTATE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwRFState;
  DWORD    dwRFDataSize;
  BYTE [1] bRFData;
} RILRFSTATE, RILRFSTATE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwRFState


### -field dwRFDataSize


### -field bRFData


## -remarks
