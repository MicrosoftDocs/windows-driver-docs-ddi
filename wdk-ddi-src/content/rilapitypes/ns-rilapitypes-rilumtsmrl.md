---
UID: NS:rilapitypes.RILUMTSMRL
title: RILUMTSMRL (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilumtsmrl_2.htm
tech.root: netvista
ms.assetid: 38235a1e-c9fd-4d4d-96a2-18559e4cf655
ms.date: 02/26/2018
ms.keywords: "*LPRILUMTSMRL, RILUMTSMRL, RILUMTSMRL structure [Network Drivers Starting with Windows Vista], netvista.rilumtsmrl_2, rilapitypes/RILUMTSMRL"
ms.topic: struct
f1_keywords:
 - "rilapitypes/RILUMTSMRL"
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
- RILUMTSMRL
product:
- Windows
targetos: Windows
req.typenames: RILUMTSMRL, *LPRILUMTSMRL
req.product: Windows 10 or later.
---

# RILUMTSMRL structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef struct _RILUMTSMRL {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwLocationAreaCode;
  DWORD  dwCellID;
  DWORD  dwUARFCN;
  DWORD  dwPrimaryScramblingCode;
  LONG   dwRSCP;
  LONG   dwECNO;
  DWORD  dwPathLoss;
} RILUMTSMRL, RILUMTSMRL;
```


## -struct-fields




### -field dwParams


### -field dwMobileCountryCode


### -field dwMobileNetworkCode


### -field dwLocationAreaCode


### -field dwCellID


### -field dwUARFCN


### -field dwPrimaryScramblingCode


### -field dwRSCP


### -field dwECNO


### -field dwPathLoss

