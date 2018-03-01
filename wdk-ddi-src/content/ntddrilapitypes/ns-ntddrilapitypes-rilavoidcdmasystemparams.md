---
UID: NS:ntddrilapitypes.RILAVOIDCDMASYSTEMPARAMS
title: RILAVOIDCDMASYSTEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilavoidcdmasystemparams.htm
old-project: netvista
ms.assetid: cf160fb9-8230-4b75-8a4f-d19ef001f54a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS, RILAVOIDCDMASYSTEMPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilavoidcdmasystemparams, ntddrilapitypes/RILAVOIDCDMASYSTEMPARAMS"
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
-	RILAVOIDCDMASYSTEMPARAMS
product: Windows
targetos: Windows
req.typenames: RILAVOIDCDMASYSTEMPARAMS, *LPRILAVOIDCDMASYSTEMPARAMS
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

