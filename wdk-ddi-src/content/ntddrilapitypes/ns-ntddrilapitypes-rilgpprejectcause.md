---
UID: NS:ntddrilapitypes.RILGPPREJECTCAUSE
title: RILGPPREJECTCAUSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgpprejectcause.htm
old-project: netvista
ms.assetid: 3008a69e-25d8-4e54-afb3-317a8ca82d34
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILGPPREJECTCAUSE, RILGPPREJECTCAUSE, RILGPPREJECTCAUSE structure [Network Drivers Starting with Windows Vista], netvista.rilgpprejectcause, ntddrilapitypes/RILGPPREJECTCAUSE"
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
-	RILGPPREJECTCAUSE
product: Windows
targetos: Windows
req.typenames: RILGPPREJECTCAUSE, *LPRILGPPREJECTCAUSE
---

# RILGPPREJECTCAUSE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILGPPREJECTCAUSE {
  DWORD  dwCauseValue;
} RILGPPREJECTCAUSE, RILGPPREJECTCAUSE;
````


## -struct-fields




### -field dwCauseValue

