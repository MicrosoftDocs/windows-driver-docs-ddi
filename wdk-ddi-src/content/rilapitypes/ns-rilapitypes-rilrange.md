---
UID: NS:rilapitypes.RILRANGE
title: RILRANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrange_2.htm
old-project: netvista
ms.assetid: f14aa2bc-1eeb-4c17-836a-52046ba388f1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILRANGE, ,, A, E, G, I, L, N, P, R, RILRANGE, RILRANGE structure [Network Drivers Starting with Windows Vista], netvista.rilrange_2, rilapitypes/RILRANGE"
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
-	RILRANGE
product: Windows
targetos: Windows
req.typenames: RILRANGE, *LPRILRANGE
req.product: Windows 10 or later.
---

# RILRANGE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRANGE {
  DWORD  dwMinValue;
  DWORD  dwMaxValue;
} RILRANGE, RILRANGE;
````


## -struct-fields




### -field dwMinValue


### -field dwMaxValue

