---
UID: NS:rilapitypes.RILPOSITIONINFOTDSCDMA
title: RILPOSITIONINFOTDSCDMA (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpositioninfotdscdma_2.htm
tech.root: netvista
ms.assetid: 9b0ba2fc-bf8f-40c0-83a2-a791413e4783
ms.date: 02/26/2018
ms.keywords: "*LPRILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfotdscdma_2, rilapitypes/RILPOSITIONINFOTDSCDMA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILPOSITIONINFOTDSCDMA
product:
- Windows
targetos: Windows
req.typenames: RILPOSITIONINFOTDSCDMA, *LPRILPOSITIONINFOTDSCDMA
req.product: Windows 10 or later.
---

# RILPOSITIONINFOTDSCDMA structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILPOSITIONINFOTDSCDMA {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwUARFCN;
  DWORD  dwCellParameterID;
  DWORD  dwTimingAdvance;
  DWORD  dwRSCP;
  DWORD  dwPathLoss;
} RILPOSITIONINFOTDSCDMA, RILPOSITIONINFOTDSCDMA;
```


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwLocationAreaCode


### -field dwCellID


### -field dwUARFCN


### -field dwCellParameterID


### -field dwTimingAdvance


### -field dwRSCP


### -field dwPathLoss

