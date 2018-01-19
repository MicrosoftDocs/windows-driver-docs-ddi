---
UID: NS:ntddrilapitypes.RILSENDFLASHPARAMS
title: RILSENDFLASHPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendflashparams.htm
old-project: netvista
ms.assetid: e45b8f47-4e46-4265-9c56-055e753eb6e6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDFLASHPARAMS, *LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS
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
req.alt-api: RILSENDFLASHPARAMS
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
req.typenames: *LPRILSENDFLASHPARAMS, RILSENDFLASHPARAMS
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
