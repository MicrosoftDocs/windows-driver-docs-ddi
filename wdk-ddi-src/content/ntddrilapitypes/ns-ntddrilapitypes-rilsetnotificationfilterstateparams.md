---
UID: NS:ntddrilapitypes.RILSETNOTIFICATIONFILTERSTATEPARAMS
title: RILSETNOTIFICATIONFILTERSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetnotificationfilterstateparams.htm
old-project: netvista
ms.assetid: bd30a156-0414-486c-92c4-21c33d32f9b8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetnotificationfilterstateparams, RILSETNOTIFICATIONFILTERSTATEPARAMS, ntddrilapitypes/RILSETNOTIFICATIONFILTERSTATEPARAMS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILSETNOTIFICATIONFILTERSTATEPARAMS
product: Windows
targetos: Windows
req.typenames: "*LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS"
---

# RILSETNOTIFICATIONFILTERSTATEPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSETNOTIFICATIONFILTERSTATEPARAMS {
  DWORD  dwFilterMask;
  DWORD  dwFilterState;
} RILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS;
````


## -struct-fields




### -field dwFilterMask



### -field dwFilterState


