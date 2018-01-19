---
UID: NS:ntddrilapitypes.RILDELETEADDITIONALNUMBERSTRINGPARAMS
title: RILDELETEADDITIONALNUMBERSTRINGPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeleteadditionalnumberstringparams.htm
old-project: netvista
ms.assetid: 89ae70b9-56d9-4169-8bbd-0eb2d916a928
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILDELETEADDITIONALNUMBERSTRINGPARAMS, *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS
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
req.alt-api: RILDELETEADDITIONALNUMBERSTRINGPARAMS
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
req.typenames: *LPRILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS
---

# RILDELETEADDITIONALNUMBERSTRINGPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILDELETEADDITIONALNUMBERSTRINGPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwNumId;
} RILDELETEADDITIONALNUMBERSTRINGPARAMS, RILDELETEADDITIONALNUMBERSTRINGPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwNumId


## -remarks
