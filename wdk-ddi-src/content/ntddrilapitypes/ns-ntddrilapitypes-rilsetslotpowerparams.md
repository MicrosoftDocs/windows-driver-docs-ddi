---
UID: NS:ntddrilapitypes.RILSETSLOTPOWERPARAMS
title: RILSETSLOTPOWERPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetslotpowerparams.htm
old-project: netvista
ms.assetid: 3e3bd3f1-08a2-4b20-b427-85b1236325b9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSETSLOTPOWERPARAMS, RILSETSLOTPOWERPARAMS, *LPRILSETSLOTPOWERPARAMS
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
req.alt-api: RILSETSLOTPOWERPARAMS
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
req.typenames: RILSETSLOTPOWERPARAMS, *LPRILSETSLOTPOWERPARAMS
---

# RILSETSLOTPOWERPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETSLOTPOWERPARAMS {
  DWORD  dwSlotIndex;
  BOOL   fPowerOn;
} RILSETSLOTPOWERPARAMS, RILSETSLOTPOWERPARAMS;
````


## -struct-fields

### -field dwSlotIndex


### -field fPowerOn


## -remarks
