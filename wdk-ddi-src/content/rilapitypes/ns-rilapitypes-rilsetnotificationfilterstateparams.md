---
UID: NS:rilapitypes.RILSETNOTIFICATIONFILTERSTATEPARAMS
title: RILSETNOTIFICATIONFILTERSTATEPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetnotificationfilterstateparams_2.htm
old-project: netvista
ms.assetid: 87dc2ef3-047c-4255-832c-508b378ca412
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS, RILSETNOTIFICATIONFILTERSTATEPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsetnotificationfilterstateparams_2, rilapitypes/RILSETNOTIFICATIONFILTERSTATEPARAMS"
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
-	rilapitypes.h
apiname:
-	RILSETNOTIFICATIONFILTERSTATEPARAMS
product: Windows
targetos: Windows
req.typenames: RILSETNOTIFICATIONFILTERSTATEPARAMS, *LPRILSETNOTIFICATIONFILTERSTATEPARAMS
req.product: Windows 10 or later.
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

