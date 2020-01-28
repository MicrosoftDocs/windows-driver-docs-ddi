---
UID: NE:rilapitypes.RILGSMMNMRPARAMMASK
title: RILGSMMNMRPARAMMASK (rilapitypes.h)
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgsmmnmrparammask_2.htm
tech.root: netvista
ms.assetid: 9e58bd61-9cb7-40fb-a6e5-1e8a8d428774
ms.date: 02/26/2018
ms.keywords: RILGSMMNMRPARAMMASK, RILGSMMNMRPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_GSMNMR_ALL, RIL_PARAM_GSMNMR_ARFCN, RIL_PARAM_GSMNMR_BSID, RIL_PARAM_GSMNMR_CELLID, RIL_PARAM_GSMNMR_LAC, RIL_PARAM_GSMNMR_MNC, RIL_PARAM_GSMNMR_RXLEVEL, netvista.rilgsmmnmrparammask_2, rilapitypes/RILGSMMNMRPARAMMASK, rilapitypes/RIL_PARAM_GSMNMR_ALL, rilapitypes/RIL_PARAM_GSMNMR_ARFCN, rilapitypes/RIL_PARAM_GSMNMR_BSID, rilapitypes/RIL_PARAM_GSMNMR_CELLID, rilapitypes/RIL_PARAM_GSMNMR_LAC, rilapitypes/RIL_PARAM_GSMNMR_MNC, rilapitypes/RIL_PARAM_GSMNMR_RXLEVEL
f1_keywords:
 - "rilapitypes/RILGSMMNMRPARAMMASK"
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
req.lib: NtosKrnl.exe
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
- RILGSMMNMRPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILGSMMNMRPARAMMASK
req.product: Windows 10 or later.
---

# RILGSMMNMRPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


```cpp
typedef enum _RILGSMMNMRPARAMMASK {
  RIL_PARAM_GSMNMR_MNC,
  RIL_PARAM_GSMNMR_LAC,
  RIL_PARAM_GSMNMR_CELLID,
  RIL_PARAM_GSMNMR_ARFCN,
  RIL_PARAM_GSMNMR_BSID,
  RIL_PARAM_GSMNMR_RXLEVEL,
  RIL_PARAM_GSMNMR_ALL
} RILGSMMNMRPARAMMASK;
```


## -enum-fields




### -field RIL_PARAM_GSMNMR_MCC


### -field RIL_PARAM_GSMNMR_MNC


### -field RIL_PARAM_GSMNMR_LAC


### -field RIL_PARAM_GSMNMR_CELLID


### -field RIL_PARAM_GSMNMR_ARFCN


### -field RIL_PARAM_GSMNMR_BSID


### -field RIL_PARAM_GSMNMR_RXLEVEL


### -field RIL_PARAM_GSMNMR_ALL

