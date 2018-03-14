---
UID: NS:ntddrilapitypes.RILGETIMSPARAMS
title: RILGETIMSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetimsparams.htm
old-project: netvista
ms.assetid: 4e8f01af-9279-483a-90f9-d0391122ba5b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILGETIMSPARAMS, RILGETIMSPARAMS, RILGETIMSPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilgetimsparams, ntddrilapitypes/RILGETIMSPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILGETIMSPARAMS
product: Windows
targetos: Windows
req.typenames: RILGETIMSPARAMS, *LPRILGETIMSPARAMS
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

