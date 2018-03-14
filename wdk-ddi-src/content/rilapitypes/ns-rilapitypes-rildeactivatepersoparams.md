---
UID: NS:rilapitypes.RILDEACTIVATEPERSOPARAMS
title: RILDEACTIVATEPERSOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeactivatepersoparams.htm
old-project: netvista
ms.assetid: 408ae5d4-f83f-4e4a-9850-a7bae70a2da2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rildeactivatepersoparams, ntddrilapitypes/RILDEACTIVATEPERSOPARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
-	RILDEACTIVATEPERSOPARAMS
product: Windows
targetos: Windows
req.typenames: RILDEACTIVATEPERSOPARAMS, *LPRILDEACTIVATEPERSOPARAMS
req.product: Windows 10 or later.
---

# RILDEACTIVATEPERSOPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILDEACTIVATEPERSOPARAMS {
  DWORD      dwPersoFeature;
  char [256] szPassword;
} RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS;
````


## -struct-fields




### -field dwPersoFeature


### -field szPassword

