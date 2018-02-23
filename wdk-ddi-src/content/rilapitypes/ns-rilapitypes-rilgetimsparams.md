---
UID: NS:rilapitypes.RILGETIMSPARAMS
title: RILGETIMSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetimsparams_2.htm
old-project: netvista
ms.assetid: fc2b7e6f-3646-40a6-bdad-a1bbb94adf09
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILGETIMSPARAMS, netvista.rilgetimsparams_2, rilapitypes/RILGETIMSPARAMS, RILGETIMSPARAMS structure [Network Drivers Starting with Windows Vista], RILGETIMSPARAMS"
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
-	RILGETIMSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETIMSPARAMS, *LPRILGETIMSPARAMS
req.product: Windows 10 or later.
---

# RILGETIMSPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILGETIMSPARAMS {
  DWORD  cbSize;
  DWORD  dwExecutor;
} RILGETIMSPARAMS, RILGETIMSPARAMS;
````


## -struct-fields




### -field cbSize


### -field dwExecutor

