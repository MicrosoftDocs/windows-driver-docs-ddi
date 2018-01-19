---
UID: NS:ntddrilapitypes.RILVERSIONPARAMS
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams.htm
old-project: netvista
ms.assetid: c6931cee-2b86-4bf8-9e9d-b04e2df9eb12
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILVERSIONPARAMS, *LPRILVERSIONPARAMS, RILVERSIONPARAMS
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
req.alt-api: RILVERSIONPARAMS
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
req.typenames: *LPRILVERSIONPARAMS, RILVERSIONPARAMS
---

# RILVERSIONPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILVERSIONPARAMS {
  WORD  Minor;
  WORD  Major;
} RILVERSIONPARAMS, RILVERSIONPARAMS;
````


## -struct-fields

### -field Minor


### -field Major


## -remarks
