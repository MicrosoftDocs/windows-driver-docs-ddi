---
UID: NS:rilapitypes.RILPOSITIONINFOLTE
title: RILPOSITIONINFOLTE (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfolte_2.htm
tech.root: netvista
ms.assetid: 4910571e-af1d-4bcf-a2d9-0d5383530171
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOLTE structure"]
ms.keywords: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE, RILPOSITIONINFOLTE structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfolte_2, rilapitypes/RILPOSITIONINFOLTE"
f1_keywords:
 - "rilapitypes/RILPOSITIONINFOLTE"
 - "RILPOSITIONINFOLTE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILPOSITIONINFOLTE
targetos: Windows
req.typenames: RILPOSITIONINFOLTE, *LPRILPOSITIONINFOLTE
req.product: Windows 10 or later.
---

# RILPOSITIONINFOLTE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILPOSITIONINFOLTE {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwCellID;
  DWORD  dwEARFCN;
  DWORD  dwPhysCellID;
  DWORD  dwTAC;
  LONG   dwRSRP;
  LONG   dwRSRQ;
  DWORD  dwTimingAdvance;
} RILPOSITIONINFOLTE, RILPOSITIONINFOLTE;
```


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwCellID


### -field dwEARFCN


### -field dwPhysCellID


### -field dwTAC


### -field dwRSRP


### -field dwRSRQ


### -field dwTimingAdvance

