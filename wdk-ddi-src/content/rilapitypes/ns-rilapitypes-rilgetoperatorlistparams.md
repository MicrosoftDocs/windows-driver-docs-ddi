---
UID: NS:rilapitypes.RILGETOPERATORLISTPARAMS
title: RILGETOPERATORLISTPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetoperatorlistparams_2.htm
old-project: netvista
ms.assetid: d5836240-81d4-4134-9222-c810cd8f5822
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS, *LPRILGETOPERATORLISTPARAMS
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
req.alt-api: RILGETOPERATORLISTPARAMS
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
req.typenames: RILGETOPERATORLISTPARAMS, *LPRILGETOPERATORLISTPARAMS
req.product: Windows 10 or later.
---

# RILGETOPERATORLISTPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILGETOPERATORLISTPARAMS {
  DWORD  dwExecutor;
  DWORD  dwSystemTypes;
} RILGETOPERATORLISTPARAMS, RILGETOPERATORLISTPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwSystemTypes


## -remarks
