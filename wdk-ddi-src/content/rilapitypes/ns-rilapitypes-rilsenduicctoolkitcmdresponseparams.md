---
UID: NS:rilapitypes.RILSENDUICCTOOLKITCMDRESPONSEPARAMS
title: RILSENDUICCTOOLKITCMDRESPONSEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsenduicctoolkitcmdresponseparams_2.htm
old-project: netvista
ms.assetid: ae203f95-3568-4c78-b799-e1eef6218c7f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSENDUICCTOOLKITCMDRESPONSEPARAMS, ,, A, C, D, E, I, K, L, M, N, O, P, R, RILSENDUICCTOOLKITCMDRESPONSEPARAMS, RILSENDUICCTOOLKITCMDRESPONSEPARAMS structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.rilsenduicctoolkitcmdresponseparams_2, rilapitypes/RILSENDUICCTOOLKITCMDRESPONSEPARAMS"
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
-	RILSENDUICCTOOLKITCMDRESPONSEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDUICCTOOLKITCMDRESPONSEPARAMS, *LPRILSENDUICCTOOLKITCMDRESPONSEPARAMS
req.product: Windows 10 or later.
---

# RILSENDUICCTOOLKITCMDRESPONSEPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILSENDUICCTOOLKITCMDRESPONSEPARAMS {
  DWORD    dwSlotIndex;
  DWORD    dwDetailsSize;
  BYTE [1] bDetails;
} RILSENDUICCTOOLKITCMDRESPONSEPARAMS, RILSENDUICCTOOLKITCMDRESPONSEPARAMS;
````


## -struct-fields




### -field dwSlotIndex


### -field dwDetailsSize


### -field bDetails

