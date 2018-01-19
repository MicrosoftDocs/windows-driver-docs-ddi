---
UID: NS:rilapitypes.RILAVOIDCDMASYSTEMPARAMS
title: RILAVOIDCDMASYSTEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilavoidcdmasystemparams_2.htm
old-project: netvista
ms.assetid: bd938bd9-479a-434c-91d6-93ec76ebe5d6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILAVOIDCDMASYSTEMPARAMS, *LPRILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS
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
req.alt-api: RILAVOIDCDMASYSTEMPARAMS
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
req.typenames: *LPRILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS
req.product: Windows 10 or later.
---

# RILAVOIDCDMASYSTEMPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILAVOIDCDMASYSTEMPARAMS {
  DWORD                       dwExecutor;
  RILCDMAAVOIDANCEREQUESTYPE  dwAvoidanceReqType;
} RILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwAvoidanceReqType


## -remarks
