---
UID: NS:rilapitypes.RILSENDFLASHPARAMS
title: RILSENDFLASHPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendflashparams_2.htm
old-project: netvista
ms.assetid: 2279c1f2-382f-4cae-a881-997f0bed7b6d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS
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
req.alt-api: RILSENDFLASHPARAMS
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS
req.product: Windows 10 or later.
---

# RILSENDFLASHPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSENDFLASHPARAMS {
  DWORD       dwExecutor;
  RILADDRESS  raAddress;
} RILSENDFLASHPARAMS, RILSENDFLASHPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field raAddress


## -remarks
